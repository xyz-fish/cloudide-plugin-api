[@codearts/plugin](../README.md) / ["@codearts/plugin"](../modules/_codearts_plugin_.md) / BuildDataItem

# Interface: BuildDataItem

["@codearts/plugin"](../modules/_codearts_plugin_.md).BuildDataItem

## Table of contents

### Properties

- [accessibilityInformation](codearts_plugin_.BuildDataItem.md#accessibilityinformation)
- [children](codearts_plugin_.BuildDataItem.md#children)
- [collapsibleState](codearts_plugin_.BuildDataItem.md#collapsiblestate)
- [command](codearts_plugin_.BuildDataItem.md#command)
- [description](codearts_plugin_.BuildDataItem.md#description)
- [iconPath](codearts_plugin_.BuildDataItem.md#iconpath)
- [label](codearts_plugin_.BuildDataItem.md#label)
- [message](codearts_plugin_.BuildDataItem.md#message)
- [range](codearts_plugin_.BuildDataItem.md#range)
- [resourceUri](codearts_plugin_.BuildDataItem.md#resourceuri)
- [suffix](codearts_plugin_.BuildDataItem.md#suffix)
- [tooltip](codearts_plugin_.BuildDataItem.md#tooltip)
- [uri](codearts_plugin_.BuildDataItem.md#uri)

## Properties

### accessibilityInformation

• `Optional` **accessibilityInformation**: [`AccessibilityInformation`](codearts_plugin_.AccessibilityInformation.md)

Accessibility information used when screen reader interacts with this tree item.
Generally, a TreeItem has no need to set the `role` of the accessibilityInformation;
however, there are cases where a TreeItem is not displayed in a tree-like way where setting the `role` may make sense.

#### Defined in

[index.d.ts:17088](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L17088)

___

### children

• `Optional` **children**: [`BuildDataItem`](codearts_plugin_.BuildDataItem.md)[]

add children

#### Defined in

[index.d.ts:17036](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L17036)

___

### collapsibleState

• `Optional` **collapsibleState**: [`TreeItemCollapsibleState`](../enums/codearts_plugin_.TreeItemCollapsibleState.md)

[TreeItemCollapsibleState](../enums/codearts_plugin_.TreeItemCollapsibleState.md) of the tree item.

#### Defined in

[index.d.ts:17081](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L17081)

___

### command

• `Optional` **command**: [`Command`](codearts_plugin_.Command.md)

The [Command](codearts_plugin_.Command.md) that should be executed when the tree item is selected.

Please use `vscode.open` or `vscode.diff` as command IDs when the tree item is opening
something in the editor. Using these commands ensures that the resulting editor will
appear consistent with how other built-in trees open editors.

#### Defined in

[index.d.ts:17076](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L17076)

___

### description

• `Optional` **description**: `string` \| `boolean`

A human-readable string which is rendered less prominent.
When `true`, it is derived from [resourceUri](../classes/codearts_plugin_.TreeItem.md#resourceuri) and when `falsy`, it is not shown.

#### Defined in

[index.d.ts:17054](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L17054)

___

### iconPath

• `Optional` **iconPath**: `string` \| [`Uri`](../classes/codearts_plugin_.Uri.md) \| [`ThemeIcon`](../classes/codearts_plugin_.ThemeIcon.md) \| { `dark`: `string` \| [`Uri`](../classes/codearts_plugin_.Uri.md) ; `light`: `string` \| [`Uri`](../classes/codearts_plugin_.Uri.md)  }

The icon path or [ThemeIcon](../classes/codearts_plugin_.ThemeIcon.md) for the tree item.
When `falsy`, [Folder Theme Icon](../classes/codearts_plugin_.ThemeIcon.md#folder) is assigned, if item is collapsible otherwise [File Theme Icon](../classes/codearts_plugin_.ThemeIcon.md#file).
When a file or folder [ThemeIcon](../classes/codearts_plugin_.ThemeIcon.md) is specified, icon is derived from the current file icon theme for the specified theme icon using [resourceUri](../classes/codearts_plugin_.TreeItem.md#resourceuri) (if provided).

#### Defined in

[index.d.ts:17048](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L17048)

___

### label

• `Optional` **label**: `string` \| [`TreeItemLabel`](codearts_plugin_.TreeItemLabel.md)

A human-readable string describing this item. When `falsy`, it is derived from [resourceUri](../classes/codearts_plugin_.TreeItem.md#resourceuri).

#### Defined in

[index.d.ts:17041](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L17041)

___

### message

• `Optional` **message**: `string`

when treeview focus show related BuildMessage [BuildMessage](codearts_plugin_.BuildMessage.md).message

#### Defined in

[index.d.ts:17031](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L17031)

___

### range

• `Optional` **range**: [`Range`](../classes/codearts_plugin_.Range.md)

Location of the test item in its [uri](codearts_plugin_.BuildDataItem.md#uri).
This is only meaningful if the `uri` points to a file.

#### Defined in

[index.d.ts:17106](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L17106)

___

### resourceUri

• `Optional` **resourceUri**: [`Uri`](../classes/codearts_plugin_.Uri.md)

The [Uri](../classes/codearts_plugin_.Uri.md) of the resource representing this item.

Will be used to derive the [label](../classes/codearts_plugin_.TreeItem.md#label), when it is not provided.
Will be used to derive the icon from current file icon theme, when [iconPath](../classes/codearts_plugin_.TreeItem.md#iconpath) has [ThemeIcon](../classes/codearts_plugin_.ThemeIcon.md) value.

#### Defined in

[index.d.ts:17062](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L17062)

___

### suffix

• `Optional` **suffix**: `string`

This field will be rendered at the end of the tree item.

#### Defined in

[index.d.ts:17093](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L17093)

___

### tooltip

• `Optional` **tooltip**: `string` \| [`MarkdownString`](../classes/codearts_plugin_.MarkdownString.md)

The tooltip text when you hover over this item.

#### Defined in

[index.d.ts:17067](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L17067)

___

### uri

• `Optional` **uri**: [`Uri`](../classes/codearts_plugin_.Uri.md)

The [Uri](../classes/codearts_plugin_.Uri.md) of the resource representing this item.
For open the resource file of this item.
Use uri when resourceUri does not exist.

#### Defined in

[index.d.ts:17100](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L17100)
