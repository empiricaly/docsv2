# @empirica/core

## Index

### Classes

- [LogsMock](modules.md#logsmock)

### Type Aliases

- [LogLine](modules.md#logline)

### Variables

- [levels](modules.md#levels)

### Functions

- [captureLogs](modules.md#capturelogs)
- [captureLogsAsync](modules.md#capturelogsasync)
- [debug](modules.md#debug)
- [error](modules.md#error)
- [info](modules.md#info)
- [log](modules.md#log)
- [mockLogging](modules.md#mocklogging)
- [setLogLevel](modules.md#setloglevel)
- [stopMockLogging](modules.md#stopmocklogging)
- [trace](modules.md#trace)
- [warn](modules.md#warn)

## Classes

### LogsMock

#### Constructors

##### constructor()

> **new LogsMock**(): [`LogsMock`](modules.md#logsmock)

###### Returns

[`LogsMock`](modules.md#logsmock)

#### Properties

##### logs

> **logs**: [`LogLine`](modules.md#logline)[] = `[]`

Defined in: [console.ts:23](https://github.com/empiricaly/empirica/blob/d1b58d0/lib/@empirica/core/src/utils/console.ts#L23)

#### Methods

##### clear()

> **clear**(): `void`

Defined in: [console.ts:29](https://github.com/empiricaly/empirica/blob/d1b58d0/lib/@empirica/core/src/utils/console.ts#L29)

###### Returns

`void`

##### log()

> **log**(line: [`LogLine`](modules.md#logline)): `void`

Defined in: [console.ts:25](https://github.com/empiricaly/empirica/blob/d1b58d0/lib/@empirica/core/src/utils/console.ts#L25)

###### Parameters

| Parameter | Type                            |
| :-------- | :------------------------------ |
| line      | [`LogLine`](modules.md#logline) |

###### Returns

`void`

---

## Type Aliases

### LogLine

> **LogLine**: `object`

Defined in: [console.ts:21](https://github.com/empiricaly/empirica/blob/d1b58d0/lib/@empirica/core/src/utils/console.ts#L21)

#### Type declaration

> **args**: `any`[]
>
> **level**: `string`

---

## Variables

### levels

> `const` **levels**: `object`

Defined in: [console.ts:80](https://github.com/empiricaly/empirica/blob/d1b58d0/lib/@empirica/core/src/utils/console.ts#L80)

#### Index signature

\[`key`: `string`\]: `number`

#### Type declaration

---

## Functions

### captureLogs()

> **captureLogs**(cb: `Function`): [`LogLine`](modules.md#logline)[]

Defined in: [console.ts:35](https://github.com/empiricaly/empirica/blob/d1b58d0/lib/@empirica/core/src/utils/console.ts#L35)

#### Parameters

| Parameter | Type         |
| :-------- | :----------- |
| cb        | () => `void` |

#### Returns

[`LogLine`](modules.md#logline)[]

---

### captureLogsAsync()

> **captureLogsAsync**(cb: `Function`): `Promise`\<[`LogLine`](modules.md#logline)[]\>

Defined in: [console.ts:44](https://github.com/empiricaly/empirica/blob/d1b58d0/lib/@empirica/core/src/utils/console.ts#L44)

#### Parameters

| Parameter | Type                      |
| :-------- | :------------------------ |
| cb        | () => `Promise`\<`void`\> |

#### Returns

`Promise`\<[`LogLine`](modules.md#logline)[]\>

---

### debug()

> **debug**(...args: `any`[]): `void`

Defined in: [console.ts:129](https://github.com/empiricaly/empirica/blob/d1b58d0/lib/@empirica/core/src/utils/console.ts#L129)

#### Parameters

| Parameter | Type    |
| :-------- | :------ |
| ...args   | `any`[] |

#### Returns

`void`

---

### error()

> **error**(...args: `any`[]): `void`

Defined in: [console.ts:129](https://github.com/empiricaly/empirica/blob/d1b58d0/lib/@empirica/core/src/utils/console.ts#L129)

#### Parameters

| Parameter | Type    |
| :-------- | :------ |
| ...args   | `any`[] |

#### Returns

`void`

---

### info()

> **info**(...args: `any`[]): `void`

Defined in: [console.ts:129](https://github.com/empiricaly/empirica/blob/d1b58d0/lib/@empirica/core/src/utils/console.ts#L129)

#### Parameters

| Parameter | Type    |
| :-------- | :------ |
| ...args   | `any`[] |

#### Returns

`void`

---

### log()

> **log**(...args: `any`[]): `void`

Defined in: [console.ts:129](https://github.com/empiricaly/empirica/blob/d1b58d0/lib/@empirica/core/src/utils/console.ts#L129)

#### Parameters

| Parameter | Type    |
| :-------- | :------ |
| ...args   | `any`[] |

#### Returns

`void`

---

### mockLogging()

> **mockLogging**(): [`LogsMock`](modules.md#logsmock)

Defined in: [console.ts:55](https://github.com/empiricaly/empirica/blob/d1b58d0/lib/@empirica/core/src/utils/console.ts#L55)

#### Returns

[`LogsMock`](modules.md#logsmock)

---

### setLogLevel()

> **setLogLevel**(level: `string` \| `number`): `void`

Defined in: [console.ts:96](https://github.com/empiricaly/empirica/blob/d1b58d0/lib/@empirica/core/src/utils/console.ts#L96)

#### Parameters

| Parameter | Type                 |
| :-------- | :------------------- |
| level     | `string` \| `number` |

#### Returns

`void`

---

### stopMockLogging()

> **stopMockLogging**(): `void`

Defined in: [console.ts:63](https://github.com/empiricaly/empirica/blob/d1b58d0/lib/@empirica/core/src/utils/console.ts#L63)

#### Returns

`void`

---

### trace()

> **trace**(...args: `any`[]): `void`

Defined in: [console.ts:129](https://github.com/empiricaly/empirica/blob/d1b58d0/lib/@empirica/core/src/utils/console.ts#L129)

#### Parameters

| Parameter | Type    |
| :-------- | :------ |
| ...args   | `any`[] |

#### Returns

`void`

---

### warn()

> **warn**(...args: `any`[]): `void`

Defined in: [console.ts:129](https://github.com/empiricaly/empirica/blob/d1b58d0/lib/@empirica/core/src/utils/console.ts#L129)

#### Parameters

| Parameter | Type    |
| :-------- | :------ |
| ...args   | `any`[] |

#### Returns

`void`

---
