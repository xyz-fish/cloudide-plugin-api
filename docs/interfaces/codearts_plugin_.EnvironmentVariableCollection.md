[@codearts/plugin](../README.md) / ["@codearts/plugin"](../modules/_codearts_plugin_.md) / EnvironmentVariableCollection

# Interface: EnvironmentVariableCollection

["@codearts/plugin"](../modules/_codearts_plugin_.md).EnvironmentVariableCollection

A collection of mutations that an extension can apply to a process environment.

## Hierarchy

- `Iterable`<[variable: string, mutator: EnvironmentVariableMutator]\>

  ↳ **`EnvironmentVariableCollection`**

## Table of contents

### Properties

- [persistent](codearts_plugin_.EnvironmentVariableCollection.md#persistent)

### Methods

- [append](codearts_plugin_.EnvironmentVariableCollection.md#append)
- [clear](codearts_plugin_.EnvironmentVariableCollection.md#clear)
- [delete](codearts_plugin_.EnvironmentVariableCollection.md#delete)
- [forEach](codearts_plugin_.EnvironmentVariableCollection.md#foreach)
- [get](codearts_plugin_.EnvironmentVariableCollection.md#get)
- [prepend](codearts_plugin_.EnvironmentVariableCollection.md#prepend)
- [replace](codearts_plugin_.EnvironmentVariableCollection.md#replace)

## Properties

### persistent

• **persistent**: `boolean`

Whether the collection should be cached for the workspace and applied to the terminal
across window reloads. When true the collection will be active immediately such when the
window reloads. Additionally, this API will return the cached version if it exists. The
collection will be invalidated when the extension is uninstalled or when the collection
is cleared. Defaults to true.

#### Defined in

[index.d.ts:11440](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L11440)

## Methods

### append

▸ **append**(`variable`, `value`): `void`

Append a value to an environment variable.

Note that an extension can only make a single change to any one variable, so this will
overwrite any previous calls to replace, append or prepend.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `variable` | `string` | The variable to append to. |
| `value` | `string` | The value to append to the variable. |

#### Returns

`void`

#### Defined in

[index.d.ts:11462](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L11462)

___

### clear

▸ **clear**(): `void`

Clears all mutators from this collection.

#### Returns

`void`

#### Defined in

[index.d.ts:11500](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L11500)

___

### delete

▸ **delete**(`variable`): `void`

Deletes this collection's mutator for a variable.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `variable` | `string` | The variable to delete the mutator for. |

#### Returns

`void`

#### Defined in

[index.d.ts:11495](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L11495)

___

### forEach

▸ **forEach**(`callback`, `thisArg?`): `void`

Iterate over each mutator in this collection.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `callback` | (`variable`: `string`, `mutator`: [`EnvironmentVariableMutator`](codearts_plugin_.EnvironmentVariableMutator.md), `collection`: [`EnvironmentVariableCollection`](codearts_plugin_.EnvironmentVariableCollection.md)) => `any` | Function to execute for each entry. |
| `thisArg?` | `any` | The `this` context used when invoking the handler function. |

#### Returns

`void`

#### Defined in

[index.d.ts:11488](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L11488)

___

### get

▸ **get**(`variable`): `undefined` \| [`EnvironmentVariableMutator`](codearts_plugin_.EnvironmentVariableMutator.md)

Gets the mutator that this collection applies to a variable, if any.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `variable` | `string` | The variable to get the mutator for. |

#### Returns

`undefined` \| [`EnvironmentVariableMutator`](codearts_plugin_.EnvironmentVariableMutator.md)

#### Defined in

[index.d.ts:11480](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L11480)

___

### prepend

▸ **prepend**(`variable`, `value`): `void`

Prepend a value to an environment variable.

Note that an extension can only make a single change to any one variable, so this will
overwrite any previous calls to replace, append or prepend.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `variable` | `string` | The variable to prepend. |
| `value` | `string` | The value to prepend to the variable. |

#### Returns

`void`

#### Defined in

[index.d.ts:11473](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L11473)

___

### replace

▸ **replace**(`variable`, `value`): `void`

Replace an environment variable with a value.

Note that an extension can only make a single change to any one variable, so this will
overwrite any previous calls to replace, append or prepend.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `variable` | `string` | The variable to replace. |
| `value` | `string` | The value to replace the variable with. |

#### Returns

`void`

#### Defined in

[index.d.ts:11451](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L11451)
