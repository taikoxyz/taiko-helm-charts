# taiko-client

![Version: 0.1.3](https://img.shields.io/badge/Version-0.1.3-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square)

A Helm chart for Kubernetes

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| d1onys1us |  |  |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| clientArgs.common[0] | string | `"--l1.ws={{ tpl .Values.global.l1Endpoints.l1Ws . }}"` |  |
| clientArgs.common[1] | string | `"--taikoL1={{ (index .Values .Values.global.network).l1ContractAddresses.taikoL1 }}"` |  |
| clientArgs.common[2] | string | `"--taikoL2={{ (index .Values .Values.global.network).l2ContractAddresses.taikoL2 }}"` |  |
| clientArgs.driver[0] | string | `"driver"` |  |
| clientArgs.driver[1] | string | `"--p2p.sync"` |  |
| clientArgs.driver[2] | string | `"--p2p.checkPointSyncUrl={{ (index .Values .Values.global.network).driver.checkpointUrl }}"` |  |
| clientArgs.driver[3] | string | `"--l1.beacon={{ tpl .Values.global.l1Endpoints.l1Beacon . }}"` |  |
| clientArgs.driver[4] | string | `"--l2.ws={{ tpl .Values.global.l2Endpoints.l2Ws . }}"` |  |
| clientArgs.driver[5] | string | `"--l2.auth={{ tpl .Values.global.l2Endpoints.l2Auth . }}"` |  |
| clientArgs.driver[6] | string | `"--jwtSecret=/jwtsecret/default"` |  |
| clientArgs.guardian[0] | string | `"prover"` |  |
| clientArgs.guardian[10] | string | `"--prover.capacity={{ (index .Values .Values.global.network).guardian.capacity }}"` |  |
| clientArgs.guardian[11] | string | `"--prover.proveUnassignedBlocks"` |  |
| clientArgs.guardian[12] | string | `"--tx.gasLimit={{ (index .Values .Values.global.network).guardian.txGasLimit }}"` |  |
| clientArgs.guardian[13] | string | `"--prover.l1NodeVersion=\"{{ (index .Values .Values.global.network).guardian.l1NodeInfo }}\""` |  |
| clientArgs.guardian[14] | string | `"--prover.l2NodeVersion=\"driver:{{ (index .Values .Values.global.network).image.tag }}/taiko-geth:{{ (index .Values .Values.global.network).guardian.taikoGethVersion }}/guardian:{{ (index .Values .Values.global.network).image.tag }}"` |  |
| clientArgs.guardian[1] | string | `"--mode.contester"` |  |
| clientArgs.guardian[2] | string | `"--l1.proverPrivKey=$(GUARDIAN_PRIVATE_KEY)"` |  |
| clientArgs.guardian[3] | string | `"--l1.http={{ tpl .Values.global.l1Endpoints.l1Http . }}"` |  |
| clientArgs.guardian[4] | string | `"--l2.ws={{ tpl .Values.global.l2Endpoints.l2Ws . }}"` |  |
| clientArgs.guardian[5] | string | `"--l2.http={{ tpl .Values.global.l2Endpoints.l2Http . }}"` |  |
| clientArgs.guardian[6] | string | `"--prover.guardianProverHealthCheckServerEndpoint={{ (index .Values .Values.global.network).guardian.healthCheckServer }}"` |  |
| clientArgs.guardian[7] | string | `"--taikoToken={{ (index .Values .Values.global.network).l1ContractAddresses.taikoToken }}"` |  |
| clientArgs.guardian[8] | string | `"--guardianProverMinority={{ (index .Values .Values.global.network).guardian.contractAddresses.guardianProverMinority }}"` |  |
| clientArgs.guardian[9] | string | `"--guardianProverMajority={{ (index .Values .Values.global.network).guardian.contractAddresses.guardianProverMajority }}"` |  |
| clientArgs.proposer[0] | string | `"proposer"` |  |
| clientArgs.proposer[1] | string | `"--l2.http={{ tpl .Values.global.l2Endpoints.l2Http . }}"` |  |
| clientArgs.proposer[2] | string | `"--l2.auth={{ tpl .Values.global.l2Endpoints.l2Auth . }}"` |  |
| clientArgs.proposer[3] | string | `"--taikoToken={{ (index .Values .Values.global.network).l1ContractAddresses.taikoToken }}"` |  |
| clientArgs.proposer[4] | string | `"--l1.proposerPrivKey=$(PROPOSER_PRIVATE_KEY)"` |  |
| clientArgs.proposer[5] | string | `"--l2.suggestedFeeRecipient={{ (index .Values .Values.global.network).proposer.suggestedFeeRecipient }}"` |  |
| clientArgs.proposer[6] | string | `"--tx.gasLimit={{ (index .Values .Values.global.network).proposer.txGasLimit }}"` |  |
| clientArgs.proposer[7] | string | `"--proverSet={{ (index .Values .Values.global.network).proposer.proverSetAddress }}"` |  |
| clientArgs.proposer[8] | string | `"--l1.blobAllowed={{ (index .Values .Values.global.network).proposer.blobAllowed }}"` |  |
| clientArgs.proposer[9] | string | `"--jwtSecret=/jwtsecret/default"` |  |
| clientArgs.prover[0] | string | `"prover"` |  |
| clientArgs.prover[10] | string | `"--proverSet={{ (index .Values .Values.global.network).prover.proverSetAddress }}"` |  |
| clientArgs.prover[1] | string | `"--l1.http={{ tpl .Values.global.l1Endpoints.l1Http . }}"` |  |
| clientArgs.prover[2] | string | `"--l2.ws={{ tpl .Values.global.l2Endpoints.l2Ws . }}"` |  |
| clientArgs.prover[3] | string | `"--l2.http={{ tpl .Values.global.l2Endpoints.l2Http . }}"` |  |
| clientArgs.prover[4] | string | `"--l1.proverPrivKey=$(PROVER_PRIVATE_KEY)"` |  |
| clientArgs.prover[5] | string | `"--prover.capacity={{ (index .Values .Values.global.network).prover.capacity }}"` |  |
| clientArgs.prover[6] | string | `"--taikoToken={{ (index .Values .Values.global.network).l1ContractAddresses.taikoToken }}"` |  |
| clientArgs.prover[7] | string | `"--raiko.host={{ (index .Values .Values.global.network).prover.raikoHost }}"` |  |
| clientArgs.prover[8] | string | `"--tx.gasLimit={{ (index .Values .Values.global.network).prover.txGasLimit }}"` |  |
| clientArgs.prover[9] | string | `"--tx.minBaseFee={{ (index .Values .Values.global.network).prover.txMinBaseFee }}"` |  |
| global.l1Endpoints.l1Beacon | string | `"http://ethereum-node-beacon:5052"` |  |
| global.l1Endpoints.l1Http | string | `"http://ethereum-node-execution:8545"` |  |
| global.l1Endpoints.l1Ws | string | `"ws://ethereum-node-execution:8546"` |  |
| global.l2Endpoints.l2Auth | string | `"http://{{ .Release.Name }}-taiko-geth:8551"` |  |
| global.l2Endpoints.l2Http | string | `"http://{{ .Release.Name }}-taiko-geth:8545"` |  |
| global.l2Endpoints.l2Ws | string | `"ws://{{ .Release.Name }}-taiko-geth:8546"` |  |
| global.mode | string | `"driver"` |  |
| global.network | string | `"hoodi"` |  |
| global.replicaCount | int | `1` |  |
| global.resources.limits.cpu | string | `"1000m"` |  |
| global.resources.limits.memory | string | `"500Mi"` |  |
| global.resources.requests.cpu | string | `"1000m"` |  |
| global.resources.requests.memory | string | `"500Mi"` |  |
| global.secret.jwt | string | `"ecb22bc24e7d4061f7ed690ccd5846d7d73f5d2b9733267e12f56790398d908a"` |  |
| hoodi.driver.checkpointUrl | string | `"https://rpc.hoodi.taiko.xyz"` |  |
| hoodi.image.pullPolicy | string | `"IfNotPresent"` |  |
| hoodi.image.repository | string | `"us-docker.pkg.dev/evmchain/images/taiko-client"` |  |
| hoodi.image.tag | string | `"taiko-client-v0.29.0"` |  |
| hoodi.l1ContractAddresses.taikoL1 | string | `"0xf6eA848c7d7aC83de84db45Ae28EAbf377fe0eF9"` |  |
| hoodi.l1ContractAddresses.taikoToken | string | `"0x6490E12d480549D333499236fF2Ba6676C296011"` |  |
| hoodi.l2ContractAddresses.taikoL2 | string | `"0x1670130000000000000000000000000000010001"` |  |
| mainnet.driver.checkpointUrl | string | `"https://rpc.mainnet.taiko.xyz"` |  |
| mainnet.image.pullPolicy | string | `"IfNotPresent"` |  |
| mainnet.image.repository | string | `"us-docker.pkg.dev/evmchain/images/taiko-client"` |  |
| mainnet.image.tag | string | `"taiko-client-v0.29.0"` |  |
| mainnet.l1ContractAddresses.taikoL1 | string | `"0x06a9Ab27c7e2255df1815E6CC0168d7755Feb19a"` |  |
| mainnet.l1ContractAddresses.taikoToken | string | `"0x10dea67478c5F8C5E2D90e5E9B26dBe60c54d800"` |  |
| mainnet.l2ContractAddresses.taikoL2 | string | `"0x1670000000000000000000000000000000010001"` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)
