Release Notes
---


## [0.4.0](https://github.com/thegraphnetwork-literev/LiteRev/compare/0.3.0...0.4.0) (2023-07-20)


### Features

* **backend:** Add begin and end dates for search on arXiv ([#182](https://github.com/thegraphnetwork-literev/LiteRev/issues/182)) ([6899635](https://github.com/thegraphnetwork-literev/LiteRev/commit/689963553d39fe3f5b5733d511ba5755b2c68728)), closes [#154](https://github.com/thegraphnetwork-literev/LiteRev/issues/154)
* **custom stopwords:** create a new set of custom stopwords from a file ([#170](https://github.com/thegraphnetwork-literev/LiteRev/issues/170)) ([284efcc](https://github.com/thegraphnetwork-literev/LiteRev/commit/284efcc0258c1ccb897a3a6881ce8fc6da642905))
* **helper button:** adding a helper button in search page ([#186](https://github.com/thegraphnetwork-literev/LiteRev/issues/186)) ([9dbcde3](https://github.com/thegraphnetwork-literev/LiteRev/commit/9dbcde34facd792305086a24ff04ca69a45f3143)), closes [#168](https://github.com/thegraphnetwork-literev/LiteRev/issues/168)
* **pdf flag, refactor:** add DOWNLOAD_PDF_ARTICLE flag, refactor pdf downloading functions ([#172](https://github.com/thegraphnetwork-literev/LiteRev/issues/172)) ([0fa5933](https://github.com/thegraphnetwork-literev/LiteRev/commit/0fa5933a763cf7f65fd55a665f9d065ba22dec2d))


### Bug Fixes

* **backend:** Fix `list_id` input as a dictionary in `generate_threads` ([#191](https://github.com/thegraphnetwork-literev/LiteRev/issues/191)) ([82fb89b](https://github.com/thegraphnetwork-literev/LiteRev/commit/82fb89b70c914428a090c972ccc455783287b130)), closes [#139](https://github.com/thegraphnetwork-literev/LiteRev/issues/139) [#182](https://github.com/thegraphnetwork-literev/LiteRev/issues/182) [#187](https://github.com/thegraphnetwork-literev/LiteRev/issues/187)
* **backend:** Fix errors from `print_research` in `view_functions` ([#178](https://github.com/thegraphnetwork-literev/LiteRev/issues/178)) ([3b94603](https://github.com/thegraphnetwork-literev/LiteRev/commit/3b94603eb9c7f6032c0c55968de4661835eca44c))
* filtering by user in historical research page ([#227](https://github.com/thegraphnetwork-literev/LiteRev/issues/227)) ([4746aa4](https://github.com/thegraphnetwork-literev/LiteRev/commit/4746aa4b2186652fd9da3887916185e9ee0515ff))
* **finish-button:** fix finish button functionality in the table select page ([#215](https://github.com/thegraphnetwork-literev/LiteRev/issues/215)) ([0b3b439](https://github.com/thegraphnetwork-literev/LiteRev/commit/0b3b439e5b1d1608bec671e0c28ccbaf64fb971e))
* fix bugs introduced by [#193](https://github.com/thegraphnetwork-literev/LiteRev/issues/193) ([#206](https://github.com/thegraphnetwork-literev/LiteRev/issues/206)) ([e067d14](https://github.com/thegraphnetwork-literev/LiteRev/commit/e067d143d85342a0773843aa59f532d4b1c786b9))
* Fix issues on the application ([#207](https://github.com/thegraphnetwork-literev/LiteRev/issues/207)) ([c14607e](https://github.com/thegraphnetwork-literev/LiteRev/commit/c14607e218d2c3a1f1092491a82306de33e7fcf3))
* Fix release-replacements ([1ff7d6c](https://github.com/thegraphnetwork-literev/LiteRev/commit/1ff7d6cab6d46ca8d2c187127c6e37239f3e8fcf))
* Fix semantic release workflow ([#211](https://github.com/thegraphnetwork-literev/LiteRev/issues/211)) ([0e063a7](https://github.com/thegraphnetwork-literev/LiteRev/commit/0e063a7ba1a3d29b17d8022526c006740415295a))
* Fix the release workflow ([#229](https://github.com/thegraphnetwork-literev/LiteRev/issues/229)) ([3d4af35](https://github.com/thegraphnetwork-literev/LiteRev/commit/3d4af355c65780c7c01c65b387383ef763ceca72))
* Fix view_functions and tests ([#185](https://github.com/thegraphnetwork-literev/LiteRev/issues/185)) ([0c7d914](https://github.com/thegraphnetwork-literev/LiteRev/commit/0c7d914577d680c2bd91be906a6dd25a5145fd15))
* Remove duplicated methods from arXiv ([#194](https://github.com/thegraphnetwork-literev/LiteRev/issues/194)) ([193ae02](https://github.com/thegraphnetwork-literev/LiteRev/commit/193ae0283615217ee89f277ac6c2e627c55f4cf6))
* **update graph function:** updating BackEnd clustering.py and view_functions.py files ([#174](https://github.com/thegraphnetwork-literev/LiteRev/issues/174)) ([fbb35f8](https://github.com/thegraphnetwork-literev/LiteRev/commit/fbb35f83776872ef8b35020cb6281c2ae84fce61))
* **updating graph code:** updating files to show proper graph results ([#195](https://github.com/thegraphnetwork-literev/LiteRev/issues/195)) ([e6f42bc](https://github.com/thegraphnetwork-literev/LiteRev/commit/e6f42bcfb29aa36f210bc9689158f5ae0c2797e9))


### Reverts

* Revert "fix(backend): Fix errors from `print_research` in `view_functions` (#178)" (#183) ([0551374](https://github.com/thegraphnetwork-literev/LiteRev/commit/05513747ddb8798c28d34b237c5457179c515f84)), closes [#178](https://github.com/thegraphnetwork-literev/LiteRev/issues/178) [#183](https://github.com/thegraphnetwork-literev/LiteRev/issues/183)

## [0.3.0](https://github.com/thegraphnetwork-literev/LiteRev/compare/0.2.0...0.3.0) (2023-06-21)


### Features

* **testing:** adding more tests ([#136](https://github.com/thegraphnetwork-literev/LiteRev/issues/136)) ([7086b88](https://github.com/thegraphnetwork-literev/LiteRev/commit/7086b887c7cfe11052e6d4b20c8522cbc8c8b69c))


### Bug Fixes

* **frontend:** adding frontend updates ([#146](https://github.com/thegraphnetwork-literev/LiteRev/issues/146)) ([63c7b41](https://github.com/thegraphnetwork-literev/LiteRev/commit/63c7b41107827b5cd67ffa592bd7d2daff4dafc3))
* Increase search limit in Research model/form ([#153](https://github.com/thegraphnetwork-literev/LiteRev/issues/153)) ([4281911](https://github.com/thegraphnetwork-literev/LiteRev/commit/428191132446c6130d47df097d05c4ab52cbece1)), closes [#85](https://github.com/thegraphnetwork-literev/LiteRev/issues/85)
* **progress bar:** fixing zero division in progress bar ([#160](https://github.com/thegraphnetwork-literev/LiteRev/issues/160)) ([6d6dcaa](https://github.com/thegraphnetwork-literev/LiteRev/commit/6d6dcaaad8254f3cdf7f7f71bbabb4e5fac19f3b))


## [0.2.0](https://github.com/thegraphnetwork-literev/LiteRev/compare/0.1.0...0.2.0) (2023-06-06)


### Features

* Adding database select in Search page ([#94](https://github.com/thegraphnetwork-literev/LiteRev/issues/94)) ([f418409](https://github.com/thegraphnetwork-literev/LiteRev/commit/f418409698852cd26a4c0a913fcecb7deeaaad0a))


### Bug Fixes

* **backend tests:** enabling and updating backend test ([#126](https://github.com/thegraphnetwork-literev/LiteRev/issues/126)) ([58a6afc](https://github.com/thegraphnetwork-literev/LiteRev/commit/58a6afc88e2724f34bfa7a1dc652ebe00ab93642))
* **dev:** Fix development workflow ([#140](https://github.com/thegraphnetwork-literev/LiteRev/issues/140)) ([ea435a5](https://github.com/thegraphnetwork-literev/LiteRev/commit/ea435a5cb89384baf2916efe93383208992d5010))
* **release:** Fix .releaserc.json ([fccffd2](https://github.com/thegraphnetwork-literev/LiteRev/commit/fccffd2e4941d2d9992f7ef8dbee1c90c042c887))
* **release:** Remove poetry command from release pipeline ([e1df732](https://github.com/thegraphnetwork-literev/LiteRev/commit/e1df73295085988e2b75b3769324848238b9826e))
