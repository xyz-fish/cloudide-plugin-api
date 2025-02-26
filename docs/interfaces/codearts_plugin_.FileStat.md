[@codearts/plugin](../README.md) / ["@codearts/plugin"](../modules/_codearts_plugin_.md) / FileStat

# Interface: FileStat

["@codearts/plugin"](../modules/_codearts_plugin_.md).FileStat

The `FileStat`-type represents metadata about a file

## Table of contents

### Properties

- [ctime](codearts_plugin_.FileStat.md#ctime)
- [mtime](codearts_plugin_.FileStat.md#mtime)
- [permissions](codearts_plugin_.FileStat.md#permissions)
- [size](codearts_plugin_.FileStat.md#size)
- [type](codearts_plugin_.FileStat.md#type)

## Properties

### ctime

• **ctime**: `number`

The creation timestamp in milliseconds elapsed since January 1, 1970 00:00:00 UTC.

#### Defined in

[index.d.ts:7915](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L7915)

___

### mtime

• **mtime**: `number`

The modification timestamp in milliseconds elapsed since January 1, 1970 00:00:00 UTC.

*Note:* If the file changed, it is important to provide an updated `mtime` that advanced
from the previous value. Otherwise there may be optimizations in place that will not show
the updated file contents in an editor for example.

#### Defined in

[index.d.ts:7923](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L7923)

___

### permissions

• `Optional` **permissions**: [`Readonly`](../enums/codearts_plugin_.FilePermission.md#readonly)

The permissions of the file, e.g. whether the file is readonly.

*Note:* This value might be a bitmask, e.g. `FilePermission.Readonly | FilePermission.Other`.

#### Defined in

[index.d.ts:7937](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L7937)

___

### size

• **size**: `number`

The size in bytes.

*Note:* If the file changed, it is important to provide an updated `size`. Otherwise there
may be optimizations in place that will not show the updated file contents in an editor for
example.

#### Defined in

[index.d.ts:7931](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L7931)

___

### type

• **type**: [`FileType`](../enums/codearts_plugin_.FileType.md)

The type of the file, e.g. is a regular file, a directory, or symbolic link
to a file.

*Note:* This value might be a bitmask, e.g. `FileType.File | FileType.SymbolicLink`.

#### Defined in

[index.d.ts:7911](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L7911)
