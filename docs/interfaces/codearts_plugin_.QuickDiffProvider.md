[@codearts/plugin](../README.md) / ["@codearts/plugin"](../modules/_codearts_plugin_.md) / QuickDiffProvider

# Interface: QuickDiffProvider

["@codearts/plugin"](../modules/_codearts_plugin_.md).QuickDiffProvider

## Table of contents

### Methods

- [provideOriginalResource](codearts_plugin_.QuickDiffProvider.md#provideoriginalresource)

## Methods

### provideOriginalResource

▸ `Optional` **provideOriginalResource**(`uri`, `token`): [`ProviderResult`](../modules/_codearts_plugin_.md#providerresult)<[`Uri`](../classes/codearts_plugin_.Uri.md)\>

Provide a [Uri](../classes/codearts_plugin_.Uri.md) to the original resource of any given resource uri.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `uri` | [`Uri`](../classes/codearts_plugin_.Uri.md) | The uri of the resource open in a text editor. |
| `token` | [`CancellationToken`](codearts_plugin_.CancellationToken.md) | A cancellation token. |

#### Returns

[`ProviderResult`](../modules/_codearts_plugin_.md#providerresult)<[`Uri`](../classes/codearts_plugin_.Uri.md)\>

A thenable that resolves to uri of the matching original resource.

#### Defined in

[index.d.ts:14751](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L14751)
