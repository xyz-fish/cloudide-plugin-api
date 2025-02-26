[@codearts/plugin](../README.md) / ["@codearts/plugin"](../modules/_codearts_plugin_.md) / CompletionList

# Class: CompletionList<T\>

["@codearts/plugin"](../modules/_codearts_plugin_.md).CompletionList

Represents a collection of [completion items](codearts_plugin_.CompletionItem.md) to be presented
in the editor.

## Type parameters

| Name | Type |
| :------ | :------ |
| `T` | extends [`CompletionItem`](codearts_plugin_.CompletionItem.md) = [`CompletionItem`](codearts_plugin_.CompletionItem.md) |

## Table of contents

### Constructors

- [constructor](codearts_plugin_.CompletionList.md#constructor)

### Properties

- [isIncomplete](codearts_plugin_.CompletionList.md#isincomplete)
- [items](codearts_plugin_.CompletionList.md#items)
- [onDidRecieveUpdate](codearts_plugin_.CompletionList.md#ondidrecieveupdate)
- [unlock](codearts_plugin_.CompletionList.md#unlock)

## Constructors

### constructor

• **new CompletionList**<`T`\>(`items?`, `isIncomplete?`)

Creates a new completion list.

#### Type parameters

| Name | Type |
| :------ | :------ |
| `T` | extends [`CompletionItem`](codearts_plugin_.CompletionItem.md)<`T`\> = [`CompletionItem`](codearts_plugin_.CompletionItem.md) |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `items?` | `T`[] | The completion items. |
| `isIncomplete?` | `boolean` | The list is not complete. |

#### Defined in

[index.d.ts:4477](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L4477)

## Properties

### isIncomplete

• `Optional` **isIncomplete**: `boolean`

This list is not complete. Further typing should result in recomputing
this list.

#### Defined in

[index.d.ts:4444](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L4444)

___

### items

• **items**: `T`[]

The completion items.

#### Defined in

[index.d.ts:4449](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L4449)

___

### onDidRecieveUpdate

• `Optional` **onDidRecieveUpdate**: [`Event`](../interfaces/codearts_plugin_.Event.md)<`undefined` \| ``null`` \| `void` \| `T` \| `T`[]\>

Allows to update completion list. Must be used in conjunction with BufferingEventEmitter buffering event emitter and [unlock](codearts_plugin_.CompletionList.md#unlock) helper method.

#### Defined in

[index.d.ts:4456](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L4456)

___

### unlock

• `Optional` **unlock**: () => `void`

#### Type declaration

▸ (): `void`

In case [update event](codearts_plugin_.CompletionList.md#ondidrecieveupdate) is defined, this method will be called by consumer when it is ready
to listen. Must be used in conjunction with BufferingEventEmitter buffering event emitter.

Example:

```ts
   const _onDidRecieveUpdate = new vscode.BufferingEventEmitter<vscode.CompletionItem[]>();
	  list.onDidRecieveUpdate = _onDidRecieveUpdate.event;
	  list.unlock = () => _onDidRecieveUpdate.unlock();
```

##### Returns

`void`

#### Defined in

[index.d.ts:4469](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L4469)
