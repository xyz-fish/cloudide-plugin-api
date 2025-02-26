[@codearts/plugin](../README.md) / ["@codearts/plugin"](../modules/_codearts_plugin_.md) / DataTransferFile

# Interface: DataTransferFile

["@codearts/plugin"](../modules/_codearts_plugin_.md).DataTransferFile

A file associated with a [`DataTransferItem`](../classes/codearts_plugin_.DataTransferItem.md).

## Table of contents

### Properties

- [name](codearts_plugin_.DataTransferFile.md#name)
- [uri](codearts_plugin_.DataTransferFile.md#uri)

### Methods

- [data](codearts_plugin_.DataTransferFile.md#data)

## Properties

### name

• `Readonly` **name**: `string`

The name of the file.

#### Defined in

[index.d.ts:10562](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L10562)

___

### uri

• `Optional` `Readonly` **uri**: [`Uri`](../classes/codearts_plugin_.Uri.md)

The full file path of the file.

May be `undefined` on web.

#### Defined in

[index.d.ts:10569](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L10569)

## Methods

### data

▸ **data**(): [`Thenable`](Thenable.md)<`Uint8Array`\>

The full file contents of the file.

#### Returns

[`Thenable`](Thenable.md)<`Uint8Array`\>

#### Defined in

[index.d.ts:10574](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L10574)
