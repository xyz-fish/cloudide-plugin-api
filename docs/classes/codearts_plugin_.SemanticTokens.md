[@codearts/plugin](../README.md) / ["@codearts/plugin"](../modules/_codearts_plugin_.md) / SemanticTokens

# Class: SemanticTokens

["@codearts/plugin"](../modules/_codearts_plugin_.md).SemanticTokens

Represents semantic tokens, either in a range or in an entire document.

**`See`**

 - [provideDocumentSemanticTokens](../interfaces/codearts_plugin_.DocumentSemanticTokensProvider.md#providedocumentsemantictokens) for an explanation of the format.
 - [SemanticTokensBuilder](codearts_plugin_.SemanticTokensBuilder.md) for a helper to create an instance.

## Table of contents

### Constructors

- [constructor](codearts_plugin_.SemanticTokens.md#constructor)

### Properties

- [data](codearts_plugin_.SemanticTokens.md#data)
- [resultId](codearts_plugin_.SemanticTokens.md#resultid)

## Constructors

### constructor

• **new SemanticTokens**(`data`, `resultId?`)

#### Parameters

| Name | Type |
| :------ | :------ |
| `data` | `Uint32Array` |
| `resultId?` | `string` |

#### Defined in

[index.d.ts:3786](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L3786)

## Properties

### data

• `Readonly` **data**: `Uint32Array`

The actual tokens data.

**`See`**

[provideDocumentSemanticTokens](../interfaces/codearts_plugin_.DocumentSemanticTokensProvider.md#providedocumentsemantictokens) for an explanation of the format.

#### Defined in

[index.d.ts:3784](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L3784)

___

### resultId

• `Readonly` **resultId**: `undefined` \| `string`

The result id of the tokens.

This is the id that will be passed to `DocumentSemanticTokensProvider.provideDocumentSemanticTokensEdits` (if implemented).

#### Defined in

[index.d.ts:3779](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L3779)
