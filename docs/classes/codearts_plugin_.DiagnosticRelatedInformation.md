[@codearts/plugin](../README.md) / ["@codearts/plugin"](../modules/_codearts_plugin_.md) / DiagnosticRelatedInformation

# Class: DiagnosticRelatedInformation

["@codearts/plugin"](../modules/_codearts_plugin_.md).DiagnosticRelatedInformation

Represents a related message and source code location for a diagnostic. This should be
used to point to code locations that cause or related to a diagnostics, e.g. when duplicating
a symbol in a scope.

## Table of contents

### Constructors

- [constructor](codearts_plugin_.DiagnosticRelatedInformation.md#constructor)

### Properties

- [location](codearts_plugin_.DiagnosticRelatedInformation.md#location)
- [message](codearts_plugin_.DiagnosticRelatedInformation.md#message)

## Constructors

### constructor

• **new DiagnosticRelatedInformation**(`location`, `message`)

Creates a new related diagnostic information object.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `location` | [`Location`](codearts_plugin_.Location.md) | The location. |
| `message` | `string` | The message. |

#### Defined in

[index.d.ts:5957](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L5957)

## Properties

### location

• **location**: [`Location`](codearts_plugin_.Location.md)

The location of this related diagnostic information.

#### Defined in

[index.d.ts:5944](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L5944)

___

### message

• **message**: `string`

The message of this related diagnostic information.

#### Defined in

[index.d.ts:5949](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L5949)
