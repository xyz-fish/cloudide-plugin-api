[@codearts/plugin](../README.md) / ["@codearts/plugin"](../modules/_codearts_plugin_.md) / TabGroup

# Interface: TabGroup

["@codearts/plugin"](../modules/_codearts_plugin_.md).TabGroup

Represents a group of tabs. A tab group itself consists of multiple tabs.

## Table of contents

### Properties

- [activeTab](codearts_plugin_.TabGroup.md#activetab)
- [isActive](codearts_plugin_.TabGroup.md#isactive)
- [tabs](codearts_plugin_.TabGroup.md#tabs)
- [viewColumn](codearts_plugin_.TabGroup.md#viewcolumn)

## Properties

### activeTab

• `Readonly` **activeTab**: `undefined` \| [`Tab`](codearts_plugin_.Tab.md)

The active [tab](codearts_plugin_.Tab.md) in the group. This is the tab whose contents are currently
being rendered.

*Note* that there can be one active tab per group but there can only be one [active group](codearts_plugin_.TabGroups.md#activetabgroup).

#### Defined in

[index.d.ts:17350](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L17350)

___

### isActive

• `Readonly` **isActive**: `boolean`

Whether or not the group is currently active.

*Note* that only one tab group is active at a time, but that multiple tab
groups can have an TabGroup.aciveTab active tab.

**`See`**

[isActive](codearts_plugin_.Tab.md#isactive)

#### Defined in

[index.d.ts:17337](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L17337)

___

### tabs

• `Readonly` **tabs**: readonly [`Tab`](codearts_plugin_.Tab.md)[]

The list of tabs contained within the group.
This can be empty if the group has no tabs open.

#### Defined in

[index.d.ts:17356](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L17356)

___

### viewColumn

• `Readonly` **viewColumn**: [`ViewColumn`](../enums/codearts_plugin_.ViewColumn.md)

The view column of the group.

#### Defined in

[index.d.ts:17342](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L17342)
