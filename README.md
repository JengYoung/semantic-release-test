# semantic-release-test

## 🚀 배경

원래 다른 레포에서 적용하는데...  
두 가지가 문제가 생겨서 급하게 테스트를 해보고자 만들었다.

> ✅ 현재 문제를 해결한 상태이다.

### 🔥`Release Note` 생성을 하지 않는다.

일부러 릴리즈 노트를 만들기 싫어서 `@semantic-release/release-note-generator`를 추가하지 않았는데, 알고보니 이 문제가 아니었다. 문제를 해결했다.

#### 헤맨 이유

너무 패키지 이름이 직관적으로 `@semantic-release/release-note-generator`이어서 이것만 추가 안하면 되겠거니 했는데, 아예 다른 역할을 하던 친구였다.

> **@semantic-release/release-notes-generator**
> Note: this is already part of semantic-release and does not have to be installed separately
> 
> generateNotes: Generate release notes for the commits added since the last release with conventional-changelog

말 그대로 기본 패키지이며 마지막 릴리즈에 대한 체인지 로그를 작성하는 착한 아이였다. 😭

오히려 주의해야 할 것은, 다음 패키지였다. (누군가에게는 필요했겠지만)

> **@semantic-release/github**
> Note: this is already part of semantic-release and does not have to be installed separately
>
> verifyConditions: Verify the presence and the validity of the GitHub authentication and release configuration
>
> **publish: Publish a GitHub release**
> success: Add a comment to GitHub issues and pull requests resolved in the release
> fail: Open a GitHub issue when a release fails

후... 원인을 결국 다 파헤쳤으니, 마음의 평안을 획득했다... 💊

---

### `CHANGELOG` 생성

`CHANGELOG.md`를 생성하지 않는 현상이 발견되었으나, 잘 해결했다.

#### 헤맨 이유

`@semantic-release/changelog`의 의존성을 볼 때, `@semantic-release/release-note-generator`라고 명시되어 있지 않았었다.

```json
"peerDependencies": {
  "semantic-release": ">=18.0.0"
},
```

이게 전부였다.

그런데 [비슷한 이슈](https://github.com/semantic-release/changelog/issues/127)가 있음을 확인했고, 모든 수단을 다하고 난 이후 최후의 방법으로 힌트를 따라 패키지를 설치했다.

결과적으로... 설마했던 게 맞았다.

#### 부연 설명

그렇지만, 그냥 오!하고 넘어가기에는 제대로 이해하지 못하는 부분들이 많다고 생각했다.  
그래서 확실한 원인을 찾아보았다.

결과적으로, 이 부분이 원인이 되는 핵심 포인트이다.

<img width="844" alt="image" src="https://user-images.githubusercontent.com/78713176/205278847-6cfc9db1-4f39-44ef-a054-b150c3d2e8b2.png">

`Changelog`는 `generate note step` 안에서 내용을 만든다는 내용!

전반적으로 `Semantic-release`는 다음과 같은 단계를 거친다고 한다.

<img width="814" alt="image" src="https://user-images.githubusercontent.com/78713176/205279748-11b1d666-c8ea-4e6e-9c0d-63a90d4c6346.png">

그중, `Generate Nodes` 단계가 무엇인지를 살펴보면, 원하는 답이 나온다.

> **Generate release notes** for the commits added since the last release.

실제 `index.js`부터 시작하면서 로직을 훑어봐도 찾지 못했는데, 이렇게 허무하게 끝났다.


## 추가 변경 사항 - Changelog Customization

`CHANGELOG.md`의 default는 `feat`과 `fix`만 지원한다.  
하지만, 이는 [release-notes-generator](https://github.com/semantic-release/release-notes-generator)을 볼 때 `presetconfig`를 통해 바꿀 수 있다.  

### `presetconfig`

이 친구는 얼핏 넘어갈 만할 정도로 짧게 서술되어 있으나, `conventional-changelog`의 config spec을 따라간다고 한다.

이는 다음과 같다.

```json
"types": [
    {"type": "feat", "section": "Features"},
    {"type": "fix", "section": "Bug Fixes"},
    {"type": "chore", "hidden": true},
    {"type": "docs", "hidden": true},
    {"type": "style", "hidden": true},
    {"type": "refactor", "hidden": true},
    {"type": "perf", "hidden": true},
    {"type": "test", "hidden": true}
]
```

따라서 `presetConfig` 역시 `.cz-config.js`와 같은 방식으로 바꾸면 된다.
