[@codearts/plugin](../README.md) / ["@codearts/plugin"](../modules/_codearts_plugin_.md) / WebviewView

# Interface: WebviewView

["@codearts/plugin"](../modules/_codearts_plugin_.md).WebviewView

A webview based view.

## Table of contents

### Properties

- [description](codearts_plugin_.WebviewView.md#description)
- [onDidChangeVisibility](codearts_plugin_.WebviewView.md#ondidchangevisibility)
- [onDidDispose](codearts_plugin_.WebviewView.md#ondiddispose)
- [title](codearts_plugin_.WebviewView.md#title)
- [viewType](codearts_plugin_.WebviewView.md#viewtype)
- [visible](codearts_plugin_.WebviewView.md#visible)
- [webview](codearts_plugin_.WebviewView.md#webview)

### Methods

- [show](codearts_plugin_.WebviewView.md#show)

## Properties

### description

• `Optional` **description**: `string`

Human-readable string which is rendered less prominently in the title.

#### Defined in

[index.d.ts:8692](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L8692)

___

### onDidChangeVisibility

• `Readonly` **onDidChangeVisibility**: [`Event`](codearts_plugin_.Event.md)<`void`\>

Event fired when the visibility of the view changes.

Actions that trigger a visibility change:

- The view is collapsed or expanded.
- The user switches to a different view group in the sidebar or panel.

Note that hiding a view using the context menu instead disposes of the view and fires `onDidDispose`.

#### Defined in

[index.d.ts:8721](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L8721)

___

### onDidDispose

• `Readonly` **onDidDispose**: [`Event`](codearts_plugin_.Event.md)<`void`\>

Event fired when the view is disposed.

Views are disposed when they are explicitly hidden by a user (this happens when a user
right clicks in a view and unchecks the webview view).

Trying to use the view after it has been disposed throws an exception.

#### Defined in

[index.d.ts:8702](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L8702)

___

### title

• `Optional` **title**: `string`

View title displayed in the UI.

The view title is initially taken from the extension `package.json` contribution.

#### Defined in

[index.d.ts:8687](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L8687)

___

### viewType

• `Readonly` **viewType**: `string`

Identifies the type of the webview view, such as `'hexEditor.dataView'`.

#### Defined in

[index.d.ts:8675](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L8675)

___

### visible

• `Readonly` **visible**: `boolean`

Tracks if the webview is currently visible.

Views are visible when they are on the screen and expanded.

#### Defined in

[index.d.ts:8709](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L8709)

___

### webview

• `Readonly` **webview**: [`Webview`](codearts_plugin_.Webview.md)

The underlying webview for the view.

#### Defined in

[index.d.ts:8680](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L8680)

## Methods

### show

▸ **show**(`preserveFocus?`): `void`

Reveal the view in the UI.

If the view is collapsed, this will expand it.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `preserveFocus?` | `boolean` | When `true` the view will not take focus. |

#### Returns

`void`

#### Defined in

[index.d.ts:8730](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L8730)
