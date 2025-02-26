[@codearts/plugin](../README.md) / ["@codearts/plugin"](../modules/_codearts_plugin_.md) / Comment

# Interface: Comment

["@codearts/plugin"](../modules/_codearts_plugin_.md).Comment

A comment is displayed within the editor or the Comments Panel, depending on how it is provided.

## Table of contents

### Properties

- [author](codearts_plugin_.Comment.md#author)
- [body](codearts_plugin_.Comment.md#body)
- [contextValue](codearts_plugin_.Comment.md#contextvalue)
- [label](codearts_plugin_.Comment.md#label)
- [mode](codearts_plugin_.Comment.md#mode)
- [reactions](codearts_plugin_.Comment.md#reactions)
- [timestamp](codearts_plugin_.Comment.md#timestamp)

## Properties

### author

• **author**: [`CommentAuthorInformation`](codearts_plugin_.CommentAuthorInformation.md)

The [author information](codearts_plugin_.CommentAuthorInformation.md) of the comment

#### Defined in

[index.d.ts:15852](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L15852)

___

### body

• **body**: `string` \| [`MarkdownString`](../classes/codearts_plugin_.MarkdownString.md)

The human-readable comment body

#### Defined in

[index.d.ts:15842](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L15842)

___

### contextValue

• `Optional` **contextValue**: `string`

Context value of the comment. This can be used to contribute comment specific actions.
For example, a comment is given a context value as `editable`. When contributing actions to `comments/comment/title`
using `menus` extension point, you can specify context value for key `comment` in `when` expression like `comment == editable`.
```json
	"contributes": {
		"menus": {
			"comments/comment/title": [
				{
					"command": "extension.deleteComment",
					"when": "comment == editable"
				}
			]
		}
	}
```
This will show action `extension.deleteComment` only for comments with `contextValue` is `editable`.

#### Defined in

[index.d.ts:15872](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L15872)

___

### label

• `Optional` **label**: `string`

Optional label describing the [Comment](codearts_plugin_.Comment.md)
Label will be rendered next to authorName if exists.

#### Defined in

[index.d.ts:15883](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L15883)

___

### mode

• **mode**: [`CommentMode`](../enums/codearts_plugin_.CommentMode.md)

[Comment mode](../enums/codearts_plugin_.CommentMode.md) of the comment

#### Defined in

[index.d.ts:15847](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L15847)

___

### reactions

• `Optional` **reactions**: [`CommentReaction`](codearts_plugin_.CommentReaction.md)[]

Optional reactions of the [Comment](codearts_plugin_.Comment.md)

#### Defined in

[index.d.ts:15877](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L15877)

___

### timestamp

• `Optional` **timestamp**: `Date`

Optional timestamp that will be displayed in comments.
The date will be formatted according to the user's locale and settings.

#### Defined in

[index.d.ts:15889](https://github.com/xyz-fish/cloudide-plugin-api/blob/9927cd6/index.d.ts#L15889)
