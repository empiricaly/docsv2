# @empirica/core

## Index

### Classes

- [Attribute](modules.md#attribute)
- [Attributes](modules.md#attributes)
- [Globals](modules.md#globals)
- [Scope](modules.md#scope)
- [Scopes](modules.md#scopes)
- [SharedScope](modules.md#sharedscope)
- [Step](modules.md#step)
- [Steps](modules.md#steps)
- [TajribaProvider](modules.md#tajribaprovider)

### Interfaces

- [AttributeChange](modules.md#attributechange)
- [AttributeOptions](modules.md#attributeoptions)
- [AttributeUpdate](modules.md#attributeupdate)
- [Json](modules.md#json)
- [JsonArray](modules.md#jsonarray)
- [ParticipantUpdate](modules.md#participantupdate)
- [ScopeIdent](modules.md#scopeident)
- [ScopeUpdate](modules.md#scopeupdate)
- [StepChange](modules.md#stepchange)
- [StepTick](modules.md#steptick)
- [StepUpdate](modules.md#stepupdate)

### Type Aliases

- [AttributeInput](modules.md#attributeinput)
- [Constructor](modules.md#constructor)
- [Epoch](modules.md#epoch)
- [JsonValue](modules.md#jsonvalue)
- [ScopeConstructor](modules.md#scopeconstructor)

### Variables

- [isDevelopment](modules.md#isdevelopment)
- [isProduction](modules.md#isproduction)
- [isTest](modules.md#istest)

### Functions

- [createNewParticipant](modules.md#createnewparticipant)

## Classes

### Attribute

#### Constructors

##### constructor()

> **new Attribute**(
> setAttributes: `Function`,
> scopeID: `string`,
> key: `string`): [`Attribute`](modules.md#attribute)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:241](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L241)

###### Parameters

| Parameter     | Type                                                       |
| :------------ | :--------------------------------------------------------- |
| setAttributes | (`input`: `SetAttributeInput`[]) => `Promise`\<`unknown`\> |
| scopeID       | `string`                                                   |
| key           | `string`                                                   |

###### Returns

[`Attribute`](modules.md#attribute)

#### Properties

##### key

> `readonly` **key**: `string`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:244](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L244)

##### scopeID

> `readonly` **scopeID**: `string`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:243](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L243)

#### Accessors

##### createdAt

> get **createdAt()**: `null` \| `Date`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:251](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L251)

##### id

> get **id()**: `undefined` \| `string`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:247](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L247)

##### items

> get **items()**: `null` \| [`Attribute`](modules.md#attribute)[]

Defined in: [lib/@empirica/core/src/shared/attributes.ts:269](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L269)

##### nodeID

> get **nodeID()**: `string`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:263](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L263)

##### obs

> get **obs()**: `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/attributes.ts:255](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L255)

##### value

> get **value()**: `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:259](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L259)

#### Methods

##### \_prepSet()

> **\_prepSet**(
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>,
> item?: `boolean`): `undefined` \| `SetAttributeInput`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:287](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L287)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |
| item?     | `boolean`                                                      |

###### Returns

`undefined` \| `SetAttributeInput`

##### \_update()

> **\_update**(attr?: [`AttributeChange`](modules.md#attributechange), item?: `boolean`): `void`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:366](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L366)

###### Parameters

| Parameter | Type                                            |
| :-------- | :---------------------------------------------- |
| attr?     | [`AttributeChange`](modules.md#attributechange) |
| item?     | `boolean`                                       |

###### Returns

`void`

##### set()

> **set**(value: [`JsonValue`](modules.md#jsonvalue), ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:277](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L277)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

---

### Attributes

#### Constructors

##### constructor()

> **new Attributes**(
> attributesObs: `Observable`\<[`AttributeUpdate`](modules.md#attributeupdate)\>,
> donesObs: `Observable`\<`string`[]\>,
> setAttributes: `Function`): [`Attributes`](modules.md#attributes)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:49](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L49)

###### Parameters

| Parameter     | Type                                                            |
| :------------ | :-------------------------------------------------------------- |
| attributesObs | `Observable`\<[`AttributeUpdate`](modules.md#attributeupdate)\> |
| donesObs      | `Observable`\<`string`[]\>                                      |
| setAttributes | (`input`: `SetAttributeInput`[]) => `Promise`\<`unknown`\>      |

###### Returns

[`Attributes`](modules.md#attributes)

#### Properties

##### setAttributes

> `readonly` **setAttributes**: `Function`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:52](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L52)

###### Type declaration

> > (input: `SetAttributeInput`[]): `Promise`\<`unknown`\>
>
> ####### Parameters
>
> | Parameter | Type                  |
> | :-------- | :-------------------- |
> | input     | `SetAttributeInput`[] |
>
> ####### Returns
>
> `Promise`\<`unknown`\>

#### Methods

##### attribute()

> **attribute**(scopeID: `string`, key: `string`): [`Attribute`](modules.md#attribute)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:67](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L67)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| scopeID   | `string` |
| key       | `string` |

###### Returns

[`Attribute`](modules.md#attribute)

##### attributePeek()

> **attributePeek**(scopeID: `string`, key: `string`): `undefined` \| [`Attribute`](modules.md#attribute)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:93](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L93)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| scopeID   | `string` |
| key       | `string` |

###### Returns

`undefined` \| [`Attribute`](modules.md#attribute)

##### attributes()

> **attributes**(scopeID: `string`): [`Attribute`](modules.md#attribute)[]

Defined in: [lib/@empirica/core/src/shared/attributes.ts:83](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L83)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| scopeID   | `string` |

###### Returns

[`Attribute`](modules.md#attribute)[]

##### nextAttributeValue()

> **nextAttributeValue**(scopeID: `string`, key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:129](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L129)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| scopeID   | `string` |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

##### scopeWasUpdated()

> **scopeWasUpdated**(scopeID?: `string`): `boolean`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:165](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L165)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| scopeID?  | `string` |

###### Returns

`boolean`

---

### Globals

#### Constructors

##### constructor()

> **new Globals**(globals: `Observable`\<`SubAttributesPayload`\>): [`Globals`](modules.md#globals)

Defined in: [lib/@empirica/core/src/shared/globals.ts:10](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/globals.ts#L10)

###### Parameters

| Parameter | Type                                   |
| :-------- | :------------------------------------- |
| globals   | `Observable`\<`SubAttributesPayload`\> |

###### Returns

[`Globals`](modules.md#globals)

#### Properties

##### self

> **self**: `BehaviorSubject`\<`undefined` \| [`Globals`](modules.md#globals)\>

Defined in: [lib/@empirica/core/src/shared/globals.ts:8](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/globals.ts#L8)

#### Methods

##### get()

> **get**(key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/globals.ts:39](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/globals.ts#L39)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

##### obs()

> **obs**(key: `string`): `BehaviorSubject`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/globals.ts:48](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/globals.ts#L48)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`BehaviorSubject`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

---

### Scope

#### Type parameters

| Parameter           |
| :------------------ |
| Context             |
| Kinds _extends_ \{} |

#### Hierarchy

- [`SharedScope`](modules.md#sharedscope)\<`Context`, `Kinds`\>.**`Scope`**

#### Constructors

##### constructor()

> **new Scope**\<Context, Kinds\>(
> ctx: `Context`,
> scope: [`ScopeIdent`](modules.md#scopeident),
> scopes: [`Scopes`](modules.md#scopes)\<`Context`, `Kinds`\>,
> attributes: [`Attributes`](modules.md#attributes),
> steps: [`Steps`](modules.md#steps)): [`Scope`](modules.md#scope)\<`Context`, `Kinds`\>

Defined in: [lib/@empirica/core/src/player/scopes.ts:45](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/scopes.ts#L45)

###### Type parameters

| Parameter           |
| :------------------ |
| Context             |
| Kinds _extends_ \{} |

###### Parameters

| Parameter  | Type                                                |
| :--------- | :-------------------------------------------------- |
| ctx        | `Context`                                           |
| scope      | [`ScopeIdent`](modules.md#scopeident)               |
| scopes     | [`Scopes`](modules.md#scopes)\<`Context`, `Kinds`\> |
| attributes | [`Attributes`](modules.md#attributes)               |
| steps      | [`Steps`](modules.md#steps)                         |

###### Returns

[`Scope`](modules.md#scope)\<`Context`, `Kinds`\>

###### Overrides

[`SharedScope`](modules.md#sharedscope).[`constructor`](modules.md#constructor)

#### Properties

##### scopes

> `readonly` **scopes**: [`Scopes`](modules.md#scopes)\<`Context`, `Kinds`\>

Defined in: [lib/@empirica/core/src/player/scopes.ts:48](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/scopes.ts#L48)

#### Accessors

##### id

> get **id()**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L209)

###### Inherited from

[`SharedScope`](modules.md#sharedscope).[`id`](modules.md#id)

#### Methods

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:269](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L269)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

[`SharedScope`](modules.md#sharedscope).[`append`](modules.md#append)

##### get()

> **get**(key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L221)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

[`SharedScope`](modules.md#sharedscope).[`get`](modules.md#get)

##### getAttribute()

> **getAttribute**(key: `string`): `undefined` \| [`Attribute`](modules.md#attribute)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L225)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`Attribute`](modules.md#attribute)

###### Inherited from

[`SharedScope`](modules.md#sharedscope).[`getAttribute`](modules.md#getattribute)

##### inspect()

> **inspect**(): `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:278](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L278)

###### Returns

`object`

###### Inherited from

[`SharedScope`](modules.md#sharedscope).[`inspect`](modules.md#inspect)

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L229)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

###### Inherited from

[`SharedScope`](modules.md#sharedscope).[`obs`](modules.md#obs)

##### scopeByKey()

> **scopeByKey**(key: `string`): `undefined` \| [`Scope`](modules.md#scope)\<`Context`, `Kinds`\>

Defined in: [lib/@empirica/core/src/player/scopes.ts:55](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/scopes.ts#L55)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`Scope`](modules.md#scope)\<`Context`, `Kinds`\>

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L233)

###### Parameters

| Parameter | Type                                            |
| :-------- | :---------------------------------------------- |
| values    | [`AttributeInput`](modules.md#attributeinput)[] |

###### Returns

`void`

###### Inherited from

[`SharedScope`](modules.md#sharedscope).[`set`](modules.md#set)

> **set**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L234)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

[`SharedScope`](modules.md#sharedscope).[`set`](modules.md#set)

---

### Scopes

#### Type parameters

| Parameter           |
| :------------------ |
| Context             |
| Kinds _extends_ \{} |

#### Hierarchy

- `Scopes`\<`Context`, `Kinds`, [`Scope`](modules.md#scope)\<`Context`, `Kinds`\>\>.**`Scopes`**

#### Constructors

##### constructor()

> **new Scopes**\<Context, Kinds\>(
> scopesObs: `Observable`\<[`ScopeUpdate`](modules.md#scopeupdate)\>,
> donesObs: `Observable`\<`string`[]\>,
> ctx: `Context`,
> kinds: `Kinds`,
> attributes: [`Attributes`](modules.md#attributes),
> steps: [`Steps`](modules.md#steps)): [`Scopes`](modules.md#scopes)\<`Context`, `Kinds`\>

Defined in: [lib/@empirica/core/src/player/scopes.ts:16](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/scopes.ts#L16)

###### Type parameters

| Parameter           |
| :------------------ |
| Context             |
| Kinds _extends_ \{} |

###### Parameters

| Parameter  | Type                                                    |
| :--------- | :------------------------------------------------------ |
| scopesObs  | `Observable`\<[`ScopeUpdate`](modules.md#scopeupdate)\> |
| donesObs   | `Observable`\<`string`[]\>                              |
| ctx        | `Context`                                               |
| kinds      | `Kinds`                                                 |
| attributes | [`Attributes`](modules.md#attributes)                   |
| steps      | [`Steps`](modules.md#steps)                             |

###### Returns

[`Scopes`](modules.md#scopes)\<`Context`, `Kinds`\>

###### Overrides

SharedScopes\<Context, Kinds, Scope\<Context, Kinds\>\>.constructor

#### Methods

##### byKind()

> **byKind**\<T\>(kind: _keyof_ `Kinds`): `Map`\<`string`, `T`\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:72](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L72)

###### Type parameters

| Parameter                                                          |
| :----------------------------------------------------------------- |
| T _extends_ [`Scope`](modules.md#scope)\<`Context`, `Kinds`, `T`\> |

###### Parameters

| Parameter | Type            |
| :-------- | :-------------- |
| kind      | _keyof_ `Kinds` |

###### Returns

`Map`\<`string`, `T`\>

###### Inherited from

SharedScopes.byKind

##### kindWasUpdated()

> **kindWasUpdated**(kind: _keyof_ `Kinds`): `boolean`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:82](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L82)

###### Parameters

| Parameter | Type            |
| :-------- | :-------------- |
| kind      | _keyof_ `Kinds` |

###### Returns

`boolean`

###### Inherited from

SharedScopes.kindWasUpdated

##### scope()

> **scope**(id: `string`): `undefined` \| [`Scope`](modules.md#scope)\<`Context`, `Kinds`\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:64](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L64)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| id        | `string` |

###### Returns

`undefined` \| [`Scope`](modules.md#scope)\<`Context`, `Kinds`\>

###### Inherited from

SharedScopes.scope

##### scopeObs()

> **scopeObs**(id: `string`): `undefined` \| `Observable`\<[`Scope`](modules.md#scope)\<`Context`, `Kinds`\>\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:68](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L68)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| id        | `string` |

###### Returns

`undefined` \| `Observable`\<[`Scope`](modules.md#scope)\<`Context`, `Kinds`\>\>

###### Inherited from

SharedScopes.scopeObs

---

### SharedScope

#### Type parameters

| Parameter           |
| :------------------ |
| Context             |
| Kinds _extends_ \{} |

#### Hierarchy

- [`Scope`](modules.md#scope)

#### Constructors

##### constructor()

> **new SharedScope**\<Context, Kinds\>(): [`SharedScope`](modules.md#sharedscope)\<`Context`, `Kinds`\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:194](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L194)

###### Type parameters

| Parameter           |
| :------------------ |
| Context             |
| Kinds _extends_ \{} |

###### Returns

[`SharedScope`](modules.md#sharedscope)\<`Context`, `Kinds`\>

#### Accessors

##### id

> get **id()**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L209)

#### Methods

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:269](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L269)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

##### get()

> **get**(key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L221)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

##### getAttribute()

> **getAttribute**(key: `string`): `undefined` \| [`Attribute`](modules.md#attribute)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L225)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`Attribute`](modules.md#attribute)

##### inspect()

> **inspect**(): `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:278](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L278)

###### Returns

`object`

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L229)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L233)

###### Parameters

| Parameter | Type                                            |
| :-------- | :---------------------------------------------- |
| values    | [`AttributeInput`](modules.md#attributeinput)[] |

###### Returns

`void`

> **set**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L234)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

---

### Step

#### Constructors

##### constructor()

> **new Step**(step: [`StepChange`](modules.md#stepchange), ticker: `Observable`\<`number`\>): [`Step`](modules.md#step)

Defined in: [lib/@empirica/core/src/player/steps.ts:89](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/steps.ts#L89)

###### Parameters

| Parameter | Type                                  |
| :-------- | :------------------------------------ |
| step      | [`StepChange`](modules.md#stepchange) |
| ticker    | `Observable`\<`number`\>              |

###### Returns

[`Step`](modules.md#step)

#### Accessors

##### current

> get **current()**: `undefined` \| [`StepTick`](modules.md#steptick)

Defined in: [lib/@empirica/core/src/player/steps.ts:117](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/steps.ts#L117)

#### Methods

##### \_stop()

> **\_stop**(): `void`

Defined in: [lib/@empirica/core/src/player/steps.ts:151](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/steps.ts#L151)

###### Returns

`void`

##### \_update()

> **\_update**(step: [`StepChange`](modules.md#stepchange)): `void`

Defined in: [lib/@empirica/core/src/player/steps.ts:122](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/steps.ts#L122)

###### Parameters

| Parameter | Type                                  |
| :-------- | :------------------------------------ |
| step      | [`StepChange`](modules.md#stepchange) |

###### Returns

`void`

##### obs()

> **obs**(): `Observable`\<`undefined` \| [`StepTick`](modules.md#steptick)\>

Defined in: [lib/@empirica/core/src/player/steps.ts:113](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/steps.ts#L113)

###### Returns

`Observable`\<`undefined` \| [`StepTick`](modules.md#steptick)\>

---

### Steps

#### Constructors

##### constructor()

> **new Steps**(stepsObs: `Observable`\<[`StepUpdate`](modules.md#stepupdate)\>, donesObs: `Observable`\<`void`\>): [`Steps`](modules.md#steps)

Defined in: [lib/@empirica/core/src/player/steps.ts:164](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/steps.ts#L164)

###### Parameters

| Parameter | Type                                                  |
| :-------- | :---------------------------------------------------- |
| stepsObs  | `Observable`\<[`StepUpdate`](modules.md#stepupdate)\> |
| donesObs  | `Observable`\<`void`\>                                |

###### Returns

[`Steps`](modules.md#steps)

#### Methods

##### hadUpdates()

> **hadUpdates**(): `boolean`

Defined in: [lib/@empirica/core/src/player/steps.ts:188](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/steps.ts#L188)

###### Returns

`boolean`

##### step()

> **step**(stepID: `string`): `undefined` \| [`Step`](modules.md#step)

Defined in: [lib/@empirica/core/src/player/steps.ts:184](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/steps.ts#L184)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| stepID    | `string` |

###### Returns

`undefined` \| [`Step`](modules.md#step)

---

### TajribaProvider

#### Constructors

##### constructor()

> **new TajribaProvider**(
> changes: `Observable`\<`ChangePayload`\>,
> globals: `Observable`\<`SubAttributesPayload`\>,
> setAttributes: `Function`): [`TajribaProvider`](modules.md#tajribaprovider)

Defined in: [lib/@empirica/core/src/player/provider.ts:25](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/provider.ts#L25)

###### Parameters

| Parameter     | Type                                                   |
| :------------ | :----------------------------------------------------- |
| changes       | `Observable`\<`ChangePayload`\>                        |
| globals       | `Observable`\<`SubAttributesPayload`\>                 |
| setAttributes | (`input`: `SetAttributeInput`[]) => `Promise`\<`any`\> |

###### Returns

[`TajribaProvider`](modules.md#tajribaprovider)

#### Properties

##### attributes

> **attributes**: `Subject`\<[`AttributeUpdate`](modules.md#attributeupdate)\>

Defined in: [lib/@empirica/core/src/player/provider.ts:20](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/provider.ts#L20)

##### dones

> **dones**: `Subject`\<`string`[]\>

Defined in: [lib/@empirica/core/src/player/provider.ts:23](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/provider.ts#L23)

##### globals

> `readonly` **globals**: `Observable`\<`SubAttributesPayload`\>

Defined in: [lib/@empirica/core/src/player/provider.ts:27](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/provider.ts#L27)

##### participants

> **participants**: `Subject`\<[`ParticipantUpdate`](modules.md#participantupdate)\>

Defined in: [lib/@empirica/core/src/player/provider.ts:21](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/provider.ts#L21)

##### scopes

> **scopes**: `Subject`\<[`ScopeUpdate`](modules.md#scopeupdate)\>

Defined in: [lib/@empirica/core/src/player/provider.ts:19](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/provider.ts#L19)

##### setAttributes

> `readonly` **setAttributes**: `Function`

Defined in: [lib/@empirica/core/src/player/provider.ts:28](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/provider.ts#L28)

###### Type declaration

> > (input: `SetAttributeInput`[]): `Promise`\<`any`\>
>
> ####### Parameters
>
> | Parameter | Type                  |
> | :-------- | :-------------------- |
> | input     | `SetAttributeInput`[] |
>
> ####### Returns
>
> `Promise`\<`any`\>

##### steps

> **steps**: `Subject`\<[`StepUpdate`](modules.md#stepupdate)\>

Defined in: [lib/@empirica/core/src/player/provider.ts:22](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/provider.ts#L22)

---

## Interfaces

### AttributeChange

#### Properties

##### createdAt

> `optional` **createdAt**: `string`

createdAt is the time the Attribute was created. int64 Date + Time
value given in Epoch with ns precision

Defined in: [lib/@empirica/core/src/shared/attributes.ts:14](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L14)

##### deleted

> `optional` **deleted**: `boolean`

deleted is true with the attribute was deleted.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:8](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L8)

##### deletedAt

> `optional` **deletedAt**: `number`

deletedAt is the time when the Attribute was deleted. int64 Date + Time
value given in Epoch with ns precision

Defined in: [lib/@empirica/core/src/shared/attributes.ts:11](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L11)

##### id

> **id**: `string`

id is the identifier for the Attribute.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:16](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L16)

##### index

> `optional` **index**: `null` \| `number`

index is the index of the attribute if the value is a vector.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:18](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L18)

##### isNew

> `optional` **isNew**: `boolean`

isNew is true if the Attribute was just created.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:20](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L20)

##### key

> **key**: `string`

key is the attribute key being updated.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:22](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L22)

##### node

> `optional` **node**: `object`

node is the Attribute's Node.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:26](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L26)

###### Type declaration

> **\_\_typename**: "Scope"
>
> **id**: `string`
>
> `optional` **kind**: `string`
>
> `optional` **name**: `string`

##### nodeID

> `optional` **nodeID**: `string`

nodeID is the identifier for the Attribute's Node.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:24](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L24)

##### val

> `optional` **val**: `null` \| `string`

value is the value of the updated attribute.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:33](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L33)

##### vector

> **vector**: `boolean`

vector indicates whether the value is a vector.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:35](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L35)

##### version

> **version**: `number`

version is the version number of this Attribute, starting at 1.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:37](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L37)

---

### AttributeOptions

#### Properties

##### append

> **append**: `null` \| `boolean`

Append, only used if the Attribute is a vector, indicates to append the
attribute to the vector.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:231](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L231)

##### immutable

> **immutable**: `boolean`

Immutable creates an Attribute that cannot be updated.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:221](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L221)

##### index

> **index**: `null` \| `number`

Index, only used if the Attribute is a vector, indicates which index to
update the value at.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:226](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L226)

##### private

> **private**: `boolean`

Private indicates the attribute will not be visible to other Participants.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:214](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L214)

##### protected

> **protected**: `boolean`

Protected indicates the attribute will not be updatable by other
Participants.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:219](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L219)

---

### AttributeUpdate

#### Properties

##### attribute

> **attribute**: [`AttributeChange`](modules.md#attributechange)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:41](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L41)

##### removed

> **removed**: `boolean`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:42](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/attributes.ts#L42)

---

### Json

#### Indexable

\[`x`: `string`\]: [`JsonValue`](modules.md#jsonvalue)

---

### JsonArray

#### Hierarchy

- `Array`\<[`JsonValue`](modules.md#jsonvalue)\>.**`JsonArray`**

#### Properties

##### length

> **length**: `number`

Gets or sets the length of the array. This is a number one higher than the highest index in the array.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1279

###### Inherited from

Array.length

#### Methods

##### [iterator]()

> **[iterator]**(): `IterableIterator`\<[`JsonValue`](modules.md#jsonvalue)\>

Iterator

Defined in: node_modules/typescript/lib/lib.es2015.iterable.d.ts:60

###### Returns

`IterableIterator`\<[`JsonValue`](modules.md#jsonvalue)\>

###### Inherited from

Array.[iterator]

##### [unscopables]()

> **[unscopables]**(): `object`

Returns an object whose properties have the value 'true'
when they will be absent when used in a 'with' statement.

Defined in: node_modules/typescript/lib/lib.es2015.symbol.wellknown.d.ts:99

###### Returns

`object`

**copyWithin**: `boolean`

**entries**: `boolean`

**fill**: `boolean`

**find**: `boolean`

**findIndex**: `boolean`

**keys**: `boolean`

**values**: `boolean`

###### Inherited from

Array.[unscopables]

##### at()

> **at**(index: `number`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Takes an integer value and returns the item at that index,
allowing for positive and negative integers.
Negative integers count back from the last item in the array.

Defined in: node_modules/@types/node/globals.d.ts:86

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| index     | `number` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

Array.at

##### concat()

> **concat**(...items: `ConcatArray`\<[`JsonValue`](modules.md#jsonvalue)\>[]): [`JsonValue`](modules.md#jsonvalue)[]

Combines two or more arrays.
This method returns a new array without modifying any existing arrays.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1303

###### Parameters

| Parameter | Type                                                   | Description                                                    |
| :-------- | :----------------------------------------------------- | :------------------------------------------------------------- |
| ...items  | `ConcatArray`\<[`JsonValue`](modules.md#jsonvalue)\>[] | Additional arrays and/or items to add to the end of the array. |

###### Returns

[`JsonValue`](modules.md#jsonvalue)[]

###### Inherited from

Array.concat

> **concat**(...items: ([`JsonValue`](modules.md#jsonvalue) \| `ConcatArray`\<[`JsonValue`](modules.md#jsonvalue)\>)[]): [`JsonValue`](modules.md#jsonvalue)[]

Combines two or more arrays.
This method returns a new array without modifying any existing arrays.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1309

###### Parameters

| Parameter | Type                                                                                            | Description                                                    |
| :-------- | :---------------------------------------------------------------------------------------------- | :------------------------------------------------------------- |
| ...items  | ([`JsonValue`](modules.md#jsonvalue) \| `ConcatArray`\<[`JsonValue`](modules.md#jsonvalue)\>)[] | Additional arrays and/or items to add to the end of the array. |

###### Returns

[`JsonValue`](modules.md#jsonvalue)[]

###### Inherited from

Array.concat

##### copyWithin()

> **copyWithin**(
> target: `number`,
> start: `number`,
> end?: `number`): [`JsonArray`](modules.md#jsonarray)

Returns the this object after copying a section of the array identified by start and end
to the same array starting at position target

Defined in: node_modules/typescript/lib/lib.es2015.core.d.ts:64

###### Parameters

| Parameter | Type     | Description                                                                                                |
| :-------- | :------- | :--------------------------------------------------------------------------------------------------------- |
| target    | `number` | If target is negative, it is treated as length+target where length is the<br />length of the array.        |
| start     | `number` | If start is negative, it is treated as length+start. If end is negative, it<br />is treated as length+end. |
| end?      | `number` | If not specified, length of the this object is used as its default value.                                  |

###### Returns

[`JsonArray`](modules.md#jsonarray)

###### Inherited from

Array.copyWithin

##### entries()

> **entries**(): `IterableIterator`\<[`number`, [`JsonValue`](modules.md#jsonvalue)]\>

Returns an iterable of key, value pairs for every entry in the array

Defined in: node_modules/typescript/lib/lib.es2015.iterable.d.ts:65

###### Returns

`IterableIterator`\<[`number`, [`JsonValue`](modules.md#jsonvalue)]\>

###### Inherited from

Array.entries

##### every()

> **every**\<S\>(predicate: `Function`, thisArg?: `any`): this is S[]

Determines whether all the members of an array satisfy the specified test.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1386

###### Type parameters

| Parameter                                       |
| :---------------------------------------------- |
| S _extends_ [`JsonValue`](modules.md#jsonvalue) |

###### Parameters

| Parameter | Type                                                                                                                            | Description                                                                                                                                                                                                                                            |
| :-------- | :------------------------------------------------------------------------------------------------------------------------------ | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| predicate | (`value`: [`JsonValue`](modules.md#jsonvalue), `index`: `number`, `array`: [`JsonValue`](modules.md#jsonvalue)[]) => value is S | A function that accepts up to three arguments. The every method calls<br />the predicate function for each element in the array until the predicate returns a value<br />which is coercible to the Boolean value false, or until the end of the array. |
| thisArg?  | `any`                                                                                                                           | An object to which the this keyword can refer in the predicate function.<br />If thisArg is omitted, undefined is used as the this value.                                                                                                              |

###### Returns

this is S[]

###### Inherited from

Array.every

> **every**(predicate: `Function`, thisArg?: `any`): `boolean`

Determines whether all the members of an array satisfy the specified test.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1395

###### Parameters

| Parameter | Type                                                                                                                           | Description                                                                                                                                                                                                                                            |
| :-------- | :----------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| predicate | (`value`: [`JsonValue`](modules.md#jsonvalue), `index`: `number`, `array`: [`JsonValue`](modules.md#jsonvalue)[]) => `unknown` | A function that accepts up to three arguments. The every method calls<br />the predicate function for each element in the array until the predicate returns a value<br />which is coercible to the Boolean value false, or until the end of the array. |
| thisArg?  | `any`                                                                                                                          | An object to which the this keyword can refer in the predicate function.<br />If thisArg is omitted, undefined is used as the this value.                                                                                                              |

###### Returns

`boolean`

###### Inherited from

Array.every

##### fill()

> **fill**(
> value: [`JsonValue`](modules.md#jsonvalue),
> start?: `number`,
> end?: `number`): [`JsonArray`](modules.md#jsonarray)

Changes all array elements from `start` to `end` index to a static `value` and returns the modified array

Defined in: node_modules/typescript/lib/lib.es2015.core.d.ts:53

###### Parameters

| Parameter | Type                                | Description                                                                                                                            |
| :-------- | :---------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------- |
| value     | [`JsonValue`](modules.md#jsonvalue) | value to fill array section with                                                                                                       |
| start?    | `number`                            | index to start filling the array at. If start is negative, it is treated as<br />length+start where length is the length of the array. |
| end?      | `number`                            | index to stop filling the array at. If end is negative, it is treated as<br />length+end.                                              |

###### Returns

[`JsonArray`](modules.md#jsonarray)

###### Inherited from

Array.fill

##### filter()

> **filter**\<S\>(predicate: `Function`, thisArg?: `any`): `S`[]

Returns the elements of an array that meet the condition specified in a callback function.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1422

###### Type parameters

| Parameter                                       |
| :---------------------------------------------- |
| S _extends_ [`JsonValue`](modules.md#jsonvalue) |

###### Parameters

| Parameter | Type                                                                                                                            | Description                                                                                                                           |
| :-------- | :------------------------------------------------------------------------------------------------------------------------------ | :------------------------------------------------------------------------------------------------------------------------------------ |
| predicate | (`value`: [`JsonValue`](modules.md#jsonvalue), `index`: `number`, `array`: [`JsonValue`](modules.md#jsonvalue)[]) => value is S | A function that accepts up to three arguments. The filter method calls the predicate function one time for each element in the array. |
| thisArg?  | `any`                                                                                                                           | An object to which the this keyword can refer in the predicate function. If thisArg is omitted, undefined is used as the this value.  |

###### Returns

`S`[]

###### Inherited from

Array.filter

> **filter**(predicate: `Function`, thisArg?: `any`): [`JsonValue`](modules.md#jsonvalue)[]

Returns the elements of an array that meet the condition specified in a callback function.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1428

###### Parameters

| Parameter | Type                                                                                                                           | Description                                                                                                                           |
| :-------- | :----------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------ |
| predicate | (`value`: [`JsonValue`](modules.md#jsonvalue), `index`: `number`, `array`: [`JsonValue`](modules.md#jsonvalue)[]) => `unknown` | A function that accepts up to three arguments. The filter method calls the predicate function one time for each element in the array. |
| thisArg?  | `any`                                                                                                                          | An object to which the this keyword can refer in the predicate function. If thisArg is omitted, undefined is used as the this value.  |

###### Returns

[`JsonValue`](modules.md#jsonvalue)[]

###### Inherited from

Array.filter

##### find()

> **find**\<S\>(predicate: `Function`, thisArg?: `any`): `undefined` \| `S`

Returns the value of the first element in the array where predicate is true, and undefined
otherwise.

Defined in: node_modules/typescript/lib/lib.es2015.core.d.ts:31

###### Type parameters

| Parameter                                       |
| :---------------------------------------------- |
| S _extends_ [`JsonValue`](modules.md#jsonvalue) |

###### Parameters

| Parameter | Type                                                                                                                                          | Description                                                                                                                                                                                                                                          |
| :-------- | :-------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| predicate | (`this`: `void`, `value`: [`JsonValue`](modules.md#jsonvalue), `index`: `number`, `obj`: [`JsonValue`](modules.md#jsonvalue)[]) => value is S | find calls predicate once for each element of the array, in ascending<br />order, until it finds one where predicate returns true. If such an element is found, find<br />immediately returns that element value. Otherwise, find returns undefined. |
| thisArg?  | `any`                                                                                                                                         | If provided, it will be used as the this value for each invocation of<br />predicate. If it is not provided, undefined is used instead.                                                                                                              |

###### Returns

`undefined` \| `S`

###### Inherited from

Array.find

> **find**(predicate: `Function`, thisArg?: `any`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: node_modules/typescript/lib/lib.es2015.core.d.ts:32

###### Parameters

| Parameter | Type                                                                                                                         |
| :-------- | :--------------------------------------------------------------------------------------------------------------------------- |
| predicate | (`value`: [`JsonValue`](modules.md#jsonvalue), `index`: `number`, `obj`: [`JsonValue`](modules.md#jsonvalue)[]) => `unknown` |
| thisArg?  | `any`                                                                                                                        |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

Array.find

##### findIndex()

> **findIndex**(predicate: `Function`, thisArg?: `any`): `number`

Returns the index of the first element in the array where predicate is true, and -1
otherwise.

Defined in: node_modules/typescript/lib/lib.es2015.core.d.ts:43

###### Parameters

| Parameter | Type                                                                                                                         | Description                                                                                                                                                                                                                                             |
| :-------- | :--------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| predicate | (`value`: [`JsonValue`](modules.md#jsonvalue), `index`: `number`, `obj`: [`JsonValue`](modules.md#jsonvalue)[]) => `unknown` | find calls predicate once for each element of the array, in ascending<br />order, until it finds one where predicate returns true. If such an element is found,<br />findIndex immediately returns that element index. Otherwise, findIndex returns -1. |
| thisArg?  | `any`                                                                                                                        | If provided, it will be used as the this value for each invocation of<br />predicate. If it is not provided, undefined is used instead.                                                                                                                 |

###### Returns

`number`

###### Inherited from

Array.findIndex

##### flat()

> **flat**\<A, D\>(this: `A`, depth?: `D`): `FlatArray`\<`A`, `D`\>[]

Returns a new array with all sub-array elements concatenated into it recursively up to the
specified depth.

Defined in: node_modules/typescript/lib/lib.es2019.array.d.ts:81

###### Type parameters

| Parameter            | Default |
| :------------------- | :------ |
| A                    | -       |
| D _extends_ `number` | 1       |

###### Parameters

| Parameter | Type | Description                 |
| :-------- | :--- | :-------------------------- |
| this      | `A`  | -                           |
| depth?    | `D`  | The maximum recursion depth |

###### Returns

`FlatArray`\<`A`, `D`\>[]

###### Inherited from

Array.flat

##### flatMap()

> **flatMap**\<U, This\>(callback: `Function`, thisArg?: `This`): `U`[]

Calls a defined callback function on each element of an array. Then, flattens the result into
a new array.
This is identical to a map followed by flat with depth 1.

Defined in: node_modules/typescript/lib/lib.es2019.array.d.ts:70

###### Type parameters

| Parameter | Default     |
| :-------- | :---------- |
| U         | -           |
| This      | `undefined` |

###### Parameters

| Parameter | Type                                                                                                                                                         | Description                                                                                                                                |
| :-------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------- |
| callback  | (`this`: `This`, `value`: [`JsonValue`](modules.md#jsonvalue), `index`: `number`, `array`: [`JsonValue`](modules.md#jsonvalue)[]) => `U` \| _readonly_ `U`[] | A function that accepts up to three arguments. The flatMap method calls the<br />callback function one time for each element in the array. |
| thisArg?  | `This`                                                                                                                                                       | An object to which the this keyword can refer in the callback function. If<br />thisArg is omitted, undefined is used as the this value.   |

###### Returns

`U`[]

###### Inherited from

Array.flatMap

##### forEach()

> **forEach**(callbackfn: `Function`, thisArg?: `any`): `void`

Performs the specified action for each element in an array.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1410

###### Parameters

| Parameter  | Type                                                                                                                        | Description                                                                                                                           |
| :--------- | :-------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------ |
| callbackfn | (`value`: [`JsonValue`](modules.md#jsonvalue), `index`: `number`, `array`: [`JsonValue`](modules.md#jsonvalue)[]) => `void` | A function that accepts up to three arguments. forEach calls the callbackfn function one time for each element in the array.          |
| thisArg?   | `any`                                                                                                                       | An object to which the this keyword can refer in the callbackfn function. If thisArg is omitted, undefined is used as the this value. |

###### Returns

`void`

###### Inherited from

Array.forEach

##### includes()

> **includes**(searchElement: [`JsonValue`](modules.md#jsonvalue), fromIndex?: `number`): `boolean`

Determines whether an array includes a certain element, returning true or false as appropriate.

Defined in: node_modules/typescript/lib/lib.es2016.array.include.d.ts:27

###### Parameters

| Parameter     | Type                                | Description                                                               |
| :------------ | :---------------------------------- | :------------------------------------------------------------------------ |
| searchElement | [`JsonValue`](modules.md#jsonvalue) | The element to search for.                                                |
| fromIndex?    | `number`                            | The position in this array at which to begin searching for searchElement. |

###### Returns

`boolean`

###### Inherited from

Array.includes

##### indexOf()

> **indexOf**(searchElement: [`JsonValue`](modules.md#jsonvalue), fromIndex?: `number`): `number`

Returns the index of the first occurrence of a value in an array, or -1 if it is not present.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1371

###### Parameters

| Parameter     | Type                                | Description                                                                                          |
| :------------ | :---------------------------------- | :--------------------------------------------------------------------------------------------------- |
| searchElement | [`JsonValue`](modules.md#jsonvalue) | The value to locate in the array.                                                                    |
| fromIndex?    | `number`                            | The array index at which to begin the search. If fromIndex is omitted, the search starts at index 0. |

###### Returns

`number`

###### Inherited from

Array.indexOf

##### join()

> **join**(separator?: `string`): `string`

Adds all the elements of an array into a string, separated by the specified separator string.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1314

###### Parameters

| Parameter  | Type     | Description                                                                                                                                          |
| :--------- | :------- | :--------------------------------------------------------------------------------------------------------------------------------------------------- |
| separator? | `string` | A string used to separate one element of the array from the next in the resulting string. If omitted, the array elements are separated with a comma. |

###### Returns

`string`

###### Inherited from

Array.join

##### keys()

> **keys**(): `IterableIterator`\<`number`\>

Returns an iterable of keys in the array

Defined in: node_modules/typescript/lib/lib.es2015.iterable.d.ts:70

###### Returns

`IterableIterator`\<`number`\>

###### Inherited from

Array.keys

##### lastIndexOf()

> **lastIndexOf**(searchElement: [`JsonValue`](modules.md#jsonvalue), fromIndex?: `number`): `number`

Returns the index of the last occurrence of a specified value in an array, or -1 if it is not present.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1377

###### Parameters

| Parameter     | Type                                | Description                                                                                                                      |
| :------------ | :---------------------------------- | :------------------------------------------------------------------------------------------------------------------------------- |
| searchElement | [`JsonValue`](modules.md#jsonvalue) | The value to locate in the array.                                                                                                |
| fromIndex?    | `number`                            | The array index at which to begin searching backward. If fromIndex is omitted, the search starts at the last index in the array. |

###### Returns

`number`

###### Inherited from

Array.lastIndexOf

##### map()

> **map**\<U\>(callbackfn: `Function`, thisArg?: `any`): `U`[]

Calls a defined callback function on each element of an array, and returns an array that contains the results.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1416

###### Type parameters

| Parameter |
| :-------- |
| U         |

###### Parameters

| Parameter  | Type                                                                                                                     | Description                                                                                                                           |
| :--------- | :----------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------ |
| callbackfn | (`value`: [`JsonValue`](modules.md#jsonvalue), `index`: `number`, `array`: [`JsonValue`](modules.md#jsonvalue)[]) => `U` | A function that accepts up to three arguments. The map method calls the callbackfn function one time for each element in the array.   |
| thisArg?   | `any`                                                                                                                    | An object to which the this keyword can refer in the callbackfn function. If thisArg is omitted, undefined is used as the this value. |

###### Returns

`U`[]

###### Inherited from

Array.map

##### pop()

> **pop**(): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Removes the last element from an array and returns it.
If the array is empty, undefined is returned and the array is not modified.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1292

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

Array.pop

##### push()

> **push**(...items: [`JsonValue`](modules.md#jsonvalue)[]): `number`

Appends new elements to the end of an array, and returns the new length of the array.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1297

###### Parameters

| Parameter | Type                                  | Description                       |
| :-------- | :------------------------------------ | :-------------------------------- |
| ...items  | [`JsonValue`](modules.md#jsonvalue)[] | New elements to add to the array. |

###### Returns

`number`

###### Inherited from

Array.push

##### reduce()

> **reduce**(callbackfn: `Function`): [`JsonValue`](modules.md#jsonvalue)

Calls the specified callback function for all the elements in an array. The return value of the callback function is the accumulated result, and is provided as an argument in the next call to the callback function.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1434

###### Parameters

| Parameter  | Type                                                                                                                                                                                                                         | Description                                                                                                                           |
| :--------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------ |
| callbackfn | (`previousValue`: [`JsonValue`](modules.md#jsonvalue), `currentValue`: [`JsonValue`](modules.md#jsonvalue), `currentIndex`: `number`, `array`: [`JsonValue`](modules.md#jsonvalue)[]) => [`JsonValue`](modules.md#jsonvalue) | A function that accepts up to four arguments. The reduce method calls the callbackfn function one time for each element in the array. |

###### Returns

[`JsonValue`](modules.md#jsonvalue)

###### Inherited from

Array.reduce

> **reduce**(callbackfn: `Function`, initialValue: [`JsonValue`](modules.md#jsonvalue)): [`JsonValue`](modules.md#jsonvalue)

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1435

###### Parameters

| Parameter    | Type                                                                                                                                                                                                                         |
| :----------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| callbackfn   | (`previousValue`: [`JsonValue`](modules.md#jsonvalue), `currentValue`: [`JsonValue`](modules.md#jsonvalue), `currentIndex`: `number`, `array`: [`JsonValue`](modules.md#jsonvalue)[]) => [`JsonValue`](modules.md#jsonvalue) |
| initialValue | [`JsonValue`](modules.md#jsonvalue)                                                                                                                                                                                          |

###### Returns

[`JsonValue`](modules.md#jsonvalue)

###### Inherited from

Array.reduce

> **reduce**\<U\>(callbackfn: `Function`, initialValue: `U`): `U`

Calls the specified callback function for all the elements in an array. The return value of the callback function is the accumulated result, and is provided as an argument in the next call to the callback function.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1441

###### Type parameters

| Parameter |
| :-------- |
| U         |

###### Parameters

| Parameter    | Type                                                                                                                                                         | Description                                                                                                                                                                                      |
| :----------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| callbackfn   | (`previousValue`: `U`, `currentValue`: [`JsonValue`](modules.md#jsonvalue), `currentIndex`: `number`, `array`: [`JsonValue`](modules.md#jsonvalue)[]) => `U` | A function that accepts up to four arguments. The reduce method calls the callbackfn function one time for each element in the array.                                                            |
| initialValue | `U`                                                                                                                                                          | If initialValue is specified, it is used as the initial value to start the accumulation. The first call to the callbackfn function provides this value as an argument instead of an array value. |

###### Returns

`U`

###### Inherited from

Array.reduce

##### reduceRight()

> **reduceRight**(callbackfn: `Function`): [`JsonValue`](modules.md#jsonvalue)

Calls the specified callback function for all the elements in an array, in descending order. The return value of the callback function is the accumulated result, and is provided as an argument in the next call to the callback function.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1447

###### Parameters

| Parameter  | Type                                                                                                                                                                                                                         | Description                                                                                                                                |
| :--------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------- |
| callbackfn | (`previousValue`: [`JsonValue`](modules.md#jsonvalue), `currentValue`: [`JsonValue`](modules.md#jsonvalue), `currentIndex`: `number`, `array`: [`JsonValue`](modules.md#jsonvalue)[]) => [`JsonValue`](modules.md#jsonvalue) | A function that accepts up to four arguments. The reduceRight method calls the callbackfn function one time for each element in the array. |

###### Returns

[`JsonValue`](modules.md#jsonvalue)

###### Inherited from

Array.reduceRight

> **reduceRight**(callbackfn: `Function`, initialValue: [`JsonValue`](modules.md#jsonvalue)): [`JsonValue`](modules.md#jsonvalue)

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1448

###### Parameters

| Parameter    | Type                                                                                                                                                                                                                         |
| :----------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| callbackfn   | (`previousValue`: [`JsonValue`](modules.md#jsonvalue), `currentValue`: [`JsonValue`](modules.md#jsonvalue), `currentIndex`: `number`, `array`: [`JsonValue`](modules.md#jsonvalue)[]) => [`JsonValue`](modules.md#jsonvalue) |
| initialValue | [`JsonValue`](modules.md#jsonvalue)                                                                                                                                                                                          |

###### Returns

[`JsonValue`](modules.md#jsonvalue)

###### Inherited from

Array.reduceRight

> **reduceRight**\<U\>(callbackfn: `Function`, initialValue: `U`): `U`

Calls the specified callback function for all the elements in an array, in descending order. The return value of the callback function is the accumulated result, and is provided as an argument in the next call to the callback function.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1454

###### Type parameters

| Parameter |
| :-------- |
| U         |

###### Parameters

| Parameter    | Type                                                                                                                                                         | Description                                                                                                                                                                                      |
| :----------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| callbackfn   | (`previousValue`: `U`, `currentValue`: [`JsonValue`](modules.md#jsonvalue), `currentIndex`: `number`, `array`: [`JsonValue`](modules.md#jsonvalue)[]) => `U` | A function that accepts up to four arguments. The reduceRight method calls the callbackfn function one time for each element in the array.                                                       |
| initialValue | `U`                                                                                                                                                          | If initialValue is specified, it is used as the initial value to start the accumulation. The first call to the callbackfn function provides this value as an argument instead of an array value. |

###### Returns

`U`

###### Inherited from

Array.reduceRight

##### reverse()

> **reverse**(): [`JsonValue`](modules.md#jsonvalue)[]

Reverses the elements in an array in place.
This method mutates the array and returns a reference to the same array.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1319

###### Returns

[`JsonValue`](modules.md#jsonvalue)[]

###### Inherited from

Array.reverse

##### shift()

> **shift**(): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Removes the first element from an array and returns it.
If the array is empty, undefined is returned and the array is not modified.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1324

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

Array.shift

##### slice()

> **slice**(start?: `number`, end?: `number`): [`JsonValue`](modules.md#jsonvalue)[]

Returns a copy of a section of an array.
For both start and end, a negative index can be used to indicate an offset from the end of the array.
For example, -2 refers to the second to last element of the array.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1334

###### Parameters

| Parameter | Type     | Description                                                                                                                                                                         |
| :-------- | :------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| start?    | `number` | The beginning index of the specified portion of the array.<br />If start is undefined, then the slice begins at index 0.                                                            |
| end?      | `number` | The end index of the specified portion of the array. This is exclusive of the element at the index 'end'.<br />If end is undefined, then the slice extends to the end of the array. |

###### Returns

[`JsonValue`](modules.md#jsonvalue)[]

###### Inherited from

Array.slice

##### some()

> **some**(predicate: `Function`, thisArg?: `any`): `boolean`

Determines whether the specified callback function returns true for any element of an array.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1404

###### Parameters

| Parameter | Type                                                                                                                           | Description                                                                                                                                                                                                                                          |
| :-------- | :----------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| predicate | (`value`: [`JsonValue`](modules.md#jsonvalue), `index`: `number`, `array`: [`JsonValue`](modules.md#jsonvalue)[]) => `unknown` | A function that accepts up to three arguments. The some method calls<br />the predicate function for each element in the array until the predicate returns a value<br />which is coercible to the Boolean value true, or until the end of the array. |
| thisArg?  | `any`                                                                                                                          | An object to which the this keyword can refer in the predicate function.<br />If thisArg is omitted, undefined is used as the this value.                                                                                                            |

###### Returns

`boolean`

###### Inherited from

Array.some

##### sort()

> **sort**(compareFn?: `Function`): [`JsonArray`](modules.md#jsonarray)

Sorts an array in place.
This method mutates the array and returns a reference to the same array.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1345

###### Parameters

| Parameter  | Type                                                                                             | Description                                                                                                                                                                                                                                                                                                                                              |
| :--------- | :----------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| compareFn? | (`a`: [`JsonValue`](modules.md#jsonvalue), `b`: [`JsonValue`](modules.md#jsonvalue)) => `number` | Function used to determine the order of the elements. It is expected to return<br />a negative value if the first argument is less than the second argument, zero if they're equal, and a positive<br />value otherwise. If omitted, the elements are sorted in ascending, ASCII character order.<br />`ts<br />[11,2,22,1].sort((a, b) => a - b)<br />` |

###### Returns

[`JsonArray`](modules.md#jsonarray)

###### Inherited from

Array.sort

##### splice()

> **splice**(start: `number`, deleteCount?: `number`): [`JsonValue`](modules.md#jsonvalue)[]

Removes elements from an array and, if necessary, inserts new elements in their place, returning the deleted elements.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1352

###### Parameters

| Parameter    | Type     | Description                                                                 |
| :----------- | :------- | :-------------------------------------------------------------------------- |
| start        | `number` | The zero-based location in the array from which to start removing elements. |
| deleteCount? | `number` | The number of elements to remove.                                           |

###### Returns

[`JsonValue`](modules.md#jsonvalue)[]

An array containing the elements that were deleted.

###### Inherited from

Array.splice

> **splice**(
> start: `number`,
> deleteCount: `number`,
> ...items: [`JsonValue`](modules.md#jsonvalue)[]): [`JsonValue`](modules.md#jsonvalue)[]

Removes elements from an array and, if necessary, inserts new elements in their place, returning the deleted elements.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1360

###### Parameters

| Parameter   | Type                                  | Description                                                                 |
| :---------- | :------------------------------------ | :-------------------------------------------------------------------------- |
| start       | `number`                              | The zero-based location in the array from which to start removing elements. |
| deleteCount | `number`                              | The number of elements to remove.                                           |
| ...items    | [`JsonValue`](modules.md#jsonvalue)[] | Elements to insert into the array in place of the deleted elements.         |

###### Returns

[`JsonValue`](modules.md#jsonvalue)[]

An array containing the elements that were deleted.

###### Inherited from

Array.splice

##### toLocaleString()

> **toLocaleString**(): `string`

Returns a string representation of an array. The elements are converted to string using their toLocaleString methods.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1287

###### Returns

`string`

###### Inherited from

Array.toLocaleString

##### toString()

> **toString**(): `string`

Returns a string representation of an array.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1283

###### Returns

`string`

###### Inherited from

Array.toString

##### unshift()

> **unshift**(...items: [`JsonValue`](modules.md#jsonvalue)[]): `number`

Inserts new elements at the start of an array, and returns the new length of the array.

Defined in: node_modules/typescript/lib/lib.es5.d.ts:1365

###### Parameters

| Parameter | Type                                  | Description                                   |
| :-------- | :------------------------------------ | :-------------------------------------------- |
| ...items  | [`JsonValue`](modules.md#jsonvalue)[] | Elements to insert at the start of the array. |

###### Returns

`number`

###### Inherited from

Array.unshift

##### values()

> **values**(): `IterableIterator`\<[`JsonValue`](modules.md#jsonvalue)\>

Returns an iterable of values in the array

Defined in: node_modules/typescript/lib/lib.es2015.iterable.d.ts:75

###### Returns

`IterableIterator`\<[`JsonValue`](modules.md#jsonvalue)\>

###### Inherited from

Array.values

---

### ParticipantUpdate

#### Properties

##### participant

> **participant**: `ParticipantChange`

Defined in: [lib/@empirica/core/src/player/provider.ts:14](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/provider.ts#L14)

##### removed

> **removed**: `boolean`

Defined in: [lib/@empirica/core/src/player/provider.ts:15](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/provider.ts#L15)

---

### ScopeIdent

#### Properties

##### id

> **id**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:19](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L19)

##### kind

> **kind**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:20](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L20)

---

### ScopeUpdate

#### Properties

##### removed

> **removed**: `boolean`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:25](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L25)

##### scope

> **scope**: [`ScopeIdent`](modules.md#scopeident)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:24](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L24)

---

### StepChange

#### Properties

##### elapsed

> `optional` **elapsed**: `number`

Defined in: [lib/@empirica/core/src/player/steps.ts:6](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/steps.ts#L6)

##### id

> **id**: `string`

Defined in: [lib/@empirica/core/src/player/steps.ts:4](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/steps.ts#L4)

##### remaining

> `optional` **remaining**: `number`

Defined in: [lib/@empirica/core/src/player/steps.ts:7](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/steps.ts#L7)

##### running

> **running**: `boolean`

Defined in: [lib/@empirica/core/src/player/steps.ts:5](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/steps.ts#L5)

---

### StepTick

#### Properties

##### duration

> **duration**: `number`

Defined in: [lib/@empirica/core/src/player/steps.ts:20](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/steps.ts#L20)

##### elapsed

> **elapsed**: `number`

Defined in: [lib/@empirica/core/src/player/steps.ts:18](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/steps.ts#L18)

##### ended

> **ended**: `boolean`

Defined in: [lib/@empirica/core/src/player/steps.ts:17](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/steps.ts#L17)

##### remaining

> **remaining**: `number`

Defined in: [lib/@empirica/core/src/player/steps.ts:19](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/steps.ts#L19)

##### started

> **started**: `boolean`

Defined in: [lib/@empirica/core/src/player/steps.ts:16](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/steps.ts#L16)

---

### StepUpdate

#### Properties

##### removed

> **removed**: `boolean`

Defined in: [lib/@empirica/core/src/player/steps.ts:12](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/steps.ts#L12)

##### step

> **step**: [`StepChange`](modules.md#stepchange)

Defined in: [lib/@empirica/core/src/player/steps.ts:11](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/steps.ts#L11)

---

## Type Aliases

### AttributeInput

> **AttributeInput**: `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:174](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L174)

#### Type declaration

> `optional` **ao**: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>
>
> **key**: `string`
>
> **value**: [`JsonValue`](modules.md#jsonvalue)

---

### Constructor

> **Constructor**: \<`T`\> `Function`

Defined in: [lib/@empirica/core/src/shared/helpers.ts:1](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/helpers.ts#L1)

#### Type parameters

| Parameter       | Default |
| :-------------- | :------ |
| T _extends_ \{} | \{}     |

#### Type declaration

> > (...args: `any`[]): `T`
>
> ##### Parameters
>
> | Parameter | Type    |
> | :-------- | :------ |
> | ...args   | `any`[] |
>
> ##### Returns
>
> `T`

---

### Epoch

> **Epoch**: `number`

Defined in: [lib/@empirica/core/src/player/steps.ts:81](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/steps.ts#L81)

---

### JsonValue

> **JsonValue**: `string` \| `number` \| `boolean` \| `Date` \| [`Json`](modules.md#json) \| [`JsonArray`](modules.md#jsonarray) \| `null`

Defined in: [lib/@empirica/core/src/utils/json.ts:1](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/utils/json.ts#L1)

---

### ScopeConstructor

> **ScopeConstructor**: \<`Context`, `Kinds`\> [`Constructor`](modules.md#constructor)\<[`SharedScope`](modules.md#sharedscope)\<`Context`, `Kinds`\>\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:28](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/shared/scopes.ts#L28)

#### Type parameters

| Parameter           |
| :------------------ |
| Context             |
| Kinds _extends_ \{} |

---

## Variables

### isDevelopment

> `const` **isDevelopment**: `boolean`

Defined in: [lib/@empirica/core/src/player/utils.ts:1](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/utils.ts#L1)

---

### isProduction

> `const` **isProduction**: `boolean`

Defined in: [lib/@empirica/core/src/player/utils.ts:2](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/utils.ts#L2)

---

### isTest

> `const` **isTest**: `boolean`

Defined in: [lib/@empirica/core/src/player/utils.ts:3](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/utils.ts#L3)

---

## Functions

### createNewParticipant()

> **createNewParticipant**(key: `string` = `"participantKey"`): `void`

Defined in: [lib/@empirica/core/src/player/utils.ts:5](https://github.com/empiricaly/empirica/blob/1eb6b17/lib/@empirica/core/src/player/utils.ts#L5)

#### Parameters

| Parameter | Type     | Default value    |
| :-------- | :------- | :--------------- |
| key       | `string` | "participantKey" |

#### Returns

`void`

---
