Repo for organizing materials related to security.

# Table of Contents
 1. [Defi incident reports](#defi-incident-reports)
 1. [Security materials](#security-materials)
 1. [Checklists](#checklists)
 1. [Tools](#tools)
 1. [External audits](#external-audits)

# Defi incident reports
  - [Reports](/incidents)

# Security materials
 - [Solidity security considerations](https://docs.soliditylang.org/en/v0.7.5/security-considerations.html)
 - [Trail of Bits curated list](https://github.com/crytic/awesome-ethereum-security)
 - [Caveats about ecrecover](https://docs.kaleido.io/faqs/why-ecrecover-fails/)
 - [2020 paradigm CTF writeup](https://github.com/DanielVF/2020_paradigm_ctf_writeup)

# Checklists
 - [ERC20 token integration checklist](https://github.com/crytic/building-secure-contracts/blob/master/development-guidelines/token_integration.md)
 - [OUSD PR checklist](https://github.com/OriginProtocol/origin-dollar/blob/master/pull_request_template.md)
 - [OUSD deployment checklist](https://docs.google.com/spreadsheets/d/1phyzOJMmTBPIqTTa0v7HY6XJkjRmbrcdULRZPo_JEoY/edit?usp=sharing)
 - Origin Protocol New employee checklist: search for "New employee" on google drive.

# Tools

## Slither
[Slither](https://github.com/crytic/slither) is a static analysis tool for Solidity contracts.

### How to run it
```
pip3 install slither-analyzer
cd origin-dollar/contracts
yarn install
yarn run slither
```

### Updating Slither DB
```
yarn run slither --triage
```
Running this command will open an interactive console where you can select the errors/warning that you want to be excluded. Once done, commit and push the updated Slither DB file. Note: make sure you are running the latest version of slither on your local.

## Echidna
[Echidna](https://github.com/crytic/echidna) is a test fuzzer for Solidity contracts.

The Echnida tests for the OUSD contracts are under [contracts/contract/crytic](https://github.com/OriginProtocol/origin-dollar/tree/master/contracts/contracts/crytic).

### How to run it
On MacOS and Linux, download the latest pre-compiled binaries from [here](https://github.com/crytic/echidna/releases).
Untar the files in a directory and add the path where the echidna-test binary was extracted to your shell's PATH.

To run the tests:
```
cd origin-dollar/contracts
yarn run echidna
```

Note that the test take about ~30min to run.

# External audits
  - OGN
    - [Sept 2019 - Trail of Bits](https://github.com/OriginProtocol/security/blob/master/audits/Trail%20of%20Bits%20-%20Origin%20Marketplace%20and%20OGN%20Token%20-%20Nov%202018.pdf)
  - OUSD
    - [Nov 2020 - Trail of Bits](https://github.com/OriginProtocol/security/blob/master/audits/Trail%20of%20Bits%20-%20Origin%20Dollar%20-%20Dec%202020.pdf)
    - [Dec 2020 Solidified](https://github.com/OriginProtocol/security/blob/master/audits/Solidified%20-%20Origin%20Dollar%20-%20Dec%202020.pdf)
  - Single Asset Staking
    - [Dec 2020 - Solidified](https://github.com/OriginProtocol/security/blob/master/audits/Solidified%20-%20OGN%20Staking%20-%20Dec%202020.pdf)

