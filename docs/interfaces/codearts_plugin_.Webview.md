[@codearts/plugin](../README.md) / ["@codearts/plugin"](../modules/_codearts_plugin_.md) / Webview

# Interface: Webview

["@codearts/plugin"](../modules/_codearts_plugin_.md).Webview

Displays html content, similarly to an iframe.

## Table of contents

### Properties

- [cspSource](codearts_plugin_.Webview.md#cspsource)
- [html](codearts_plugin_.Webview.md#html)
- [onDidReceiveMessage](codearts_plugin_.Webview.md#ondidreceivemessage)
- [options](codearts_plugin_.Webview.md#options)

### Methods

- [asWebviewUri](codearts_plugin_.Webview.md#aswebviewuri)
- [postMessage](codearts_plugin_.Webview.md#postmessage)

## Properties

### cspSource

• `Readonly` **cspSource**: `string`

Content security policy source for webview resources.

This is the origin that should be used in a content security policy rule:

```ts
`img-src https: ${webview.cspSource} ...;`
```

#### Defined in

[index.d.ts:8440](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L8440)

___

### html

• **html**: `string`

HTML contents of the webview.

This should be a complete, valid html document. Changing this property causes the webview to be reloaded.

Webviews are sandboxed from normal extension process, so all communication with the webview must use
message passing. To send a message from the extension to the webview, use [`postMessage`](codearts_plugin_.Webview.md#postmessage).
To send message from the webview back to an extension, use the `acquireVsCodeApi` function inside the webview
to get a handle to the editor's api and then call `.postMessage()`:

```html
<script>
    const vscode = acquireVsCodeApi(); // acquireVsCodeApi can only be invoked once
    vscode.postMessage({ message: 'hello!' });
</script>
```

To load a resources from the workspace inside a webview, use the [`asWebviewUri`](codearts_plugin_.Webview.md#aswebviewuri) method
and ensure the resource's directory is listed in [`localResourceRoots`](codearts_plugin_.WebviewOptions.md#localresourceroots).

Keep in mind that even though webviews are sandboxed, they still allow running scripts and loading arbitrary content,
so extensions must follow all standard web security best practices when working with webviews. This includes
properly sanitizing all untrusted input (including content from the workspace) and
setting a [content security policy](https://aka.ms/vscode-api-webview-csp).

#### Defined in

[index.d.ts:8374](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L8374)

___

### onDidReceiveMessage

• `Readonly` **onDidReceiveMessage**: [`Event`](codearts_plugin_.Event.md)<`any`\>

Fired when the webview content posts a message.

Webview content can post strings or json serializable objects back to an extension. They cannot
post `Blob`, `File`, `ImageData` and other DOM specific objects since the extension that receives the
message does not run in a browser environment.

#### Defined in

[index.d.ts:8383](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L8383)

___

### options

• **options**: [`WebviewOptions`](codearts_plugin_.WebviewOptions.md)

Content settings for the webview.

#### Defined in

[index.d.ts:8347](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L8347)

## Methods

### asWebviewUri

▸ **asWebviewUri**(`localResource`): [`Uri`](../classes/codearts_plugin_.Uri.md)

Convert a uri for the local file system to one that can be used inside webviews.

Webviews cannot directly load resources from the workspace or local file system using `file:` uris. The
`asWebviewUri` function takes a local `file:` uri and converts it into a uri that can be used inside of
a webview to load the same resource:

```ts
webview.html = `<img src="${webview.asWebviewUri(vscode.Uri.file('/Users/codey/workspace/cat.gif'))}">`
```

#### Parameters

| Name | Type |
| :------ | :------ |
| `localResource` | [`Uri`](../classes/codearts_plugin_.Uri.md) |

#### Returns

[`Uri`](../classes/codearts_plugin_.Uri.md)

#### Defined in

[index.d.ts:8429](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L8429)

___

### postMessage

▸ **postMessage**(`message`): [`Thenable`](Thenable.md)<`boolean`\>

Post a message to the webview content.

Messages are only delivered if the webview is live (either visible or in the
background with `retainContextWhenHidden`).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `message` | `any` | Body of the message. This must be a string or other json serializable object.    For older versions of vscode, if an `ArrayBuffer` is included in `message`,   it will not be serialized properly and will not be received by the webview.   Similarly any TypedArrays, such as a `Uint8Array`, will be very inefficiently   serialized and will also not be recreated as a typed array inside the webview.    However if your extension targets vscode 1.57+ in the `engines` field of its   `package.json`, any `ArrayBuffer` values that appear in `message` will be more   efficiently transferred to the webview and will also be correctly recreated inside   of the webview. |

#### Returns

[`Thenable`](Thenable.md)<`boolean`\>

A promise that resolves when the message is posted to a webview or when it is
dropped because the message was not deliverable.

  Returns `true` if the message was posted to the webview. Messages can only be posted to
live webviews (i.e. either visible webviews or hidden webviews that set `retainContextWhenHidden`).

  A response of `true` does not mean that the message was actually received by the webview.
  For example, no message listeners may be have been hooked up inside the webview or the webview may
  have been destroyed after the message was posted but before it was received.

  If you want confirm that a message as actually received, you can try having your webview posting a
  confirmation message back to your extension.

#### Defined in

[index.d.ts:8416](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L8416)
