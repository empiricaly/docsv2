# @empirica/core

## Index

### Classes

- [Attribute](modules.md#attribute)
- [Attributes](modules.md#attributes)
- [Context](modules.md#context)
- [Game](modules.md#game)
- [Player](modules.md#player)
- [PlayerGame](modules.md#playergame)
- [PlayerRound](modules.md#playerround)
- [PlayerStage](modules.md#playerstage)
- [Round](modules.md#round)
- [Scope](modules.md#scope)
- [Scopes](modules.md#scopes)
- [SharedScope](modules.md#sharedscope)
- [Stage](modules.md#stage)
- [Step](modules.md#step)
- [Steps](modules.md#steps)

### Interfaces

- [AttributeChange](modules.md#attributechange)
- [AttributeOptions](modules.md#attributeoptions)
- [AttributeUpdate](modules.md#attributeupdate)
- [ConsentProps](modules.md#consentprops)
- [EmpiricaContextProps](modules.md#empiricacontextprops)
- [Json](modules.md#json)
- [JsonArray](modules.md#jsonarray)
- [PlayerCreateProps](modules.md#playercreateprops)
- [ScopeIdent](modules.md#scopeident)
- [ScopeUpdate](modules.md#scopeupdate)
- [SliderProps](modules.md#sliderprops)
- [StepChange](modules.md#stepchange)
- [StepTick](modules.md#steptick)
- [StepUpdate](modules.md#stepupdate)

### Type Aliases

- [Attributable](modules.md#attributable)
- [AttributeInput](modules.md#attributeinput)
- [ChatProps](modules.md#chatprops)
- [Constructor](modules.md#constructor)
- [EmpiricaClassicKinds](modules.md#empiricaclassickinds)
- [JsonValue](modules.md#jsonvalue)
- [ScopeConstructor](modules.md#scopeconstructor)
- [StepsFunc](modules.md#stepsfunc)
- [StepsProps](modules.md#stepsprops)
- [WithChildren](modules.md#withchildren)

### Functions

- [Chat](modules.md#chat)
- [EmpiricaContext](modules.md#empiricacontext)
- [Lobby](modules.md#lobby)
- [Quiz](modules.md#quiz)
- [Slider](modules.md#slider)
- [Sweeper](modules.md#sweeper)
- [useGame](modules.md#usegame)
- [usePartModeCtx](modules.md#usepartmodectx)
- [usePartModeCtxKey](modules.md#usepartmodectxkey)
- [usePlayer](modules.md#useplayer)
- [usePlayers](modules.md#useplayers)
- [useRound](modules.md#useround)
- [useStage](modules.md#usestage)
- [useStageTimer](modules.md#usestagetimer)

## Classes

### Attribute

#### Constructors

##### constructor()

> **new Attribute**(
> setAttributes: `Function`,
> scopeID: `string`,
> key: `string`): [`Attribute`](modules.md#attribute)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:246](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L246)

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

Defined in: [lib/@empirica/core/src/shared/attributes.ts:249](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L249)

##### scopeID

> `readonly` **scopeID**: `string`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:248](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L248)

#### Accessors

##### createdAt

> get **createdAt()**: `null` \| `Date`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:256](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L256)

##### id

> get **id()**: `undefined` \| `string`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:252](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L252)

##### items

> get **items()**: `null` \| [`Attribute`](modules.md#attribute)[]

Defined in: [lib/@empirica/core/src/shared/attributes.ts:274](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L274)

##### nodeID

> get **nodeID()**: `string`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:268](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L268)

##### obs

> get **obs()**: `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/attributes.ts:260](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L260)

##### value

> get **value()**: `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:264](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L264)

#### Methods

##### \_prepSet()

> **\_prepSet**(
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>,
> item?: `boolean`): `undefined` \| `SetAttributeInput`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:292](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L292)

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

Defined in: [lib/@empirica/core/src/shared/attributes.ts:372](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L372)

###### Parameters

| Parameter | Type                                            |
| :-------- | :---------------------------------------------- |
| attr?     | [`AttributeChange`](modules.md#attributechange) |
| item?     | `boolean`                                       |

###### Returns

`void`

##### set()

> **set**(value: [`JsonValue`](modules.md#jsonvalue), ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:282](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L282)

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

Defined in: [lib/@empirica/core/src/shared/attributes.ts:49](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L49)

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

Defined in: [lib/@empirica/core/src/shared/attributes.ts:52](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L52)

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

Defined in: [lib/@empirica/core/src/shared/attributes.ts:67](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L67)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| scopeID   | `string` |
| key       | `string` |

###### Returns

[`Attribute`](modules.md#attribute)

##### attributePeek()

> **attributePeek**(scopeID: `string`, key: `string`): `undefined` \| [`Attribute`](modules.md#attribute)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:93](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L93)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| scopeID   | `string` |
| key       | `string` |

###### Returns

`undefined` \| [`Attribute`](modules.md#attribute)

##### attributes()

> **attributes**(scopeID: `string`): [`Attribute`](modules.md#attribute)[]

Defined in: [lib/@empirica/core/src/shared/attributes.ts:83](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L83)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| scopeID   | `string` |

###### Returns

[`Attribute`](modules.md#attribute)[]

##### nextAttributeValue()

> **nextAttributeValue**(scopeID: `string`, key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:129](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L129)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| scopeID   | `string` |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

##### scopeWasUpdated()

> **scopeWasUpdated**(scopeID?: `string`): `boolean`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:165](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L165)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| scopeID?  | `string` |

###### Returns

`boolean`

---

### Context

#### Constructors

##### constructor()

> **new Context**(): [`Context`](modules.md#context)

###### Returns

[`Context`](modules.md#context)

#### Properties

##### game

> `optional` **game**: `null` \| [`Game`](modules.md#game)

Defined in: [lib/@empirica/core/src/player/classic/classic.ts:95](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/classic.ts#L95)

##### stage

> `optional` **stage**: `null` \| [`Stage`](modules.md#stage)

Defined in: [lib/@empirica/core/src/player/classic/classic.ts:96](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/classic.ts#L96)

---

### Game

#### Hierarchy

- [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>.**`Game`**

#### Constructors

##### constructor()

> **new Game**(
> ctx: [`Context`](modules.md#context),
> scope: [`ScopeIdent`](modules.md#scopeident),
> scopes: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>,
> attributes: [`Attributes`](modules.md#attributes),
> steps: [`Steps`](modules.md#steps)): [`Game`](modules.md#game)

Defined in: [lib/@empirica/core/src/player/scopes.ts:45](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L45)

###### Parameters

| Parameter  | Type                                                                                                                        |
| :--------- | :-------------------------------------------------------------------------------------------------------------------------- |
| ctx        | [`Context`](modules.md#context)                                                                                             |
| scope      | [`ScopeIdent`](modules.md#scopeident)                                                                                       |
| scopes     | [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\> |
| attributes | [`Attributes`](modules.md#attributes)                                                                                       |
| steps      | [`Steps`](modules.md#steps)                                                                                                 |

###### Returns

[`Game`](modules.md#game)

###### Inherited from

[`Scope`](modules.md#scope).[`constructor`](modules.md#constructor)

#### Properties

##### scopes

> `readonly` **scopes**: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

Defined in: [lib/@empirica/core/src/player/scopes.ts:48](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L48)

###### Inherited from

[`Scope`](modules.md#scope).[`scopes`](modules.md#scopes)

#### Accessors

##### hasEnded

> get **hasEnded()**: `boolean`

Defined in: [lib/@empirica/core/src/player/classic/classic.ts:13](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/classic.ts#L13)

##### id

> get **id()**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L209)

###### Inherited from

[`Scope`](modules.md#scope).[`id`](modules.md#id)

##### round

> get **round()**: `undefined` \| [`Round`](modules.md#round)

Defined in: [lib/@empirica/core/src/player/classic/classic.ts:21](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/classic.ts#L21)

##### stage

> get **stage()**: `undefined` \| [`Stage`](modules.md#stage)

Defined in: [lib/@empirica/core/src/player/classic/classic.ts:17](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/classic.ts#L17)

#### Methods

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:269](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L269)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`append`](modules.md#append)

##### get()

> **get**(key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L221)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

[`Scope`](modules.md#scope).[`get`](modules.md#get)

##### getAttribute()

> **getAttribute**(key: `string`): `undefined` \| [`Attribute`](modules.md#attribute)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L225)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`Attribute`](modules.md#attribute)

###### Inherited from

[`Scope`](modules.md#scope).[`getAttribute`](modules.md#getattribute)

##### inspect()

> **inspect**(): `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:278](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L278)

###### Returns

`object`

###### Inherited from

[`Scope`](modules.md#scope).[`inspect`](modules.md#inspect)

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L229)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

###### Inherited from

[`Scope`](modules.md#scope).[`obs`](modules.md#obs)

##### scopeByKey()

> **scopeByKey**(key: `string`): `undefined` \| [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

Defined in: [lib/@empirica/core/src/player/scopes.ts:55](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L55)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

###### Inherited from

[`Scope`](modules.md#scope).[`scopeByKey`](modules.md#scopebykey)

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L233)

###### Parameters

| Parameter | Type                                            |
| :-------- | :---------------------------------------------- |
| values    | [`AttributeInput`](modules.md#attributeinput)[] |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`set`](modules.md#set)

> **set**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L234)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`set`](modules.md#set)

---

### Player

#### Hierarchy

- [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>.**`Player`**

#### Constructors

##### constructor()

> **new Player**(
> ctx: [`Context`](modules.md#context),
> scope: [`ScopeIdent`](modules.md#scopeident),
> scopes: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>,
> attributes: [`Attributes`](modules.md#attributes),
> steps: [`Steps`](modules.md#steps)): [`Player`](modules.md#player)

Defined in: [lib/@empirica/core/src/player/scopes.ts:45](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L45)

###### Parameters

| Parameter  | Type                                                                                                                        |
| :--------- | :-------------------------------------------------------------------------------------------------------------------------- |
| ctx        | [`Context`](modules.md#context)                                                                                             |
| scope      | [`ScopeIdent`](modules.md#scopeident)                                                                                       |
| scopes     | [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\> |
| attributes | [`Attributes`](modules.md#attributes)                                                                                       |
| steps      | [`Steps`](modules.md#steps)                                                                                                 |

###### Returns

[`Player`](modules.md#player)

###### Inherited from

[`Scope`](modules.md#scope).[`constructor`](modules.md#constructor)

#### Properties

##### scopes

> `readonly` **scopes**: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

Defined in: [lib/@empirica/core/src/player/scopes.ts:48](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L48)

###### Inherited from

[`Scope`](modules.md#scope).[`scopes`](modules.md#scopes)

#### Accessors

##### game

> get **game()**: `undefined` \| [`PlayerGame`](modules.md#playergame)

Defined in: [lib/@empirica/core/src/player/classic/classic.ts:27](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/classic.ts#L27)

##### id

> get **id()**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L209)

###### Inherited from

[`Scope`](modules.md#scope).[`id`](modules.md#id)

##### round

> get **round()**: `undefined` \| [`PlayerRound`](modules.md#playerround)

Defined in: [lib/@empirica/core/src/player/classic/classic.ts:37](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/classic.ts#L37)

##### stage

> get **stage()**: `undefined` \| [`PlayerStage`](modules.md#playerstage)

Defined in: [lib/@empirica/core/src/player/classic/classic.ts:52](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/classic.ts#L52)

#### Methods

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:269](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L269)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`append`](modules.md#append)

##### get()

> **get**(key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L221)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

[`Scope`](modules.md#scope).[`get`](modules.md#get)

##### getAttribute()

> **getAttribute**(key: `string`): `undefined` \| [`Attribute`](modules.md#attribute)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L225)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`Attribute`](modules.md#attribute)

###### Inherited from

[`Scope`](modules.md#scope).[`getAttribute`](modules.md#getattribute)

##### hasUpdated()

> **hasUpdated**(): `boolean`

Defined in: [lib/@empirica/core/src/player/classic/classic.ts:62](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/classic.ts#L62)

###### Returns

`boolean`

###### Overrides

Scope.hasUpdated

##### inspect()

> **inspect**(): `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:278](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L278)

###### Returns

`object`

###### Inherited from

[`Scope`](modules.md#scope).[`inspect`](modules.md#inspect)

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L229)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

###### Inherited from

[`Scope`](modules.md#scope).[`obs`](modules.md#obs)

##### scopeByKey()

> **scopeByKey**(key: `string`): `undefined` \| [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

Defined in: [lib/@empirica/core/src/player/scopes.ts:55](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L55)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

###### Inherited from

[`Scope`](modules.md#scope).[`scopeByKey`](modules.md#scopebykey)

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L233)

###### Parameters

| Parameter | Type                                            |
| :-------- | :---------------------------------------------- |
| values    | [`AttributeInput`](modules.md#attributeinput)[] |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`set`](modules.md#set)

> **set**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L234)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`set`](modules.md#set)

---

### PlayerGame

#### Hierarchy

- [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>.**`PlayerGame`**

#### Constructors

##### constructor()

> **new PlayerGame**(
> ctx: [`Context`](modules.md#context),
> scope: [`ScopeIdent`](modules.md#scopeident),
> scopes: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>,
> attributes: [`Attributes`](modules.md#attributes),
> steps: [`Steps`](modules.md#steps)): [`PlayerGame`](modules.md#playergame)

Defined in: [lib/@empirica/core/src/player/scopes.ts:45](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L45)

###### Parameters

| Parameter  | Type                                                                                                                        |
| :--------- | :-------------------------------------------------------------------------------------------------------------------------- |
| ctx        | [`Context`](modules.md#context)                                                                                             |
| scope      | [`ScopeIdent`](modules.md#scopeident)                                                                                       |
| scopes     | [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\> |
| attributes | [`Attributes`](modules.md#attributes)                                                                                       |
| steps      | [`Steps`](modules.md#steps)                                                                                                 |

###### Returns

[`PlayerGame`](modules.md#playergame)

###### Inherited from

[`Scope`](modules.md#scope).[`constructor`](modules.md#constructor)

#### Properties

##### scopes

> `readonly` **scopes**: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

Defined in: [lib/@empirica/core/src/player/scopes.ts:48](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L48)

###### Inherited from

[`Scope`](modules.md#scope).[`scopes`](modules.md#scopes)

#### Accessors

##### id

> get **id()**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L209)

###### Inherited from

[`Scope`](modules.md#scope).[`id`](modules.md#id)

#### Methods

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:269](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L269)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`append`](modules.md#append)

##### get()

> **get**(key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L221)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

[`Scope`](modules.md#scope).[`get`](modules.md#get)

##### getAttribute()

> **getAttribute**(key: `string`): `undefined` \| [`Attribute`](modules.md#attribute)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L225)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`Attribute`](modules.md#attribute)

###### Inherited from

[`Scope`](modules.md#scope).[`getAttribute`](modules.md#getattribute)

##### inspect()

> **inspect**(): `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:278](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L278)

###### Returns

`object`

###### Inherited from

[`Scope`](modules.md#scope).[`inspect`](modules.md#inspect)

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L229)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

###### Inherited from

[`Scope`](modules.md#scope).[`obs`](modules.md#obs)

##### scopeByKey()

> **scopeByKey**(key: `string`): `undefined` \| [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

Defined in: [lib/@empirica/core/src/player/scopes.ts:55](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L55)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

###### Inherited from

[`Scope`](modules.md#scope).[`scopeByKey`](modules.md#scopebykey)

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L233)

###### Parameters

| Parameter | Type                                            |
| :-------- | :---------------------------------------------- |
| values    | [`AttributeInput`](modules.md#attributeinput)[] |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`set`](modules.md#set)

> **set**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L234)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`set`](modules.md#set)

---

### PlayerRound

#### Hierarchy

- [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>.**`PlayerRound`**

#### Constructors

##### constructor()

> **new PlayerRound**(
> ctx: [`Context`](modules.md#context),
> scope: [`ScopeIdent`](modules.md#scopeident),
> scopes: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>,
> attributes: [`Attributes`](modules.md#attributes),
> steps: [`Steps`](modules.md#steps)): [`PlayerRound`](modules.md#playerround)

Defined in: [lib/@empirica/core/src/player/scopes.ts:45](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L45)

###### Parameters

| Parameter  | Type                                                                                                                        |
| :--------- | :-------------------------------------------------------------------------------------------------------------------------- |
| ctx        | [`Context`](modules.md#context)                                                                                             |
| scope      | [`ScopeIdent`](modules.md#scopeident)                                                                                       |
| scopes     | [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\> |
| attributes | [`Attributes`](modules.md#attributes)                                                                                       |
| steps      | [`Steps`](modules.md#steps)                                                                                                 |

###### Returns

[`PlayerRound`](modules.md#playerround)

###### Inherited from

[`Scope`](modules.md#scope).[`constructor`](modules.md#constructor)

#### Properties

##### scopes

> `readonly` **scopes**: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

Defined in: [lib/@empirica/core/src/player/scopes.ts:48](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L48)

###### Inherited from

[`Scope`](modules.md#scope).[`scopes`](modules.md#scopes)

#### Accessors

##### id

> get **id()**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L209)

###### Inherited from

[`Scope`](modules.md#scope).[`id`](modules.md#id)

#### Methods

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:269](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L269)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`append`](modules.md#append)

##### get()

> **get**(key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L221)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

[`Scope`](modules.md#scope).[`get`](modules.md#get)

##### getAttribute()

> **getAttribute**(key: `string`): `undefined` \| [`Attribute`](modules.md#attribute)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L225)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`Attribute`](modules.md#attribute)

###### Inherited from

[`Scope`](modules.md#scope).[`getAttribute`](modules.md#getattribute)

##### inspect()

> **inspect**(): `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:278](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L278)

###### Returns

`object`

###### Inherited from

[`Scope`](modules.md#scope).[`inspect`](modules.md#inspect)

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L229)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

###### Inherited from

[`Scope`](modules.md#scope).[`obs`](modules.md#obs)

##### scopeByKey()

> **scopeByKey**(key: `string`): `undefined` \| [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

Defined in: [lib/@empirica/core/src/player/scopes.ts:55](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L55)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

###### Inherited from

[`Scope`](modules.md#scope).[`scopeByKey`](modules.md#scopebykey)

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L233)

###### Parameters

| Parameter | Type                                            |
| :-------- | :---------------------------------------------- |
| values    | [`AttributeInput`](modules.md#attributeinput)[] |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`set`](modules.md#set)

> **set**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L234)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`set`](modules.md#set)

---

### PlayerStage

#### Hierarchy

- [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>.**`PlayerStage`**

#### Constructors

##### constructor()

> **new PlayerStage**(
> ctx: [`Context`](modules.md#context),
> scope: [`ScopeIdent`](modules.md#scopeident),
> scopes: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>,
> attributes: [`Attributes`](modules.md#attributes),
> steps: [`Steps`](modules.md#steps)): [`PlayerStage`](modules.md#playerstage)

Defined in: [lib/@empirica/core/src/player/scopes.ts:45](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L45)

###### Parameters

| Parameter  | Type                                                                                                                        |
| :--------- | :-------------------------------------------------------------------------------------------------------------------------- |
| ctx        | [`Context`](modules.md#context)                                                                                             |
| scope      | [`ScopeIdent`](modules.md#scopeident)                                                                                       |
| scopes     | [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\> |
| attributes | [`Attributes`](modules.md#attributes)                                                                                       |
| steps      | [`Steps`](modules.md#steps)                                                                                                 |

###### Returns

[`PlayerStage`](modules.md#playerstage)

###### Inherited from

[`Scope`](modules.md#scope).[`constructor`](modules.md#constructor)

#### Properties

##### scopes

> `readonly` **scopes**: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

Defined in: [lib/@empirica/core/src/player/scopes.ts:48](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L48)

###### Inherited from

[`Scope`](modules.md#scope).[`scopes`](modules.md#scopes)

#### Accessors

##### id

> get **id()**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L209)

###### Inherited from

[`Scope`](modules.md#scope).[`id`](modules.md#id)

#### Methods

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:269](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L269)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`append`](modules.md#append)

##### get()

> **get**(key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L221)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

[`Scope`](modules.md#scope).[`get`](modules.md#get)

##### getAttribute()

> **getAttribute**(key: `string`): `undefined` \| [`Attribute`](modules.md#attribute)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L225)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`Attribute`](modules.md#attribute)

###### Inherited from

[`Scope`](modules.md#scope).[`getAttribute`](modules.md#getattribute)

##### inspect()

> **inspect**(): `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:278](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L278)

###### Returns

`object`

###### Inherited from

[`Scope`](modules.md#scope).[`inspect`](modules.md#inspect)

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L229)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

###### Inherited from

[`Scope`](modules.md#scope).[`obs`](modules.md#obs)

##### scopeByKey()

> **scopeByKey**(key: `string`): `undefined` \| [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

Defined in: [lib/@empirica/core/src/player/scopes.ts:55](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L55)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

###### Inherited from

[`Scope`](modules.md#scope).[`scopeByKey`](modules.md#scopebykey)

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L233)

###### Parameters

| Parameter | Type                                            |
| :-------- | :---------------------------------------------- |
| values    | [`AttributeInput`](modules.md#attributeinput)[] |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`set`](modules.md#set)

> **set**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L234)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`set`](modules.md#set)

---

### Round

#### Hierarchy

- [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>.**`Round`**

#### Constructors

##### constructor()

> **new Round**(
> ctx: [`Context`](modules.md#context),
> scope: [`ScopeIdent`](modules.md#scopeident),
> scopes: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>,
> attributes: [`Attributes`](modules.md#attributes),
> steps: [`Steps`](modules.md#steps)): [`Round`](modules.md#round)

Defined in: [lib/@empirica/core/src/player/scopes.ts:45](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L45)

###### Parameters

| Parameter  | Type                                                                                                                        |
| :--------- | :-------------------------------------------------------------------------------------------------------------------------- |
| ctx        | [`Context`](modules.md#context)                                                                                             |
| scope      | [`ScopeIdent`](modules.md#scopeident)                                                                                       |
| scopes     | [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\> |
| attributes | [`Attributes`](modules.md#attributes)                                                                                       |
| steps      | [`Steps`](modules.md#steps)                                                                                                 |

###### Returns

[`Round`](modules.md#round)

###### Inherited from

[`Scope`](modules.md#scope).[`constructor`](modules.md#constructor)

#### Properties

##### scopes

> `readonly` **scopes**: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

Defined in: [lib/@empirica/core/src/player/scopes.ts:48](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L48)

###### Inherited from

[`Scope`](modules.md#scope).[`scopes`](modules.md#scopes)

#### Accessors

##### id

> get **id()**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L209)

###### Inherited from

[`Scope`](modules.md#scope).[`id`](modules.md#id)

#### Methods

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:269](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L269)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`append`](modules.md#append)

##### get()

> **get**(key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L221)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

[`Scope`](modules.md#scope).[`get`](modules.md#get)

##### getAttribute()

> **getAttribute**(key: `string`): `undefined` \| [`Attribute`](modules.md#attribute)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L225)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`Attribute`](modules.md#attribute)

###### Inherited from

[`Scope`](modules.md#scope).[`getAttribute`](modules.md#getattribute)

##### inspect()

> **inspect**(): `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:278](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L278)

###### Returns

`object`

###### Inherited from

[`Scope`](modules.md#scope).[`inspect`](modules.md#inspect)

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L229)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

###### Inherited from

[`Scope`](modules.md#scope).[`obs`](modules.md#obs)

##### scopeByKey()

> **scopeByKey**(key: `string`): `undefined` \| [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

Defined in: [lib/@empirica/core/src/player/scopes.ts:55](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L55)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

###### Inherited from

[`Scope`](modules.md#scope).[`scopeByKey`](modules.md#scopebykey)

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L233)

###### Parameters

| Parameter | Type                                            |
| :-------- | :---------------------------------------------- |
| values    | [`AttributeInput`](modules.md#attributeinput)[] |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`set`](modules.md#set)

> **set**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L234)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`set`](modules.md#set)

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

Defined in: [lib/@empirica/core/src/player/scopes.ts:45](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L45)

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

Defined in: [lib/@empirica/core/src/player/scopes.ts:48](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L48)

#### Accessors

##### id

> get **id()**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L209)

###### Inherited from

[`SharedScope`](modules.md#sharedscope).[`id`](modules.md#id)

#### Methods

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:269](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L269)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L221)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L225)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:278](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L278)

###### Returns

`object`

###### Inherited from

[`SharedScope`](modules.md#sharedscope).[`inspect`](modules.md#inspect)

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L229)

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

Defined in: [lib/@empirica/core/src/player/scopes.ts:55](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L55)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`Scope`](modules.md#scope)\<`Context`, `Kinds`\>

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L233)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L234)

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

Defined in: [lib/@empirica/core/src/player/scopes.ts:16](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L16)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:72](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L72)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:82](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L82)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:64](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L64)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:68](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L68)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:194](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L194)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L209)

#### Methods

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:269](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L269)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L221)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

##### getAttribute()

> **getAttribute**(key: `string`): `undefined` \| [`Attribute`](modules.md#attribute)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L225)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`Attribute`](modules.md#attribute)

##### inspect()

> **inspect**(): `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:278](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L278)

###### Returns

`object`

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L229)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L233)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L234)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

---

### Stage

#### Hierarchy

- [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>.**`Stage`**

#### Constructors

##### constructor()

> **new Stage**(
> ctx: [`Context`](modules.md#context),
> scope: [`ScopeIdent`](modules.md#scopeident),
> scopes: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>,
> attributes: [`Attributes`](modules.md#attributes),
> steps: [`Steps`](modules.md#steps)): [`Stage`](modules.md#stage)

Defined in: [lib/@empirica/core/src/player/scopes.ts:45](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L45)

###### Parameters

| Parameter  | Type                                                                                                                        |
| :--------- | :-------------------------------------------------------------------------------------------------------------------------- |
| ctx        | [`Context`](modules.md#context)                                                                                             |
| scope      | [`ScopeIdent`](modules.md#scopeident)                                                                                       |
| scopes     | [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\> |
| attributes | [`Attributes`](modules.md#attributes)                                                                                       |
| steps      | [`Steps`](modules.md#steps)                                                                                                 |

###### Returns

[`Stage`](modules.md#stage)

###### Inherited from

[`Scope`](modules.md#scope).[`constructor`](modules.md#constructor)

#### Properties

##### scopes

> `readonly` **scopes**: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

Defined in: [lib/@empirica/core/src/player/scopes.ts:48](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L48)

###### Inherited from

[`Scope`](modules.md#scope).[`scopes`](modules.md#scopes)

#### Accessors

##### id

> get **id()**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L209)

###### Inherited from

[`Scope`](modules.md#scope).[`id`](modules.md#id)

##### round

> get **round()**: `undefined` \| [`Round`](modules.md#round)

Defined in: [lib/@empirica/core/src/player/classic/classic.ts:84](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/classic.ts#L84)

##### timer

> get **timer()**: `undefined` \| [`Step`](modules.md#step)

Defined in: [lib/@empirica/core/src/player/classic/classic.ts:88](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/classic.ts#L88)

#### Methods

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:269](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L269)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`append`](modules.md#append)

##### get()

> **get**(key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L221)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

[`Scope`](modules.md#scope).[`get`](modules.md#get)

##### getAttribute()

> **getAttribute**(key: `string`): `undefined` \| [`Attribute`](modules.md#attribute)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L225)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`Attribute`](modules.md#attribute)

###### Inherited from

[`Scope`](modules.md#scope).[`getAttribute`](modules.md#getattribute)

##### inspect()

> **inspect**(): `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:278](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L278)

###### Returns

`object`

###### Inherited from

[`Scope`](modules.md#scope).[`inspect`](modules.md#inspect)

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L229)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

###### Inherited from

[`Scope`](modules.md#scope).[`obs`](modules.md#obs)

##### scopeByKey()

> **scopeByKey**(key: `string`): `undefined` \| [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

Defined in: [lib/@empirica/core/src/player/scopes.ts:55](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/scopes.ts#L55)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`EmpiricaClassicKinds`](modules.md#empiricaclassickinds)\>

###### Inherited from

[`Scope`](modules.md#scope).[`scopeByKey`](modules.md#scopebykey)

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L233)

###### Parameters

| Parameter | Type                                            |
| :-------- | :---------------------------------------------- |
| values    | [`AttributeInput`](modules.md#attributeinput)[] |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`set`](modules.md#set)

> **set**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L234)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

[`Scope`](modules.md#scope).[`set`](modules.md#set)

---

### Step

#### Constructors

##### constructor()

> **new Step**(step: [`StepChange`](modules.md#stepchange), ticker: `Observable`\<`number`\>): [`Step`](modules.md#step)

Defined in: [lib/@empirica/core/src/player/steps.ts:89](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/steps.ts#L89)

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

Defined in: [lib/@empirica/core/src/player/steps.ts:117](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/steps.ts#L117)

#### Methods

##### \_stop()

> **\_stop**(): `void`

Defined in: [lib/@empirica/core/src/player/steps.ts:151](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/steps.ts#L151)

###### Returns

`void`

##### \_update()

> **\_update**(step: [`StepChange`](modules.md#stepchange)): `void`

Defined in: [lib/@empirica/core/src/player/steps.ts:122](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/steps.ts#L122)

###### Parameters

| Parameter | Type                                  |
| :-------- | :------------------------------------ |
| step      | [`StepChange`](modules.md#stepchange) |

###### Returns

`void`

##### obs()

> **obs**(): `Observable`\<`undefined` \| [`StepTick`](modules.md#steptick)\>

Defined in: [lib/@empirica/core/src/player/steps.ts:113](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/steps.ts#L113)

###### Returns

`Observable`\<`undefined` \| [`StepTick`](modules.md#steptick)\>

---

### Steps

#### Constructors

##### constructor()

> **new Steps**(stepsObs: `Observable`\<[`StepUpdate`](modules.md#stepupdate)\>, donesObs: `Observable`\<`void`\>): [`Steps`](modules.md#steps)

Defined in: [lib/@empirica/core/src/player/steps.ts:164](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/steps.ts#L164)

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

Defined in: [lib/@empirica/core/src/player/steps.ts:188](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/steps.ts#L188)

###### Returns

`boolean`

##### step()

> **step**(stepID: `string`): `undefined` \| [`Step`](modules.md#step)

Defined in: [lib/@empirica/core/src/player/steps.ts:184](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/steps.ts#L184)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| stepID    | `string` |

###### Returns

`undefined` \| [`Step`](modules.md#step)

---

## Interfaces

### AttributeChange

#### Properties

##### createdAt

> `optional` **createdAt**: `string`

createdAt is the time the Attribute was created. int64 Date + Time
value given in Epoch with ns precision

Defined in: [lib/@empirica/core/src/shared/attributes.ts:14](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L14)

##### deleted

> `optional` **deleted**: `boolean`

deleted is true with the attribute was deleted.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:8](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L8)

##### deletedAt

> `optional` **deletedAt**: `number`

deletedAt is the time when the Attribute was deleted. int64 Date + Time
value given in Epoch with ns precision

Defined in: [lib/@empirica/core/src/shared/attributes.ts:11](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L11)

##### id

> **id**: `string`

id is the identifier for the Attribute.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:16](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L16)

##### index

> `optional` **index**: `null` \| `number`

index is the index of the attribute if the value is a vector.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:18](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L18)

##### isNew

> `optional` **isNew**: `boolean`

isNew is true if the Attribute was just created.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:20](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L20)

##### key

> **key**: `string`

key is the attribute key being updated.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:22](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L22)

##### node

> `optional` **node**: `object`

node is the Attribute's Node.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:26](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L26)

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

Defined in: [lib/@empirica/core/src/shared/attributes.ts:24](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L24)

##### val

> `optional` **val**: `null` \| `string`

value is the value of the updated attribute.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:33](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L33)

##### vector

> **vector**: `boolean`

vector indicates whether the value is a vector.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:35](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L35)

##### version

> **version**: `number`

version is the version number of this Attribute, starting at 1.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:37](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L37)

---

### AttributeOptions

#### Properties

##### append

> **append**: `null` \| `boolean`

Append, only used if the Attribute is a vector, indicates to append the
attribute to the vector.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:236](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L236)

##### ephemeral

> **ephemeral**: `boolean`

ephemeral indicates the Attribute should not be persisted. Ephemeral
Attributes are not stored in the database and are only synced to the
connected clients. An ephemeral Attribute cannot become non-ephemeral and
vice versa.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:226](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L226)

##### immutable

> **immutable**: `boolean`

Immutable creates an Attribute that cannot be updated.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:221](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L221)

##### index

> **index**: `null` \| `number`

Index, only used if the Attribute is a vector, indicates which index to
update the value at.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:231](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L231)

##### private

> **private**: `boolean`

Private indicates the attribute will not be visible to other Participants.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:214](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L214)

##### protected

> **protected**: `boolean`

Protected indicates the attribute will not be updatable by other
Participants.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:219](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L219)

---

### AttributeUpdate

#### Properties

##### attribute

> **attribute**: [`AttributeChange`](modules.md#attributechange)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:41](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L41)

##### removed

> **removed**: `boolean`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:42](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/attributes.ts#L42)

---

### ConsentProps

#### Properties

##### buttonText

> `optional` **buttonText**: `string`

Defined in: [lib/@empirica/core/src/player/react/Consent.tsx:6](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/react/Consent.tsx#L6)

##### onConsent

> **onConsent**: `Function`

Defined in: [lib/@empirica/core/src/player/react/Consent.tsx:7](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/react/Consent.tsx#L7)

###### Type declaration

> > (): `void`
>
> ####### Returns
>
> `void`

##### text

> `optional` **text**: `string`

Defined in: [lib/@empirica/core/src/player/react/Consent.tsx:5](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/react/Consent.tsx#L5)

##### title

> `optional` **title**: `string`

Defined in: [lib/@empirica/core/src/player/react/Consent.tsx:4](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/react/Consent.tsx#L4)

---

### EmpiricaContextProps

#### Properties

##### children

> **children**: `ReactNode`

Defined in: [lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx:19](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx#L19)

##### connecting

> `optional` **connecting**: `ElementType`\<`any`\>

Defined in: [lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx:28](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx#L28)

##### consent

> `optional` **consent**: `ElementType`\<[`ConsentProps`](modules.md#consentprops)\>

Defined in: [lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx:21](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx#L21)

##### disableConsent

> `optional` **disableConsent**: `boolean`

Defined in: [lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx:47](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx#L47)

##### disableNoGames

> `optional` **disableNoGames**: `boolean`

Defined in: [lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx:51](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx#L51)

##### disableURLParamsCapture

> `optional` **disableURLParamsCapture**: `boolean`

Defined in: [lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx:55](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx#L55)

##### exitSteps

> `optional` **exitSteps**: `ElementType`\<`any`\>[] \| [`StepsFunc`](modules.md#stepsfunc)

Defined in: [lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx:25](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx#L25)

##### finished

> `optional` **finished**: `ElementType`\<`any`\>

Defined in: [lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx:26](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx#L26)

##### introSteps

> `optional` **introSteps**: `ElementType`\<`any`\>[] \| [`StepsFunc`](modules.md#stepsfunc)

Defined in: [lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx:24](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx#L24)

##### loading

> `optional` **loading**: `ElementType`\<`any`\>

Defined in: [lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx:27](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx#L27)

##### lobby

> `optional` **lobby**: `ElementType`\<`any`\>

Defined in: [lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx:23](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx#L23)

##### noGames

> `optional` **noGames**: `ElementType`\<`any`\>

Defined in: [lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx:20](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx#L20)

##### playerCreate

> `optional` **playerCreate**: `ElementType`\<[`PlayerCreateProps`](modules.md#playercreateprops)\>

Defined in: [lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx:22](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx#L22)

##### unmanagedAssignment

> `optional` **unmanagedAssignment**: `boolean`

Defined in: [lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx:43](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx#L43)

##### unmanagedGame

> `optional` **unmanagedGame**: `boolean`

Defined in: [lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx:38](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx#L38)

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

### PlayerCreateProps

#### Properties

##### connecting

> **connecting**: `boolean`

Defined in: [lib/@empirica/core/src/player/react/PlayerCreate.tsx:5](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/react/PlayerCreate.tsx#L5)

##### onPlayerID

> **onPlayerID**: `Function`

Defined in: [lib/@empirica/core/src/player/react/PlayerCreate.tsx:4](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/react/PlayerCreate.tsx#L4)

###### Type declaration

> > (playerID: `string`): `void`
>
> ####### Parameters
>
> | Parameter | Type     |
> | :-------- | :------- |
> | playerID  | `string` |
>
> ####### Returns
>
> `void`

---

### ScopeIdent

#### Properties

##### id

> **id**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:19](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L19)

##### kind

> **kind**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:20](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L20)

---

### ScopeUpdate

#### Properties

##### removed

> **removed**: `boolean`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:25](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L25)

##### scope

> **scope**: [`ScopeIdent`](modules.md#scopeident)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:24](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L24)

---

### SliderProps

#### Properties

##### disabled

> `optional` **disabled**: `boolean`

Defined in: [lib/@empirica/core/src/player/classic/react/Slider.tsx:9](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/Slider.tsx#L9)

##### max

> `optional` **max**: `number`

Defined in: [lib/@empirica/core/src/player/classic/react/Slider.tsx:7](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/Slider.tsx#L7)

##### min

> `optional` **min**: `number`

Defined in: [lib/@empirica/core/src/player/classic/react/Slider.tsx:6](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/Slider.tsx#L6)

##### onChange

> **onChange**: `ChangeEventHandler`\<`HTMLInputElement`\>

Defined in: [lib/@empirica/core/src/player/classic/react/Slider.tsx:5](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/Slider.tsx#L5)

##### stepSize

> `optional` **stepSize**: `number`

Defined in: [lib/@empirica/core/src/player/classic/react/Slider.tsx:8](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/Slider.tsx#L8)

##### value

> **value**: `number`

Defined in: [lib/@empirica/core/src/player/classic/react/Slider.tsx:4](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/Slider.tsx#L4)

---

### StepChange

#### Properties

##### elapsed

> `optional` **elapsed**: `number`

Defined in: [lib/@empirica/core/src/player/steps.ts:6](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/steps.ts#L6)

##### id

> **id**: `string`

Defined in: [lib/@empirica/core/src/player/steps.ts:4](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/steps.ts#L4)

##### remaining

> `optional` **remaining**: `number`

Defined in: [lib/@empirica/core/src/player/steps.ts:7](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/steps.ts#L7)

##### running

> **running**: `boolean`

Defined in: [lib/@empirica/core/src/player/steps.ts:5](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/steps.ts#L5)

---

### StepTick

#### Properties

##### duration

> **duration**: `number`

Defined in: [lib/@empirica/core/src/player/steps.ts:20](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/steps.ts#L20)

##### elapsed

> **elapsed**: `number`

Defined in: [lib/@empirica/core/src/player/steps.ts:18](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/steps.ts#L18)

##### ended

> **ended**: `boolean`

Defined in: [lib/@empirica/core/src/player/steps.ts:17](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/steps.ts#L17)

##### remaining

> **remaining**: `number`

Defined in: [lib/@empirica/core/src/player/steps.ts:19](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/steps.ts#L19)

##### started

> **started**: `boolean`

Defined in: [lib/@empirica/core/src/player/steps.ts:16](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/steps.ts#L16)

---

### StepUpdate

#### Properties

##### removed

> **removed**: `boolean`

Defined in: [lib/@empirica/core/src/player/steps.ts:12](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/steps.ts#L12)

##### step

> **step**: [`StepChange`](modules.md#stepchange)

Defined in: [lib/@empirica/core/src/player/steps.ts:11](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/steps.ts#L11)

---

## Type Aliases

### Attributable

> **Attributable**: `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:7](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L7)

#### Type declaration

> **append**: `Function`
>
> ##### Type declaration - append
>
> > > (
> > > key: `string`,
> > > value: [`JsonValue`](modules.md#jsonvalue),
> > > ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`
> >
> > ###### Parameters
> >
> > | Parameter | Type                                                           |
> > | :-------- | :------------------------------------------------------------- |
> > | key       | `string`                                                       |
> > | value     | [`JsonValue`](modules.md#jsonvalue)                            |
> > | ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |
> >
> > ###### Returns
> >
> > `void`
>
> **get**: `Function`
>
> ##### Type declaration - get
>
> > > (key: `string`): [`JsonValue`](modules.md#jsonvalue) \| `undefined`
> >
> > ###### Parameters
> >
> > | Parameter | Type     |
> > | :-------- | :------- |
> > | key       | `string` |
> >
> > ###### Returns
> >
> > [`JsonValue`](modules.md#jsonvalue) \| `undefined`
>
> **getAttribute**: `Function`
>
> ##### Type declaration - getAttribute
>
> > > (key: `string`): [`Attribute`](modules.md#attribute) \| `undefined`
> >
> > ###### Parameters
> >
> > | Parameter | Type     |
> > | :-------- | :------- |
> > | key       | `string` |
> >
> > ###### Returns
> >
> > [`Attribute`](modules.md#attribute) \| `undefined`
>
> **set**: `Function`
>
> ##### Type declaration - set
>
> > > (
> > > key: `string`,
> > > value: [`JsonValue`](modules.md#jsonvalue),
> > > ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`
> >
> > ###### Parameters
> >
> > | Parameter | Type                                                           |
> > | :-------- | :------------------------------------------------------------- |
> > | key       | `string`                                                       |
> > | value     | [`JsonValue`](modules.md#jsonvalue)                            |
> > | ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |
> >
> > ###### Returns
> >
> > `void`

---

### AttributeInput

> **AttributeInput**: `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:174](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L174)

#### Type declaration

> `optional` **ao**: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>
>
> **key**: `string`
>
> **value**: [`JsonValue`](modules.md#jsonvalue)

---

### ChatProps

> **ChatProps**: [`WithChildren`](modules.md#withchildren)\<\{attribute: `string`;
> loading: `React.ElementType`;
> scope: [`Attributable`](modules.md#attributable);}\>

Defined in: [lib/@empirica/core/src/player/classic/react/chat/Chat.tsx:15](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/chat/Chat.tsx#L15)

---

### Constructor

> **Constructor**: \<`T`\> `Function`

Defined in: [lib/@empirica/core/src/shared/helpers.ts:1](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/helpers.ts#L1)

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

### EmpiricaClassicKinds

> **EmpiricaClassicKinds**: `object`

Defined in: [lib/@empirica/core/src/player/classic/classic.ts:99](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/classic.ts#L99)

#### Type declaration

> **game**: [`Constructor`](modules.md#constructor)\<[`Game`](modules.md#game)\>
>
> **player**: [`Constructor`](modules.md#constructor)\<[`Player`](modules.md#player)\>
>
> **playerGame**: [`Constructor`](modules.md#constructor)\<[`PlayerGame`](modules.md#playergame)\>
>
> **playerRound**: [`Constructor`](modules.md#constructor)\<[`PlayerRound`](modules.md#playerround)\>
>
> **playerStage**: [`Constructor`](modules.md#constructor)\<[`PlayerStage`](modules.md#playerstage)\>
>
> **round**: [`Constructor`](modules.md#constructor)\<[`Round`](modules.md#round)\>
>
> **stage**: [`Constructor`](modules.md#constructor)\<[`Stage`](modules.md#stage)\>

---

### JsonValue

> **JsonValue**: `string` \| `number` \| `boolean` \| `Date` \| [`Json`](modules.md#json) \| [`JsonArray`](modules.md#jsonarray) \| `null`

Defined in: [lib/@empirica/core/src/utils/json.ts:1](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/utils/json.ts#L1)

---

### ScopeConstructor

> **ScopeConstructor**: \<`Context`, `Kinds`\> [`Constructor`](modules.md#constructor)\<[`SharedScope`](modules.md#sharedscope)\<`Context`, `Kinds`\>\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:28](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/shared/scopes.ts#L28)

#### Type parameters

| Parameter           |
| :------------------ |
| Context             |
| Kinds _extends_ \{} |

---

### StepsFunc

> **StepsFunc**: `Function`

Defined in: [lib/@empirica/core/src/player/classic/react/Steps.tsx:8](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/Steps.tsx#L8)

#### Type declaration

> > (props: `object`): `React.ElementType`[] \| `undefined`
>
> ##### Parameters
>
> | Parameter | Type     |
> | :-------- | :------- |
> | props     | `object` |
>
> ##### Returns
>
> `React.ElementType`[] \| `undefined`

---

### StepsProps

> **StepsProps**: [`WithChildren`](modules.md#withchildren)\<\{doneKey: `string`;
> object: [`Attributable`](modules.md#attributable);
> progressKey: `string`;
> steps: `React.ElementType`[] \| [`StepsFunc`](modules.md#stepsfunc);}\>

Defined in: [lib/@empirica/core/src/player/classic/react/Steps.tsx:13](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/Steps.tsx#L13)

---

### WithChildren

> **WithChildren**: \<`T`\> `T` & \{children: `React.ReactNode`;}

Defined in: [lib/@empirica/core/src/player/react/helpers.ts:3](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/react/helpers.ts#L3)

#### Type parameters

| Parameter | Default |
| :-------- | :------ |
| T         | \{}     |

---

## Functions

### Chat()

> **Chat**(\_\_namedParameters: [`ChatProps`](modules.md#chatprops)): `Element`

Defined in: [lib/@empirica/core/src/player/classic/react/chat/Chat.tsx:30](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/chat/Chat.tsx#L30)

#### Parameters

| Parameter           | Type                                |
| :------------------ | :---------------------------------- |
| \_\_namedParameters | [`ChatProps`](modules.md#chatprops) |

#### Returns

`Element`

---

### EmpiricaContext()

> **EmpiricaContext**(\_\_namedParameters: [`EmpiricaContextProps`](modules.md#empiricacontextprops)): `Element`

Defined in: [lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx:58](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/EmpiricaContext.tsx#L58)

#### Parameters

| Parameter           | Type                                                      |
| :------------------ | :-------------------------------------------------------- |
| \_\_namedParameters | [`EmpiricaContextProps`](modules.md#empiricacontextprops) |

#### Returns

`Element`

---

### Lobby()

> **Lobby**(): `Element`

Defined in: [lib/@empirica/core/src/player/classic/react/Lobby.tsx:6](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/Lobby.tsx#L6)

#### Returns

`Element`

---

### Quiz()

> **Quiz**(\_\_namedParameters: `object`): `Element`

Defined in: [lib/@empirica/core/src/player/classic/react/Quiz.tsx:3](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/Quiz.tsx#L3)

#### Parameters

| Parameter           | Type     |
| :------------------ | :------- |
| \_\_namedParameters | `object` |

#### Returns

`Element`

---

### Slider()

> **Slider**(\_\_namedParameters: [`SliderProps`](modules.md#sliderprops)): `Element`

Defined in: [lib/@empirica/core/src/player/classic/react/Slider.tsx:12](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/Slider.tsx#L12)

#### Parameters

| Parameter           | Type                                    |
| :------------------ | :-------------------------------------- |
| \_\_namedParameters | [`SliderProps`](modules.md#sliderprops) |

#### Returns

`Element`

---

### Sweeper()

> **Sweeper**(): `null` \| `Element`

Defined in: [lib/@empirica/core/src/player/classic/react/examples/Sweeper.tsx:35](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/examples/Sweeper.tsx#L35)

#### Returns

`null` \| `Element`

---

### useGame()

> **useGame**(): `undefined` \| `null` \| [`Game`](modules.md#game)

Defined in: [lib/@empirica/core/src/player/classic/react/hooks.ts:14](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/hooks.ts#L14)

#### Returns

`undefined` \| `null` \| [`Game`](modules.md#game)

---

### usePartModeCtx()

> **usePartModeCtx**\<M\>(): `undefined` \| `M`

Defined in: [lib/@empirica/core/src/player/classic/react/hooks.ts:67](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/hooks.ts#L67)

#### Type parameters

| Parameter |
| :-------- |
| M         |

#### Returns

`undefined` \| `M`

---

### usePartModeCtxKey()

> **usePartModeCtxKey**\<M, K, R\>(name: `K`): `R` \| `undefined`

Defined in: [lib/@empirica/core/src/player/classic/react/hooks.ts:90](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/hooks.ts#L90)

#### Type parameters

| Parameter                                    |
| :------------------------------------------- |
| M                                            |
| K _extends_ `string` \| `number` \| `symbol` |
| R                                            |

#### Parameters

| Parameter | Type |
| :-------- | :--- |
| name      | `K`  |

#### Returns

`R` \| `undefined`

---

### usePlayer()

> **usePlayer**(): `undefined` \| `null` \| [`Player`](modules.md#player)

Defined in: [lib/@empirica/core/src/player/classic/react/hooks.ts:8](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/hooks.ts#L8)

#### Returns

`undefined` \| `null` \| [`Player`](modules.md#player)

---

### usePlayers()

> **usePlayers**(): `undefined` \| [`Player`](modules.md#player)[]

Defined in: [lib/@empirica/core/src/player/classic/react/hooks.ts:61](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/hooks.ts#L61)

#### Returns

`undefined` \| [`Player`](modules.md#player)[]

---

### useRound()

> **useRound**(): `undefined` \| `null` \| [`Round`](modules.md#round)

Defined in: [lib/@empirica/core/src/player/classic/react/hooks.ts:18](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/hooks.ts#L18)

#### Returns

`undefined` \| `null` \| [`Round`](modules.md#round)

---

### useStage()

> **useStage**(): `undefined` \| `null` \| [`Stage`](modules.md#stage)

Defined in: [lib/@empirica/core/src/player/classic/react/hooks.ts:24](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/hooks.ts#L24)

#### Returns

`undefined` \| `null` \| [`Stage`](modules.md#stage)

---

### useStageTimer()

> **useStageTimer**(): `undefined` \| [`StepTick`](modules.md#steptick)

Defined in: [lib/@empirica/core/src/player/classic/react/hooks.ts:30](https://github.com/empiricaly/empirica/blob/c9e8647/lib/@empirica/core/src/player/classic/react/hooks.ts#L30)

#### Returns

`undefined` \| [`StepTick`](modules.md#steptick)

---
