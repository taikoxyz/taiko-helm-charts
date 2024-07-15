# taiko-client

![Version: 0.1.1](https://img.shields.io/badge/Version-0.1.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square)

A Helm chart for Kubernetes

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| d1onys1us |  |  |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| clientArgs.common[0] | string | `"--l1.ws={{ tpl .Values.global.endpoints.l1Ws . }}"` |  |
| clientArgs.common[1] | string | `"--taikoL1={{ (index .Values .Values.global.network).l1ContractAddresses.taikoL1 }}"` |  |
| clientArgs.common[2] | string | `"--taikoL2={{ (index .Values .Values.global.network).l2ContractAddresses.taikoL2 }}"` |  |
| clientArgs.driver[0] | string | `"driver"` |  |
| clientArgs.driver[1] | string | `"--p2p.sync"` |  |
| clientArgs.driver[2] | string | `"--p2p.checkPointSyncUrl={{ (index .Values .Values.global.network).driver.checkpointUrl }}"` |  |
| clientArgs.driver[3] | string | `"--l1.beacon={{ tpl .Values.global.endpoints.l1Beacon . }}"` |  |
| clientArgs.driver[4] | string | `"--l2.ws={{ tpl .Values.global.endpoints.l2Ws . }}"` |  |
| clientArgs.driver[5] | string | `"--l2.auth={{ tpl .Values.global.endpoints.l2Auth . }}"` |  |
| clientArgs.driver[6] | string | `"--jwtSecret=/jwtsecret/default"` |  |
| clientArgs.proposer[0] | string | `"proposer"` |  |
| clientArgs.proposer[1] | string | `"--l2.http={{ tpl .Values.global.endpoints.l2Http . }}"` |  |
| clientArgs.proposer[2] | string | `"--l2.auth={{ tpl .Values.global.endpoints.l2Auth . }}"` |  |
| clientArgs.proposer[3] | string | `"--taikoToken={{ (index .Values .Values.global.network).l1ContractAddresses.taikoToken }}"` |  |
| clientArgs.proposer[4] | string | `"--l1.proposerPrivKey=$(PROPOSER_PRIVATE_KEY)"` |  |
| clientArgs.proposer[5] | string | `"--l2.suggestedFeeRecipient={{ (index .Values .Values.global.network).proposer.suggestedFeeRecipient }}"` |  |
| clientArgs.proposer[6] | string | `"--proverEndpoints={{ (index .Values .Values.global.network).proposer.proverEndpoints }}"` |  |
| clientArgs.proposer[7] | string | `"--tierFee.optimistic={{ (index .Values .Values.global.network).proposer.blockProposalFeeGwei }}"` |  |
| clientArgs.proposer[8] | string | `"--tierFee.sgx={{ (index .Values .Values.global.network).proposer.blockProposalFeeGwei }}"` |  |
| clientArgs.proposer[9] | string | `"--jwtSecret=/jwtsecret/default"` |  |
| clientArgs.prover[0] | string | `"prover"` |  |
| clientArgs.prover[1] | string | `"--l1.http={{ tpl .Values.global.endpoints.l1Http . }}"` |  |
| clientArgs.prover[2] | string | `"--l2.ws={{ tpl .Values.global.endpoints.l2Ws . }}"` |  |
| clientArgs.prover[3] | string | `"--l2.http={{ tpl .Values.global.endpoints.l2Http . }}"` |  |
| clientArgs.prover[4] | string | `"--l1.proverPrivKey=$(PROVER_PRIVATE_KEY)"` |  |
| clientArgs.prover[5] | string | `"--prover.capacity={{ (index .Values .Values.global.network).prover.capacity }}"` |  |
| clientArgs.prover[6] | string | `"--taikoToken={{ (index .Values .Values.global.network).l1ContractAddresses.taikoToken }}"` |  |
| clientArgs.prover[7] | string | `"--raiko.host={{ (index .Values .Values.global.network).prover.raikoHost }}"` |  |
| clientArgs.prover[8] | string | `"--tx.gasLimit={{ (index .Values .Values.global.network).prover.txGasLimit }}"` |  |
| clientArgs.prover[9] | string | `"--tx.minBaseFee={{ (index .Values .Values.global.network).prover.txMinBaseFee }}"` |  |
| global.endpoints.l1Beacon | string | `"http://{{ .Release.Name }}-beacon:5052"` |  |
| global.endpoints.l1Http | string | `"http://{{ .Release.Name }}-execution:8545"` |  |
| global.endpoints.l1Ws | string | `"ws://{{ .Release.Name }}-execution:8546"` |  |
| global.endpoints.l2Auth | string | `"http://{{ .Release.Name }}-taiko-geth:8551"` |  |
| global.endpoints.l2Http | string | `"http://{{ .Release.Name }}-taiko-geth:8545"` |  |
| global.endpoints.l2Ws | string | `"ws://{{ .Release.Name }}-taiko-geth:8546"` |  |
| global.mode | string | `"driver"` |  |
| global.network | string | `"hekla"` |  |
| global.replicaCount | int | `1` |  |
| global.resources.limits.cpu | string | `"1000m"` |  |
| global.resources.limits.memory | string | `"500Mi"` |  |
| global.resources.requests.cpu | string | `"1000m"` |  |
| global.resources.requests.memory | string | `"500Mi"` |  |
| global.secret.jwt | string | `"ecb22bc24e7d4061f7ed690ccd5846d7d73f5d2b9733267e12f56790398d908a"` |  |
| hekla.driver.checkpointUrl | string | `"https://rpc.hekla.taiko.xyz"` |  |
| hekla.image.pullPolicy | string | `"IfNotPresent"` |  |
| hekla.image.repository | string | `"us-docker.pkg.dev/evmchain/hekla/taiko-client"` |  |
| hekla.image.tag | string | `"sha-f5b09d4"` |  |
| hekla.l1ContractAddresses.assignmentHook | string | `"0x9e640a6aadf4f664CF467B795c31332f44AcBe6c"` |  |
| hekla.l1ContractAddresses.guardianProverMajority | string | `"0x92F195a8702da2104aE8E3E10779176E7C35d6BC"` |  |
| hekla.l1ContractAddresses.guardianProverMinority | string | `"0x31d4d27da5c299d4b6CE19c869B8891C0002795d"` |  |
| hekla.l1ContractAddresses.taikoL1 | string | `"0x79C9109b764609df928d16fC4a91e9081F7e87DB"` |  |
| hekla.l1ContractAddresses.taikoToken | string | `"0x6490E12d480549D333499236fF2Ba6676C296011"` |  |
| hekla.l2ContractAddresses.taikoL2 | string | `"0x1670090000000000000000000000000000010001"` |  |
| mainnet.driver.checkpointUrl | string | `"https://rpc.mainnet.taiko.xyz"` |  |
| mainnet.image.pullPolicy | string | `"IfNotPresent"` |  |
| mainnet.image.repository | string | `"us-docker.pkg.dev/evmchain/images/taiko-client"` |  |
| mainnet.image.tag | string | `"taiko-client-v0.26.0"` |  |
| mainnet.l1ContractAddresses.assignmentHook | string | `"0x537a2f0D3a5879b41BCb5A2afE2EA5c4961796F6"` |  |
| mainnet.l1ContractAddresses.guardianProverMajority | string | `"0xE3D777143Ea25A6E031d1e921F396750885f43aC"` |  |
| mainnet.l1ContractAddresses.guardianProverMinority | string | `"0x579A8d63a2Db646284CBFE31FE5082c9989E985c"` |  |
| mainnet.l1ContractAddresses.taikoL1 | string | `"0x06a9Ab27c7e2255df1815E6CC0168d7755Feb19a"` |  |
| mainnet.l1ContractAddresses.taikoToken | string | `"0x10dea67478c5F8C5E2D90e5E9B26dBe60c54d800"` |  |
| mainnet.l2ContractAddresses.taikoL2 | string | `"0x1670000000000000000000000000000000010001"` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)
