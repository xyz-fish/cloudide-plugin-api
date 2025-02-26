[@codearts/plugin](../README.md) / ["@codearts/plugin"](../modules/_codearts_plugin_.md) / AuthenticationSessionsChangeEvent

# Interface: AuthenticationSessionsChangeEvent

["@codearts/plugin"](../modules/_codearts_plugin_.md).AuthenticationSessionsChangeEvent

An [Event](codearts_plugin_.Event.md) which fires when an [AuthenticationSession](codearts_plugin_.AuthenticationSession.md) is added, removed, or changed.

## Table of contents

### Properties

- [provider](codearts_plugin_.AuthenticationSessionsChangeEvent.md#provider)

## Properties

### provider

• `Readonly` **provider**: [`AuthenticationProviderInformation`](codearts_plugin_.AuthenticationProviderInformation.md)

The [AuthenticationProvider](codearts_plugin_.AuthenticationProvider.md) that has had its sessions change.

#### Defined in

[index.d.ts:16115](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L16115)
