<p align="center"><h1 align="center">
 ⚠️ IMPORTANT NOTICE ⚠️
  </h1>
</p>
  
<p align="center">
    This project gratuated into the OWASP family and is now managed at <a href="https://github.com/OWASP/cwe-sdk-javascript">OWASP/cwe-sdk-javascript</a>
</p>

---

<p align="center"><h1 align="center">
  cwe-sdk
</h1>

<p align="center">
  A Common Weakness Enumeration (CWE) Node.js SDK compliant with MITRE / CAPEC
</p>

<p align="center">
  <a href="https://www.npmjs.org/package/cwe-sdk"><img src="https://badgen.net/npm/v/cwe-sdk" alt="npm version"/></a>
  <a href="https://www.npmjs.org/package/cwe-sdk"><img src="https://badgen.net/npm/license/cwe-sdk" alt="license"/></a>
  <a href="https://www.npmjs.org/package/cwe-sdk"><img src="https://badgen.net/npm/dt/cwe-sdk" alt="downloads"/></a>
  <a href="https://github.com/lirantal/cwe-sdk/actions?workflow=CI"><img src="https://github.com/lirantal/cwe-sdk/workflows/CI/badge.svg" alt="build"/></a>
  <a href="https://codecov.io/gh/lirantal/cwe-sdk"><img src="https://badgen.net/codecov/c/github/lirantal/cwe-sdk" alt="codecov"/></a>
  <a href="https://snyk.io/test/github/lirantal/cwe-sdk"><img src="https://snyk.io/test/github/lirantal/cwe-sdk/badge.svg" alt="Known Vulnerabilities"/></a>
  <a href="./SECURITY.md"><img src="https://img.shields.io/badge/Security-Responsible%20Disclosure-yellow.svg" alt="Responsible Disclosure Policy" /></a>
</p>

# Install

```bash
yarn add cwe-sdk
```

# Usage

Require the CweManager class and use its methods

```js
const { CweManager } = require('cwe-sdk')
```

# Example

```js
const { CweManager } = require('cwe-sdk')

const cweManager = new CweManager()
const result = cweManager.isChildOf({ weaknessId: '117', parentId: '116' })

console.log(result) // true
```

# Build

This CWE SDK has a build process that prepares the JSON data by downloading the latest version of the CWE archive (e.g. https://cwe.mitre.org/data/xml/cwec_v4.1.xml.zip) and then crunches it to create the following data snapshots:

1. A mirror JSON object, available at `./raw/cwe-archive.json`
2. A JSON dictionary to easily access CWEs by their ID, available at `./raw/cwe-dictionary.json`
3. A JSON array for the relationship hierarchy between CWEs, available at `./raw/cwe-hierarchy.json`

This work is made possible thanks to scripts in `./build/`

# Contributing

Please consult [CONTRIBUTING](./CONTRIBUTING.md) for guidelines on contributing to this project.

# Author

**cwe-sdk** © [Liran Tal](https://github.com/lirantal), Released under the [Apache-2.0](./LICENSE) License.
