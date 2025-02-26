[@codearts/plugin](../README.md) / ["@codearts/plugin"](../modules/_codearts_plugin_.md) / TerminalOptions

# Interface: TerminalOptions

["@codearts/plugin"](../modules/_codearts_plugin_.md).TerminalOptions

Value-object describing what options a terminal should use.

## Table of contents

### Properties

- [color](codearts_plugin_.TerminalOptions.md#color)
- [cwd](codearts_plugin_.TerminalOptions.md#cwd)
- [env](codearts_plugin_.TerminalOptions.md#env)
- [hideFromUser](codearts_plugin_.TerminalOptions.md#hidefromuser)
- [iconPath](codearts_plugin_.TerminalOptions.md#iconpath)
- [isTransient](codearts_plugin_.TerminalOptions.md#istransient)
- [location](codearts_plugin_.TerminalOptions.md#location)
- [message](codearts_plugin_.TerminalOptions.md#message)
- [name](codearts_plugin_.TerminalOptions.md#name)
- [shellArgs](codearts_plugin_.TerminalOptions.md#shellargs)
- [shellPath](codearts_plugin_.TerminalOptions.md#shellpath)
- [strictEnv](codearts_plugin_.TerminalOptions.md#strictenv)

## Properties

### color

• `Optional` **color**: [`ThemeColor`](../classes/codearts_plugin_.ThemeColor.md)

The icon [ThemeColor](../classes/codearts_plugin_.ThemeColor.md) for the terminal.
The `terminal.ansi*` theme keys are
recommended for the best contrast and consistency across themes.

#### Defined in

[index.d.ts:11151](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L11151)

___

### cwd

• `Optional` **cwd**: `string` \| [`Uri`](../classes/codearts_plugin_.Uri.md)

A path or Uri for the current working directory to be used for the terminal.

#### Defined in

[index.d.ts:11109](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L11109)

___

### env

• `Optional` **env**: `Object`

Object with environment variables that will be added to the editor process.

#### Index signature

▪ [key: `string`]: `string` \| ``null`` \| `undefined`

#### Defined in

[index.d.ts:11114](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L11114)

___

### hideFromUser

• `Optional` **hideFromUser**: `boolean`

When enabled the terminal will run the process as normal but not be surfaced to the user
until `Terminal.show` is called. The typical usage for this is when you need to run
something that may need interactivity but only want to tell the user about it when
interaction is needed. Note that the terminals will still be exposed to all extensions
as normal.

#### Defined in

[index.d.ts:11132](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L11132)

___

### iconPath

• `Optional` **iconPath**: [`Uri`](../classes/codearts_plugin_.Uri.md) \| [`ThemeIcon`](../classes/codearts_plugin_.ThemeIcon.md) \| { `dark`: [`Uri`](../classes/codearts_plugin_.Uri.md) ; `light`: [`Uri`](../classes/codearts_plugin_.Uri.md)  }

The icon path or [ThemeIcon](../classes/codearts_plugin_.ThemeIcon.md) for the terminal.

#### Defined in

[index.d.ts:11144](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L11144)

___

### isTransient

• `Optional` **isTransient**: `boolean`

Opt-out of the default terminal persistence on restart and reload.
This will only take effect when `terminal.integrated.enablePersistentSessions` is enabled.

#### Defined in

[index.d.ts:11162](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L11162)

___

### location

• `Optional` **location**: [`TerminalEditorLocationOptions`](codearts_plugin_.TerminalEditorLocationOptions.md) \| [`TerminalSplitLocationOptions`](codearts_plugin_.TerminalSplitLocationOptions.md) \| [`TerminalLocation`](../enums/codearts_plugin_.TerminalLocation.md)

The [TerminalLocation](../enums/codearts_plugin_.TerminalLocation.md) or [TerminalEditorLocationOptions](codearts_plugin_.TerminalEditorLocationOptions.md) or [TerminalSplitLocationOptions](codearts_plugin_.TerminalSplitLocationOptions.md) for the terminal.

#### Defined in

[index.d.ts:11156](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L11156)

___

### message

• `Optional` **message**: `string`

A message to write to the terminal on first launch, note that this is not sent to the
process but, rather written directly to the terminal. This supports escape sequences such
a setting text style.

#### Defined in

[index.d.ts:11139](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L11139)

___

### name

• `Optional` **name**: `string`

A human-readable string which will be used to represent the terminal in the UI.

#### Defined in

[index.d.ts:11093](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L11093)

___

### shellArgs

• `Optional` **shellArgs**: `string` \| `string`[]

Args for the custom shell executable. A string can be used on Windows only which allows
specifying shell args in [command-line format](https://msdn.microsoft.com/en-au/08dfcab2-eb6e-49a4-80eb-87d4076c98c6).

#### Defined in

[index.d.ts:11104](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L11104)

___

### shellPath

• `Optional` **shellPath**: `string`

A path to a custom shell executable to be used in the terminal.

#### Defined in

[index.d.ts:11098](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L11098)

___

### strictEnv

• `Optional` **strictEnv**: `boolean`

Whether the terminal process environment should be exactly as provided in
`TerminalOptions.env`. When this is false (default), the environment will be based on the
window's environment and also apply configured platform settings like
`terminal.integrated.windows.env` on top. When this is true, the complete environment
must be provided as nothing will be inherited from the process or any configuration.

#### Defined in

[index.d.ts:11123](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L11123)
