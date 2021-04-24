# Angular Style Guide

## Table of contents
1. [Coding guidelines](#coding-guidelines)
    1. [Code formatting](#code-formatting)
    1. [Imports order](#imports-order)
    1. [Imports type](#imports-type)
    1. [Access modifiers](#access-modifiers)
    1. [Interfaces naming](#interfaces-naming)
    1. [Types naming](#types-naming)
    1. [Classes fields](#classes-fields)
2. [Commit Message Guidelines](#commit-message-guidelines)

## Coding guidelines

[Angular Coding Style guide](https://angular.io/guide/styleguide) should be followed.
Rules which are placed below can conflict with [Angular Coding Style guide](https://angular.io/guide/styleguide) and have a higher precendence.

### Code formatting

Let [prettier](https://prettier.io) do code formatting.

### Imports order

Third party imports should be placed at the top of the file and be separated by an empty line.

Bad
```typescript
import { Action } from 'flux-standard-action';
import { BASE_FONT_SIZE } from 'src/common';
import { Component } from '@angular/core';
import { RelativeRange } from 'src/app/domain';
```

Good
```typescript
import { Action } from 'flux-standard-action';
import { Component } from '@angular/core';

import { BASE_FONT_SIZE } from 'src/common';
import { RelativeRange } from 'src/app/domain';
```

### Imports type

Prefer imports with an absolute path instead of relative.

Bad
```typescript
import { BASE_FONT_SIZE } from '../../../../common';
```

Good
```typescript
import { BASE_FONT_SIZE } from 'src/common';
```

### Access modifiers

1. Always prefer explicit access modifiers over implicit. It means lets use `public` despite the fact that it is default.
2. Lets use `private` modifier if property/field is not used in component template

Bad
```typescript
class Foo {
  foo = 0;
}
```

Good
```typescript
class Foo {
  public foo = 0;
}
```

### Interfaces naming

All entities created with `interface` keyword should follow the following pattern:
  ```I<PascalCase>```

### Types naming

All entities created with `type` keyword should follow the following pattern:
  ```<PascalCase>```

### Classes fields

Use next order of class fields:
1. `@Input`
2. `@Output`
3. Other decorated properties
4. `public` properties
5. `private` properties
6.  `constructor`
7. lifesicle methods e.g. `ngOnInit`
8. eventListeners with `on` prefix e.g. `onItemDelete() {}`
9. `public` methods
10. `private` methods

## Commit Message Guidelines

### Commit Message Format

Each commit message consists of a **header**, and a **body**.  The header has a special format that includes a **type**, a **scope**, a **subject**:

```
<type>(<scope>): <subject> (<JIRA ticket>)
<BLANK LINE>
<body>
```

The **header** is mandatory and the **scope** of the header is optional.

### Revert

If the commit reverts a previous commit, it should begin with `revert: `, followed by the header of the reverted commit. In the body it should say: `This reverts commit <hash>.`, where the hash is the SHA of the commit being reverted.

### Type

Must be one of the following:

* **feat**: A new feature
* **fix**: A bug fix
* **docs**: Documentation only changes
* **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing
  semi-colons, etc)
* **refactor**: A code change that neither fixes a bug nor adds a feature
* **perf**: A code change that improves performance
* **test**: Adding missing tests
* **chore**: Changes to the build process or auxiliary tools and libraries such as documentation
  generation

### Scope

The scope could be anything specifying place of the commit change. For example
`header`, `main`, `footer`, etc.

### Subject

The subject contains succinct description of the change:

* use the imperative, present tense: "change" not "changed" nor "changes"
* don't capitalize first letter
* no dot (.) at the end

### Body

Just as in the **subject**, use the imperative, present tense: "change" not "changed" nor "changes".
The body should include the motivation for the change and contrast this with previous behavior.

