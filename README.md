# semantic-release-test

## π λ°°κ²½

μλ λ€λ₯Έ λ ν¬μμ μ μ©νλλ°...  
λ κ°μ§κ° λ¬Έμ κ° μκ²¨μ κΈνκ² νμ€νΈλ₯Ό ν΄λ³΄κ³ μ λ§λ€μλ€.

> β νμ¬ λ¬Έμ λ₯Ό ν΄κ²°ν μνμ΄λ€.

### π₯`Release Note` μμ±μ νμ§ μλλ€.

μΌλΆλ¬ λ¦΄λ¦¬μ¦ λΈνΈλ₯Ό λ§λ€κΈ° μ«μ΄μ `@semantic-release/release-note-generator`λ₯Ό μΆκ°νμ§ μμλλ°, μκ³ λ³΄λ μ΄ λ¬Έμ κ° μλμλ€. λ¬Έμ λ₯Ό ν΄κ²°νλ€.

#### ν€λ§¨ μ΄μ 

λλ¬΄ ν¨ν€μ§ μ΄λ¦μ΄ μ§κ΄μ μΌλ‘ `@semantic-release/release-note-generator`μ΄μ΄μ μ΄κ²λ§ μΆκ° μνλ©΄ λκ² κ±°λ νλλ°, μμ λ€λ₯Έ μ­ν μ νλ μΉκ΅¬μλ€.

> **@semantic-release/release-notes-generator**
> Note: this is already part of semantic-release and does not have to be installed separately
> 
> generateNotes: Generate release notes for the commits added since the last release with conventional-changelog

λ§ κ·Έλλ‘ κΈ°λ³Έ ν¨ν€μ§μ΄λ©° λ§μ§λ§ λ¦΄λ¦¬μ¦μ λν μ²΄μΈμ§ λ‘κ·Έλ₯Ό μμ±νλ μ°©ν μμ΄μλ€. π­

μ€νλ € μ£Όμν΄μΌ ν  κ²μ, λ€μ ν¨ν€μ§μλ€. (λκ΅°κ°μκ²λ νμνκ² μ§λ§)

> **@semantic-release/github**
> Note: this is already part of semantic-release and does not have to be installed separately
>
> verifyConditions: Verify the presence and the validity of the GitHub authentication and release configuration
>
> **publish: Publish a GitHub release**
> success: Add a comment to GitHub issues and pull requests resolved in the release
> fail: Open a GitHub issue when a release fails

ν... μμΈμ κ²°κ΅­ λ€ νν€μ³€μΌλ, λ§μμ νμμ νλνλ€... π

---

### `CHANGELOG` μμ±

`CHANGELOG.md`λ₯Ό μμ±νμ§ μλ νμμ΄ λ°κ²¬λμμΌλ, μ ν΄κ²°νλ€.

#### ν€λ§¨ μ΄μ 

`@semantic-release/changelog`μ μμ‘΄μ±μ λ³Ό λ, `@semantic-release/release-note-generator`λΌκ³  λͺμλμ΄ μμ§ μμμλ€.

```json
"peerDependencies": {
  "semantic-release": ">=18.0.0"
},
```

μ΄κ² μ λΆμλ€.

κ·Έλ°λ° [λΉμ·ν μ΄μ](https://github.com/semantic-release/changelog/issues/127)κ° μμμ νμΈνκ³ , λͺ¨λ  μλ¨μ λ€νκ³  λ μ΄ν μ΅νμ λ°©λ²μΌλ‘ ννΈλ₯Ό λ°λΌ ν¨ν€μ§λ₯Ό μ€μΉνλ€.

κ²°κ³Όμ μΌλ‘... μ€λ§νλ κ² λ§μλ€.

#### λΆμ° μ€λͺ

κ·Έλ μ§λ§, κ·Έλ₯ μ€!νκ³  λμ΄κ°κΈ°μλ μ λλ‘ μ΄ν΄νμ§ λͺ»νλ λΆλΆλ€μ΄ λ§λ€κ³  μκ°νλ€.  
κ·Έλμ νμ€ν μμΈμ μ°Ύμλ³΄μλ€.

κ²°κ³Όμ μΌλ‘, μ΄ λΆλΆμ΄ μμΈμ΄ λλ ν΅μ¬ ν¬μΈνΈμ΄λ€.

<img width="844" alt="image" src="https://user-images.githubusercontent.com/78713176/205278847-6cfc9db1-4f39-44ef-a054-b150c3d2e8b2.png">

`Changelog`λ `generate note step` μμμ λ΄μ©μ λ§λ λ€λ λ΄μ©!

μ λ°μ μΌλ‘ `Semantic-release`λ λ€μκ³Ό κ°μ λ¨κ³λ₯Ό κ±°μΉλ€κ³  νλ€.

<img width="814" alt="image" src="https://user-images.githubusercontent.com/78713176/205279748-11b1d666-c8ea-4e6e-9c0d-63a90d4c6346.png">

κ·Έμ€, `Generate Nodes` λ¨κ³κ° λ¬΄μμΈμ§λ₯Ό μ΄ν΄λ³΄λ©΄, μνλ λ΅μ΄ λμ¨λ€.

> **Generate release notes** for the commits added since the last release.

μ€μ  `index.js`λΆν° μμνλ©΄μ λ‘μ§μ νμ΄λ΄λ μ°Ύμ§ λͺ»νλλ°, μ΄λ κ² νλ¬΄νκ² λλ¬λ€.


## μΆκ° λ³κ²½ μ¬ν­ - Changelog Customization

`CHANGELOG.md`μ defaultλ `feat`κ³Ό `fix`λ§ μ§μνλ€.  
νμ§λ§, μ΄λ [release-notes-generator](https://github.com/semantic-release/release-notes-generator)μ λ³Ό λ `presetconfig`λ₯Ό ν΅ν΄ λ°κΏ μ μλ€.  

### `presetconfig`

μ΄ μΉκ΅¬λ μΌν λμ΄κ° λ§ν  μ λλ‘ μ§§κ² μμ λμ΄ μμΌλ, `conventional-changelog`μ config specμ λ°λΌκ°λ€κ³  νλ€.

μ΄λ λ€μκ³Ό κ°λ€.

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

λ°λΌμ `presetConfig` μ­μ `.cz-config.js`μ κ°μ λ°©μμΌλ‘ λ°κΎΈλ©΄ λλ€.
