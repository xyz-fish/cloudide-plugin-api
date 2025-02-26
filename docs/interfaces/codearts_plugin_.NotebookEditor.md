[@codearts/plugin](../README.md) / ["@codearts/plugin"](../modules/_codearts_plugin_.md) / NotebookEditor

# Interface: NotebookEditor

["@codearts/plugin"](../modules/_codearts_plugin_.md).NotebookEditor

Represents a notebook editor that is attached to a [notebook](codearts_plugin_.NotebookDocument.md).
Additional properties of the NotebookEditor are available in the proposed
API, which will be finalized later.

## Table of contents

### Properties

- [notebook](codearts_plugin_.NotebookEditor.md#notebook)
- [selection](codearts_plugin_.NotebookEditor.md#selection)
- [selections](codearts_plugin_.NotebookEditor.md#selections)
- [viewColumn](codearts_plugin_.NotebookEditor.md#viewcolumn)
- [visibleRanges](codearts_plugin_.NotebookEditor.md#visibleranges)

### Methods

- [revealRange](codearts_plugin_.NotebookEditor.md#revealrange)

## Properties

### notebook

• `Readonly` **notebook**: [`NotebookDocument`](codearts_plugin_.NotebookDocument.md)

The [notebook document](codearts_plugin_.NotebookDocument.md) associated with this notebook editor.

#### Defined in

[index.d.ts:13755](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L13755)

___

### selection

• **selection**: [`NotebookRange`](../classes/codearts_plugin_.NotebookRange.md)

The primary selection in this notebook editor.

#### Defined in

[index.d.ts:13760](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L13760)

___

### selections

• **selections**: readonly [`NotebookRange`](../classes/codearts_plugin_.NotebookRange.md)[]

All selections in this notebook editor.

The primary selection (or focused range) is `selections[0]`. When the document has no cells, the primary selection is empty `{ start: 0, end: 0 }`;

#### Defined in

[index.d.ts:13767](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L13767)

___

### viewColumn

• `Optional` `Readonly` **viewColumn**: [`ViewColumn`](../enums/codearts_plugin_.ViewColumn.md)

The column in which this editor shows.

#### Defined in

[index.d.ts:13777](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L13777)

___

### visibleRanges

• `Readonly` **visibleRanges**: readonly [`NotebookRange`](../classes/codearts_plugin_.NotebookRange.md)[]

The current visible ranges in the editor (vertically).

#### Defined in

[index.d.ts:13772](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L13772)

## Methods

### revealRange

▸ **revealRange**(`range`, `revealType?`): `void`

Scroll as indicated by `revealType` in order to reveal the given range.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `range` | [`NotebookRange`](../classes/codearts_plugin_.NotebookRange.md) | A range. |
| `revealType?` | [`NotebookEditorRevealType`](../enums/codearts_plugin_.NotebookEditorRevealType.md) | The scrolling strategy for revealing `range`. |

#### Returns

`void`

#### Defined in

[index.d.ts:13785](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L13785)
