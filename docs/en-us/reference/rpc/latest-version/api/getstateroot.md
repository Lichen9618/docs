# getstateroot Method

Gets the state root information of the block.

#### Parameters

key: Block height or block hash

#### Examples

##### Example 1 - Get verified StateRoot

Request text:

```json
{
  "jsonrpc": "2.0",
  "method": "getstateroot",
  "params": [6144040],
  "id": 1
}
```

Response text:

```json
{w
  "jsonrpc": "2.0",
  "id": 1,
  "result": {
    "flag": "Verified",
    "stateroot": {
      "version": 0,
      "index": 6144040,
      "prehash": "0x38867af92d68ffad18cc0784c646ca6b72612910780966f67e34857e9b8a89de",
      "stateroot": "0xcd916f4ba134370a46ef55a55b872117676729e10ff497e5b7f7156fecc7ea22",
      "witness": {
        "invocation": "40dadb67c290045203f8fbb50f6992aa80722bc4c9af46a7cec4d2401ae306f4da5edb998a90ae9366b3b164a91934e04cda0f8b835d477f5de6ea595b7e9ab8f540aed25a66aea3271699efaf6be37db5cc488dae0520dfb51d25e0df158d3ce7992151ca9aab3041e67605d56a9a8b352dd6231d0bab1cfab01a867d9af4b7e3264070ce9293306c1617cfd5fae47ac3c105d5c3a1f1720d91284ae9bd76b9f54bf4142f2556a2a4125e05d054cbc2d39eaa4f420d04e27ad6e00660f3ac334b867d401b2f9dcbf24e80a4f568e4283f243880238f137cf773ef60d1dee1f585932d46d6bffb2173090e4156d4d24b1b88ee2896117ef79d365c560c33f52aae1d6f16402c513d547202a086bce9c1a0561a5c1692ed1f2cd76399b1583e0e70c6743384b9f3a00d4abf75d68c8539f703db10142b9d2c3ca4f26207620559e559216e22",
        "verification": "5521024c7b7fb6c310fccf1ba33b082519d82964ea93868d676662d4a59ad548df0e7d21025bdf3f181f53e9696227843950deb72dcd374ded17c057159513c3d0abe20b6421035e819642a8915a2572f972ddbdbe3042ae6437349295edce9bdc3b8884bbf9a32103b209fd4f53a7170ea4444e0cb0a6bb6a53c2bd016926989cf85f9b0fba17a70c2103b8d9d5771d8f513aa0869b9cc8d50986403b78c6da36890638c3d46a5adce04a2102ca0e27697b9c248f6f16e085fd0061e26f44da85b58ee835c110caa5ec3ba5542102df48f60e8f3e01c48ff40b9b7f1310d7a8b2a193188befe1c2e3df740e89509357ae"
      }
    }
  }
}
```

##### Example 2 - Get unverified StateRoot

Request text:

```json
{
  "jsonrpc": "2.0",
  "method": "getstateroot",
  "params": [2000000],
  "id": 1
}
```

Response text:

```json
{
  "jsonrpc": "2.0",
  "id": 1,
  "result": {
    "flag": "Unverified",
    "stateroot": {
      "version": 0,
      "index": 2000000,
      "prehash": "0xa777b4ec9efb3027c3ad9c011de4bff5a144e4492641e13a3254fb73169b8922",
      "stateroot": "0x5f897f3c1080019987e695edcba2700950a0adb43fb2003e494efeb1f0ce31cc",
      "witness": {}
    }
  }
}
```

Response text:

`flag` represents whether the StateRoot has been verified with two values：

- `Verified`: StateRoot has been confirmed and has multi-party signatures by consensus nodes
- `unverified`: StateRoot is a value calculated locally by the node, and it has not been checked for consistency with the StateRoot confirmed by the consensus node. If the value is `Invalid`, it means that the local calculation result is inconsistent with the consensus calculation and it cannot be trusted.