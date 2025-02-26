[@codearts/plugin](../README.md) / ["@codearts/plugin"](../modules/_codearts_plugin_.md) / CompletionItemLabel

# Interface: CompletionItemLabel

["@codearts/plugin"](../modules/_codearts_plugin_.md).CompletionItemLabel

A structured label for a [completion item](../classes/codearts_plugin_.CompletionItem.md).

## Table of contents

### Properties

- [description](codearts_plugin_.CompletionItemLabel.md#description)
- [detail](codearts_plugin_.CompletionItemLabel.md#detail)
- [label](codearts_plugin_.CompletionItemLabel.md#label)

## Properties

### description

• `Optional` **description**: `string`

An optional string which is rendered less prominently after [detail](codearts_plugin_.CompletionItemLabel.md#detail). Should be used
for fully qualified names or file path.

#### Defined in

[index.d.ts:4238](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L4238)

___

### detail

• `Optional` **detail**: `string`

An optional string which is rendered less prominently directly after [label](codearts_plugin_.CompletionItemLabel.md#label),
without any spacing. Should be used for function signatures or type annotations.

#### Defined in

[index.d.ts:4232](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L4232)

___

### label

• **label**: `string`

The label of this completion item.

By default this is also the text that is inserted when this completion is selected.

#### Defined in

[index.d.ts:4226](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L4226)
