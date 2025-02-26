[@codearts/plugin](../README.md) / ["@codearts/plugin"](../modules/_codearts_plugin_.md) / TreeViewOptions

# Interface: TreeViewOptions<T\>

["@codearts/plugin"](../modules/_codearts_plugin_.md).TreeViewOptions

Options for creating a [TreeView](codearts_plugin_.TreeView.md)

## Type parameters

| Name |
| :------ |
| `T` |

## Table of contents

### Properties

- [canSelectMany](codearts_plugin_.TreeViewOptions.md#canselectmany)
- [dragAndDropController](codearts_plugin_.TreeViewOptions.md#draganddropcontroller)
- [showCollapseAll](codearts_plugin_.TreeViewOptions.md#showcollapseall)
- [treeDataProvider](codearts_plugin_.TreeViewOptions.md#treedataprovider)

## Properties

### canSelectMany

• `Optional` **canSelectMany**: `boolean`

Whether the tree supports multi-select. When the tree supports multi-select and a command is executed from the tree,
the first argument to the command is the tree item that the command was executed on and the second argument is an
array containing all selected tree items.

#### Defined in

[index.d.ts:10500](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L10500)

___

### dragAndDropController

• `Optional` **dragAndDropController**: [`TreeDragAndDropController`](codearts_plugin_.TreeDragAndDropController.md)<`T`\>

An optional interface to implement drag and drop in the tree view.

#### Defined in

[index.d.ts:10505](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L10505)

___

### showCollapseAll

• `Optional` **showCollapseAll**: `boolean`

Whether to show collapse all action or not.

#### Defined in

[index.d.ts:10493](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L10493)

___

### treeDataProvider

• **treeDataProvider**: [`TreeDataProvider`](codearts_plugin_.TreeDataProvider.md)<`T`\>

A data provider that provides tree data.

#### Defined in

[index.d.ts:10488](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L10488)
