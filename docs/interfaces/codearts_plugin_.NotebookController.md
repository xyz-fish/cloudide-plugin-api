[@codearts/plugin](../README.md) / ["@codearts/plugin"](../modules/_codearts_plugin_.md) / NotebookController

# Interface: NotebookController

["@codearts/plugin"](../modules/_codearts_plugin_.md).NotebookController

A notebook controller represents an entity that can execute notebook cells. This is often referred to as a kernel.

There can be multiple controllers and the editor will let users choose which controller to use for a certain notebook. The
[`notebookType`](codearts_plugin_.NotebookController.md#notebooktype)-property defines for what kind of notebooks a controller is for and
the [`updateNotebookAffinity`](codearts_plugin_.NotebookController.md#updatenotebookaffinity)-function allows controllers to set a preference
for specific notebook documents. When a controller has been selected its
[onDidChangeSelectedNotebooks](codearts_plugin_.NotebookController.md#ondidchangeselectednotebooks)-event fires.

When a cell is being run the editor will invoke the [`executeHandler`](codearts_plugin_.NotebookController.md#executehandler) and a controller
is expected to create and finalize a [notebook cell execution](codearts_plugin_.NotebookCellExecution.md). However, controllers are also free
to create executions by themselves.

## Table of contents

### Properties

- [description](codearts_plugin_.NotebookController.md#description)
- [detail](codearts_plugin_.NotebookController.md#detail)
- [executeHandler](codearts_plugin_.NotebookController.md#executehandler)
- [id](codearts_plugin_.NotebookController.md#id)
- [interruptHandler](codearts_plugin_.NotebookController.md#interrupthandler)
- [label](codearts_plugin_.NotebookController.md#label)
- [notebookType](codearts_plugin_.NotebookController.md#notebooktype)
- [onDidChangeSelectedNotebooks](codearts_plugin_.NotebookController.md#ondidchangeselectednotebooks)
- [supportedLanguages](codearts_plugin_.NotebookController.md#supportedlanguages)
- [supportsExecutionOrder](codearts_plugin_.NotebookController.md#supportsexecutionorder)

### Methods

- [createNotebookCellExecution](codearts_plugin_.NotebookController.md#createnotebookcellexecution)
- [dispose](codearts_plugin_.NotebookController.md#dispose)
- [updateNotebookAffinity](codearts_plugin_.NotebookController.md#updatenotebookaffinity)

## Properties

### description

• `Optional` **description**: `string`

The human-readable description which is rendered less prominent.

#### Defined in

[index.d.ts:14422](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L14422)

___

### detail

• `Optional` **detail**: `string`

The human-readable detail which is rendered less prominent.

#### Defined in

[index.d.ts:14427](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L14427)

___

### executeHandler

• **executeHandler**: (`cells`: [`NotebookCell`](codearts_plugin_.NotebookCell.md)[], `notebook`: [`NotebookDocument`](codearts_plugin_.NotebookDocument.md), `controller`: [`NotebookController`](codearts_plugin_.NotebookController.md)) => `void` \| [`Thenable`](Thenable.md)<`void`\>

#### Type declaration

▸ (`cells`, `notebook`, `controller`): `void` \| [`Thenable`](Thenable.md)<`void`\>

The execute handler is invoked when the run gestures in the UI are selected, e.g Run Cell, Run All,
Run Selection etc. The execute handler is responsible for creating and managing [execution](codearts_plugin_.NotebookCellExecution.md)-objects.

##### Parameters

| Name | Type |
| :------ | :------ |
| `cells` | [`NotebookCell`](codearts_plugin_.NotebookCell.md)[] |
| `notebook` | [`NotebookDocument`](codearts_plugin_.NotebookDocument.md) |
| `controller` | [`NotebookController`](codearts_plugin_.NotebookController.md) |

##### Returns

`void` \| [`Thenable`](Thenable.md)<`void`\>

#### Defined in

[index.d.ts:14454](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L14454)

___

### id

• `Readonly` **id**: `string`

The identifier of this notebook controller.

_Note_ that controllers are remembered by their identifier and that extensions should use
stable identifiers across sessions.

#### Defined in

[index.d.ts:14390](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L14390)

___

### interruptHandler

• `Optional` **interruptHandler**: (`notebook`: [`NotebookDocument`](codearts_plugin_.NotebookDocument.md)) => `void` \| [`Thenable`](Thenable.md)<`void`\>

#### Type declaration

▸ (`notebook`): `void` \| [`Thenable`](Thenable.md)<`void`\>

Optional interrupt handler.

By default cell execution is canceled via [tokens](codearts_plugin_.NotebookCellExecution.md#token). Cancellation
tokens require that a controller can keep track of its execution so that it can cancel a specific execution at a later
point. Not all scenarios allow for that, eg. REPL-style controllers often work by interrupting whatever is currently
running. For those cases the interrupt handler exists - it can be thought of as the equivalent of `SIGINT`
or `Control+C` in terminals.

_Note_ that supporting [cancellation tokens](codearts_plugin_.NotebookCellExecution.md#token) is preferred and that interrupt handlers should
only be used when tokens cannot be supported.

##### Parameters

| Name | Type |
| :------ | :------ |
| `notebook` | [`NotebookDocument`](codearts_plugin_.NotebookDocument.md) |

##### Returns

`void` \| [`Thenable`](Thenable.md)<`void`\>

#### Defined in

[index.d.ts:14468](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L14468)

___

### label

• **label**: `string`

The human-readable label of this notebook controller.

#### Defined in

[index.d.ts:14417](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L14417)

___

### notebookType

• `Readonly` **notebookType**: `string`

The notebook type this controller is for.

#### Defined in

[index.d.ts:14395](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L14395)

___

### onDidChangeSelectedNotebooks

• `Readonly` **onDidChangeSelectedNotebooks**: [`Event`](codearts_plugin_.Event.md)<{ `notebook`: [`NotebookDocument`](codearts_plugin_.NotebookDocument.md) ; `selected`: `boolean`  }\>

An event that fires whenever a controller has been selected or un-selected for a notebook document.

There can be multiple controllers for a notebook and in that case a controllers needs to be _selected_. This is a user gesture
and happens either explicitly or implicitly when interacting with a notebook for which a controller was _suggested_. When possible,
the editor _suggests_ a controller that is most likely to be _selected_.

_Note_ that controller selection is persisted (by the controllers [id](codearts_plugin_.NotebookController.md#id)) and restored as soon as a
controller is re-created or as a notebook is [opened](../modules/codearts_plugin_.workspace.md#ondidopennotebookdocument).

#### Defined in

[index.d.ts:14480](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L14480)

___

### supportedLanguages

• `Optional` **supportedLanguages**: `string`[]

An array of language identifiers that are supported by this
controller. Any language identifier from [`getLanguages`](../modules/codearts_plugin_.languages.md#getlanguages)
is possible. When falsy all languages are supported.

Samples:
```js
// support JavaScript and TypeScript
myController.supportedLanguages = ['javascript', 'typescript']

// support all languages
myController.supportedLanguages = undefined; // falsy
myController.supportedLanguages = []; // falsy
```

#### Defined in

[index.d.ts:14412](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L14412)

___

### supportsExecutionOrder

• `Optional` **supportsExecutionOrder**: `boolean`

Whether this controller supports execution order so that the
editor can render placeholders for them.

#### Defined in

[index.d.ts:14433](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L14433)

## Methods

### createNotebookCellExecution

▸ **createNotebookCellExecution**(`cell`): [`NotebookCellExecution`](codearts_plugin_.NotebookCellExecution.md)

Create a cell execution task.

_Note_ that there can only be one execution per cell at a time and that an error is thrown if
a cell execution is created while another is still active.

This should be used in response to the [execution handler](codearts_plugin_.NotebookController.md#executehandler)
being called or when cell execution has been started else, e.g when a cell was already
executing or when cell execution was triggered from another source.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `cell` | [`NotebookCell`](codearts_plugin_.NotebookCell.md) | The notebook cell for which to create the execution. |

#### Returns

[`NotebookCellExecution`](codearts_plugin_.NotebookCellExecution.md)

A notebook cell execution.

#### Defined in

[index.d.ts:14448](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L14448)

___

### dispose

▸ **dispose**(): `void`

Dispose and free associated resources.

#### Returns

`void`

#### Defined in

[index.d.ts:14494](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L14494)

___

### updateNotebookAffinity

▸ **updateNotebookAffinity**(`notebook`, `affinity`): `void`

A controller can set affinities for specific notebook documents. This allows a controller
to be presented more prominent for some notebooks.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `notebook` | [`NotebookDocument`](codearts_plugin_.NotebookDocument.md) | The notebook for which a priority is set. |
| `affinity` | [`NotebookControllerAffinity`](../enums/codearts_plugin_.NotebookControllerAffinity.md) | A controller affinity |

#### Returns

`void`

#### Defined in

[index.d.ts:14489](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L14489)
