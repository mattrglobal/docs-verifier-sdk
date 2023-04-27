Mattr Verifier SDK React Native / [Exports](modules.md)

# verifier-sdk-react-native

# Table of Contents

- [Features](#features)
- [Getting started](#getting-started)
- [Usage](#usage)
  - [Verifier](#verifier)
  - [Error handling](#error-handling)

# Features

- Verify credentials
- Refresh cached revocation lists and trusted issuers
- Get the expiry date of the most-soon-to-expire item in the cache

# Getting started

## How to get access to MATTR Pi Verifier SDK

To gain access to the MATTR Pi Verifier SDK, please follow these steps:

1. Request or download the ["Terms of Agreement"](https://learn.mattr.global/docs/terms/verifier-sdk-licence-agreement).
2. Read the "Terms of Agreement", sign it, and return it to us.
3. Create an account at [NPMJS - Node package manager for JavaScript](https://www.npmjs.com).
4. Ensure multi-factor authentication (MFA) is configured on NPMJS Account.
5. Create a personal access token
   [Create a personal access token](https://docs.npmjs.com/creating-and-viewing-access-tokens).
6. Supply the NPMJS (Node package manager for JavaScript) account name back to MATTR.
7. MATTR will process the request and provision access to the MATTR Pi Verifier SDK if approved.

> Please reach out to us in case you need any assistance [Get in touch](https://mattr.global/contact).

## Install dependencies

Add this SDK as a dependency to the react native app:

```
yarn add @mattrglobal/verifier-sdk-react-native
```

The SDK relies on a set of peer dependencies that contain native libraries and iOS pods. With React Native >=0.60 these
dependencies will be autolinked.

Install the peer dependencies:

```
yarn add @mattrglobal/react-native-cryptography@^1.0.0 react-native-securerandom@^1.0.0 react-native-fs@^2.20.0 react-native-secure-key-store@^2.0.10 react-native-get-random-values@^1.8.0 react-native-mmkv@^2.5.1
```

# Usage

## Verifier

Create a verifier:

```typescript
import { init } from "@mattrglobal/verifier-sdk-react-native";

const initOptions: InitOptions = {
  issuerCacheTtl: 60000,
  revocationListCacheTtl: 60000,
  trustedIssuers: ["did:web:example.com"], // defaults to trust any issuer
  assertExpiry: true, // defaults to true
  assertNotBefore: true, // defaults to true
  checkRevocation: true, // defaults to true
};

const verifier = await init(initOptions);
```

Verify a credential:

```typescript
const verifyResult = await verifier.verify({ payload });

if (verifyResult.isErr()) {
  // Handle error from verifyResult.error
  return;
}

const { verified } = verifyResult.value;
```

Close the verifier:

```typescript
console.log(verifier.isOpen()); // true

const closeVerifierResult = await verifier.close();

if (closeVerifierResult.isErr()) {
  // Handle error from closeVerifierResult.error
  return;
}

console.log(verifier.isOpen()); // false
```

Destroy the verifier:

```typescript
await verifier.destroy();

console.log(verifier.isOpen()); // false
```

## Cache

Get the cache expiry date:

```typescript
const expiry = await verifier.getCacheExpiry();
```

Refresh the items in the cache:

```typescript
const refreshCacheResult = await verifierSdk.refreshCache();

if (refreshCacheResult.isErr()) {
  /**
   * The error contains the cache expiry date
   * This date may have changed after partial refresh
   */
  console.log(refreshCacheResult.error.expiryDate);
  // Handle error from refreshCacheResult.error
  return;
}

// New expiry date of the cache
const { expiryDate } = refreshCacheResult.value;
```

## Error handling

Functions that are expected to have an error path return a
[Neverthrow Result](https://www.npmjs.com/package/neverthrow#synchronous-api-result) type that represents either success
(`Ok`) or failure (`Err`).

Although this pattern is more verbose, it encourages the handling of possible errors and reserves throwing exceptions
for truly exceptional situations.

```typescript
import { open } from "@mattrglobal/verifier-sdk-react-native";

const openVerifierResult = await open();

if (openVerifierResult.isErr()) {
  // Handle error from openVerifierResult.error
  return;
}

const verifier = openVerifierResult.value;
```

### unwrap

A utility function is provided for convenience if you decide not to handle your errors as results. This function will
simply throw an error if the function passed in returns a `Result` where `Resut.isErr()` is true.

```typescript
import { unwrap } from "@mattrglobal/verifier-sdk-react-native";

try {
  const verifier = unwrap(await open());
} catch (error) {
  // Handle thrown error
}
```

## Licensing

See [here](https://learn.mattr.global/docs/terms/verifier-sdk-licence-agreement) for licence information
