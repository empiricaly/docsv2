# @empirica/core

## Index

### Enumerations

- [ExportFormat](modules.md#exportformat)
- [TajribaEvent](modules.md#tajribaevent)

### Classes

- [Attributes](modules.md#attributes)
- [Batch](modules.md#batch)
- [ClassicListenersCollector](modules.md#classiclistenerscollector)
- [Context](modules.md#context)
- [EventContext](modules.md#eventcontext)
- [EventProxy](modules.md#eventproxy)
- [Game](modules.md#game)
- [Globals](modules.md#globals)
- [ListenersCollector](modules.md#listenerscollector)
- [ListenersCollectorProxy](modules.md#listenerscollectorproxy)
- [Player](modules.md#player)
- [PlayerGame](modules.md#playergame)
- [PlayerRound](modules.md#playerround)
- [PlayerStage](modules.md#playerstage)
- [Round](modules.md#round)
- [Scope](modules.md#scope)
- [Scopes](modules.md#scopes)
- [SharedAttribute](modules.md#sharedattribute)
- [SharedAttributes](modules.md#sharedattributes)
- [SharedGlobals](modules.md#sharedglobals)
- [SharedScope](modules.md#sharedscope)
- [Stage](modules.md#stage)
- [TajribaAdminAccess](modules.md#tajribaadminaccess)

### Interfaces

- [AddLinkPayload](modules.md#addlinkpayload)
- [AddScopePayload](modules.md#addscopepayload)
- [AddTransitionPayload](modules.md#addtransitionpayload)
- [AttributeChange](modules.md#attributechange)
- [AttributeOptions](modules.md#attributeoptions)
- [AttributeUpdate](modules.md#attributeupdate)
- [Json](modules.md#json)
- [JsonArray](modules.md#jsonarray)
- [ScopeIdent](modules.md#scopeident)
- [ScopeSubscriptionInput](modules.md#scopesubscriptioninput)
- [ScopeUpdate](modules.md#scopeupdate)
- [StartTajribaOptions](modules.md#starttajribaoptions)
- [StepPayload](modules.md#steppayload)
- [TajServer](modules.md#tajserver)

### Type Aliases

- [AttrInput](modules.md#attrinput)
- [Attributable](modules.md#attributable)
- [AttributeInput](modules.md#attributeinput)
- [AttributeMsg](modules.md#attributemsg)
- [ClassicConfig](modules.md#classicconfig)
- [ClassicKinds](modules.md#classickinds)
- [Constructor](modules.md#constructor)
- [EvtCtxCallback](modules.md#evtctxcallback)
- [Finalizer](modules.md#finalizer)
- [JsonValue](modules.md#jsonvalue)
- [KV](modules.md#kv)
- [LobbyConfig](modules.md#lobbyconfig)
- [ScopeConstructor](modules.md#scopeconstructor)

### Variables

- [classicKinds](modules.md#classickinds)

### Functions

- [Classic](modules.md#classic)
- [ClassicLoader](modules.md#classicloader)
- [Lobby](modules.md#lobby)
- [evt](modules.md#evt)
- [runExport](modules.md#runexport)
- [withTajriba](modules.md#withtajriba)

## Enumerations

### ExportFormat

#### Enumeration Members

##### CSV

> **CSV**: "csv"

Defined in: [lib/@empirica/core/src/admin/classic/export/export.ts:9](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/export/export.ts#L9)

##### JSON

> **JSON**: "json"

Defined in: [lib/@empirica/core/src/admin/classic/export/export.ts:10](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/export/export.ts#L10)

---

### TajribaEvent

#### Enumeration Members

##### ParticipantConnect

> **ParticipantConnect**: "PARTICIPANT_CONNECT"

Defined in: [lib/@empirica/core/src/admin/events.ts:21](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L21)

##### ParticipantDisconnect

> **ParticipantDisconnect**: "PARTICIPANT_DISCONNECT"

Defined in: [lib/@empirica/core/src/admin/events.ts:22](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L22)

##### TransitionAdd

> **TransitionAdd**: "TRANSITION_ADD"

Defined in: [lib/@empirica/core/src/admin/events.ts:20](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L20)

---

## Classes

### Attributes

#### Hierarchy

- [`SharedAttributes`](modules.md#sharedattributes).**`Attributes`**

#### Constructors

##### constructor()

> **new Attributes**(
> attributesObs: `Observable`\<[`AttributeUpdate`](modules.md#attributeupdate)\>,
> donesObs: `Observable`\<`string`[]\>,
> setAttributes: `Function`): [`Attributes`](modules.md#attributes)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:49](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L49)

###### Parameters

| Parameter     | Type                                                            |
| :------------ | :-------------------------------------------------------------- |
| attributesObs | `Observable`\<[`AttributeUpdate`](modules.md#attributeupdate)\> |
| donesObs      | `Observable`\<`string`[]\>                                      |
| setAttributes | (`input`: `SetAttributeInput`[]) => `Promise`\<`unknown`\>      |

###### Returns

[`Attributes`](modules.md#attributes)

###### Inherited from

[`SharedAttributes`](modules.md#sharedattributes).[`constructor`](modules.md#constructor)

#### Properties

##### setAttributes

> `readonly` **setAttributes**: `Function`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:52](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L52)

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

###### Inherited from

[`SharedAttributes`](modules.md#sharedattributes).[`setAttributes`](modules.md#setattributes)

#### Methods

##### attribute()

> **attribute**(scopeID: `string`, key: `string`): [`SharedAttribute`](modules.md#sharedattribute)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:67](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L67)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| scopeID   | `string` |
| key       | `string` |

###### Returns

[`SharedAttribute`](modules.md#sharedattribute)

###### Inherited from

[`SharedAttributes`](modules.md#sharedattributes).[`attribute`](modules.md#attribute)

##### attributePeek()

> **attributePeek**(scopeID: `string`, key: `string`): `undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:93](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L93)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| scopeID   | `string` |
| key       | `string` |

###### Returns

`undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

###### Inherited from

[`SharedAttributes`](modules.md#sharedattributes).[`attributePeek`](modules.md#attributepeek)

##### attributes()

> **attributes**(scopeID: `string`): [`SharedAttribute`](modules.md#sharedattribute)[]

Defined in: [lib/@empirica/core/src/shared/attributes.ts:83](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L83)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| scopeID   | `string` |

###### Returns

[`SharedAttribute`](modules.md#sharedattribute)[]

###### Inherited from

[`SharedAttributes`](modules.md#sharedattributes).[`attributes`](modules.md#attributes)

##### nextAttributeValue()

> **nextAttributeValue**(scopeID: `string`, key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:129](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L129)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| scopeID   | `string` |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

[`SharedAttributes`](modules.md#sharedattributes).[`nextAttributeValue`](modules.md#nextattributevalue)

##### scopeWasUpdated()

> **scopeWasUpdated**(scopeID?: `string`): `boolean`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:165](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L165)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| scopeID?  | `string` |

###### Returns

`boolean`

###### Inherited from

[`SharedAttributes`](modules.md#sharedattributes).[`scopeWasUpdated`](modules.md#scopewasupdated)

##### subscribeAttribute()

> **subscribeAttribute**(kind: `string`, key: `string`): `Observable`\<[`AttributeMsg`](modules.md#attributemsg)\>

Defined in: [lib/@empirica/core/src/admin/attributes.ts:24](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/attributes.ts#L24)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| kind      | `string` |
| key       | `string` |

###### Returns

`Observable`\<[`AttributeMsg`](modules.md#attributemsg)\>

---

### Batch

#### Hierarchy

- [`Scope`](modules.md#scope)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>.**`Batch`**

#### Constructors

##### constructor()

> **new Batch**(
> ctx: [`Context`](modules.md#context),
> scope: [`ScopeIdent`](modules.md#scopeident),
> scopes: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>,
> attributes: [`Attributes`](modules.md#attributes)): [`Batch`](modules.md#batch)

Defined in: [lib/@empirica/core/src/admin/scopes.ts:109](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/scopes.ts#L109)

###### Parameters

| Parameter  | Type                                                                                                        |
| :--------- | :---------------------------------------------------------------------------------------------------------- |
| ctx        | [`Context`](modules.md#context)                                                                             |
| scope      | [`ScopeIdent`](modules.md#scopeident)                                                                       |
| scopes     | [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\> |
| attributes | [`Attributes`](modules.md#attributes)                                                                       |

###### Returns

[`Batch`](modules.md#batch)

###### Inherited from

[`Scope`](modules.md#scope).[`constructor`](modules.md#constructor)

#### Accessors

##### games

> get **games()**: [`Game`](modules.md#game)[]

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:43](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L43)

##### hasEnded

> get **hasEnded()**: `boolean`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:96](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L96)

##### id

> get **id()**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L209)

###### Inherited from

[`Scope`](modules.md#scope).[`id`](modules.md#id)

##### isRunning

> get **isRunning()**: `boolean`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:39](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L39)

##### lobbyConfig

> get **lobbyConfig()**: `object`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:100](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L100)

#### Methods

##### addGame()

> **addGame**(attributes: [`AttrInput`](modules.md#attrinput)[] \| \{}): `object`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:47](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L47)

###### Parameters

| Parameter  | Type                                         |
| :--------- | :------------------------------------------- |
| attributes | [`AttrInput`](modules.md#attrinput)[] \| \{} |

###### Returns

`object`

`readonly` **set**: `Function`

####### Type declaration - set

> > (
> > key: `string`,
> > value: [`JsonValue`](modules.md#jsonvalue),
> > ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`
>
> ######## Parameters
>
> | Parameter | Type                                                           |
> | :-------- | :------------------------------------------------------------- |
> | key       | `string`                                                       |
> | value     | [`JsonValue`](modules.md#jsonvalue)                            |
> | ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |
>
> ######## Returns
>
> `void`

`readonly` **get**

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:262](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L262)

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

##### end()

> **end**(reason: `string`): `void`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:87](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L87)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| reason    | `string` |

###### Returns

`void`

##### get()

> **get**(key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L221)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

[`Scope`](modules.md#scope).[`get`](modules.md#get)

##### getAttribute()

> **getAttribute**(key: `string`): `undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L225)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

###### Inherited from

[`Scope`](modules.md#scope).[`getAttribute`](modules.md#getattribute)

##### inspect()

> **inspect**(): `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:271](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L271)

###### Returns

`object`

###### Inherited from

[`Scope`](modules.md#scope).[`inspect`](modules.md#inspect)

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L229)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

###### Inherited from

[`Scope`](modules.md#scope).[`obs`](modules.md#obs)

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L233)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L234)

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

### ClassicListenersCollector

Collects event listeners.

#### Hierarchy

- [`ListenersCollector`](modules.md#listenerscollector)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>.**`ClassicListenersCollector`**

#### Constructors

##### constructor()

> **new ClassicListenersCollector**(): [`ClassicListenersCollector`](modules.md#classiclistenerscollector)

###### Returns

[`ClassicListenersCollector`](modules.md#classiclistenerscollector)

###### Inherited from

[`ListenersCollector`](modules.md#listenerscollector).[`constructor`](modules.md#constructor)

#### Accessors

##### unique

> get **unique()**: [`ListenersCollectorProxy`](modules.md#listenerscollectorproxy)\<`Context`, `Kinds`\>

Defined in: [lib/@empirica/core/src/admin/events.ts:140](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L140)

###### Inherited from

[`ListenersCollector`](modules.md#listenerscollector).[`unique`](modules.md#unique)

#### Methods

##### after()

> **after**(
> kindOrEvent: `string`,
> keyOrNodeIDOrEventOrCallback?: `string` \| [`EvtCtxCallback`](modules.md#evtctxcallback)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\> \| (`ctx`: [`EventContext`](modules.md#eventcontext)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>) => `void`,
> callback?: [`EvtCtxCallback`](modules.md#evtctxcallback)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>,
> uniqueCall?: `boolean`): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:204](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L204)

###### Parameters

| Parameter                     | Type                                                                                                                                                                                                                                                                                  |
| :---------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| kindOrEvent                   | `string`                                                                                                                                                                                                                                                                              |
| keyOrNodeIDOrEventOrCallback? | `string` \| [`EvtCtxCallback`](modules.md#evtctxcallback)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\> \| (`ctx`: [`EventContext`](modules.md#eventcontext)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>) => `void` |
| callback?                     | [`EvtCtxCallback`](modules.md#evtctxcallback)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>                                                                                                                                                           |
| uniqueCall?                   | `boolean`                                                                                                                                                                                                                                                                             |

###### Returns

`void`

###### Inherited from

[`ListenersCollector`](modules.md#listenerscollector).[`after`](modules.md#after)

##### before()

> **before**(
> kindOrEvent: `string`,
> keyOrNodeIDOrEventOrCallback?: `string` \| [`EvtCtxCallback`](modules.md#evtctxcallback)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\> \| (`ctx`: [`EventContext`](modules.md#eventcontext)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>) => `void`,
> callback?: [`EvtCtxCallback`](modules.md#evtctxcallback)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>,
> uniqueCall?: `boolean`): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:185](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L185)

###### Parameters

| Parameter                     | Type                                                                                                                                                                                                                                                                                  |
| :---------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| kindOrEvent                   | `string`                                                                                                                                                                                                                                                                              |
| keyOrNodeIDOrEventOrCallback? | `string` \| [`EvtCtxCallback`](modules.md#evtctxcallback)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\> \| (`ctx`: [`EventContext`](modules.md#eventcontext)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>) => `void` |
| callback?                     | [`EvtCtxCallback`](modules.md#evtctxcallback)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>                                                                                                                                                           |
| uniqueCall?                   | `boolean`                                                                                                                                                                                                                                                                             |

###### Returns

`void`

###### Inherited from

[`ListenersCollector`](modules.md#listenerscollector).[`before`](modules.md#before)

##### flush()

> **flush**(): `Promise`\<`void`\>

Defined in: [lib/@empirica/core/src/admin/events.ts:124](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L124)

###### Returns

`Promise`\<`void`\>

###### Inherited from

[`ListenersCollector`](modules.md#listenerscollector).[`flush`](modules.md#flush)

##### flushAfter()

> **flushAfter**(cb: `Function`): `void` \| () => `Promise`\<`void`\>

Defined in: [lib/@empirica/core/src/admin/events.ts:132](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L132)

###### Parameters

| Parameter | Type                      |
| :-------- | :------------------------ |
| cb        | () => `Promise`\<`void`\> |

###### Returns

`void` \| () => `Promise`\<`void`\>

###### Inherited from

[`ListenersCollector`](modules.md#listenerscollector).[`flushAfter`](modules.md#flushafter)

##### on()

> **on**(kind: "start" \| "ready", callback: `Function`): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:146](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L146)

###### Parameters

| Parameter | Type                                                                                                                                       |
| :-------- | :----------------------------------------------------------------------------------------------------------------------------------------- |
| kind      | "start" \| "ready"                                                                                                                         |
| callback  | (`ctx`: [`EventContext`](modules.md#eventcontext)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>) => `void` |

###### Returns

`void`

###### Inherited from

[`ListenersCollector`](modules.md#listenerscollector).[`on`](modules.md#on)

> **on**(event: [`TajribaEvent`](modules.md#tajribaevent), callback: [`EvtCtxCallback`](modules.md#evtctxcallback)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:152](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L152)

###### Parameters

| Parameter | Type                                                                                                                        |
| :-------- | :-------------------------------------------------------------------------------------------------------------------------- |
| event     | [`TajribaEvent`](modules.md#tajribaevent)                                                                                   |
| callback  | [`EvtCtxCallback`](modules.md#evtctxcallback)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\> |

###### Returns

`void`

###### Inherited from

[`ListenersCollector`](modules.md#listenerscollector).[`on`](modules.md#on)

> **on**\<Kind\>(kind: `Kind`, callback: [`EvtCtxCallback`](modules.md#evtctxcallback)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:155](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L155)

###### Type parameters

| Parameter               |
| :---------------------- |
| Kind _extends_ `string` |

###### Parameters

| Parameter | Type                                                                                                                        |
| :-------- | :-------------------------------------------------------------------------------------------------------------------------- |
| kind      | `Kind`                                                                                                                      |
| callback  | [`EvtCtxCallback`](modules.md#evtctxcallback)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\> |

###### Returns

`void`

###### Inherited from

[`ListenersCollector`](modules.md#listenerscollector).[`on`](modules.md#on)

> **on**\<Kind\>(
> kind: `Kind`,
> key: `string`,
> callback: [`EvtCtxCallback`](modules.md#evtctxcallback)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>,
> uniqueCall?: `boolean`): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:161](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L161)

###### Type parameters

| Parameter                                                        |
| :--------------------------------------------------------------- |
| Kind _extends_ _keyof_ [`ClassicKinds`](modules.md#classickinds) |

###### Parameters

| Parameter   | Type                                                                                                                        |
| :---------- | :-------------------------------------------------------------------------------------------------------------------------- |
| kind        | `Kind`                                                                                                                      |
| key         | `string`                                                                                                                    |
| callback    | [`EvtCtxCallback`](modules.md#evtctxcallback)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\> |
| uniqueCall? | `boolean`                                                                                                                   |

###### Returns

`void`

###### Inherited from

[`ListenersCollector`](modules.md#listenerscollector).[`on`](modules.md#on)

##### onGameEnded()

> **onGameEnded**(cb: `Function`): `void`

Defined in: [lib/@empirica/core/src/admin/classic/proxy.ts:101](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/proxy.ts#L101)

###### Parameters

| Parameter | Type                                                     |
| :-------- | :------------------------------------------------------- |
| cb        | (`props`: \{game: [`Game`](modules.md#game);}) => `void` |

###### Returns

`void`

##### onGameStart()

> **onGameStart**(cb: `Function`): `void`

onGameStart is triggered just before the game start. It is a great place to
create rounds and stages and initialize values on the game, the players,
the rounds, and the stages.

Players are accessible on the game, `game.players`.
You can add Rounds to a Game with `game.addRound({ some: "attribute" })`.
`game.AddRound` returns a Round object. On the Round object, you can create
Stages: `round.addStage({ some: "value" })`.

###### Example

```js
const round = game.addRound({
  name: "Round 1 - Jelly Beans",
  task: "jellybeans",
});
round.addStage({ name: "Answer", duration: 300 });
round.addStage({ name: "Result", duration: 120 });

game.players.forEach((player) => player.set("score", 0));
```

Defined in: [lib/@empirica/core/src/admin/classic/proxy.ts:31](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/proxy.ts#L31)

###### Parameters

| Parameter | Type                                                     |
| :-------- | :------------------------------------------------------- |
| cb        | (`props`: \{game: [`Game`](modules.md#game);}) => `void` |

###### Returns

`void`

##### onRoundEnded()

> **onRoundEnded**(cb: `Function`): `void`

Defined in: [lib/@empirica/core/src/admin/classic/proxy.ts:87](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/proxy.ts#L87)

###### Parameters

| Parameter | Type                                                        |
| :-------- | :---------------------------------------------------------- |
| cb        | (`props`: \{round: [`Round`](modules.md#round);}) => `void` |

###### Returns

`void`

##### onRoundStart()

> **onRoundStart**(cb: `Function`): `void`

Defined in: [lib/@empirica/core/src/admin/classic/proxy.ts:45](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/proxy.ts#L45)

###### Parameters

| Parameter | Type                                                        |
| :-------- | :---------------------------------------------------------- |
| cb        | (`props`: \{round: [`Round`](modules.md#round);}) => `void` |

###### Returns

`void`

##### onStageEnded()

> **onStageEnded**(cb: `Function`): `void`

Defined in: [lib/@empirica/core/src/admin/classic/proxy.ts:73](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/proxy.ts#L73)

###### Parameters

| Parameter | Type                                                        |
| :-------- | :---------------------------------------------------------- |
| cb        | (`props`: \{stage: [`Stage`](modules.md#stage);}) => `void` |

###### Returns

`void`

##### onStageStart()

> **onStageStart**(cb: `Function`): `void`

Defined in: [lib/@empirica/core/src/admin/classic/proxy.ts:59](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/proxy.ts#L59)

###### Parameters

| Parameter | Type                                                        |
| :-------- | :---------------------------------------------------------- |
| cb        | (`props`: \{stage: [`Stage`](modules.md#stage);}) => `void` |

###### Returns

`void`

---

### Context

#### Constructors

##### constructor()

> **new Context**(): [`Context`](modules.md#context)

###### Returns

[`Context`](modules.md#context)

---

### EventContext

#### Type parameters

| Parameter           |
| :------------------ |
| Context             |
| Kinds _extends_ \{} |

#### Constructors

##### constructor()

> **new EventContext**\<Context, Kinds\>(): [`EventContext`](modules.md#eventcontext)\<`Context`, `Kinds`\>

Defined in: [lib/@empirica/core/src/admin/events.ts:375](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L375)

###### Type parameters

| Parameter           |
| :------------------ |
| Context             |
| Kinds _extends_ \{} |

###### Returns

[`EventContext`](modules.md#eventcontext)\<`Context`, `Kinds`\>

#### Accessors

##### globals

> get **globals()**: [`Globals`](modules.md#globals)

Defined in: [lib/@empirica/core/src/admin/events.ts:459](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L459)

#### Methods

##### addGroups()

> **addGroups**(input: `AddGroupInput`[]): `Promise`\<\{id: `string`;}[]\>

Defined in: [lib/@empirica/core/src/admin/events.ts:435](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L435)

###### Parameters

| Parameter | Type              |
| :-------- | :---------------- |
| input     | `AddGroupInput`[] |

###### Returns

`Promise`\<\{id: `string`;}[]\>

##### addLinks()

> **addLinks**(input: `LinkInput`[]): `Promise`\<[`AddLinkPayload`](modules.md#addlinkpayload)[]\>

Defined in: [lib/@empirica/core/src/admin/events.ts:440](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L440)

###### Parameters

| Parameter | Type          |
| :-------- | :------------ |
| input     | `LinkInput`[] |

###### Returns

`Promise`\<[`AddLinkPayload`](modules.md#addlinkpayload)[]\>

##### addScopes()

> **addScopes**(input: `AddScopeInput`[]): `Promise`\<[`AddScopePayload`](modules.md#addscopepayload)[]\>

Defined in: [lib/@empirica/core/src/admin/events.ts:430](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L430)

###### Parameters

| Parameter | Type              |
| :-------- | :---------------- |
| input     | `AddScopeInput`[] |

###### Returns

`Promise`\<[`AddScopePayload`](modules.md#addscopepayload)[]\>

##### addSteps()

> **addSteps**(input: `AddStepInput`[]): `Promise`\<[`StepPayload`](modules.md#steppayload)[]\>

Defined in: [lib/@empirica/core/src/admin/events.ts:445](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L445)

###### Parameters

| Parameter | Type             |
| :-------- | :--------------- |
| input     | `AddStepInput`[] |

###### Returns

`Promise`\<[`StepPayload`](modules.md#steppayload)[]\>

##### addTransitions()

> **addTransitions**(input: `TransitionInput`[]): `Promise`\<[`AddTransitionPayload`](modules.md#addtransitionpayload)[]\>

Defined in: [lib/@empirica/core/src/admin/events.ts:450](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L450)

###### Parameters

| Parameter | Type                |
| :-------- | :------------------ |
| input     | `TransitionInput`[] |

###### Returns

`Promise`\<[`AddTransitionPayload`](modules.md#addtransitionpayload)[]\>

##### flush()

> **flush**(): `Promise`\<`void`\>

Defined in: [lib/@empirica/core/src/admin/events.ts:386](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L386)

###### Returns

`Promise`\<`void`\>

##### flushAfter()

> **flushAfter**(cb: `Function`): `void` \| () => `Promise`\<`void`\>

Defined in: [lib/@empirica/core/src/admin/events.ts:390](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L390)

###### Parameters

| Parameter | Type                      |
| :-------- | :------------------------ |
| cb        | () => `Promise`\<`void`\> |

###### Returns

`void` \| () => `Promise`\<`void`\>

##### participantsSub()

> **participantsSub**(): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:420](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L420)

###### Returns

`void`

##### scopeSub()

> **scopeSub**(...inputs: `Partial`\<[`ScopeSubscriptionInput`](modules.md#scopesubscriptioninput)\>[]): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:414](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L414)

###### Parameters

| Parameter | Type                                                                         |
| :-------- | :--------------------------------------------------------------------------- |
| ...inputs | `Partial`\<[`ScopeSubscriptionInput`](modules.md#scopesubscriptioninput)\>[] |

###### Returns

`void`

##### scopesByKind()

> **scopesByKind**\<T\>(kind: _keyof_ `Kinds`): `Map`\<`string`, `T`\>

Defined in: [lib/@empirica/core/src/admin/events.ts:394](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L394)

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

##### scopesByKindID()

> **scopesByKindID**\<T\>(kind: _keyof_ `Kinds`, id: `string`): `undefined` \| `T`

Defined in: [lib/@empirica/core/src/admin/events.ts:398](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L398)

###### Type parameters

| Parameter                                                          |
| :----------------------------------------------------------------- |
| T _extends_ [`Scope`](modules.md#scope)\<`Context`, `Kinds`, `T`\> |

###### Parameters

| Parameter | Type            |
| :-------- | :-------------- |
| kind      | _keyof_ `Kinds` |
| id        | `string`        |

###### Returns

`undefined` \| `T`

##### scopesByKindMatching()

> **scopesByKindMatching**\<T\>(
> kind: _keyof_ `Kinds`,
> key: `string`,
> val: `string`): `T`[]

Defined in: [lib/@empirica/core/src/admin/events.ts:405](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L405)

###### Type parameters

| Parameter                                                          |
| :----------------------------------------------------------------- |
| T _extends_ [`Scope`](modules.md#scope)\<`Context`, `Kinds`, `T`\> |

###### Parameters

| Parameter | Type            |
| :-------- | :-------------- |
| kind      | _keyof_ `Kinds` |
| key       | `string`        |
| val       | `string`        |

###### Returns

`T`[]

##### transitionsSub()

> **transitionsSub**(stepID: `string`): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:424](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L424)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| stepID    | `string` |

###### Returns

`void`

---

### EventProxy

#### Constructors

##### constructor()

> **new EventProxy**(ctx: [`EventContext`](modules.md#eventcontext)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>): [`EventProxy`](modules.md#eventproxy)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:1022](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L1022)

###### Parameters

| Parameter | Type                                                                                                                    |
| :-------- | :---------------------------------------------------------------------------------------------------------------------- |
| ctx       | [`EventContext`](modules.md#eventcontext)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\> |

###### Returns

[`EventProxy`](modules.md#eventproxy)

#### Accessors

##### batches

> get **batches()**: [`Batch`](modules.md#batch)[]

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:1025](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L1025)

##### games

> get **games()**: [`Game`](modules.md#game)[]

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:1030](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L1030)

##### players

> get **players()**: [`Player`](modules.md#player)[]

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:1035](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L1035)

---

### Game

#### Hierarchy

- `BatchOwned`.**`Game`**

#### Constructors

##### constructor()

> **new Game**(
> ctx: [`Context`](modules.md#context),
> scope: [`ScopeIdent`](modules.md#scopeident),
> scopes: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>,
> attributes: [`Attributes`](modules.md#attributes)): [`Game`](modules.md#game)

Defined in: [lib/@empirica/core/src/admin/scopes.ts:109](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/scopes.ts#L109)

###### Parameters

| Parameter  | Type                                                                                                        |
| :--------- | :---------------------------------------------------------------------------------------------------------- |
| ctx        | [`Context`](modules.md#context)                                                                             |
| scope      | [`ScopeIdent`](modules.md#scopeident)                                                                       |
| scopes     | [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\> |
| attributes | [`Attributes`](modules.md#attributes)                                                                       |

###### Returns

[`Game`](modules.md#game)

###### Inherited from

BatchOwned.constructor

#### Accessors

##### batch

> get **batch()**: `undefined` \| [`Batch`](modules.md#batch)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:106](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L106)

###### Inherited from

BatchOwned.batch

##### currentRound

> get **currentRound()**: `undefined` \| [`Round`](modules.md#round)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:140](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L140)

##### currentStage

> get **currentStage()**: `undefined` \| [`Stage`](modules.md#stage)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:136](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L136)

##### hasEnded

> get **hasEnded()**: `boolean`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:144](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L144)

##### hasNotStarted

> get **hasNotStarted()**: `boolean`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:156](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L156)

##### hasStarted

> get **hasStarted()**: `boolean`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:152](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L152)

##### id

> get **id()**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L209)

###### Inherited from

BatchOwned.id

##### isRunning

> get **isRunning()**: `boolean`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:162](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L162)

##### lobbyConfig

> get **lobbyConfig()**: `object`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:166](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L166)

##### players

> get **players()**: [`Player`](modules.md#player)[]

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:132](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L132)

##### rounds

> get **rounds()**: [`Round`](modules.md#round)[]

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:120](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L120)

##### stages

> get **stages()**: [`Stage`](modules.md#stage)[]

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:126](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L126)

#### Methods

##### addRound()

> **addRound**(attributes: [`AttrInput`](modules.md#attrinput)[] \| \{}): `object`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:370](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L370)

###### Parameters

| Parameter  | Type                                         |
| :--------- | :------------------------------------------- |
| attributes | [`AttrInput`](modules.md#attrinput)[] \| \{} |

###### Returns

`object`

**addStage**: `Function`

####### Type declaration - addStage

> > (attributes: [`AttrInput`](modules.md#attrinput)[] \| \{}): `object`
>
> ######## Parameters
>
> | Parameter  | Type                                         |
> | :--------- | :------------------------------------------- |
> | attributes | [`AttrInput`](modules.md#attrinput)[] \| \{} |
>
> ######## Returns
>
> `object`
>
> `readonly` **set**: `Function`
>
> ######### Type declaration - set
>
> > > (
> > > key: `string`,
> > > value: [`JsonValue`](modules.md#jsonvalue),
> > > ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`
> >
> > ########## Parameters
> >
> > | Parameter | Type                                                           |
> > | :-------- | :------------------------------------------------------------- |
> > | key       | `string`                                                       |
> > | value     | [`JsonValue`](modules.md#jsonvalue)                            |
> > | ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |
> >
> > ########## Returns
> >
> > `void`
>
> `readonly` **get**

**set**: `Function`

####### Type declaration - set

> > (
> > key: `string`,
> > value: [`JsonValue`](modules.md#jsonvalue),
> > ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`
>
> ######## Parameters
>
> | Parameter | Type                                                           |
> | :-------- | :------------------------------------------------------------- |
> | key       | `string`                                                       |
> | value     | [`JsonValue`](modules.md#jsonvalue)                            |
> | ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |
>
> ######## Returns
>
> `void`

**get**

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:262](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L262)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

BatchOwned.append

##### assignPlayer()

> **assignPlayer**(player: [`Player`](modules.md#player)): `Promise`\<`void`\>

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:177](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L177)

###### Parameters

| Parameter | Type                          |
| :-------- | :---------------------------- |
| player    | [`Player`](modules.md#player) |

###### Returns

`Promise`\<`void`\>

##### createPlayerGame()

> **createPlayerGame**(player: [`Player`](modules.md#player)): `Promise`\<`undefined` \| `string`\>

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:610](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L610)

###### Parameters

| Parameter | Type                          |
| :-------- | :---------------------------- |
| player    | [`Player`](modules.md#player) |

###### Returns

`Promise`\<`undefined` \| `string`\>

##### end()

> **end**(status: `string`, reason: `string`): `void`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:588](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L588)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| status    | `string` |
| reason    | `string` |

###### Returns

`void`

##### get()

> **get**(key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L221)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

BatchOwned.get

##### getAttribute()

> **getAttribute**(key: `string`): `undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L225)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

###### Inherited from

BatchOwned.getAttribute

##### inspect()

> **inspect**(): `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:271](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L271)

###### Returns

`object`

###### Inherited from

BatchOwned.inspect

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L229)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

###### Inherited from

BatchOwned.obs

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L233)

###### Parameters

| Parameter | Type                                            |
| :-------- | :---------------------------------------------- |
| values    | [`AttributeInput`](modules.md#attributeinput)[] |

###### Returns

`void`

###### Inherited from

BatchOwned.set

> **set**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L234)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

BatchOwned.set

##### start()

> **start**(): `void`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:171](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L171)

###### Returns

`void`

---

### Globals

#### Hierarchy

- [`SharedGlobals`](modules.md#sharedglobals).**`Globals`**

#### Constructors

##### constructor()

> **new Globals**(
> globals: `Observable`\<`SubAttributesPayload`\>,
> globalScopeID: `string`,
> setAttributes: `Function`): [`Globals`](modules.md#globals)

Defined in: [lib/@empirica/core/src/admin/globals.ts:9](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/globals.ts#L9)

###### Parameters

| Parameter     | Type                                                       |
| :------------ | :--------------------------------------------------------- |
| globals       | `Observable`\<`SubAttributesPayload`\>                     |
| globalScopeID | `string`                                                   |
| setAttributes | (`input`: `SetAttributeInput`[]) => `Promise`\<`unknown`\> |

###### Returns

[`Globals`](modules.md#globals)

###### Overrides

[`SharedGlobals`](modules.md#sharedglobals).[`constructor`](modules.md#constructor)

#### Properties

##### self

> **self**: `BehaviorSubject`\<`undefined` \| [`SharedGlobals`](modules.md#sharedglobals)\>

Defined in: [lib/@empirica/core/src/shared/globals.ts:8](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/globals.ts#L8)

###### Inherited from

[`SharedGlobals`](modules.md#sharedglobals).[`self`](modules.md#self)

#### Methods

##### get()

> **get**(key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/globals.ts:39](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/globals.ts#L39)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

[`SharedGlobals`](modules.md#sharedglobals).[`get`](modules.md#get)

##### obs()

> **obs**(key: `string`): `BehaviorSubject`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/globals.ts:48](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/globals.ts#L48)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`BehaviorSubject`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

###### Inherited from

[`SharedGlobals`](modules.md#sharedglobals).[`obs`](modules.md#obs)

##### set()

> **set**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/admin/globals.ts:17](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/globals.ts#L17)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

---

### ListenersCollector

#### Type parameters

| Parameter           |
| :------------------ |
| Context             |
| Kinds _extends_ \{} |

#### Hierarchy

- [`ListenersCollectorProxy`](modules.md#listenerscollectorproxy)
- [`ClassicListenersCollector`](modules.md#classiclistenerscollector)

#### Constructors

##### constructor()

> **new ListenersCollector**\<Context, Kinds\>(): [`ListenersCollector`](modules.md#listenerscollector)\<`Context`, `Kinds`\>

###### Type parameters

| Parameter           |
| :------------------ |
| Context             |
| Kinds _extends_ \{} |

###### Returns

[`ListenersCollector`](modules.md#listenerscollector)\<`Context`, `Kinds`\>

#### Accessors

##### unique

> get **unique()**: [`ListenersCollectorProxy`](modules.md#listenerscollectorproxy)\<`Context`, `Kinds`\>

Defined in: [lib/@empirica/core/src/admin/events.ts:140](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L140)

#### Methods

##### after()

> **after**(
> kindOrEvent: `string`,
> keyOrNodeIDOrEventOrCallback?: `string` \| [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\> \| (`ctx`: [`EventContext`](modules.md#eventcontext)\<`Context`, `Kinds`\>) => `void`,
> callback?: [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\>,
> uniqueCall?: `boolean`): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:204](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L204)

###### Parameters

| Parameter                     | Type                                                                                                                                                                  |
| :---------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| kindOrEvent                   | `string`                                                                                                                                                              |
| keyOrNodeIDOrEventOrCallback? | `string` \| [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\> \| (`ctx`: [`EventContext`](modules.md#eventcontext)\<`Context`, `Kinds`\>) => `void` |
| callback?                     | [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\>                                                                                                   |
| uniqueCall?                   | `boolean`                                                                                                                                                             |

###### Returns

`void`

##### before()

> **before**(
> kindOrEvent: `string`,
> keyOrNodeIDOrEventOrCallback?: `string` \| [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\> \| (`ctx`: [`EventContext`](modules.md#eventcontext)\<`Context`, `Kinds`\>) => `void`,
> callback?: [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\>,
> uniqueCall?: `boolean`): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:185](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L185)

###### Parameters

| Parameter                     | Type                                                                                                                                                                  |
| :---------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| kindOrEvent                   | `string`                                                                                                                                                              |
| keyOrNodeIDOrEventOrCallback? | `string` \| [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\> \| (`ctx`: [`EventContext`](modules.md#eventcontext)\<`Context`, `Kinds`\>) => `void` |
| callback?                     | [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\>                                                                                                   |
| uniqueCall?                   | `boolean`                                                                                                                                                             |

###### Returns

`void`

##### flush()

> **flush**(): `Promise`\<`void`\>

Defined in: [lib/@empirica/core/src/admin/events.ts:124](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L124)

###### Returns

`Promise`\<`void`\>

##### flushAfter()

> **flushAfter**(cb: `Function`): `void` \| () => `Promise`\<`void`\>

Defined in: [lib/@empirica/core/src/admin/events.ts:132](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L132)

###### Parameters

| Parameter | Type                      |
| :-------- | :------------------------ |
| cb        | () => `Promise`\<`void`\> |

###### Returns

`void` \| () => `Promise`\<`void`\>

##### on()

> **on**(kind: "start" \| "ready", callback: `Function`): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:146](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L146)

###### Parameters

| Parameter | Type                                                                               |
| :-------- | :--------------------------------------------------------------------------------- |
| kind      | "start" \| "ready"                                                                 |
| callback  | (`ctx`: [`EventContext`](modules.md#eventcontext)\<`Context`, `Kinds`\>) => `void` |

###### Returns

`void`

> **on**(event: [`TajribaEvent`](modules.md#tajribaevent), callback: [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\>): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:152](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L152)

###### Parameters

| Parameter | Type                                                                |
| :-------- | :------------------------------------------------------------------ |
| event     | [`TajribaEvent`](modules.md#tajribaevent)                           |
| callback  | [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\> |

###### Returns

`void`

> **on**\<Kind\>(kind: `Kind`, callback: [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\>): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:155](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L155)

###### Type parameters

| Parameter               |
| :---------------------- |
| Kind _extends_ `string` |

###### Parameters

| Parameter | Type                                                                |
| :-------- | :------------------------------------------------------------------ |
| kind      | `Kind`                                                              |
| callback  | [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\> |

###### Returns

`void`

> **on**\<Kind\>(
> kind: `Kind`,
> key: `string`,
> callback: [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\>,
> uniqueCall?: `boolean`): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:161](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L161)

###### Type parameters

| Parameter                                       |
| :---------------------------------------------- |
| Kind _extends_ `string` \| `number` \| `symbol` |

###### Parameters

| Parameter   | Type                                                                |
| :---------- | :------------------------------------------------------------------ |
| kind        | `Kind`                                                              |
| key         | `string`                                                            |
| callback    | [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\> |
| uniqueCall? | `boolean`                                                           |

###### Returns

`void`

---

### ListenersCollectorProxy

#### Type parameters

| Parameter           |
| :------------------ |
| Context             |
| Kinds _extends_ \{} |

#### Hierarchy

- [`ListenersCollector`](modules.md#listenerscollector)\<`Context`, `Kinds`\>.**`ListenersCollectorProxy`**

#### Constructors

##### constructor()

> **new ListenersCollectorProxy**\<Context, Kinds\>(coll: [`ListenersCollector`](modules.md#listenerscollector)\<`Context`, `Kinds`\>): [`ListenersCollectorProxy`](modules.md#listenerscollectorproxy)\<`Context`, `Kinds`\>

Defined in: [lib/@empirica/core/src/admin/events.ts:319](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L319)

###### Type parameters

| Parameter           |
| :------------------ |
| Context             |
| Kinds _extends_ \{} |

###### Parameters

| Parameter | Type                                                                        |
| :-------- | :-------------------------------------------------------------------------- |
| coll      | [`ListenersCollector`](modules.md#listenerscollector)\<`Context`, `Kinds`\> |

###### Returns

[`ListenersCollectorProxy`](modules.md#listenerscollectorproxy)\<`Context`, `Kinds`\>

###### Overrides

[`ListenersCollector`](modules.md#listenerscollector).[`constructor`](modules.md#constructor)

#### Accessors

##### unique

> get **unique()**: [`ListenersCollectorProxy`](modules.md#listenerscollectorproxy)\<`Context`, `Kinds`\>

Defined in: [lib/@empirica/core/src/admin/events.ts:140](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L140)

###### Inherited from

[`ListenersCollector`](modules.md#listenerscollector).[`unique`](modules.md#unique)

#### Methods

##### after()

> **after**(
> kindOrEvent: `string`,
> keyOrNodeIDOrEventOrCallback?: `string` \| [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\> \| (`ctx`: [`EventContext`](modules.md#eventcontext)\<`Context`, `Kinds`\>) => `void`,
> callback?: [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\>,
> uniqueCall?: `boolean`): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:204](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L204)

###### Parameters

| Parameter                     | Type                                                                                                                                                                  |
| :---------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| kindOrEvent                   | `string`                                                                                                                                                              |
| keyOrNodeIDOrEventOrCallback? | `string` \| [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\> \| (`ctx`: [`EventContext`](modules.md#eventcontext)\<`Context`, `Kinds`\>) => `void` |
| callback?                     | [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\>                                                                                                   |
| uniqueCall?                   | `boolean`                                                                                                                                                             |

###### Returns

`void`

###### Inherited from

[`ListenersCollector`](modules.md#listenerscollector).[`after`](modules.md#after)

##### before()

> **before**(
> kindOrEvent: `string`,
> keyOrNodeIDOrEventOrCallback?: `string` \| [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\> \| (`ctx`: [`EventContext`](modules.md#eventcontext)\<`Context`, `Kinds`\>) => `void`,
> callback?: [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\>,
> uniqueCall?: `boolean`): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:185](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L185)

###### Parameters

| Parameter                     | Type                                                                                                                                                                  |
| :---------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| kindOrEvent                   | `string`                                                                                                                                                              |
| keyOrNodeIDOrEventOrCallback? | `string` \| [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\> \| (`ctx`: [`EventContext`](modules.md#eventcontext)\<`Context`, `Kinds`\>) => `void` |
| callback?                     | [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\>                                                                                                   |
| uniqueCall?                   | `boolean`                                                                                                                                                             |

###### Returns

`void`

###### Inherited from

[`ListenersCollector`](modules.md#listenerscollector).[`before`](modules.md#before)

##### flush()

> **flush**(): `Promise`\<`void`\>

Defined in: [lib/@empirica/core/src/admin/events.ts:124](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L124)

###### Returns

`Promise`\<`void`\>

###### Inherited from

[`ListenersCollector`](modules.md#listenerscollector).[`flush`](modules.md#flush)

##### flushAfter()

> **flushAfter**(cb: `Function`): `void` \| () => `Promise`\<`void`\>

Defined in: [lib/@empirica/core/src/admin/events.ts:132](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L132)

###### Parameters

| Parameter | Type                      |
| :-------- | :------------------------ |
| cb        | () => `Promise`\<`void`\> |

###### Returns

`void` \| () => `Promise`\<`void`\>

###### Inherited from

[`ListenersCollector`](modules.md#listenerscollector).[`flushAfter`](modules.md#flushafter)

##### on()

> **on**(kind: "start" \| "ready", callback: `Function`): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:146](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L146)

###### Parameters

| Parameter | Type                                                                               |
| :-------- | :--------------------------------------------------------------------------------- |
| kind      | "start" \| "ready"                                                                 |
| callback  | (`ctx`: [`EventContext`](modules.md#eventcontext)\<`Context`, `Kinds`\>) => `void` |

###### Returns

`void`

###### Inherited from

[`ListenersCollector`](modules.md#listenerscollector).[`on`](modules.md#on)

> **on**(event: [`TajribaEvent`](modules.md#tajribaevent), callback: [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\>): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:152](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L152)

###### Parameters

| Parameter | Type                                                                |
| :-------- | :------------------------------------------------------------------ |
| event     | [`TajribaEvent`](modules.md#tajribaevent)                           |
| callback  | [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\> |

###### Returns

`void`

###### Inherited from

[`ListenersCollector`](modules.md#listenerscollector).[`on`](modules.md#on)

> **on**\<Kind\>(kind: `Kind`, callback: [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\>): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:155](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L155)

###### Type parameters

| Parameter               |
| :---------------------- |
| Kind _extends_ `string` |

###### Parameters

| Parameter | Type                                                                |
| :-------- | :------------------------------------------------------------------ |
| kind      | `Kind`                                                              |
| callback  | [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\> |

###### Returns

`void`

###### Inherited from

[`ListenersCollector`](modules.md#listenerscollector).[`on`](modules.md#on)

> **on**\<Kind\>(
> kind: `Kind`,
> key: `string`,
> callback: [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\>,
> uniqueCall?: `boolean`): `void`

Defined in: [lib/@empirica/core/src/admin/events.ts:161](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L161)

###### Type parameters

| Parameter                                       |
| :---------------------------------------------- |
| Kind _extends_ `string` \| `number` \| `symbol` |

###### Parameters

| Parameter   | Type                                                                |
| :---------- | :------------------------------------------------------------------ |
| kind        | `Kind`                                                              |
| key         | `string`                                                            |
| callback    | [`EvtCtxCallback`](modules.md#evtctxcallback)\<`Context`, `Kinds`\> |
| uniqueCall? | `boolean`                                                           |

###### Returns

`void`

###### Inherited from

[`ListenersCollector`](modules.md#listenerscollector).[`on`](modules.md#on)

---

### Player

#### Hierarchy

- `GameOwned`.**`Player`**

#### Constructors

##### constructor()

> **new Player**(
> ctx: [`Context`](modules.md#context),
> scope: [`ScopeIdent`](modules.md#scopeident),
> scopes: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>,
> attributes: [`Attributes`](modules.md#attributes)): [`Player`](modules.md#player)

Defined in: [lib/@empirica/core/src/admin/scopes.ts:109](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/scopes.ts#L109)

###### Parameters

| Parameter  | Type                                                                                                        |
| :--------- | :---------------------------------------------------------------------------------------------------------- |
| ctx        | [`Context`](modules.md#context)                                                                             |
| scope      | [`ScopeIdent`](modules.md#scopeident)                                                                       |
| scopes     | [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\> |
| attributes | [`Attributes`](modules.md#attributes)                                                                       |

###### Returns

[`Player`](modules.md#player)

###### Inherited from

GameOwned.constructor

#### Properties

##### participantID

> `optional` **participantID**: `string`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:660](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L660)

#### Accessors

##### batch

> get **batch()**: `undefined` \| [`Batch`](modules.md#batch)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:106](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L106)

###### Inherited from

GameOwned.batch

##### currentGame

> get **currentGame()**: `undefined` \| [`Game`](modules.md#game)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:654](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L654)

###### Inherited from

GameOwned.currentGame

##### currentRound

> get **currentRound()**: `undefined` \| [`Round`](modules.md#round)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:673](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L673)

##### currentStage

> get **currentStage()**: `undefined` \| [`Stage`](modules.md#stage)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:688](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L688)

##### game

> get **game()**: `undefined` \| [`PlayerGame`](modules.md#playergame)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:662](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L662)

##### id

> get **id()**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L209)

###### Inherited from

GameOwned.id

##### round

> get **round()**: `undefined` \| [`PlayerRound`](modules.md#playerround)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:677](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L677)

##### stage

> get **stage()**: `undefined` \| [`PlayerStage`](modules.md#playerstage)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:692](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L692)

#### Methods

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:262](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L262)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

GameOwned.append

##### exit()

> **exit**(reason: `string`): `void`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:703](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L703)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| reason    | `string` |

###### Returns

`void`

##### get()

> **get**(key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L221)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

GameOwned.get

##### getAttribute()

> **getAttribute**(key: `string`): `undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L225)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

###### Inherited from

GameOwned.getAttribute

##### hasUpdated()

> **hasUpdated**(): `boolean`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:711](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L711)

###### Returns

`boolean`

###### Overrides

GameOwned.hasUpdated

##### inspect()

> **inspect**(): `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:271](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L271)

###### Returns

`object`

###### Inherited from

GameOwned.inspect

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L229)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

###### Inherited from

GameOwned.obs

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L233)

###### Parameters

| Parameter | Type                                            |
| :-------- | :---------------------------------------------- |
| values    | [`AttributeInput`](modules.md#attributeinput)[] |

###### Returns

`void`

###### Inherited from

GameOwned.set

> **set**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L234)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

GameOwned.set

---

### PlayerGame

#### Hierarchy

- `GameOwned`.**`PlayerGame`**

#### Constructors

##### constructor()

> **new PlayerGame**(
> ctx: [`Context`](modules.md#context),
> scope: [`ScopeIdent`](modules.md#scopeident),
> scopes: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>,
> attributes: [`Attributes`](modules.md#attributes)): [`PlayerGame`](modules.md#playergame)

Defined in: [lib/@empirica/core/src/admin/scopes.ts:109](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/scopes.ts#L109)

###### Parameters

| Parameter  | Type                                                                                                        |
| :--------- | :---------------------------------------------------------------------------------------------------------- |
| ctx        | [`Context`](modules.md#context)                                                                             |
| scope      | [`ScopeIdent`](modules.md#scopeident)                                                                       |
| scopes     | [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\> |
| attributes | [`Attributes`](modules.md#attributes)                                                                       |

###### Returns

[`PlayerGame`](modules.md#playergame)

###### Inherited from

GameOwned.constructor

#### Accessors

##### batch

> get **batch()**: `undefined` \| [`Batch`](modules.md#batch)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:106](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L106)

###### Inherited from

GameOwned.batch

##### currentGame

> get **currentGame()**: `undefined` \| [`Game`](modules.md#game)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:654](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L654)

###### Inherited from

GameOwned.currentGame

##### id

> get **id()**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L209)

###### Inherited from

GameOwned.id

#### Methods

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:262](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L262)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

GameOwned.append

##### get()

> **get**(key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L221)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

GameOwned.get

##### getAttribute()

> **getAttribute**(key: `string`): `undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L225)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

###### Inherited from

GameOwned.getAttribute

##### inspect()

> **inspect**(): `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:271](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L271)

###### Returns

`object`

###### Inherited from

GameOwned.inspect

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L229)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

###### Inherited from

GameOwned.obs

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L233)

###### Parameters

| Parameter | Type                                            |
| :-------- | :---------------------------------------------- |
| values    | [`AttributeInput`](modules.md#attributeinput)[] |

###### Returns

`void`

###### Inherited from

GameOwned.set

> **set**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L234)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

GameOwned.set

---

### PlayerRound

#### Hierarchy

- `GameOwned`.**`PlayerRound`**

#### Constructors

##### constructor()

> **new PlayerRound**(
> ctx: [`Context`](modules.md#context),
> scope: [`ScopeIdent`](modules.md#scopeident),
> scopes: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>,
> attributes: [`Attributes`](modules.md#attributes)): [`PlayerRound`](modules.md#playerround)

Defined in: [lib/@empirica/core/src/admin/scopes.ts:109](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/scopes.ts#L109)

###### Parameters

| Parameter  | Type                                                                                                        |
| :--------- | :---------------------------------------------------------------------------------------------------------- |
| ctx        | [`Context`](modules.md#context)                                                                             |
| scope      | [`ScopeIdent`](modules.md#scopeident)                                                                       |
| scopes     | [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\> |
| attributes | [`Attributes`](modules.md#attributes)                                                                       |

###### Returns

[`PlayerRound`](modules.md#playerround)

###### Inherited from

GameOwned.constructor

#### Accessors

##### batch

> get **batch()**: `undefined` \| [`Batch`](modules.md#batch)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:106](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L106)

###### Inherited from

GameOwned.batch

##### currentGame

> get **currentGame()**: `undefined` \| [`Game`](modules.md#game)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:654](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L654)

###### Inherited from

GameOwned.currentGame

##### id

> get **id()**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L209)

###### Inherited from

GameOwned.id

#### Methods

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:262](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L262)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

GameOwned.append

##### get()

> **get**(key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L221)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

GameOwned.get

##### getAttribute()

> **getAttribute**(key: `string`): `undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L225)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

###### Inherited from

GameOwned.getAttribute

##### inspect()

> **inspect**(): `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:271](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L271)

###### Returns

`object`

###### Inherited from

GameOwned.inspect

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L229)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

###### Inherited from

GameOwned.obs

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L233)

###### Parameters

| Parameter | Type                                            |
| :-------- | :---------------------------------------------- |
| values    | [`AttributeInput`](modules.md#attributeinput)[] |

###### Returns

`void`

###### Inherited from

GameOwned.set

> **set**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L234)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

GameOwned.set

---

### PlayerStage

#### Hierarchy

- `GameOwned`.**`PlayerStage`**

#### Constructors

##### constructor()

> **new PlayerStage**(
> ctx: [`Context`](modules.md#context),
> scope: [`ScopeIdent`](modules.md#scopeident),
> scopes: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>,
> attributes: [`Attributes`](modules.md#attributes)): [`PlayerStage`](modules.md#playerstage)

Defined in: [lib/@empirica/core/src/admin/scopes.ts:109](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/scopes.ts#L109)

###### Parameters

| Parameter  | Type                                                                                                        |
| :--------- | :---------------------------------------------------------------------------------------------------------- |
| ctx        | [`Context`](modules.md#context)                                                                             |
| scope      | [`ScopeIdent`](modules.md#scopeident)                                                                       |
| scopes     | [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\> |
| attributes | [`Attributes`](modules.md#attributes)                                                                       |

###### Returns

[`PlayerStage`](modules.md#playerstage)

###### Inherited from

GameOwned.constructor

#### Accessors

##### batch

> get **batch()**: `undefined` \| [`Batch`](modules.md#batch)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:106](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L106)

###### Inherited from

GameOwned.batch

##### currentGame

> get **currentGame()**: `undefined` \| [`Game`](modules.md#game)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:654](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L654)

###### Inherited from

GameOwned.currentGame

##### id

> get **id()**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L209)

###### Inherited from

GameOwned.id

##### player

> get **player()**: `undefined` \| [`Player`](modules.md#player)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:733](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L733)

##### stage

> get **stage()**: `undefined` \| [`Stage`](modules.md#stage)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:729](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L729)

#### Methods

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:262](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L262)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

GameOwned.append

##### get()

> **get**(key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L221)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

GameOwned.get

##### getAttribute()

> **getAttribute**(key: `string`): `undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L225)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

###### Inherited from

GameOwned.getAttribute

##### inspect()

> **inspect**(): `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:271](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L271)

###### Returns

`object`

###### Inherited from

GameOwned.inspect

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L229)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

###### Inherited from

GameOwned.obs

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L233)

###### Parameters

| Parameter | Type                                            |
| :-------- | :---------------------------------------------- |
| values    | [`AttributeInput`](modules.md#attributeinput)[] |

###### Returns

`void`

###### Inherited from

GameOwned.set

> **set**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L234)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

GameOwned.set

---

### Round

#### Hierarchy

- `GameOwned`.**`Round`**

#### Constructors

##### constructor()

> **new Round**(
> ctx: [`Context`](modules.md#context),
> scope: [`ScopeIdent`](modules.md#scopeident),
> scopes: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>,
> attributes: [`Attributes`](modules.md#attributes)): [`Round`](modules.md#round)

Defined in: [lib/@empirica/core/src/admin/scopes.ts:109](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/scopes.ts#L109)

###### Parameters

| Parameter  | Type                                                                                                        |
| :--------- | :---------------------------------------------------------------------------------------------------------- |
| ctx        | [`Context`](modules.md#context)                                                                             |
| scope      | [`ScopeIdent`](modules.md#scopeident)                                                                       |
| scopes     | [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\> |
| attributes | [`Attributes`](modules.md#attributes)                                                                       |

###### Returns

[`Round`](modules.md#round)

###### Inherited from

GameOwned.constructor

#### Accessors

##### batch

> get **batch()**: `undefined` \| [`Batch`](modules.md#batch)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:106](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L106)

###### Inherited from

GameOwned.batch

##### currentGame

> get **currentGame()**: `undefined` \| [`Game`](modules.md#game)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:654](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L654)

###### Inherited from

GameOwned.currentGame

##### id

> get **id()**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L209)

###### Inherited from

GameOwned.id

##### stages

> get **stages()**: [`Stage`](modules.md#stage)[]

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:749](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L749)

#### Methods

##### addStage()

> **addStage**(attributes: [`AttrInput`](modules.md#attrinput)[] \| \{}): `object`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:759](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L759)

###### Parameters

| Parameter  | Type                                         |
| :--------- | :------------------------------------------- |
| attributes | [`AttrInput`](modules.md#attrinput)[] \| \{} |

###### Returns

`object`

`readonly` **set**: `Function`

####### Type declaration - set

> > (
> > key: `string`,
> > value: [`JsonValue`](modules.md#jsonvalue),
> > ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`
>
> ######## Parameters
>
> | Parameter | Type                                                           |
> | :-------- | :------------------------------------------------------------- |
> | key       | `string`                                                       |
> | value     | [`JsonValue`](modules.md#jsonvalue)                            |
> | ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |
>
> ######## Returns
>
> `void`

`readonly` **get**

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:262](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L262)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

GameOwned.append

##### createPlayerRound()

> **createPlayerRound**(player: [`Player`](modules.md#player)): `Promise`\<`undefined` \| `string`\>

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:866](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L866)

###### Parameters

| Parameter | Type                          |
| :-------- | :---------------------------- |
| player    | [`Player`](modules.md#player) |

###### Returns

`Promise`\<`undefined` \| `string`\>

##### get()

> **get**(key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L221)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

GameOwned.get

##### getAttribute()

> **getAttribute**(key: `string`): `undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L225)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

###### Inherited from

GameOwned.getAttribute

##### inspect()

> **inspect**(): `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:271](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L271)

###### Returns

`object`

###### Inherited from

GameOwned.inspect

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L229)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

###### Inherited from

GameOwned.obs

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L233)

###### Parameters

| Parameter | Type                                            |
| :-------- | :---------------------------------------------- |
| values    | [`AttributeInput`](modules.md#attributeinput)[] |

###### Returns

`void`

###### Inherited from

GameOwned.set

> **set**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L234)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

GameOwned.set

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
> attributes: [`Attributes`](modules.md#attributes)): [`Scope`](modules.md#scope)\<`Context`, `Kinds`\>

Defined in: [lib/@empirica/core/src/admin/scopes.ts:109](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/scopes.ts#L109)

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

###### Returns

[`Scope`](modules.md#scope)\<`Context`, `Kinds`\>

###### Overrides

[`SharedScope`](modules.md#sharedscope).[`constructor`](modules.md#constructor)

#### Accessors

##### id

> get **id()**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L209)

###### Inherited from

[`SharedScope`](modules.md#sharedscope).[`id`](modules.md#id)

#### Methods

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:262](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L262)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L221)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

[`SharedScope`](modules.md#sharedscope).[`get`](modules.md#get)

##### getAttribute()

> **getAttribute**(key: `string`): `undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L225)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

###### Inherited from

[`SharedScope`](modules.md#sharedscope).[`getAttribute`](modules.md#getattribute)

##### inspect()

> **inspect**(): `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:271](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L271)

###### Returns

`object`

###### Inherited from

[`SharedScope`](modules.md#sharedscope).[`inspect`](modules.md#inspect)

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L229)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

###### Inherited from

[`SharedScope`](modules.md#sharedscope).[`obs`](modules.md#obs)

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L233)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L234)

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
> taj: [`TajribaAdminAccess`](modules.md#tajribaadminaccess)): [`Scopes`](modules.md#scopes)\<`Context`, `Kinds`\>

Defined in: [lib/@empirica/core/src/admin/scopes.ts:36](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/scopes.ts#L36)

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
| taj        | [`TajribaAdminAccess`](modules.md#tajribaadminaccess)   |

###### Returns

[`Scopes`](modules.md#scopes)\<`Context`, `Kinds`\>

###### Overrides

SharedScopes\<Context, Kinds, Scope\<Context, Kinds\>\>.constructor

#### Properties

##### taj

> `readonly` **taj**: [`TajribaAdminAccess`](modules.md#tajribaadminaccess)

Defined in: [lib/@empirica/core/src/admin/scopes.ts:42](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/scopes.ts#L42)

#### Methods

##### byKind()

> **byKind**\<T\>(kind: _keyof_ `Kinds`): `Map`\<`string`, `T`\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:72](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L72)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:82](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L82)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:64](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L64)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:68](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L68)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| id        | `string` |

###### Returns

`undefined` \| `Observable`\<[`Scope`](modules.md#scope)\<`Context`, `Kinds`\>\>

###### Inherited from

SharedScopes.scopeObs

---

### SharedAttribute

#### Constructors

##### constructor()

> **new SharedAttribute**(
> setAttributes: `Function`,
> scopeID: `string`,
> key: `string`): [`SharedAttribute`](modules.md#sharedattribute)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:240](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L240)

###### Parameters

| Parameter     | Type                                                       |
| :------------ | :--------------------------------------------------------- |
| setAttributes | (`input`: `SetAttributeInput`[]) => `Promise`\<`unknown`\> |
| scopeID       | `string`                                                   |
| key           | `string`                                                   |

###### Returns

[`SharedAttribute`](modules.md#sharedattribute)

#### Properties

##### key

> `readonly` **key**: `string`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:243](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L243)

##### scopeID

> `readonly` **scopeID**: `string`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:242](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L242)

#### Accessors

##### createdAt

> get **createdAt()**: `null` \| `Date`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:250](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L250)

##### id

> get **id()**: `undefined` \| `string`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:246](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L246)

##### items

> get **items()**: `null` \| [`SharedAttribute`](modules.md#sharedattribute)[]

Defined in: [lib/@empirica/core/src/shared/attributes.ts:268](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L268)

##### nodeID

> get **nodeID()**: `string`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:262](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L262)

##### obs

> get **obs()**: `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/attributes.ts:254](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L254)

##### value

> get **value()**: `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:258](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L258)

#### Methods

##### \_prepSet()

> **\_prepSet**(
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>,
> item?: `boolean`): `SetAttributeInput`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:282](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L282)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |
| item?     | `boolean`                                                      |

###### Returns

`SetAttributeInput`

##### \_update()

> **\_update**(attr?: [`AttributeChange`](modules.md#attributechange), item?: `boolean`): `void`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:343](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L343)

###### Parameters

| Parameter | Type                                            |
| :-------- | :---------------------------------------------- |
| attr?     | [`AttributeChange`](modules.md#attributechange) |
| item?     | `boolean`                                       |

###### Returns

`void`

##### set()

> **set**(value: [`JsonValue`](modules.md#jsonvalue), ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:276](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L276)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

---

### SharedAttributes

#### Hierarchy

- [`Attributes`](modules.md#attributes)

#### Constructors

##### constructor()

> **new SharedAttributes**(
> attributesObs: `Observable`\<[`AttributeUpdate`](modules.md#attributeupdate)\>,
> donesObs: `Observable`\<`string`[]\>,
> setAttributes: `Function`): [`SharedAttributes`](modules.md#sharedattributes)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:49](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L49)

###### Parameters

| Parameter     | Type                                                            |
| :------------ | :-------------------------------------------------------------- |
| attributesObs | `Observable`\<[`AttributeUpdate`](modules.md#attributeupdate)\> |
| donesObs      | `Observable`\<`string`[]\>                                      |
| setAttributes | (`input`: `SetAttributeInput`[]) => `Promise`\<`unknown`\>      |

###### Returns

[`SharedAttributes`](modules.md#sharedattributes)

#### Properties

##### setAttributes

> `readonly` **setAttributes**: `Function`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:52](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L52)

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

> **attribute**(scopeID: `string`, key: `string`): [`SharedAttribute`](modules.md#sharedattribute)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:67](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L67)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| scopeID   | `string` |
| key       | `string` |

###### Returns

[`SharedAttribute`](modules.md#sharedattribute)

##### attributePeek()

> **attributePeek**(scopeID: `string`, key: `string`): `undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:93](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L93)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| scopeID   | `string` |
| key       | `string` |

###### Returns

`undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

##### attributes()

> **attributes**(scopeID: `string`): [`SharedAttribute`](modules.md#sharedattribute)[]

Defined in: [lib/@empirica/core/src/shared/attributes.ts:83](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L83)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| scopeID   | `string` |

###### Returns

[`SharedAttribute`](modules.md#sharedattribute)[]

##### nextAttributeValue()

> **nextAttributeValue**(scopeID: `string`, key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:129](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L129)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| scopeID   | `string` |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

##### scopeWasUpdated()

> **scopeWasUpdated**(scopeID?: `string`): `boolean`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:165](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L165)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| scopeID?  | `string` |

###### Returns

`boolean`

---

### SharedGlobals

#### Hierarchy

- [`Globals`](modules.md#globals)

#### Constructors

##### constructor()

> **new SharedGlobals**(globals: `Observable`\<`SubAttributesPayload`\>): [`SharedGlobals`](modules.md#sharedglobals)

Defined in: [lib/@empirica/core/src/shared/globals.ts:10](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/globals.ts#L10)

###### Parameters

| Parameter | Type                                   |
| :-------- | :------------------------------------- |
| globals   | `Observable`\<`SubAttributesPayload`\> |

###### Returns

[`SharedGlobals`](modules.md#sharedglobals)

#### Properties

##### self

> **self**: `BehaviorSubject`\<`undefined` \| [`SharedGlobals`](modules.md#sharedglobals)\>

Defined in: [lib/@empirica/core/src/shared/globals.ts:8](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/globals.ts#L8)

#### Methods

##### get()

> **get**(key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/globals.ts:39](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/globals.ts#L39)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

##### obs()

> **obs**(key: `string`): `BehaviorSubject`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/globals.ts:48](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/globals.ts#L48)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`BehaviorSubject`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:194](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L194)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L209)

#### Methods

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:262](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L262)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L221)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

##### getAttribute()

> **getAttribute**(key: `string`): `undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L225)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

##### inspect()

> **inspect**(): `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:271](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L271)

###### Returns

`object`

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L229)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L233)

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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L234)

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

- `GameOwned`.**`Stage`**

#### Constructors

##### constructor()

> **new Stage**(
> ctx: [`Context`](modules.md#context),
> scope: [`ScopeIdent`](modules.md#scopeident),
> scopes: [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>,
> attributes: [`Attributes`](modules.md#attributes)): [`Stage`](modules.md#stage)

Defined in: [lib/@empirica/core/src/admin/scopes.ts:109](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/scopes.ts#L109)

###### Parameters

| Parameter  | Type                                                                                                        |
| :--------- | :---------------------------------------------------------------------------------------------------------- |
| ctx        | [`Context`](modules.md#context)                                                                             |
| scope      | [`ScopeIdent`](modules.md#scopeident)                                                                       |
| scopes     | [`Scopes`](modules.md#scopes)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\> |
| attributes | [`Attributes`](modules.md#attributes)                                                                       |

###### Returns

[`Stage`](modules.md#stage)

###### Inherited from

GameOwned.constructor

#### Accessors

##### batch

> get **batch()**: `undefined` \| [`Batch`](modules.md#batch)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:106](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L106)

###### Inherited from

GameOwned.batch

##### currentGame

> get **currentGame()**: `undefined` \| [`Game`](modules.md#game)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:654](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L654)

###### Inherited from

GameOwned.currentGame

##### id

> get **id()**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:209](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L209)

###### Inherited from

GameOwned.id

##### round

> get **round()**: `undefined` \| [`Round`](modules.md#round)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:916](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L916)

#### Methods

##### append()

> **append**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:262](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L262)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

GameOwned.append

##### createPlayerStage()

> **createPlayerStage**(player: [`Player`](modules.md#player)): `Promise`\<`undefined` \| `string`\>

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:942](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L942)

###### Parameters

| Parameter | Type                          |
| :-------- | :---------------------------- |
| player    | [`Player`](modules.md#player) |

###### Returns

`Promise`\<`undefined` \| `string`\>

##### end()

> **end**(status: `string`, reason: `string`): `void`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:924](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L924)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| status    | `string` |
| reason    | `string` |

###### Returns

`void`

##### get()

> **get**(key: `string`): `undefined` \| [`JsonValue`](modules.md#jsonvalue)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:221](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L221)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`JsonValue`](modules.md#jsonvalue)

###### Inherited from

GameOwned.get

##### getAttribute()

> **getAttribute**(key: `string`): `undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:225](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L225)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`undefined` \| [`SharedAttribute`](modules.md#sharedattribute)

###### Inherited from

GameOwned.getAttribute

##### inspect()

> **inspect**(): `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:271](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L271)

###### Returns

`object`

###### Inherited from

GameOwned.inspect

##### isCurrent()

> **isCurrent**(): `boolean`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:920](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L920)

###### Returns

`boolean`

##### obs()

> **obs**(key: `string`): `Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:229](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L229)

###### Parameters

| Parameter | Type     |
| :-------- | :------- |
| key       | `string` |

###### Returns

`Observable`\<`undefined` \| [`JsonValue`](modules.md#jsonvalue)\>

###### Inherited from

GameOwned.obs

##### set()

> **set**(values: [`AttributeInput`](modules.md#attributeinput)[]): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:233](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L233)

###### Parameters

| Parameter | Type                                            |
| :-------- | :---------------------------------------------- |
| values    | [`AttributeInput`](modules.md#attributeinput)[] |

###### Returns

`void`

###### Inherited from

GameOwned.set

> **set**(
> key: `string`,
> value: [`JsonValue`](modules.md#jsonvalue),
> ao?: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>): `void`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:234](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L234)

###### Parameters

| Parameter | Type                                                           |
| :-------- | :------------------------------------------------------------- |
| key       | `string`                                                       |
| value     | [`JsonValue`](modules.md#jsonvalue)                            |
| ao?       | `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\> |

###### Returns

`void`

###### Inherited from

GameOwned.set

---

### TajribaAdminAccess

#### Constructors

##### constructor()

> **new TajribaAdminAccess**(
> addFinalizer: `Function`,
> addScopes: `Function`,
> addGroups: `Function`,
> addLinks: `Function`,
> addSteps: `Function`,
> addTransitions: `Function`,
> globals: [`Globals`](modules.md#globals)): [`TajribaAdminAccess`](modules.md#tajribaadminaccess)

Defined in: [lib/@empirica/core/src/admin/context.ts:225](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/context.ts#L225)

###### Parameters

| Parameter      | Type                                                                                                       |
| :------------- | :--------------------------------------------------------------------------------------------------------- |
| addFinalizer   | (`cb`: [`Finalizer`](modules.md#finalizer)) => `void`                                                      |
| addScopes      | (`input`: `AddScopeInput`[]) => `Promise`\<[`AddScopePayload`](modules.md#addscopepayload)[]\>             |
| addGroups      | (`input`: `AddGroupInput`[]) => `Promise`\<\{id: `string`;}[]\>                                            |
| addLinks       | (`input`: `LinkInput`[]) => `Promise`\<[`AddLinkPayload`](modules.md#addlinkpayload)[]\>                   |
| addSteps       | (`input`: `AddStepInput`[]) => `Promise`\<[`StepPayload`](modules.md#steppayload)[]\>                      |
| addTransitions | (`input`: `TransitionInput`[]) => `Promise`\<[`AddTransitionPayload`](modules.md#addtransitionpayload)[]\> |
| globals        | [`Globals`](modules.md#globals)                                                                            |

###### Returns

[`TajribaAdminAccess`](modules.md#tajribaadminaccess)

#### Properties

##### addFinalizer

> `readonly` **addFinalizer**: `Function`

Defined in: [lib/@empirica/core/src/admin/context.ts:226](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/context.ts#L226)

###### Type declaration

> > (cb: [`Finalizer`](modules.md#finalizer)): `void`
>
> ####### Parameters
>
> | Parameter | Type                                |
> | :-------- | :---------------------------------- |
> | cb        | [`Finalizer`](modules.md#finalizer) |
>
> ####### Returns
>
> `void`

##### addGroups

> `readonly` **addGroups**: `Function`

Defined in: [lib/@empirica/core/src/admin/context.ts:228](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/context.ts#L228)

###### Type declaration

> > (input: `AddGroupInput`[]): `Promise`\<\{id: `string`;}[]\>
>
> ####### Parameters
>
> | Parameter | Type              |
> | :-------- | :---------------- |
> | input     | `AddGroupInput`[] |
>
> ####### Returns
>
> `Promise`\<\{id: `string`;}[]\>

##### addLinks

> `readonly` **addLinks**: `Function`

Defined in: [lib/@empirica/core/src/admin/context.ts:229](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/context.ts#L229)

###### Type declaration

> > (input: `LinkInput`[]): `Promise`\<[`AddLinkPayload`](modules.md#addlinkpayload)[]\>
>
> ####### Parameters
>
> | Parameter | Type          |
> | :-------- | :------------ |
> | input     | `LinkInput`[] |
>
> ####### Returns
>
> `Promise`\<[`AddLinkPayload`](modules.md#addlinkpayload)[]\>

##### addScopes

> `readonly` **addScopes**: `Function`

Defined in: [lib/@empirica/core/src/admin/context.ts:227](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/context.ts#L227)

###### Type declaration

> > (input: `AddScopeInput`[]): `Promise`\<[`AddScopePayload`](modules.md#addscopepayload)[]\>
>
> ####### Parameters
>
> | Parameter | Type              |
> | :-------- | :---------------- |
> | input     | `AddScopeInput`[] |
>
> ####### Returns
>
> `Promise`\<[`AddScopePayload`](modules.md#addscopepayload)[]\>

##### addSteps

> `readonly` **addSteps**: `Function`

Defined in: [lib/@empirica/core/src/admin/context.ts:230](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/context.ts#L230)

###### Type declaration

> > (input: `AddStepInput`[]): `Promise`\<[`StepPayload`](modules.md#steppayload)[]\>
>
> ####### Parameters
>
> | Parameter | Type             |
> | :-------- | :--------------- |
> | input     | `AddStepInput`[] |
>
> ####### Returns
>
> `Promise`\<[`StepPayload`](modules.md#steppayload)[]\>

##### addTransitions

> `readonly` **addTransitions**: `Function`

Defined in: [lib/@empirica/core/src/admin/context.ts:231](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/context.ts#L231)

###### Type declaration

> > (input: `TransitionInput`[]): `Promise`\<[`AddTransitionPayload`](modules.md#addtransitionpayload)[]\>
>
> ####### Parameters
>
> | Parameter | Type                |
> | :-------- | :------------------ |
> | input     | `TransitionInput`[] |
>
> ####### Returns
>
> `Promise`\<[`AddTransitionPayload`](modules.md#addtransitionpayload)[]\>

##### globals

> `readonly` **globals**: [`Globals`](modules.md#globals)

Defined in: [lib/@empirica/core/src/admin/context.ts:234](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/context.ts#L234)

---

## Interfaces

### AddLinkPayload

#### Properties

##### nodes

> **nodes**: \{id: `string`;}[]

Defined in: [lib/@empirica/core/src/admin/context.ts:193](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/context.ts#L193)

##### participants

> **participants**: \{id: `string`;}[]

Defined in: [lib/@empirica/core/src/admin/context.ts:194](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/context.ts#L194)

---

### AddScopePayload

#### Properties

##### attributes

> **attributes**: `object`

Defined in: [lib/@empirica/core/src/admin/context.ts:207](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/context.ts#L207)

###### Type declaration

> **edges**: \{node: \{id: `string`;
> immutable: `boolean`;
> index: `null` \| `number`;
> key: `string`;
> private: `boolean`;
> protected: `boolean`;
> val: `null` \| `string`;};}[]

##### id

> **id**: `string`

Defined in: [lib/@empirica/core/src/admin/context.ts:204](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/context.ts#L204)

##### kind

> `optional` **kind**: `null` \| `string`

Defined in: [lib/@empirica/core/src/admin/context.ts:206](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/context.ts#L206)

##### name

> `optional` **name**: `null` \| `string`

Defined in: [lib/@empirica/core/src/admin/context.ts:205](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/context.ts#L205)

---

### AddTransitionPayload

#### Properties

##### from

> **from**: `State`

Defined in: [lib/@empirica/core/src/admin/context.ts:199](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/context.ts#L199)

##### id

> **id**: `string`

Defined in: [lib/@empirica/core/src/admin/context.ts:198](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/context.ts#L198)

##### to

> **to**: `State`

Defined in: [lib/@empirica/core/src/admin/context.ts:200](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/context.ts#L200)

---

### AttributeChange

#### Properties

##### createdAt

> `optional` **createdAt**: `string`

createdAt is the time the Attribute was created. int64 Date + Time
value given in Epoch with ns precision

Defined in: [lib/@empirica/core/src/shared/attributes.ts:14](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L14)

##### deleted

> `optional` **deleted**: `boolean`

deleted is true with the attribute was deleted.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:8](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L8)

##### deletedAt

> `optional` **deletedAt**: `number`

deletedAt is the time when the Attribute was deleted. int64 Date + Time
value given in Epoch with ns precision

Defined in: [lib/@empirica/core/src/shared/attributes.ts:11](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L11)

##### id

> **id**: `string`

id is the identifier for the Attribute.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:16](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L16)

##### index

> `optional` **index**: `null` \| `number`

index is the index of the attribute if the value is a vector.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:18](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L18)

##### isNew

> `optional` **isNew**: `boolean`

isNew is true if the Attribute was just created.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:20](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L20)

##### key

> **key**: `string`

key is the attribute key being updated.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:22](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L22)

##### node

> `optional` **node**: `object`

node is the Attribute's Node.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:26](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L26)

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

Defined in: [lib/@empirica/core/src/shared/attributes.ts:24](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L24)

##### val

> `optional` **val**: `null` \| `string`

value is the value of the updated attribute.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:33](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L33)

##### vector

> **vector**: `boolean`

vector indicates whether the value is a vector.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:35](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L35)

##### version

> **version**: `number`

version is the version number of this Attribute, starting at 1.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:37](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L37)

---

### AttributeOptions

#### Properties

##### append

> **append**: `null` \| `boolean`

Append, only used if the Attribute is a vector, indicates to append the
attribute to the vector.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:231](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L231)

##### immutable

> **immutable**: `boolean`

Immutable creates an Attribute that cannot be updated.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:221](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L221)

##### index

> **index**: `null` \| `number`

Index, only used if the Attribute is a vector, indicates which index to
update the value at.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:226](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L226)

##### private

> **private**: `boolean`

Private indicates the attribute will not be visible to other Participants.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:214](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L214)

##### protected

> **protected**: `boolean`

Protected indicates the attribute will not be updatable by other
Participants.

Defined in: [lib/@empirica/core/src/shared/attributes.ts:219](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L219)

---

### AttributeUpdate

#### Properties

##### attribute

> **attribute**: [`AttributeChange`](modules.md#attributechange)

Defined in: [lib/@empirica/core/src/shared/attributes.ts:41](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L41)

##### removed

> **removed**: `boolean`

Defined in: [lib/@empirica/core/src/shared/attributes.ts:42](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/attributes.ts#L42)

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

### ScopeIdent

#### Properties

##### id

> **id**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:19](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L19)

##### kind

> **kind**: `string`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:20](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L20)

---

### ScopeSubscriptionInput

#### Properties

##### ids

> **ids**: `string`[]

ids of the matching Scopes.

Defined in: [lib/@empirica/core/src/admin/subscriptions.ts:14](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/subscriptions.ts#L14)

##### keys

> **keys**: `string`[]

keys to Attributes in matching Scope.

Defined in: [lib/@empirica/core/src/admin/subscriptions.ts:18](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/subscriptions.ts#L18)

##### kinds

> **kinds**: `string`[]

kinds of the matching Scopes.

Defined in: [lib/@empirica/core/src/admin/subscriptions.ts:16](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/subscriptions.ts#L16)

##### kvs

> **kvs**: [`KV`](modules.md#kv)[]

kvs to Attributes in matching Scope.

Defined in: [lib/@empirica/core/src/admin/subscriptions.ts:20](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/subscriptions.ts#L20)

##### names

> **names**: `string`[]

names of the matching Scopes.

Defined in: [lib/@empirica/core/src/admin/subscriptions.ts:22](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/subscriptions.ts#L22)

---

### ScopeUpdate

#### Properties

##### removed

> **removed**: `boolean`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:25](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L25)

##### scope

> **scope**: [`ScopeIdent`](modules.md#scopeident)

Defined in: [lib/@empirica/core/src/shared/scopes.ts:24](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L24)

---

### StartTajribaOptions

#### Properties

##### configFile

> `optional` **configFile**: `string`

Defined in: [lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts:48](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts#L48)

##### logLevel

> `optional` **logLevel**: `string`

Defined in: [lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts:50](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts#L50)

##### password

> `optional` **password**: `string`

Defined in: [lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts:54](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts#L54)

##### printLogs

> `optional` **printLogs**: `boolean`

Defined in: [lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts:51](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts#L51)

##### srtoken

> `optional` **srtoken**: `string`

Defined in: [lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts:52](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts#L52)

##### tajFile

> `optional` **tajFile**: `string`

Defined in: [lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts:49](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts#L49)

##### username

> `optional` **username**: `string`

Defined in: [lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts:53](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts#L53)

---

### StepPayload

#### Properties

##### duration

> **duration**: `number`

Defined in: [lib/@empirica/core/src/admin/context.ts:189](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/context.ts#L189)

##### id

> **id**: `string`

Defined in: [lib/@empirica/core/src/admin/context.ts:188](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/context.ts#L188)

---

### TajServer

#### Properties

##### password

> **password**: `string`

Defined in: [lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts:17](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts#L17)

##### port

> **port**: `number`

Defined in: [lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts:14](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts#L14)

##### srtoken

> **srtoken**: `string`

Defined in: [lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts:18](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts#L18)

##### stop

> **stop**: `Function`

Defined in: [lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts:13](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts#L13)

###### Type declaration

> > (): `void`
>
> ####### Returns
>
> `void`

##### url

> **url**: `string`

Defined in: [lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts:15](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts#L15)

##### username

> **username**: `string`

Defined in: [lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts:16](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts#L16)

---

## Type Aliases

### AttrInput

> **AttrInput**: `object`

Defined in: [lib/@empirica/core/src/admin/classic/helpers.ts:59](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/helpers.ts#L59)

#### Type declaration

> `optional` **append**: `boolean`
>
> `optional` **immutable**: `boolean`
>
> `optional` **index**: `number`
>
> **key**: `string`
>
> `optional` **nodeID**: `string`
>
> `optional` **private**: `boolean`
>
> `optional` **protected**: `boolean`
>
> **value**: [`JsonValue`](modules.md#jsonvalue)
>
> `optional` **vector**: `boolean`

---

### Attributable

> **Attributable**: `object`

Defined in: [lib/@empirica/core/src/shared/scopes.ts:7](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L7)

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
> > > (key: `string`): [`SharedAttribute`](modules.md#sharedattribute) \| `undefined`
> >
> > ###### Parameters
> >
> > | Parameter | Type     |
> > | :-------- | :------- |
> > | key       | `string` |
> >
> > ###### Returns
> >
> > [`SharedAttribute`](modules.md#sharedattribute) \| `undefined`
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

Defined in: [lib/@empirica/core/src/shared/scopes.ts:174](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L174)

#### Type declaration

> `optional` **ao**: `Partial`\<[`AttributeOptions`](modules.md#attributeoptions)\>
>
> **key**: `string`
>
> **value**: [`JsonValue`](modules.md#jsonvalue)

---

### AttributeMsg

> **AttributeMsg**: `object`

Defined in: [lib/@empirica/core/src/admin/attributes.ts:9](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/attributes.ts#L9)

#### Type declaration

> `optional` **attribute**: [`SharedAttribute`](modules.md#sharedattribute)
>
> **done**: `boolean`

---

### ClassicConfig

> **ClassicConfig**: `object`

Defined in: [lib/@empirica/core/src/admin/classic/classic.ts:30](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/classic.ts#L30)

#### Type declaration

> `optional` **disableAssignment**: `boolean`
>
> `optional` **disableBatchAutoend**: `boolean`
>
> `optional` **disableGameCreation**: `boolean`
>
> `optional` **disableIntroCheck**: `boolean`

---

### ClassicKinds

> **ClassicKinds**: `object`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:999](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L999)

#### Type declaration

> **batch**: [`Constructor`](modules.md#constructor)\<[`Batch`](modules.md#batch)\>
>
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

### Constructor

> **Constructor**: \<`T`\> `Function`

Defined in: [lib/@empirica/core/src/shared/helpers.ts:1](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/helpers.ts#L1)

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

### EvtCtxCallback

> **EvtCtxCallback**: \<`Context`, `Kinds`\> `Function`

Defined in: [lib/@empirica/core/src/admin/events.ts:67](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/events.ts#L67)

#### Type parameters

| Parameter           |
| :------------------ |
| Context             |
| Kinds _extends_ \{} |

#### Type declaration

> > (ctx: [`EventContext`](modules.md#eventcontext)\<`Context`, `Kinds`\>, props: `any`): `void`
>
> ##### Parameters
>
> | Parameter | Type                                                            |
> | :-------- | :-------------------------------------------------------------- |
> | ctx       | [`EventContext`](modules.md#eventcontext)\<`Context`, `Kinds`\> |
> | props     | `any`                                                           |
>
> ##### Returns
>
> `void`

---

### Finalizer

> **Finalizer**: `Function`

Defined in: [lib/@empirica/core/src/admin/context.ts:222](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/context.ts#L222)

#### Type declaration

> > (): `Promise`\<`void`\>
>
> ##### Returns
>
> `Promise`\<`void`\>

---

### JsonValue

> **JsonValue**: `string` \| `number` \| `boolean` \| `Date` \| [`Json`](modules.md#json) \| [`JsonArray`](modules.md#jsonarray) \| `null`

Defined in: [lib/@empirica/core/src/utils/json.ts:1](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/utils/json.ts#L1)

---

### KV

> **KV**: `object`

Defined in: [lib/@empirica/core/src/admin/subscriptions.ts:3](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/subscriptions.ts#L3)

#### Type declaration

> **key**: `string`
>
> **val**: `string`

---

### LobbyConfig

> **LobbyConfig**: `object`

Defined in: [lib/@empirica/core/src/admin/classic/lobby.ts:17](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/lobby.ts#L17)

#### Type declaration

---

### ScopeConstructor

> **ScopeConstructor**: \<`Context`, `Kinds`\> [`Constructor`](modules.md#constructor)\<[`SharedScope`](modules.md#sharedscope)\<`Context`, `Kinds`\>\>

Defined in: [lib/@empirica/core/src/shared/scopes.ts:28](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/shared/scopes.ts#L28)

#### Type parameters

| Parameter           |
| :------------------ |
| Context             |
| Kinds _extends_ \{} |

---

## Variables

### classicKinds

> `const` **classicKinds**: `object`

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:1010](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L1010)

#### Type declaration

> **batch**: _typeof_ [`Batch`](modules.md#batch) = `Batch`
>
> **game**: _typeof_ [`Game`](modules.md#game) = `Game`
>
> **player**: _typeof_ [`Player`](modules.md#player) = `Player`
>
> **playerGame**: _typeof_ [`PlayerGame`](modules.md#playergame) = `PlayerGame`
>
> **playerRound**: _typeof_ [`PlayerRound`](modules.md#playerround) = `PlayerRound`
>
> **playerStage**: _typeof_ [`PlayerStage`](modules.md#playerstage) = `PlayerStage`
>
> **round**: _typeof_ [`Round`](modules.md#round) = `Round`
>
> **stage**: _typeof_ [`Stage`](modules.md#stage) = `Stage`

---

## Functions

### Classic()

> **Classic**(\_\_namedParameters: [`ClassicConfig`](modules.md#classicconfig) = `{}`): `Function`

Defined in: [lib/@empirica/core/src/admin/classic/classic.ts:54](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/classic.ts#L54)

#### Parameters

| Parameter           | Type                                        |
| :------------------ | :------------------------------------------ |
| \_\_namedParameters | [`ClassicConfig`](modules.md#classicconfig) |

#### Returns

`Function`

> > (\_: [`ListenersCollector`](modules.md#listenerscollector)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>): `void`
>
> ##### Parameters
>
> | Parameter | Type                                                                                                                                |
> | :-------- | :---------------------------------------------------------------------------------------------------------------------------------- |
> | \_        | [`ListenersCollector`](modules.md#listenerscollector)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\> |
>
> ##### Returns
>
> `void`

---

### ClassicLoader()

> **ClassicLoader**(\_: [`ListenersCollector`](modules.md#listenerscollector)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>): `void`

ClassicLoader loads.

Defined in: [lib/@empirica/core/src/admin/classic/loader.ts:8](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/loader.ts#L8)

#### Parameters

| Parameter | Type                                                                                                                                | Description          |
| :-------- | :---------------------------------------------------------------------------------------------------------------------------------- | :------------------- |
| \_        | [`ListenersCollector`](modules.md#listenerscollector)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\> | This is the listener |

#### Returns

`void`

---

### Lobby()

> **Lobby**(\_: [`LobbyConfig`](modules.md#lobbyconfig) = `{}`): `Function`

Defined in: [lib/@empirica/core/src/admin/classic/lobby.ts:19](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/lobby.ts#L19)

#### Parameters

| Parameter | Type                                    |
| :-------- | :-------------------------------------- |
| \_        | [`LobbyConfig`](modules.md#lobbyconfig) |

#### Returns

`Function`

> > (\_: [`ListenersCollector`](modules.md#listenerscollector)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>): `void`
>
> ##### Parameters
>
> | Parameter | Type                                                                                                                                |
> | :-------- | :---------------------------------------------------------------------------------------------------------------------------------- |
> | \_        | [`ListenersCollector`](modules.md#listenerscollector)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\> |
>
> ##### Returns
>
> `void`

---

### evt()

> **evt**(ctx: [`EventContext`](modules.md#eventcontext)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\>): [`EventProxy`](modules.md#eventproxy)

Defined in: [lib/@empirica/core/src/admin/classic/models.ts:1040](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/models.ts#L1040)

#### Parameters

| Parameter | Type                                                                                                                    |
| :-------- | :---------------------------------------------------------------------------------------------------------------------- |
| ctx       | [`EventContext`](modules.md#eventcontext)\<[`Context`](modules.md#context), [`ClassicKinds`](modules.md#classickinds)\> |

#### Returns

[`EventProxy`](modules.md#eventproxy)

---

### runExport()

> **runExport**(
> url: `string`,
> token: `null` \| `string`,
> srtoken: `string`,
> format: [`ExportFormat`](modules.md#exportformat),
> output: `string`): `Promise`\<`void`\>

Defined in: [lib/@empirica/core/src/admin/classic/export/export.ts:13](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/export/export.ts#L13)

#### Parameters

| Parameter | Type                                      |
| :-------- | :---------------------------------------- |
| url       | `string`                                  |
| token     | `null` \| `string`                        |
| srtoken   | `string`                                  |
| format    | [`ExportFormat`](modules.md#exportformat) |
| output    | `string`                                  |

#### Returns

`Promise`\<`void`\>

---

### withTajriba()

> **withTajriba**(fn: `Function`, options: [`StartTajribaOptions`](modules.md#starttajribaoptions) = `{}`): `Promise`\<`void`\>

Defined in: [lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts:158](https://github.com/empiricaly/empirica/blob/2d7972a/lib/@empirica/core/src/admin/classic/api/connection_test_helper.ts#L158)

#### Parameters

| Parameter | Type                                                         |
| :-------- | :----------------------------------------------------------- |
| fn        | (`tajServer`: [`TajServer`](modules.md#tajserver)) => `void` |
| options   | [`StartTajribaOptions`](modules.md#starttajribaoptions)      |

#### Returns

`Promise`\<`void`\>

---
