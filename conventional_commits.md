# Conventional Commits 

## Summary

The commit message should be structured as follows:

---
```
<Emoji> <type>(<scope>): <subject>
|<----   Using a Maximum Of 50 Characters   ---->|

<body>
|<---------   Try To Limit Each Line to a Maximum Of 80 Characters   --------->|

<footer>
```
---

  * [Why Use Conventional Commits](#why-use-conventional-commits)
  * [Message footer](#message-footer)
    + [Breaking changes](#breaking-changes)
    + [Referencing issues](#referencing-issues)
  * [Message body](#message-body)
  * [Message subject First Line](#message-subject-first-line)
    + [SCOPE](#scope)
    + [Allowed TYPE values](#allowed-type-values)
    + [Allowed EMOJIS values](#allowed-emojis-values)
  * [Example commit message](#example-commit-message)
    + [Commit message for bug fix](#commit-message-for-bug-fix)
    + [Commit message with no body](#commit-message-with-no-body)
    + [Commit message with scope](#commit-message-with-scope)
    + [Commit message for revert changes](#commit-message-for-revert-changes)
  * [Template](#template)

## Why Use Conventional Commits

* Determining a semantic version bump (based on the types of commits landed)
* simple navigation through git history (e.g. ignoring style changes)
* Communicating the nature of changes to teammates, the public, and other stakeholders

## Message footer

### Breaking changes

All breaking changes have to be mentioned in footer with the
description of the change, justification and migration notes.

### Referencing issues

Closed issues should be listed on a separate line in the footer prefixed with "Closes" keyword like this:

```
Closes #234
```

or in the case of multiple issues:

```
Closes #123, #245, #992
```

## Message body

* Uses the imperative, present tense: “change” not “changed” nor “changes”
* Includes motivation for the change and contrasts with previous behavior
* No dot (.) at the end
* Separate subject and footer from body with a blank line

## Message subject First Line

The first line cannot be longer than 50 characters, the second line is always blank and
other lines should be wrapped at 80 characters. The type and scope should
always be lowercase and no dot (.) at the end.

### SCOPE

The `<scope>` may be provided to a commit’s type, to provide additional contextual information and is contained within parenthesis. The `<scope>` can be empty (e.g. if the change is a global or difficult
to assign to a single component), in which case the parentheses are
omitted.

### Allowed TYPE values

| Type          | Description |
|:-------------:|-------------|
| `new`         | for new feature implementing commit|
| `feature`     | for new feature implementing commit (equal `new`) |
| `bug`         | for bug fix commit |
| `security`    | for security issue fix commit |
| `performance` | for performance issue fix commit |
| `improvement` | for backwards-compatible enhancement commit |
| `breaking`    | for backwards-incompatible enhancement commit |
| `deprecated`  | for deprecated feature commit |
| `refactor`    | for refactoring commit |
| `docs`        | for documentation commit |
| `examples`    | for example code commit |
| `test`        | for testing commit |
| `dependency`  | for dependencies upgrading or downgrading commit |
| `config`      | for configuration commit |
| `build`       | for packaging or bundling commit |
| `release`     | for publishing commit |
| `update`      | for update commit |
| `wip`         | for work in progress commit |
| `chore`       | for other operations commit |

### Allowed EMOJIS values

| Emoji                      | Raw Emoji Code               | Type               | Description |
|:--------------------------:|------------------------------|--------------------|-------------|
| :star:                     | `:star:`                     | `new` or `feature` | add **new feature** |
| :bug:                      | `:bug:`                      | `bug`              | fix **bug** issue |
| :lock:                     | `:lock:`                     | `security`         | fix **security** issue |
| :chart_with_upwards_trend: | `:chart_with_upwards_trend:` | `performance`      | fix **performance** issue |
| :zap:                      | `:zap:`                      | `improvement`      | update **backwards-compatible** feature |
| :boom:                     | `:boom:`                      | `breaking`         | update **backwards-incompatible** feature |
| :warning:                  | `:warning:`                  | `deprecated`       | **deprecate** feature |
| :lipstick:                 | `:lipstick:`                 | `update`           | update **UI/Cosmetic** |
| :up:                       | `:up:`                       | `update`           | update **other** |
| :globe_with_meridians:     | `:globe_with_meridians:`     | `update`           | update or fix **internationalization** |
| :shirt:                    | `:shirt:`                    | `refactor`         | remove **linter**/strict/deprecation warnings or **refactoring** or code **layouting** |
| :white_check_mark:         | `:white_check_mark:`         | `test`             | add **tests** |
| :green_heart:              | `:green_heart:`              | `test`             | fix **tests** failur or **CI** building |
| :pencil:                   | `:pencil:`                   | `docs`             | update **documentation** |
| :copyright:                | `:copyright:`                | `docs`             | decide or change **license** |
| :lollipop:                 | `:lollipop:`                 | `examples`         | for **example** codes |
| :arrow_up:                 | `:arrow_up:`                 | `dependency`       | upgrade **dependencies** |
| :arrow_down:               | `:arrow_down:`               | `dependency`       | downgrade **dependencies** |
| :pushpin:                  | `:pushpin:`                  | `dependency`       | pin **dependencies** |
| :wrench:                   | `:wrench:`                   | `config`           | update **configuration** |
| :package:                  | `:package:`                  | `build`            | **packaging** or **bundling** or **building** |
| :hatching_chick:           | `:hatching_chick:`           | `release`          | **initial** commit |
| :confetti_ball:            | `:confetti_ball:`            | `release`          | release **major** version |
| :tada:                     | `:tada:`                     | `release`          | release **minor** version |
| :sparkles:                 | `:sparkles:`                 | `release`          | release **patch** version |
| :rocket:                   | `:rocket:`                   | `release`          | **deploy** to production enviroment |
| :back:                     | `:back:`                     | `revert`           | **revert** commiting |
| :construction:             | `:construction:`             | `wip`              | **WIP** commiting |
| :twisted_rightwards_arrows:| `:twisted_rightwards_arrows:`| -                  | merge **conflict resolution** |
| :heavy_plus_sign:          | `:heavy_plus_sign:`          | -                  | **add** files, dependencies, ... |
| :heavy_minus_sign:         | `:heavy_minus_sign:`         | -                  | **remove** files, dependencies, ... |
| :on:                       | `:on:`                       | -                  | **enable** feature and something ... |
---

## Example commit message

### Commit message for bug fix
```
fix(middleware): ensure Range headers adhere more closely to RFC 2616

Add one new dependency, use `range-parser` (Express dependency) to compute
range. It is more well-tested in the wild.

Fixes #1234
```

### Commit message with no body
```
docs: correct spelling of CHANGELOG
```

### Commit message with scope
```
feat(lang): added polish language
```

### Commit message for revert changes
```
:back: revert: new: add 'graphiteWidth' option

This reverts commit 667ecc1654a317a13331b17617d973392f415f02.
```

## Template

Use the following piece of code as a simple template for your Git Commit Messages (.gitmessage)

```
:emoji: type(scope): subject

body

footer
```