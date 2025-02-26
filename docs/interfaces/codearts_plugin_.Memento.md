[@codearts/plugin](../README.md) / ["@codearts/plugin"](../modules/_codearts_plugin_.md) / Memento

# Interface: Memento

["@codearts/plugin"](../modules/_codearts_plugin_.md).Memento

A memento represents a storage utility. It can store and retrieve
values.

## Table of contents

### Methods

- [get](codearts_plugin_.Memento.md#get)
- [keys](codearts_plugin_.Memento.md#keys)
- [update](codearts_plugin_.Memento.md#update)

## Methods

### get

▸ **get**<`T`\>(`key`): `undefined` \| `T`

Return a value.

#### Type parameters

| Name |
| :------ |
| `T` |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `key` | `string` | A string. |

#### Returns

`undefined` \| `T`

The stored value or `undefined`.

#### Defined in

[index.d.ts:7089](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L7089)

▸ **get**<`T`\>(`key`, `defaultValue`): `T`

Return a value.

#### Type parameters

| Name |
| :------ |
| `T` |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `key` | `string` | A string. |
| `defaultValue` | `T` | A value that should be returned when there is no value (`undefined`) with the given key. |

#### Returns

`T`

The stored value or the defaultValue.

#### Defined in

[index.d.ts:7099](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L7099)

___

### keys

▸ **keys**(): readonly `string`[]

Returns the stored keys.

#### Returns

readonly `string`[]

The stored keys.

#### Defined in

[index.d.ts:7081](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L7081)

___

### update

▸ **update**(`key`, `value`): [`Thenable`](Thenable.md)<`void`\>

Store a value. The value must be JSON-stringifyable.

*Note* that using `undefined` as value removes the key from the underlying
storage.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `key` | `string` | A string. |
| `value` | `any` | A value. MUST not contain cyclic references. |

#### Returns

[`Thenable`](Thenable.md)<`void`\>

#### Defined in

[index.d.ts:7110](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L7110)
