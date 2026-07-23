# China Platforms

## Scope And Collection Rule

Treat China as a first-class market, written `China (CN)`, and keep it separate from language. A Chinese-language capture in another market is not a China capture; a China capture in another language is not a `zh-CN` capture. Select both values before collection.

Use this note only for Baidu, Quark, Doubao, Tencent Yuanbao, Kimi, or DeepSeek consumer-product observations. It was produced from the direct official pages listed below and bounded, explicitly recorded product behavior. Do not import third-party crawler lists, optimization guidance, or generalized product claims.

## Canonical Identity Registry

Keep provider, platform, and product as separate fields even when their canonical IDs happen to be equal. These IDs are audit-local identifiers for stable matching, not claims about corporate structure, product architecture, or shared behavior.

Normalize an observed alias by trimming surrounding whitespace, applying Unicode NFC, and ASCII-case-folding Latin letters. Match the complete normalized value against the exact alias lists below. Preserve the observed label beside the canonical ID. Do not translate, fuzzy-match, substring-match, or infer an identity from language, domain resemblance, or another field. An unregistered alias is `unavailable` until a current direct official source supports a registry update.

| Candidate | Provider ID and exact aliases | Platform ID and exact aliases | Product ID and exact aliases |
| --- | --- | --- | --- |
| Baidu | `baidu`: `Baidu`, `百度` | `baidu`: `Baidu`, `百度` | `baidu-wenxin-assistant`: `百度文心助手`, `文心助手` |
| Quark | `quark`: `Quark`, `夸克` | `quark`: `Quark`, `夸克` | `quark`: `Quark`, `夸克` |
| Doubao | `bytedance`: `ByteDance`, `字节跳动` | `doubao`: `Doubao`, `豆包` | `doubao`: `Doubao`, `豆包` |
| Tencent Yuanbao | `tencent`: `Tencent`, `腾讯` | `tencent-yuanbao`: `Tencent Yuanbao`, `腾讯元宝`, `元宝` | `tencent-yuanbao`: `Tencent Yuanbao`, `腾讯元宝`, `元宝` |
| Kimi | `kimi`: `Kimi`, `Kimi AI` | `kimi`: `Kimi`, `Kimi AI` | `kimi`: `Kimi`, `Kimi AI` |
| DeepSeek | `deepseek`: `DeepSeek`, `深度求索` | `deepseek`: `DeepSeek`, `深度求索` | `deepseek`: `DeepSeek`, `深度求索` |

Use the registry only to normalize identity labels. It does not establish that a product exposed a model, network mode, citation feature, crawler, or any other capability.

## Current Direct Official Sources

The pages below were retrieved and their title plus relevant visible or metadata content inspected on **2026-07-23**. `Not exposed` means no editorial publication or update date was visible in the captured source. An HTTP `Last-Modified` header or request-time metadata is not treated as an editorial source date.

| Candidate | Direct official source and recorded title | Exposed publication/update date | Exact supported scope | Limitation |
| --- | --- | --- | --- | --- |
| Baidu | [`百度文心助手 - 办公学习一站解决`](https://chat.baidu.com/) | Not exposed | The official entry redirects to Baidu's Wenxin site; its title identifies `百度文心助手`, and its description identifies an assistant that advertises AI search, creation, and reading functions. | Establishes landing-page identity and advertised functions only. It does not establish answer availability, citation behavior, crawler identity, retrieval, indexing, training, ranking, or robots effects. |
| Quark | [`夸克_AI旗舰应用官网`](https://www.quark.cn/) | Generated metadata exposed `2026-7-23T16:40:19+08:00`; treat it as request-time metadata, not an editorial date. | The official page's visible heading identifies `夸克` with `AI浏览器`, `AI搜索`, and `AI助手` surfaces. | Establishes official landing-page labels only. It does not establish which surface answered a query, network use, citation behavior, crawler behavior, or cross-market equivalence. |
| Doubao | [`豆包 - 字节跳动旗下 AI 智能助手`](https://www.doubao.com/) | Not exposed | The official title identifies Doubao as ByteDance's AI assistant; the description advertises chat, question answering, writing, translation, and programming uses. | Establishes product identity and advertised uses only. It does not establish model exposure, search/network state, login requirements for a particular attempt, citations, retrieval, or crawler behavior. |
| Tencent Yuanbao | [No HTML title exposed; visible heading `Hi~ 我是元宝`](https://yuanbao.tencent.com/) | No editorial date exposed; HTTP `Last-Modified` was 2026-07-20 and is transport metadata only. | The official page visibly identifies Yuanbao and calls it an intelligent assistant for questions and creation. | Establishes only the captured landing-page identity and text. It does not establish answer, login, model, search/network, citation, crawler, ranking, or training behavior. |
| Kimi | [`Kimi AI 官网 - K3 上线，专为智能体编程与知识工作打造`](https://www.kimi.com/) | Not exposed | The official title identifies Kimi AI and the then-advertised K3 product positioning. | Establishes landing-page identity and that title's advertised positioning only. It does not establish any named crawler, robots behavior, answer retrieval, source use, training use, citation behavior, or stable product behavior. |
| DeepSeek | [`DeepSeek`](https://chat.deepseek.com/) | Not exposed | The official chat page title identifies DeepSeek; its description advertises an AI assistant for coding, content creation, file reading, and conversation. | Establishes consumer-entry identity and advertised uses only. It does not establish model exposure, search/network state, citation behavior, crawler behavior, or ranking. |
| DeepSeek API | [`Your First API Call \| DeepSeek API Docs`](https://api-docs.deepseek.com/) | No editorial date exposed; HTTP `Last-Modified` was 2026-07-13 and is transport metadata only. | The official page documents a first API call and an API key. | Applies to the API page only. Do not transfer it to the consumer chat surface or use it to claim consumer search, citation, retrieval, crawler, or training behavior. |

## Capability Status

Within this bounded direct-source set, current official documentation is **unavailable** for all of these consumer-product claims:

- a supported crawler name or user agent;
- robots directives governing consumer answers, retrieval, indexing, or training;
- a promise that allowing a crawler causes an answer, mention, citation, rank, or traffic result;
- a stable consumer citation/source presentation contract;
- a cross-market or cross-language equivalence rule;
- a consumer answer-ranking factor.

`Unavailable` describes this captured evidence set; it does not assert that documentation or a capability does not exist. Recheck a current direct official source when one of these claims matters. Record source title, URL, exposed publication/update date or `not exposed`, retrieval date, exact supported text, product and surface scope, and limitation.

Do not infer common behavior across these products. Do not infer training, crawler, indexing, retrieval, citation, or ranking behavior from a landing page, internal script/configuration, robots file, API documentation for another surface, answer citation, or another provider's documentation.

## Permitted Manual Observation

Use ordinary permitted product access only. A manual record may establish exactly what its retained artifact shows: observed provider/platform/product labels, registered canonical IDs, product source URL, surface, displayed model or `unexposed`, exposure, displayed search/network state or `unexposed`, login state, market and language preselection/control states, timestamp window, repetition, collection method/protocol, response metadata, answer state, named-entity mention, inspectable citation URL instances, and error.

An observation does not become a normative platform rule. A displayed search toggle does not prove a network fetch. A cited URL does not prove a particular crawler, ordinary indexing, training use, or why the answer selected that source. A login gate makes the answer observation unavailable under the logged-out condition; do not bypass it or replace it with a logged-in result.

If the answer is inspectable but the citation/source surface is cropped, omitted from the export, or otherwise uninspectable, preserve the answer and mention observation but record `citation/source URLs=unavailable`. Use an empty URL list only when the complete citation/source surface was inspectable and showed no URLs.
