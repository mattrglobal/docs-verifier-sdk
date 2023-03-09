[Mattr Verifier SDK React Native](README.md) / Exports

# Mattr Verifier SDK React Native

## Table of contents

### Namespaces

- [Result](modules/Result.md)

### Enumerations

- [CommonVerifyErrorType](enums/CommonVerifyErrorType.md)
- [IssuerResolverErrorType](enums/IssuerResolverErrorType.md)
- [RefreshCacheErrorType](enums/RefreshCacheErrorType.md)
- [RevocationListResolverErrorType](enums/RevocationListResolverErrorType.md)

### Type Aliases

- [BaseSDKError](modules.md#basesdkerror)
- [CloseVerifierError](modules.md#closeverifiererror)
- [CommonVerifyError](modules.md#commonverifyerror)
- [CompactSemanticCredentialPayload](modules.md#compactsemanticcredentialpayload)
- [CompactSemanticCredentialVcPayload](modules.md#compactsemanticcredentialvcpayload)
- [CompactSemanticVerifyError](modules.md#compactsemanticverifyerror)
- [CompactSemanticVerifyErrorType](modules.md#compactsemanticverifyerrortype)
- [CompactSemanticVerifyFailureReasonType](modules.md#compactsemanticverifyfailurereasontype)
- [CompactSemanticVerifyResult](modules.md#compactsemanticverifyresult)
- [CompactVerifyError](modules.md#compactverifyerror)
- [CompactVerifyErrorType](modules.md#compactverifyerrortype)
- [CompactVerifyFailureReasonType](modules.md#compactverifyfailurereasontype)
- [CompactVerifyResult](modules.md#compactverifyresult)
- [DestroyVerifierError](modules.md#destroyverifiererror)
- [EncryptionKeyNotFoundError](modules.md#encryptionkeynotfounderror)
- [GenericPayload](modules.md#genericpayload)
- [InitOptions](modules.md#initoptions)
- [IssuerResolverError](modules.md#issuerresolvererror)
- [MalformedEncryptionKeyError](modules.md#malformedencryptionkeyerror)
- [PropertiesMappingConfig](modules.md#propertiesmappingconfig)
- [RefreshCacheError](modules.md#refreshcacheerror)
- [RefreshCacheSuccess](modules.md#refreshcachesuccess)
- [ResolverError](modules.md#resolvererror)
- [Result](modules.md#result)
- [Verifier](modules.md#verifier)
- [VerifierBase](modules.md#verifierbase)
- [VerifierExtension](modules.md#verifierextension)
- [VerifyCredentialError](modules.md#verifycredentialerror)
- [VerifyCredentialOptions](modules.md#verifycredentialoptions)
- [VerifyCredentialResult](modules.md#verifycredentialresult)

### Functions

- [init](modules.md#init)
- [unwrap](modules.md#unwrap)

## Type Aliases

### BaseSDKError

Ƭ **BaseSDKError**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `cause?` | `Error` \| `unknown` |
| `message` | `string` |
| `type` | `string` |

___

### CloseVerifierError

Ƭ **CloseVerifierError**: [`BaseSDKError`](modules.md#basesdkerror) & { `type`: ``"CloseVerifierError"``  }

___

### CommonVerifyError

Ƭ **CommonVerifyError**: [`BaseSDKError`](modules.md#basesdkerror) & { `type`: [`CommonVerifyErrorType`](enums/CommonVerifyErrorType.md)  }

___

### CompactSemanticCredentialPayload

Ƭ **CompactSemanticCredentialPayload**: `ImplementsZodType`<`TypeOf`<typeof `CompactSemanticCredentialPayloadValidator`\>, { `aud?`: `string` ; `exp?`: `number` ; `iat?`: `number` ; `iss`: `string` ; `jti`: `string` ; `nbf`: `number` ; `status?`: `CwtStatus` ; `sub?`: `string` ; `vc`: [`CompactSemanticCredentialVcPayload`](modules.md#compactsemanticcredentialvcpayload)  }\>

___

### CompactSemanticCredentialVcPayload

Ƭ **CompactSemanticCredentialVcPayload**: `ImplementsZodType`<`TypeOf`<typeof `CompactSemanticCredentialVcPayloadValidator`\>, { `@context`: `JsonLdContext` ; `credentialSubject`: `Record`<`string`, `string` \| `number` \| `boolean`\> ; `type`: `string`[]  }\>

___

### CompactSemanticVerifyError

Ƭ **CompactSemanticVerifyError**: `BaseError` & { `type`: [`CompactSemanticVerifyErrorType`](modules.md#compactsemanticverifyerrortype)  }

___

### CompactSemanticVerifyErrorType

Ƭ **CompactSemanticVerifyErrorType**: `VerifyErrorType`

___

### CompactSemanticVerifyFailureReasonType

Ƭ **CompactSemanticVerifyFailureReasonType**: `VerifyFailureReasonType`

___

### CompactSemanticVerifyResult

Ƭ **CompactSemanticVerifyResult**: `Omit`<`VerifyResult`, ``"payload"`` \| ``"reason"``\> & { `header?`: `CwtHeader` ; `payload?`: [`CompactSemanticCredentialPayload`](modules.md#compactsemanticcredentialpayload) ; `reason`: { `details?`: `VerifyFailedResultReasonDetails` ; `message`: `string` ; `type`: [`CompactSemanticVerifyFailureReasonType`](modules.md#compactsemanticverifyfailurereasontype)  } ; `verified`: ``false``  } \| `Omit`<`VerifyResult`, ``"payload"``\> & { `header`: `CwtHeader` ; `payload`: [`CompactSemanticCredentialPayload`](modules.md#compactsemanticcredentialpayload) ; `verified`: ``true``  }

___

### CompactVerifyError

Ƭ **CompactVerifyError**: `BaseError` & { `type`: [`CompactVerifyErrorType`](modules.md#compactverifyerrortype)  }

___

### CompactVerifyErrorType

Ƭ **CompactVerifyErrorType**: `VerifyErrorType`

___

### CompactVerifyFailureReasonType

Ƭ **CompactVerifyFailureReasonType**: `VerifyFailureReasonType`

___

### CompactVerifyResult

Ƭ **CompactVerifyResult**: `Omit`<`VerifyResult`, ``"payload"`` \| ``"reason"``\> & { `header?`: `CwtHeader` ; `payload?`: `CompactCredentialPayload` ; `reason`: { `details?`: `VerifyFailedResultReasonDetails` ; `message`: `string` ; `type`: [`CompactVerifyFailureReasonType`](modules.md#compactverifyfailurereasontype)  } ; `verified`: ``false``  } \| `Omit`<`VerifyResult`, ``"payload"``\> & { `header`: `CwtHeader` ; `payload`: `CompactCredentialPayload` ; `verified`: ``true``  }

___

### DestroyVerifierError

Ƭ **DestroyVerifierError**: [`BaseSDKError`](modules.md#basesdkerror) & { `type`: ``"DestroyVerifierError"``  }

___

### EncryptionKeyNotFoundError

Ƭ **EncryptionKeyNotFoundError**: [`BaseSDKError`](modules.md#basesdkerror) & { `type`: ``"EncryptionKeyNotFoundError"``  }

___

### GenericPayload

Ƭ **GenericPayload**: `Record`<`string`, `unknown`\>

___

### InitOptions

Ƭ **InitOptions**: `Object`

Options to configure when initialising a verifier

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `assertExpiry?` | `boolean` | Set whether to check the credential's expiry date during verification. If `true`, verification will fail if the credential is expired.  **`remarks`** Default to `true`. |
| `assertNotBefore?` | `boolean` | Set whether to check the credential's not before date during verification. If `true`, verification will fail if the credential is not active i.e. current date is before the not before date.  **`remarks`** Not before date is the date a credential is activated and becomes active. Default to `true`. |
| `checkRevocation?` | `boolean` | Set whether to check the credential's revocation status during verification. If `true`, verification will fail if the credential is revoked.  **`remarks`** Revocation status represents the validity of the credential as determined by the issuer. Default to `true`. |
| `issuerCacheTtl` | `number` | Duration that an issuer is kept in the cache after it is added or re-added |
| `revocationListCacheTtl` | `number` | Duration that a revocation list is kept in the cache after it is added or re-added |
| `trustedIssuers?` | `ReadonlyArray`<`string`\> | List of issuers we want to trust the credentials of  **`remarks`** Issuers defined here are cached up front. If this is empty, all issuers will be considered trusted. |

___

### IssuerResolverError

Ƭ **IssuerResolverError**: `BaseError` & { `type`: [`IssuerResolverErrorType`](enums/IssuerResolverErrorType.md)  }

___

### MalformedEncryptionKeyError

Ƭ **MalformedEncryptionKeyError**: [`BaseSDKError`](modules.md#basesdkerror) & { `type`: ``"MalformedEncryptionKeyError"``  }

___

### PropertiesMappingConfig

Ƭ **PropertiesMappingConfig**: `Record`<`string`, (`value`: `unknown`) => [`string`, `unknown`]\>

A record of transformation functions that maps an existing key and value to a new key and value
The existing value is passed as the parameter to the transformation function

**`example`**
```
 // Defines a single transformation to map an object of type { foo: any } to { bar: "something" }
 const propertyMappingConfig = {
   foo: (_foosValue) => ["bar", "something"],
 };
```

___

### RefreshCacheError

Ƭ **RefreshCacheError**<`E`\>: [`BaseSDKError`](modules.md#basesdkerror) & { `cause?`: readonly [`ResolverError`](modules.md#resolvererror)<`E`\>[] ; `expiryDate`: `Date` \| `undefined` ; `type`: [`RefreshCacheErrorType`](enums/RefreshCacheErrorType.md)  }

#### Type parameters

| Name |
| :------ |
| `E` |

___

### RefreshCacheSuccess

Ƭ **RefreshCacheSuccess**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `expiryDate` | `Date` \| `undefined` |

___

### ResolverError

Ƭ **ResolverError**<`E`\>: `Object`

#### Type parameters

| Name |
| :------ |
| `E` |

#### Type declaration

| Name | Type |
| :------ | :------ |
| `error` | `E` |
| `key` | `string` |

___

### Result

Ƭ **Result**<`T`, `E`\>: `Ok`<`T`, `E`\> \| `Err`<`T`, `E`\>

#### Type parameters

| Name |
| :------ |
| `T` |
| `E` |

___

### Verifier

Ƭ **Verifier**: [`VerifierBase`](modules.md#verifierbase) & [`VerifierExtension`](modules.md#verifierextension)

___

### VerifierBase

Ƭ **VerifierBase**: `Object`

An instance of a verifier

#### Type declaration

| Name | Type |
| :------ | :------ |
| `close` | () => `Promise`<[`Result`](modules.md#result)<`void`, [`CloseVerifierError`](modules.md#closeverifiererror)\>\> |
| `getCacheExpiry` | () => `Promise`<`undefined` \| `Date`\> |
| `isOpen` | () => `boolean` |
| `refreshCache` | () => `Promise`<[`Result`](modules.md#result)<[`RefreshCacheSuccess`](modules.md#refreshcachesuccess), [`RefreshCacheError`](modules.md#refreshcacheerror)<[`IssuerResolverError`](modules.md#issuerresolvererror) \| `RevocationListResolverError`\>\>\> |
| `verify` | (`options`: [`VerifyCredentialOptions`](modules.md#verifycredentialoptions)) => `Promise`<[`Result`](modules.md#result)<[`VerifyCredentialResult`](modules.md#verifycredentialresult), [`VerifyCredentialError`](modules.md#verifycredentialerror)\>\> |

___

### VerifierExtension

Ƭ **VerifierExtension**: `Object`

React Native specific verifier that has been extended with additional functionality

#### Type declaration

| Name | Type |
| :------ | :------ |
| `destroy` | () => `Promise`<[`Result`](modules.md#result)<`void`, [`DestroyVerifierError`](modules.md#destroyverifiererror)\>\> |

___

### VerifyCredentialError

Ƭ **VerifyCredentialError**: [`CommonVerifyError`](modules.md#commonverifyerror) \| [`CompactVerifyError`](modules.md#compactverifyerror) \| [`CompactSemanticVerifyError`](modules.md#compactsemanticverifyerror)

___

### VerifyCredentialOptions

Ƭ **VerifyCredentialOptions**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `payload` | `string` | The credential payload to verify |
| `propertyMappingConfig?` | [`PropertiesMappingConfig`](modules.md#propertiesmappingconfig) | The mapping configuration that lists transformation functions to apply for designated properties of the returned payload |

___

### VerifyCredentialResult

Ƭ **VerifyCredentialResult**: [`CompactVerifyResult`](modules.md#compactverifyresult) \| [`CompactSemanticVerifyResult`](modules.md#compactsemanticverifyresult) & { `transformedPayload?`: [`GenericPayload`](modules.md#genericpayload)  }

## Functions

### init

▸ **init**(`options`): `Promise`<[`Verifier`](modules.md#verifier)\>

Initialise a verifier.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options` | [`InitOptions`](modules.md#initoptions) | [InitOptions](modules.md#initoptions) containing the options for the init function |

#### Returns

`Promise`<[`Verifier`](modules.md#verifier)\>

A [Result](modules.md#result) containing the initialised [Verifier](modules.md#verifier) object

___

### unwrap

▸ **unwrap**<`T`\>(`result`): `T`

A utility function to get the value from a [Result](modules.md#result) or throw if there was an error

**`remarks`**
Allows you to get the value of a result directly or handle an error [Result](modules.md#result) as an exception

#### Type parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `T` | `unknown` | the expected value of an ok result |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `result` | [`Result`](modules.md#result)<`T`, `unknown`\> | The [Result](modules.md#result) to unwrap |

#### Returns

`T`
