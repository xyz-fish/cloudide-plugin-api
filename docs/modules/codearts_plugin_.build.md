[@codearts/plugin](../README.md) / ["@codearts/plugin"](_codearts_plugin_.md) / build

# Namespace: build

["@codearts/plugin"](_codearts_plugin_.md).build

Namespace for build functionality. Handlers are published by registering
[BuildController](../interfaces/codearts_plugin_.BuildController.md) instances.

## Table of contents

### Functions

- [createBuildController](codearts_plugin_.build.md#createbuildcontroller)

## Functions

### createBuildController

▸ **createBuildController**(`id`, `label`, `options?`): [`BuildController`](../interfaces/codearts_plugin_.BuildController.md)

Creates a new build controller.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | Identifier for the controller, must be globally unique. |
| `label` | `string` | A human-readable label for the controller. |
| `options?` | [`BuildOption`](../interfaces/codearts_plugin_.BuildOption.md) | - |

#### Returns

[`BuildController`](../interfaces/codearts_plugin_.BuildController.md)

An instance of the [BuildController](../interfaces/codearts_plugin_.BuildController.md).

#### Defined in

[index.d.ts:16867](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L16867)
