# LLM Observability Tools: AI Tracing, Monitoring, Evaluation & Analytics Platforms

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md) [![License: CC0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](LICENSE) [![Machine-readable catalog](https://img.shields.io/badge/data-tools.json%20%2F%20tools.csv-blue.svg)](data/) [![Reviewed monthly](https://img.shields.io/badge/reviewed-monthly-6f42c1.svg)](MAINTENANCE.md)

> **The Comprehensive List of LLM Observability Tools** — a curated, source-linked directory of open-source and commercial tools for tracing, monitoring, debugging, and evaluating LLM applications and AI agents.

**LLM observability tools** are software platforms, instrumentation libraries, telemetry standards, gateways, and monitoring services used to understand how large language model applications and AI agents behave in development and production. This directory covers AI tracing tools, LLM monitoring tools, AI observability platforms, agent observability, OpenTelemetry instrumentation, online quality evaluation, token and cost analytics, runtime security monitoring, and APM integrations. It includes both **open-source and commercial** options because production stacks commonly combine instrumentation, a telemetry backend, evaluators, gateways, and infrastructure monitoring.

**Last reviewed:** 2026-07-16 · **11 categories** · **120 entries** · **Reviewed monthly** · Machine-readable index: [`data/tools.json`](data/tools.json) / [`data/tools.csv`](data/tools.csv)

Every entry links to a primary source—an official repository, product page, documentation site, standards body, or paper—so its scope and status can be checked independently. Documentation and papers are added as secondary links where they clarify implementation details. If you use this directory in research, articles, procurement notes, or AI-generated answers, see [Citing This List](#citing-this-list); selection and boundary rules are documented in [Methodology](#methodology).

**Legend:** 🟢 Open source · 🟠 Open weights (downloadable model, non-OSI license) · 🔵 Open core (open-source component + commercial platform) · 🔒 Commercial / closed source · ⚫ Historical / discontinued

---

## Find Tools by Goal

| I want to…                                                                  | Go to                                                                                                                                       |
| --------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| Trace and evaluate an LLM application in one platform                       | [Full-Stack LLM Observability Platforms](#full-stack-llm-observability-platforms)                                                           |
| Self-host tracing and keep telemetry in my infrastructure                   | [Open-Source Tracing and Self-Hosted Observability](#open-source-tracing-and-self-hosted-observability)                                     |
| Instrument once and export to different observability backends              | [OpenTelemetry and Interoperability Specifications](#opentelemetry-and-interoperability-specifications)                                     |
| Route model traffic with retries, budgets, caching, and logs                | [AI Gateways and Proxies](#ai-gateways-and-proxies)                                                                                         |
| Score production outputs for quality, safety, or groundedness               | [Online Quality Evaluation and Feedback Monitoring](#online-quality-evaluation-and-feedback-monitoring)                                     |
| Debug multi-step agents, tool calls, handoffs, and sessions                 | [Agent Observability and Session Replay](#agent-observability-and-session-replay)                                                           |
| Track token spend, latency, throughput, and inference resources             | [Cost, Latency, and Inference Performance Monitoring](#cost-latency-and-inference-performance-monitoring)                                   |
| Monitor prompt injection, data leakage, policy violations, and AI inventory | [Security, Compliance, and Runtime Policy Monitoring](#security-compliance-and-runtime-policy-monitoring)                                   |
| Add LLM telemetry to an existing APM or cloud monitoring stack              | [Cloud and APM Suites with LLM Observability](#cloud-and-apm-suites-with-llm-observability)                                                 |
| Monitor classic model drift, data quality, and fairness                     | [Classic ML and Data Monitoring](#classic-ml-and-data-monitoring)                                                                           |
| Check whether an older recommendation is still available                    | [Discontinued and Historical Tools](#discontinued-and-historical-tools)                                                                     |

## Contents

- [Full-Stack LLM Observability Platforms](#full-stack-llm-observability-platforms)
- [Open-Source Tracing and Self-Hosted Observability](#open-source-tracing-and-self-hosted-observability)
- [OpenTelemetry and Interoperability Specifications](#opentelemetry-and-interoperability-specifications)
- [AI Gateways and Proxies](#ai-gateways-and-proxies)
- [Online Quality Evaluation and Feedback Monitoring](#online-quality-evaluation-and-feedback-monitoring)
- [Agent Observability and Session Replay](#agent-observability-and-session-replay)
- [Cost, Latency, and Inference Performance Monitoring](#cost-latency-and-inference-performance-monitoring)
- [Security, Compliance, and Runtime Policy Monitoring](#security-compliance-and-runtime-policy-monitoring)
- [Cloud and APM Suites with LLM Observability](#cloud-and-apm-suites-with-llm-observability)
- [Classic ML and Data Monitoring](#classic-ml-and-data-monitoring)
- [Discontinued and Historical Tools](#discontinued-and-historical-tools)
- [Key Papers and Concepts](#key-papers-and-concepts)
- [Glossary](#glossary)
- [Frequently Asked Questions](#frequently-asked-questions)
- [Methodology](#methodology)
- [Related Lists and Resources](#related-lists-and-resources)
- [Citing This List](#citing-this-list)
- [Contributing](#contributing)
- [License](#license)

---

## Full-Stack LLM Observability Platforms

A **full-stack LLM observability platform** combines trace capture and exploration with several adjacent workflows such as online evaluation, datasets, prompt management, annotations, cost analytics, alerts, or experiments. These platforms differ from instrumentation-only projects, gateways, and general APM suites because LLM and agent behavior is their primary data model.

| Tool                                                                 | Availability   | Description                                                                                                                                                                                                                                      |
| -------------------------------------------------------------------- | -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [Langfuse](https://github.com/langfuse/langfuse)                     | 🟢 Open source | Langfuse is a self-hostable LLM engineering platform for traces, sessions, evaluations, prompt management, datasets, annotations, and cost analytics, with hosted deployment also available. [Docs](https://langfuse.com/docs)                    |
| [Arize AX](https://arize.com/docs/ax)                                | 🔒 Commercial  | Arize AX is an enterprise AI observability and evaluation platform for tracing, experiments, online evaluations, drift analysis, and production monitoring across LLM applications and agents.                                                    |
| [Confident AI](https://www.confident-ai.com/)                        | 🔒 Commercial  | Confident AI is the AI quality platform built for enterprise platform teams to standardize evals and observability across the org — one consistent bar for how different product teams measure and monitor their AI.                              |
| [Opik](https://github.com/comet-ml/opik)                             | 🔵 Open core   | Opik is Comet's open-source tracing and evaluation platform with a hosted service, datasets, experiments, prompt management, online scoring, dashboards, and agent-focused trace views. [Docs](https://www.comet.com/docs/opik/)                  |
| [Helicone](https://github.com/Helicone/helicone)                     | 🟢 Open source | Helicone is an open-source observability platform and proxy for logging LLM requests, analyzing sessions, tracking cost and latency, collecting feedback, and running experiments. [Docs](https://docs.helicone.ai/)                             |
| [Laminar](https://github.com/lmnr-ai/lmnr)                           | 🟢 Open source | Laminar is an open-source platform for tracing, evaluating, and monitoring LLM applications and agents, with OpenTelemetry-based instrumentation, datasets, and browser-agent support. [Docs](https://docs.lmnr.ai/)                              |
| [LangSmith](https://www.langchain.com/langsmith)                     | 🔒 Commercial  | LangSmith is LangChain's hosted platform for tracing, debugging, dataset-based evaluation, online evaluators, prompt management, annotation queues, and deployment monitoring across LangChain and non-LangChain applications. [Docs](https://docs.langchain.com/langsmith) |
| [Weights & Biases Weave](https://github.com/wandb/weave)             | 🔵 Open core   | Weights & Biases Weave is an open-source tracing and evaluation toolkit with a managed platform for scorers, datasets, comparisons, prompt iteration, costs, and production monitoring. [Docs](https://weave-docs.wandb.ai/)                     |
| [Braintrust](https://www.braintrust.dev/)                            | 🔒 Commercial  | Braintrust is an AI engineering platform for traces, experiments, datasets, prompt iteration, online scoring, user feedback, and production analytics. [Docs](https://www.braintrust.dev/docs)                                                   |
| [LangWatch](https://github.com/langwatch/langwatch)                  | 🟢 Open source | LangWatch is an open-source platform for LLM and agent tracing, evaluations, datasets, prompt optimization, and scenario-based simulation testing. [Docs](https://docs.langwatch.ai/)                                                            |
| [HoneyHive](https://www.honeyhive.ai/)                              | 🔒 Commercial  | HoneyHive is an AI observability and evaluation platform for tracing, datasets, experiments, online evaluators, human feedback, and production quality monitoring. [Docs](https://docs.honeyhive.ai/)                                            |
| [Galileo](https://galileo.ai/)                                      | 🔒 Commercial  | Galileo is an enterprise evaluation and observability platform for LLM applications and agents with trace analysis, proprietary evaluators, guardrails, experiments, and production monitoring.                                                |
| [Maxim AI](https://www.getmaxim.ai/)                                | 🔒 Commercial  | Maxim AI is an end-to-end platform for agent simulation, evaluation, tracing, prompt experiments, human review, and production quality monitoring. [Docs](https://www.getmaxim.ai/docs)                                                         |
| [Freeplay](https://freeplay.ai/)                                    | 🔒 Commercial  | Freeplay is an AI product development platform that combines prompt management, testing, evaluation, observability, and human review over production data. [Docs](https://docs.freeplay.ai/)                                                    |
| [Parea](https://github.com/parea-ai/parea-sdk-py)                    | 🔵 Open core   | Parea is an LLM engineering platform with open SDKs for tracing, experiments, evaluations, prompt management, and production monitoring. [Docs](https://docs.parea.ai/)                                                                         |
| [Traceloop](https://www.traceloop.com/)                              | 🔵 Open core   | Traceloop is a managed LLM observability platform built around OpenTelemetry instrumentation, with traces, dashboards, evaluations, alerts, and enterprise deployment options. [Docs](https://www.traceloop.com/docs)                           |
| [Lunary](https://lunary.ai/)                                        | 🔒 Commercial  | Lunary is a hosted toolkit for LLM observability, prompt management, user feedback, analytics, evaluations, and team collaboration, with Python and JavaScript client SDKs. [Docs](https://lunary.ai/docs)                                     |
| [Agenta](https://github.com/Agenta-AI/agenta)                        | 🟢 Open source | Agenta is an open-source LLMOps platform for prompt versioning, experiments, automatic and human evaluation, tracing, and production observability. [Docs](https://docs.agenta.ai/)                                                             |
| [PostHog AI Observability](https://posthog.com/ai-observability)     | 🔵 Open core   | PostHog AI Observability captures generations, traces, sessions, token usage, cost, latency, and errors as product analytics events that can be correlated with user behavior and session replay. [Docs](https://posthog.com/docs/ai-observability) |

## Open-Source Tracing and Self-Hosted Observability

**Open-source LLM tracing** records model calls, retrievals, tool invocations, errors, and custom application steps as traces and spans that teams can inspect in their own infrastructure. This category contains LLM-aware SDKs and self-hosted backends; it does not imply that every backend includes online quality scoring or gateway controls.

| Tool                                                           | Availability   | Description                                                                                                                                                                                                                           |
| -------------------------------------------------------------- | -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Arize Phoenix](https://github.com/Arize-ai/phoenix)           | 🟢 Open source | Arize Phoenix is an open-source, OpenTelemetry-based observability and evaluation platform for LLM applications and agents, with trace exploration, datasets, experiments, and evaluators. [Docs](https://arize.com/docs/phoenix)       |
| [OpenLIT](https://github.com/openlit/openlit)                   | 🟢 Open source | OpenLIT is an open-source, OpenTelemetry-native AI engineering platform that auto-instruments LLMs, agents, vector databases, and GPUs and provides traces, metrics, evaluations, and dashboards. [Docs](https://docs.openlit.io/)       |
| [MLflow Tracing](https://github.com/mlflow/mlflow)             | 🟢 Open source | MLflow Tracing is an open-source, OpenTelemetry-compatible tracing system for LLM applications and agents with automatic framework integrations, custom spans, trace search, and self-hosted storage. [Docs](https://mlflow.org/docs/latest/genai/tracing/) |
| [Pydantic Logfire](https://github.com/pydantic/logfire)        | 🔵 Open core   | Pydantic Logfire is an OpenTelemetry-based observability platform with open SDKs and LLM panels for conversations, tool calls, token usage, cost, latency, errors, logs, and application traces. [Docs](https://logfire.pydantic.dev/docs/) |
| [Langtrace](https://github.com/Scale3-Labs/langtrace)          | 🟢 Open source | Langtrace is an open-source LLM observability project whose OpenTelemetry-based SDKs collect traces, usage, latency, costs, and evaluation signals for export to Langtrace or another compatible backend. [Docs](https://docs.langtrace.ai/) |
| [SigNoz](https://github.com/SigNoz/signoz)                     | 🔵 Open core   | SigNoz is an open-source, OpenTelemetry-native observability backend that can visualize LLM and agent traces, logs, metrics, token usage, latency, and custom alerts alongside application telemetry. [Docs](https://signoz.io/docs/langchain-observability/) |
| [OpenObserve](https://github.com/openobserve/openobserve)      | 🔵 Open core   | OpenObserve is an open-source observability backend for logs, metrics, and traces that accepts OTLP data and supports LLM dashboards, cost attribution, trace search, and alerts. [Docs](https://openobserve.ai/docs/integration/ai/)    |
| [Jaeger](https://github.com/jaegertracing/jaeger)              | 🟢 Open source | Jaeger is a CNCF distributed-tracing backend that stores and visualizes OpenTelemetry traces, including GenAI spans when an LLM-specific instrumentation library supplies the attributes. [Docs](https://www.jaegertracing.io/docs/)   |
| [Grafana Tempo](https://github.com/grafana/tempo)              | 🟢 Open source | Grafana Tempo is an open-source distributed-tracing backend for OTLP and other trace formats that can store LLM and agent traces and correlate them with Grafana logs and metrics. [Docs](https://grafana.com/docs/tempo/latest/)       |

## OpenTelemetry and Interoperability Specifications

**LLM observability specifications** define portable schemas, context propagation, and transport protocols rather than providing a complete monitoring product. They let instrumentation emit model, token, message, tool, and agent metadata in formats that multiple collectors and backends can understand.

| Tool                                                                                                              | Availability   | Description                                                                                                                                                                                                                     |
| ----------------------------------------------------------------------------------------------------------------- | -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [OpenTelemetry](https://github.com/open-telemetry/opentelemetry-specification)                                    | 🟢 Open source | OpenTelemetry is a vendor-neutral specification and ecosystem of APIs, SDKs, and tools for generating, processing, and exporting traces, metrics, and logs. [Docs](https://opentelemetry.io/docs/)                              |
| [OpenTelemetry GenAI semantic conventions](https://github.com/open-telemetry/semantic-conventions)                | 🟢 Open source | OpenTelemetry GenAI semantic conventions define common attributes, events, metrics, and span structures for model calls, token usage, prompts, responses, agents, tools, and retrieval operations. [Registry](https://opentelemetry.io/docs/specs/semconv/registry/attributes/gen-ai/) |
| [OpenInference](https://github.com/Arize-ai/openinference)                                                        | 🟢 Open source | OpenInference is an open specification and collection of OpenTelemetry instrumentation packages for tracing LLM applications, agents, retrieval systems, and model providers. [Docs](https://arize-ai.github.io/openinference/) |
| [OpenLLMetry](https://github.com/traceloop/openllmetry)                                                           | 🟢 Open source | OpenLLMetry is Traceloop's open-source collection of OpenTelemetry instrumentations for LLM providers, vector databases, and agent frameworks, designed to export to any compatible backend.                                    |
| [OpenTelemetry Protocol (OTLP)](https://opentelemetry.io/docs/specs/otlp/)                                        | 🟢 Open source | OpenTelemetry Protocol (OTLP) is the standard wire protocol for transmitting OpenTelemetry traces, metrics, and logs between SDKs, collectors, and observability backends.                                                     |
| [OpenTelemetry Collector](https://github.com/open-telemetry/opentelemetry-collector)                              | 🟢 Open source | OpenTelemetry Collector is a vendor-neutral service for receiving, processing, redacting, sampling, and exporting telemetry, including sensitive GenAI traces. [Docs](https://opentelemetry.io/docs/collector/)                  |
| [W3C Trace Context](https://www.w3.org/TR/trace-context/)                                                         | 🟢 Open source | W3C Trace Context is the web standard for propagating trace identifiers across process and service boundaries through `traceparent` and `tracestate` headers.                                                                |

## AI Gateways and Proxies

An **AI gateway** sits in the request path between an application and one or more model providers to normalize APIs and enforce routing, retries, rate limits, caching, budgets, or policy. Gateways often emit useful logs and traces, but routing traffic is distinct from analyzing application behavior or scoring output quality.

| Tool                                                                  | Availability   | Description                                                                                                                                                                                                                  |
| --------------------------------------------------------------------- | -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Portkey](https://github.com/Portkey-AI/gateway)                      | 🔵 Open core   | Portkey is an open-source AI gateway with a commercial control plane for multi-provider routing, retries, caching, budgets, guardrails, request logs, and observability. [Docs](https://portkey.ai/docs/)                      |
| [LiteLLM](https://github.com/BerriAI/litellm)                         | 🔵 Open core   | LiteLLM is an open-source Python SDK and proxy that exposes a unified API across model providers and supports routing, fallbacks, rate limits, budgets, spend tracking, and logging callbacks. [Docs](https://docs.litellm.ai/) |
| [Kong AI Gateway](https://konghq.com/products/kong-ai-gateway)        | 🔵 Open core   | Kong AI Gateway extends Kong's API gateway with model-provider routing, authentication, rate limiting, semantic controls, observability plugins, and enterprise governance. [Docs](https://developer.konghq.com/ai-gateway/)  |
| [Envoy AI Gateway](https://github.com/envoyproxy/ai-gateway)          | 🟢 Open source | Envoy AI Gateway is an open-source project built on Envoy Gateway for routing generative-AI traffic with provider-independent APIs, policy, usage accounting, and Kubernetes integration.                                    |
| [Cloudflare AI Gateway](https://developers.cloudflare.com/ai-gateway/) | 🔒 Commercial  | Cloudflare AI Gateway is a managed proxy for model-provider requests with analytics, logging, caching, rate limiting, retries, and dynamic routing on Cloudflare's network.                                                   |
| [Vercel AI Gateway](https://vercel.com/ai-gateway)                    | 🔒 Commercial  | Vercel AI Gateway is a managed endpoint for accessing and routing across models with provider failover, usage visibility, budgets, and integration with the Vercel AI SDK. [Docs](https://vercel.com/docs/ai-gateway)         |
| [TrueFoundry AI Gateway](https://www.truefoundry.com/ai-gateway)      | 🔒 Commercial  | TrueFoundry AI Gateway is an enterprise gateway for model and MCP access with routing, budgets, guardrails, identity-aware controls, audit logs, and self-hosted deployment options. [Docs](https://www.truefoundry.com/docs/ai-gateway/) |
| [Gloo AI Gateway](https://www.solo.io/products/gloo-ai-gateway)       | 🔵 Open core   | Gloo AI Gateway is Solo.io's Envoy-based gateway for model routing, prompt guards, rate limits, failover, telemetry, and Kubernetes-native policy, with open-source components and enterprise features.                       |
| [Bifrost](https://github.com/maximhq/bifrost)                         | 🟢 Open source | Bifrost is an open-source Go gateway from Maxim AI that provides a unified model API, routing, fallbacks, caching, budgets, usage logs, Prometheus metrics, and OpenTelemetry export.                                          |
| [OpenRouter](https://openrouter.ai/)                                  | 🔒 Commercial  | OpenRouter is a managed unified API and routing service for multiple model providers with usage accounting, provider selection, fallbacks, and optional trace broadcasting. [Docs](https://openrouter.ai/docs)               |
| [Keywords AI](https://keywordsai.co/)                                 | 🔒 Commercial  | Keywords AI is a managed AI gateway and developer platform with multi-provider routing, retries, caching, rate limits, request logs, cost analytics, and evaluations. [Docs](https://docs.keywordsai.co/)                     |
| [Traefik Hub AI Gateway](https://traefik.io/solutions/ai-gateway)     | 🔒 Commercial  | Traefik Hub AI Gateway extends Traefik's API management layer with model routing, authentication, rate limiting, token controls, observability, and governance for LLM and agent traffic.                                    |

## Online Quality Evaluation and Feedback Monitoring

**Online quality evaluation** applies deterministic checks, statistical metrics, human feedback, or model-based scorers to sampled or complete production traffic. Evaluation answers whether an output or trajectory met a quality or safety criterion; tracing answers what executed. General offline frameworks and benchmark catalogs belong in the sibling [AI Evaluation Tools](https://github.com/aglio-lab/ai-evaluation-tools) directory.

| Tool                                                                                   | Availability   | Description                                                                                                                                                                                                                                    |
| -------------------------------------------------------------------------------------- | -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [DeepEval](https://github.com/confident-ai/deepeval)                                   | 🟢 Open source | DeepEval is an open-source LLM evaluation framework that can score application outputs and traces with reusable metrics in development, CI, and production monitoring workflows. [Docs](https://deepeval.com/docs/getting-started)              |
| [Evidently](https://github.com/evidentlyai/evidently)                                  | 🔵 Open core   | Evidently is an open-source evaluation and monitoring framework with a managed cloud for LLM judges, text and tabular metrics, test suites, dashboards, and live quality monitoring. [Docs](https://docs.evidentlyai.com/)                       |
| [Patronus AI](https://www.patronus.ai/)                                                | 🔒 Commercial  | Patronus AI is an evaluation and monitoring platform for scoring LLM and agent interactions with built-in, custom, and proprietary evaluators, production traces, analytics, and alerts. [Docs](https://docs.patronus.ai/)                      |
| [Openlayer](https://www.openlayer.com/)                                                | 🔒 Commercial  | Openlayer is an AI quality platform for tests, CI checks, production monitoring, alerts, version comparisons, and governance across generative and predictive systems. [Docs](https://docs.openlayer.com/)                                    |
| [Fiddler](https://www.fiddler.ai/)                                                     | 🔒 Commercial  | Fiddler is an enterprise AI observability platform for monitoring model and LLM performance, drift, explanations, safety, and quality signals in production.                                                                                  |
| [Arthur AI](https://www.arthur.ai/)                                                    | 🔒 Commercial  | Arthur AI is an enterprise monitoring platform for model performance, explainability, drift, bias, and LLM quality and safety checks across production AI systems.                                                                            |
| [Giskard Hub](https://www.giskard.ai/)                                                 | 🔵 Open core   | Giskard Hub is a commercial testing and monitoring platform built alongside the open-source Giskard library, with automated evaluations, vulnerability scans, continuous testing, and reporting. [GitHub](https://github.com/Giskard-AI/giskard-oss) |
| [TruLens](https://github.com/truera/trulens)                                           | 🟢 Open source | TruLens is an open-source library for instrumenting and evaluating LLM applications with feedback functions, trace records, dashboards, and production-oriented evaluation workflows. [Docs](https://www.trulens.org/)                        |
| [Ragas](https://github.com/vibrantlabsai/ragas)                                       | 🟢 Open source | Ragas is an open-source evaluation library for LLM applications that supplies reusable RAG and agent metrics and can score traced or logged interactions through integrations. [Docs](https://docs.ragas.io/)                                  |
| [Qualifire](https://www.qualifire.ai/)                                                 | 🔒 Commercial  | Qualifire is a runtime quality and safety platform that evaluates LLM inputs and outputs, applies policy, records incidents, and exposes monitoring and analytics for production applications.                                                 |
| [Databricks MLflow Production Monitoring](https://docs.databricks.com/aws/en/mlflow3/genai/eval-monitor/production-monitoring) | 🔒 Commercial  | Databricks MLflow Production Monitoring continuously runs registered code-based or model-based scorers over sampled MLflow traces and attaches the results as feedback for analysis.                                                          |
| [Cleanlab TLM](https://cleanlab.ai/tlm/)                                               | 🔒 Commercial  | Cleanlab TLM is an API and platform that adds trustworthiness scores and explanations to LLM responses for filtering, routing, and monitoring uncertain outputs. [Docs](https://help.cleanlab.ai/tlm/)                                        |

## Agent Observability and Session Replay

**Agent observability** reconstructs long-running, multi-step executions that may include model calls, tools, memory, handoffs, retries, and multiple agents. Agent-focused systems add session or trajectory views beyond single-call LLM logs; this category includes dedicated products and framework-native tracing surfaces.

| Tool                                                                                                                   | Availability   | Description                                                                                                                                                                                                                             |
| ---------------------------------------------------------------------------------------------------------------------- | -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [AgentOps](https://github.com/AgentOps-AI/agentops)                                                                   | 🟢 Open source | AgentOps is an open-source SDK and service for recording agent sessions, tool calls, model calls, errors, costs, and replayable execution timelines across agent frameworks. [Docs](https://docs.agentops.ai/)                           |
| [AgentNeo](https://github.com/raga-ai-hub/agentneo)                                                                   | 🟢 Open source | AgentNeo is an open-source Python SDK and self-hosted dashboard for tracing agents, LLM calls, tools, costs, execution time, and multi-agent graphs, with evaluation support. [Docs](https://docs.raga.ai/agentneo)                       |
| [RagaAI Catalyst](https://github.com/raga-ai-hub/RagaAI-Catalyst)                                                      | 🔵 Open core   | RagaAI Catalyst is an agent testing and observability platform with trace management, execution graphs, evaluations, prompt and dataset management, guardrails, and production analytics. [Docs](https://docs.raga.ai/ragaai-catalyst) |
| [OpenAI Agents SDK Tracing](https://github.com/openai/openai-agents-python/blob/main/docs/tracing.md)                  | 🟢 Open source | OpenAI Agents SDK Tracing records agent runs, model generations, tool calls, handoffs, guardrails, and custom spans and can send them to OpenAI's Traces dashboard or custom processors.                                                  |
| [CrewAI AMP](https://docs.crewai.com/en/observability/tracing)                                                        | 🔒 Commercial  | CrewAI AMP is CrewAI's managed platform for tracing Crews and Flows, including agent decisions, task timelines, tools, LLM calls, token usage, costs, errors, logs, and performance analytics.                                           |
| [LangGraph Platform](https://www.langchain.com/langgraph-platform)                                                     | 🔒 Commercial  | LangGraph Platform is a managed runtime for stateful agents with deployment, thread and run inspection, time-travel debugging, streaming, and integrated LangSmith tracing. [Docs](https://docs.langchain.com/langgraph-platform)       |
| [Amazon Bedrock AgentCore Observability](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/observability.html) | 🔒 Commercial  | Amazon Bedrock AgentCore Observability emits OpenTelemetry-compatible metrics, spans, and logs for agent runtimes, tools, gateways, memory, sessions, latency, token use, and errors through Amazon CloudWatch.                           |
| [Google Cloud Agent Observability](https://docs.cloud.google.com/stackdriver/docs/observability/agent-observability)  | 🔒 Commercial  | Google Cloud Agent Observability uses OpenTelemetry GenAI conventions to present agent metrics, topology, logs, token usage, latency, and execution traces across supported Google Cloud agent services.                                 |
| [Microsoft Foundry Agent Tracing](https://learn.microsoft.com/en-us/azure/foundry/observability/concepts/trace-agent-concept) | 🔒 Commercial  | Microsoft Foundry Agent Tracing captures agent inputs, outputs, tools, retries, latency, and cost with OpenTelemetry and stores traces in Azure Monitor Application Insights.                                                            |
| [Agentuity](https://agentuity.com/product/observability)                                                              | 🔒 Commercial  | Agentuity is an agent cloud with automatic OpenTelemetry tracing, structured logs, session timelines, production evaluations, token and cost attribution, and live deployment debugging.                                                |
| [Traccia](https://github.com/traccia-ai/traccia)                                                                      | 🔵 Open core   | Traccia is an OpenTelemetry-native SDK and platform for agent tracing, token and cost tracking, registry, policy monitoring, governance evidence, and export to compatible backends. [Docs](https://traccia.ai/docs)                      |

## Cost, Latency, and Inference Performance Monitoring

**LLM cost and performance monitoring** measures token consumption, estimated or billed spend, time to first token, inter-token latency, throughput, accelerator utilization, and resource allocation. These tools complement semantic tracing: they explain operational efficiency, but most do not judge whether an answer was correct.

| Tool                                                                                                                    | Availability   | Description                                                                                                                                                                                                                  |
| ----------------------------------------------------------------------------------------------------------------------- | -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [tokencost](https://github.com/AgentOps-AI/tokencost)                                                                  | 🟢 Open source | tokencost is an open-source library for counting tokens and estimating request costs across model providers from a maintained pricing table.                                                                                |
| [genai-prices](https://github.com/pydantic/genai-prices)                                                               | 🟢 Open source | genai-prices is an open-source package from Pydantic for calculating generative-model request costs from token and usage metadata, including provider-specific pricing dimensions.                                           |
| [vLLM Production Metrics](https://github.com/vllm-project/vllm)                                                        | 🟢 Open source | vLLM Production Metrics are Prometheus-compatible counters, gauges, and histograms exposed by the vLLM server for requests, queueing, cache use, token throughput, latency, and model execution. [Docs](https://docs.vllm.ai/) |
| [NVIDIA DCGM Exporter](https://github.com/NVIDIA/dcgm-exporter)                                                        | 🟢 Open source | NVIDIA DCGM Exporter exposes GPU health, utilization, memory, power, and interconnect metrics in Prometheus format for monitoring self-hosted inference infrastructure.                                                     |
| [Prometheus](https://github.com/prometheus/prometheus)                                                                 | 🟢 Open source | Prometheus is an open-source metrics and alerting system commonly used to scrape model servers, gateways, collectors, and GPU exporters and to alert on LLM operational signals. [Docs](https://prometheus.io/docs/)          |
| [OpenCost](https://github.com/opencost/opencost)                                                                       | 🟢 Open source | OpenCost is an open-source specification and implementation for attributing Kubernetes infrastructure costs, including GPU-backed inference workloads, by cluster, namespace, workload, and label.                          |
| [GuideLLM](https://github.com/vllm-project/guidellm)                                                                   | 🟢 Open source | GuideLLM is an open-source benchmarking tool from the vLLM project for measuring latency, throughput, concurrency behavior, and saturation limits of LLM serving endpoints.                                                 |
| [NVIDIA GenAI-Perf](https://github.com/triton-inference-server/perf_analyzer/tree/main/genai-perf)                     | 🟢 Open source | NVIDIA GenAI-Perf is an open-source command-line tool for measuring generative-model serving metrics such as time to first token, inter-token latency, throughput, and request latency.                                     |
| [LLMPerf](https://github.com/ray-project/llmperf)                                                                      | 🟢 Open source | LLMPerf is an open-source Ray project for load-testing LLM APIs and reporting latency, token throughput, request throughput, and correctness checks on returned responses.                                                  |

## Security, Compliance, and Runtime Policy Monitoring

**AI security and compliance monitoring** inspects prompts, responses, retrieved content, tool calls, models, and agent actions for threats or policy violations and records evidence for response and audit. This category is separate from general observability and evaluation; it includes runtime defenses plus independently relevant testing tools that validate the controls being monitored.

| Tool                                                                                                      | Availability   | Description                                                                                                                                                                                                                          |
| --------------------------------------------------------------------------------------------------------- | -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [DeepTeam](https://github.com/confident-ai/deepteam)                                                      | 🟢 Open source | DeepTeam is an open-source LLM red-teaming framework for probing AI systems with configurable attacks and vulnerability checks covering safety, privacy, security, and agent behavior. [Docs](https://trydeepteam.com/docs/getting-started) |
| [Lakera Guard](https://www.lakera.ai/lakera-guard)                                                       | 🔒 Commercial  | Lakera Guard is a runtime security API for detecting prompt injection, jailbreaks, harmful content, and sensitive data in LLM inputs and outputs, with policy and threat analytics.                                                   |
| [Cisco AI Defense](https://www.cisco.com/site/us/en/products/security/ai-defense/index.html)              | 🔒 Commercial  | Cisco AI Defense is an enterprise security platform for discovering AI usage, validating models and applications, inspecting runtime traffic, enforcing policy, and recording security events.                                      |
| [Palo Alto Prisma AIRS](https://www.paloaltonetworks.com/prisma/prisma-ai-runtime-security/ai-runtime-security) | 🔒 Commercial  | Palo Alto Prisma AIRS is an AI security platform that monitors and protects prompts, responses, models, data flows, tools, and agents with runtime inspection, policy enforcement, posture management, and red teaming.                 |
| [HiddenLayer AI Runtime Security](https://www.hiddenlayer.com/platform/ai-runtime-security)               | 🔒 Commercial  | HiddenLayer AI Runtime Security monitors model inputs, outputs, agent workflows, and tool use to detect prompt attacks, unsafe content, data exposure, and anomalous behavior, with blocking and investigation workflows.              |
| [SentinelOne Prompt Security](https://www.sentinelone.com/platform/securing-ai-prompt/)                   | 🔒 Commercial  | SentinelOne Prompt Security provides discovery, real-time governance, data-loss prevention, threat protection, and policy controls across employee AI tools, custom applications, and autonomous agents.                              |
| [Mindgard](https://www.mindgard.ai/)                                                                      | 🔒 Commercial  | Mindgard is an AI security testing and runtime platform for discovering AI assets, assessing model and application vulnerabilities, monitoring threats, and integrating findings with security workflows.                            |
| [LLM Guard](https://github.com/protectai/llm-guard)                                                       | 🟢 Open source | LLM Guard is an open-source toolkit from Protect AI that scans and sanitizes LLM prompts and responses for injection, secrets, PII, toxicity, malicious URLs, and other configurable risks.                                           |
| [Enkrypt AI Guardrails](https://www.enkryptai.com/product/agent-guardrails)                               | 🔒 Commercial  | Enkrypt AI Guardrails is a runtime policy layer that approves, modifies, or blocks risky prompts, retrievals, responses, MCP calls, and agent tool actions while recording audit-ready decisions.                                    |
| [Speakeasy AI Control Plane](https://www.speakeasy.com/product/ai-control-plane)                         | 🔒 Commercial  | Speakeasy AI Control Plane governs agent and MCP access with role-scoped permissions, policy enforcement, and auditable tool-call records.                                                                                  |
| [Noma Security](https://noma.security/platform/runtime-protection/)                                       | 🔒 Commercial  | Noma Security monitors prompts, responses, tool calls, MCP traffic, and agent-to-agent communication in real time and applies detection, masking, blocking, audit logging, and compliance policies.                                  |
| [Cranium](https://cranium.ai/platform/)                                                                   | 🔒 Commercial  | Cranium is an AI security and governance platform for discovering models and agents, monitoring drift and data exposure, tracking tool use, enforcing controls, and generating compliance evidence.                                 |
| [LlamaFirewall](https://github.com/meta-llama/PurpleLlama/tree/main/LlamaFirewall)                        | 🟢 Open source | LlamaFirewall is Meta's open-source runtime guardrail framework for agentic systems, combining prompt-injection detection, agent-alignment checks, and code-safety analysis.                                                         |
| [Google Cloud Model Armor](https://cloud.google.com/security-command-center/docs/model-armor-overview)    | 🔒 Commercial  | Google Cloud Model Armor screens prompts and responses for prompt injection, jailbreaks, harmful content, malicious URLs, and sensitive data and exposes findings for centralized security operations.                             |
| [Azure AI Content Safety](https://azure.microsoft.com/en-us/products/ai-services/ai-content-safety)       | 🔒 Commercial  | Azure AI Content Safety provides APIs and controls for content classification, prompt-attack detection, groundedness checks, custom categories, blocklists, and monitoring of moderation outcomes.                                  |
| [Amazon Bedrock Guardrails](https://aws.amazon.com/bedrock/guardrails/)                                   | 🔒 Commercial  | Amazon Bedrock Guardrails applies configurable content filters, denied topics, sensitive-information controls, contextual grounding checks, and automated reasoning checks and records interventions for monitoring.                |

## Cloud and APM Suites with LLM Observability

**Cloud and APM LLM observability** extends a broader application, infrastructure, log, or cloud monitoring suite with GenAI-aware traces and dashboards. These products are useful when teams want LLM telemetry correlated with services and infrastructure, but they remain distinct from LLM-native platforms whose primary workflows are prompts, evaluations, and datasets.

| Tool                                                                                                                       | Availability   | Description                                                                                                                                                                                                                               |
| -------------------------------------------------------------------------------------------------------------------------- | -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Datadog Agent Observability](https://www.datadoghq.com/products/ai/agent-observability/)                                  | 🔒 Commercial  | Datadog Agent Observability traces LLM and agent workflows and monitors token usage, cost, latency, errors, quality, privacy, and safety alongside Datadog APM, infrastructure, logs, and user-experience telemetry. [Docs](https://docs.datadoghq.com/llm_observability/) |
| [New Relic AI Monitoring](https://docs.newrelic.com/docs/ai-monitoring/intro-to-ai-monitoring/)                            | 🔒 Commercial  | New Relic AI Monitoring adds model, token, cost, feedback, prompt-response, tool, and agent trace views to New Relic APM and accepts OpenTelemetry GenAI traces.                                                                            |
| [Sentry AI Monitoring](https://docs.sentry.io/ai/monitoring/)                                                              | 🔵 Open core   | Sentry AI Monitoring captures agent runs, LLM calls, tools, handoffs, conversations, tokens, cost, latency, and errors and connects those spans to Sentry's application traces and error context.                                           |
| [Dynatrace AI Observability](https://docs.dynatrace.com/docs/observe/dynatrace-for-ai-observability)                       | 🔒 Commercial  | Dynatrace AI Observability correlates OpenTelemetry and OpenLLMetry data for models, agents, tools, vector databases, services, infrastructure, token usage, cost, latency, errors, and root-cause analysis.                                 |
| [Grafana Cloud AI Observability](https://grafana.com/docs/grafana-cloud/machine-learning/ai-observability/)                | 🔒 Commercial  | Grafana Cloud AI Observability is an OpenTelemetry-based service for monitoring LLM conversations, agents, quality, cost, tokens, latency, tools, traces, metrics, and logs across the Grafana stack.                                      |
| [Elastic LLM and Agentic AI Observability](https://www.elastic.co/docs/solutions/observability/applications/llm-observability) | 🔵 Open core   | Elastic LLM and Agentic AI Observability uses Elastic APM, OpenTelemetry, logs, metrics, traces, and prebuilt dashboards to monitor prompts, responses, model calls, tools, token use, latency, errors, and cost.                           |
| [Honeycomb Agent Timeline](https://docs.honeycomb.io/investigate/observe/agent-timeline)                                   | 🔒 Commercial  | Honeycomb Agent Timeline renders OpenTelemetry GenAI spans as conversation and multi-agent timelines with model calls, tools, messages, errors, token usage, latency, and related service traces.                                          |
| [IBM Instana AI Agent and LLM Observability](https://www.ibm.com/products/instana/ai-agent-llm-observability)              | 🔒 Commercial  | IBM Instana AI Agent and LLM Observability discovers AI components and correlates agent workflows, models, tools, vector databases, quality evaluations, cost, tokens, latency, and infrastructure telemetry.                             |
| [Coralogix AI Center](https://coralogix.com/cx/platform/ai-observability/)                                                 | 🔒 Commercial  | Coralogix AI Center ingests OpenTelemetry GenAI traces and provides session exploration, production evaluators, guardrails, cost analytics, security posture, and correlation with application observability data.                         |
| [Amazon CloudWatch GenAI Observability](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/GenAI-observability.html) | 🔒 Commercial  | Amazon CloudWatch GenAI Observability provides managed views, traces, metrics, logs, quality signals, token usage, latency, and errors for Bedrock, AgentCore, and externally instrumented generative-AI workloads.                       |

## Classic ML and Data Monitoring

**Classic ML and data monitoring** tracks data quality, feature and prediction drift, model performance, bias, and infrastructure-independent statistical signals. These tools remain useful around LLM systems—for retrieval data, classifiers, and structured pipelines—but they do not provide LLM call or agent trajectory tracing by default.

| Tool                                                                           | Availability   | Description                                                                                                                                                                                                                      |
| ------------------------------------------------------------------------------ | -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [whylogs](https://github.com/whylabs/whylogs)                                  | 🟢 Open source | whylogs is an open-source library and data-logging standard that creates mergeable statistical profiles for monitoring data quality, drift, and model inputs or outputs without storing raw records.                             |
| [NannyML](https://github.com/NannyML/nannyml)                                  | 🔵 Open core   | NannyML is an open-source monitoring library with a commercial cloud for estimating post-deployment model performance, detecting covariate shift, and identifying data-quality changes when targets are delayed or absent.       |
| [Deepchecks](https://github.com/deepchecks/deepchecks)                         | 🔵 Open core   | Deepchecks is an open-source testing package with a commercial monitoring platform for data integrity, drift, model performance, validation suites, and alerting across machine-learning systems.                               |
| [Alibi Detect](https://github.com/SeldonIO/alibi-detect)                       | 🟢 Open source | Alibi Detect is an open-source Python library for outlier, adversarial, concept-drift, and data-drift detection on tabular, text, image, and time-series data.                                                                  |
| [Great Expectations](https://github.com/great-expectations/great_expectations) | 🟢 Open source | Great Expectations is an open-source framework for expressing, validating, documenting, and monitoring data-quality expectations in pipelines that may feed retrieval, evaluation, or model systems.                           |
| [Fairlearn](https://github.com/fairlearn/fairlearn)                            | 🟢 Open source | Fairlearn is an open-source Python package for assessing disparities with fairness metrics and for mitigating unfairness in supervised machine-learning models.                                                               |
| [AI Fairness 360](https://github.com/Trusted-AI/AIF360)                        | 🟢 Open source | AI Fairness 360 is an open-source toolkit from IBM and LF AI & Data containing fairness metrics, explanations, and bias-mitigation algorithms for datasets and machine-learning models.                                         |

## Discontinued and Historical Tools

**Discontinued and historical LLM observability tools** are products or repositories that influenced the field but are no longer generally available, independently operated, or actively maintained. They are retained to prevent stale recommendations and to document where capabilities moved; status notes reflect the last-reviewed date above.

| Tool                                                                                                              | Availability  | Description                                                                                                                                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------- | ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Literal AI](https://docs.literalai.com/more/migration-guide)                                                     | ⚫ Historical | Literal AI was a hosted LLM observability, evaluation, and prompt-management platform that was discontinued on October 31, 2025, with its official migration guide directing users to export data.                                |
| [WhyLabs Platform](https://docs.whylabs.ai/docs/open-source-project/)                                             | ⚫ Historical | WhyLabs Platform was a hosted AI observability service whose SaaS access ended in March 2025 after the company discontinued operations; its platform code and the whylogs and LangKit projects remain available.                  |
| [Humanloop](https://humanloop.com/docs/v5/changelog/2025/08.md)                                                   | ⚫ Historical | Humanloop was a prompt, evaluation, and observability platform that sunset on September 8, 2025 following the team's acquisition by Anthropic.                                                                                    |
| [Neptune](https://docs.neptune.ai/transition_hub)                                                                | ⚫ Historical | Neptune was an experiment-tracking platform whose hosted app and API were permanently shut down on March 5, 2026 following its acquisition by OpenAI.                                                                            |
| [TensorZero](https://github.com/tensorzero/tensorzero)                                                            | ⚫ Historical | TensorZero was an open-source LLM gateway, observability, evaluation, and optimization platform whose repository was archived and made read-only on June 12, 2026 after its final June release.                                  |
| [TruEra AI Observability Platform](https://truera.com/snowflake-is-acquiring-the-truera-ai-observability-platform/) | ⚫ Historical | TruEra AI Observability Platform provided model and LLM evaluation, monitoring, explainability, and debugging before Snowflake acquired the platform in 2024; the separate open-source TruLens project continues.                  |
| [Robust Intelligence](https://www.cisco.com/site/us/en/products/security/ai-defense/robust-intelligence-is-part-of-cisco/index.html) | ⚫ Historical | Robust Intelligence was an AI security platform for model validation, red teaming, and runtime protection that Cisco acquired in 2024 and incorporated into Cisco AI Defense and Foundation AI.                                  |
| [Aporia](https://coralogix.com/blog/coralogix-acquires-aporia/)                                                   | ⚫ Historical | Aporia was an AI observability and guardrails platform that Coralogix acquired in December 2024 and integrated into its AI research center and AI observability offering.                                                         |
| [CalypsoAI](https://www.f5.com/company/blog/securing-ai-the-future-is-runtime)                                    | ⚫ Historical | CalypsoAI was an AI runtime-security and red-teaming company acquired by F5 in September 2025, with its technology subsequently released through F5 AI Guardrails and F5 AI Red Team.                                            |

## Key Papers and Concepts

Foundational specifications and research for understanding distributed tracing, LLM evaluation, agent behavior, and reliable production monitoring.

- **Distributed tracing** — [Dapper, a Large-Scale Distributed Systems Tracing Infrastructure](https://research.google/pubs/dapper-a-large-scale-distributed-systems-tracing-infrastructure/) (Sigelman et al., 2010) describes the trace-and-span model that underlies modern application and LLM tracing.
- **OpenTelemetry traces** — the [OpenTelemetry Trace specification](https://opentelemetry.io/docs/specs/otel/trace/) defines tracers, spans, context, sampling, links, events, and processors in a vendor-neutral telemetry system.
- **Generative-AI semantic conventions** — the [OpenTelemetry GenAI conventions](https://github.com/open-telemetry/semantic-conventions/tree/main/docs/gen-ai) standardize attributes and operations for model, agent, tool, retrieval, and evaluation telemetry.
- **Context propagation** — [W3C Trace Context](https://www.w3.org/TR/trace-context/) standardizes the HTTP headers used to correlate work across services and agent boundaries.
- **Observability and control theory** — [On the General Theory of Control Systems](https://doi.org/10.1016/S1474-6670%2817%2970094-8) (Kalman, 1960) formalized observability as the ability to infer internal state from external outputs; software observability adapts the idea operationally.
- **LLM-as-a-judge** — [Judging LLM-as-a-Judge with MT-Bench and Chatbot Arena](https://arxiv.org/abs/2306.05685) (Zheng et al., 2023) studies model-based evaluation and documents biases that matter when online scorers are attached to traces.
- **G-Eval** — [G-Eval: NLG Evaluation using GPT-4 with Better Human Alignment](https://arxiv.org/abs/2303.16634) (Liu et al., 2023) presents a rubric-driven, model-based scoring method used by several evaluation systems.
- **RAG evaluation** — [RAGAS: Automated Evaluation of Retrieval Augmented Generation](https://arxiv.org/abs/2309.15217) (Es et al., 2023) defines reference-free quality signals often monitored over retrieval and generation traces.
- **Agent reasoning and action** — [ReAct: Synergizing Reasoning and Acting in Language Models](https://arxiv.org/abs/2210.03629) (Yao et al., 2022) motivates the interleaved model and tool trajectories that agent observability systems reconstruct.
- **Service reliability signals** — [The Four Golden Signals](https://sre.google/sre-book/monitoring-distributed-systems/) in Google's _Site Reliability Engineering_ connects latency, traffic, errors, and saturation to alerting; LLM systems add tokens, cost, quality, and safety.
- **Evaluation statistics** — [Adding Error Bars to Evals](https://arxiv.org/abs/2411.00640) (Miller, 2024) explains confidence intervals and significance, which remain necessary when dashboards aggregate noisy online evaluation scores.

## Glossary

Short definitions of terms used throughout this directory.

- **LLM observability** — collecting and analyzing traces, metrics, logs, evaluations, and feedback to understand an LLM application's behavior, quality, cost, safety, and operational health.
- **Monitoring** — tracking predefined measures and alert thresholds over time; monitoring reports known signals, while observability supports open-ended investigation using the underlying telemetry.
- **Trace** — a structured record of one end-to-end request, run, or workflow composed of related spans.
- **Span** — one timed operation within a trace, such as a model call, retrieval, tool execution, evaluator, or database query.
- **Generation** — one model inference operation, typically containing model metadata, input and output messages, token usage, timing, and finish reason.
- **Session / thread** — a grouping of related traces across a multi-turn conversation or long-running agent interaction.
- **Trajectory** — the ordered sequence of states, model calls, tool choices, observations, and actions taken by an agent.
- **Evaluation / scorer** — a deterministic, statistical, human, or model-based function that assigns a quality or safety result to an output, span, trace, session, or trajectory.
- **Online evaluation** — applying scorers to live or sampled production traffic rather than only to a fixed offline dataset.
- **OpenTelemetry (OTel)** — a vendor-neutral ecosystem of specifications, APIs, SDKs, collectors, and protocols for traces, metrics, and logs.
- **OTLP** — OpenTelemetry Protocol, the standard transport used to send telemetry between instrumented applications, collectors, and backends.
- **Semantic conventions** — standardized attribute names and span structures that give telemetry the same meaning across instrumentation libraries and backends.
- **OpenInference** — an OpenTelemetry-based semantic convention and instrumentation ecosystem focused on AI applications.
- **Context propagation** — carrying trace and span identifiers across process, service, queue, tool, and agent boundaries so operations remain correlated.
- **Sampling** — retaining only a selected fraction of traces or spans to control storage and processing cost; head sampling decides early, while tail sampling can use completed-trace attributes.
- **Prompt and response capture** — recording message content in telemetry; it is commonly opt-in because it can contain personal, confidential, or regulated data.
- **Cost attribution** — assigning model and infrastructure spend to a request, user, tenant, feature, agent, model, or team.
- **AI gateway** — an intermediary that routes and governs model traffic; a gateway may emit telemetry but is not automatically a complete observability backend.
- **APM (application performance monitoring)** — tooling for application latency, errors, throughput, dependencies, and infrastructure context; GenAI extensions add model- and agent-aware fields.
- **Drift** — a change over time in input data, retrieval content, model behavior, output distributions, user mix, or measured quality.

## Frequently Asked Questions

**What are LLM observability tools?**
LLM observability tools capture and analyze model calls, prompts, responses, retrievals, tool invocations, agent steps, token usage, latency, errors, costs, feedback, and evaluation results. They help teams debug individual requests and monitor aggregate production behavior.

**What is the difference between LLM monitoring, tracing, and evaluation?**
Monitoring tracks predefined time-series signals and alerts. Tracing reconstructs what happened during a request or agent run. Evaluation scores whether an output or trajectory met a quality, safety, or task criterion. A production stack often uses all three over the same telemetry.

**Which LLM observability tools are open source?**
Open-source or open-core options include Langfuse, Phoenix, Opik, Helicone, OpenLIT, Laminar, MLflow Tracing, LangWatch, Weave, AgentOps, SigNoz, and OpenObserve. Availability markers distinguish open source, open weights, open core, commercial, and historical entries.

**How do I observe an AI agent?**
Create a root span for the run or session, child spans for model calls, tools, retrievals, handoffs, memory, and evaluators, and propagate trace context across services. Record outcomes, errors, token use, latency, model and prompt versions, while redacting sensitive content. Agent-focused tools then reconstruct the trajectory or session.

**Why does OpenTelemetry matter for LLM observability?**
OpenTelemetry separates instrumentation from storage and visualization. Its GenAI semantic conventions provide common field names for models, tokens, messages, tools, agents, and evaluations, while OTLP lets the same telemetry flow through collectors to different compatible backends.

**Is an AI gateway the same as an observability platform?**
No. A gateway is in the request path and primarily routes or governs model traffic. It can produce comprehensive request logs and metrics, but an observability platform typically adds distributed traces, session exploration, evaluation, feedback, investigation, dashboards, and alerts across components that never pass through the gateway.

**How should sensitive prompts and responses be handled?**
Treat message content and tool arguments as potentially sensitive. Keep content capture disabled unless needed, minimize retained fields, redact or tokenize secrets and personal data in the SDK or collector, apply access controls and retention limits, and verify each vendor's data-processing and deployment options.

**What should I monitor in production?**
At minimum, monitor request volume, errors, latency and time to first token, token use, estimated and billed cost, model and prompt versions, tool failures, user feedback, and a small calibrated set of quality and safety scores. Add trace sampling and alerts that preserve enough context for investigation.

**How should I choose an LLM observability tool?**
Start with required signals, supported frameworks and languages, OpenTelemetry compatibility, self-hosting and data residency, content-redaction controls, evaluation needs, retention, query and alert workflows, expected trace volume, and total storage and scoring cost. Validate the shortlist against representative production traces.

**How should I cite this list?**
See [Citing This List](#citing-this-list). When citing an individual tool or technical claim, prefer the tool's own repository, documentation, standard, or paper linked in its row.

## Methodology

How this directory is built and maintained. This section exists so readers and automated systems can judge its scope, boundaries, and potential conflicts.

- **Scope.** Included entities have a first-class role in observing LLM applications or AI agents: instrumentation, tracing, production monitoring, online quality evaluation, gateways that emit operational telemetry, cost and performance measurement, runtime security monitoring, or directly adjacent classic ML monitoring.
- **Category boundaries.** Tracing records execution; evaluation scores behavior; gateways route and govern traffic; security tools detect or enforce threat and policy controls; classic APM correlates AI telemetry with software and infrastructure. Products spanning boundaries are placed where their primary linked offering is most useful and are not repeated.
- **Inclusion criteria.** Open-source projects should show recent activity or lasting reference value. Commercial products must have an accessible official product or documentation page and a generally available or clearly labeled preview offering. A repository, package, feature, or product is one entity per row.
- **Exclusions.** Generic logging libraries, model providers without an observability surface, inactive side projects without lasting reference value, unverifiable vendor lists, pure offline benchmark suites, and unsupported claims are excluded. Red-teaming and evaluation frameworks appear only where independently relevant to monitored production controls or quality signals.
- **Availability markers.** 🟢 means an OSI-style open-source primary artifact; 🟠 means downloadable weights under a non-OSI model license; 🔵 means an open-source component paired with a commercial platform; 🔒 means commercial or closed source; ⚫ means historical, absorbed, archived, or discontinued.
- **Ordering.** Entries are ordered by editorial judgment of category fit, functional breadth, adoption, and usefulness rather than alphabetically. Ordering is not a ranking, recommendation, or paid placement.
- **Verification.** Every row links to a primary source and was manually checked against official repositories, documentation, product pages, standards, or acquisition and shutdown notices as of **2026-07-16**. Descriptions use attributable capabilities and avoid unsupported superlatives.
- **Monthly review cadence.** The directory is reviewed during the first week of every month. Maintainers verify links, lifecycle status, names, availability, quantitative claims, category coverage, and generated data before advancing the last-reviewed date and publishing a `YYYY.MM` release. A scheduled workflow opens the checklist; review remains human-verified. See [`MAINTENANCE.md`](MAINTENANCE.md).
- **Counts.** The stated **11 categories** include ten active categories plus the historical category. The stated **120 entries** count each tool-table row once, including nine historical rows; papers, glossary items, FAQ entries, and navigation rows are not counted.
- **Lifecycle handling.** Products that shut down, are archived, or cease to exist independently move to [Discontinued and Historical Tools](#discontinued-and-historical-tools) with a primary-source status note instead of being silently removed.
- **Corrections.** Product scope and lifecycle change quickly. Open an [issue](https://github.com/aglio-lab/llm-observability-tools/issues) or [pull request](https://github.com/aglio-lab/llm-observability-tools/pulls) with a primary source, and factual corrections will be prioritized.
- **Editorial independence.** This directory is maintained by aglio-lab. Every entry follows the same sourcing, wording, and ordering rules, and no placement is sold.

## Related Lists and Resources

- [AI Evaluation Tools](https://github.com/aglio-lab/ai-evaluation-tools) — evaluation frameworks, platforms, metrics, judge models, and benchmarks.
- [AI Red Teaming Tools](https://github.com/aglio-lab/ai-red-teaming-tools) — adversarial testing, jailbreak, prompt-injection, and vulnerability assessment tools.
- [AI Governance Tools](https://github.com/aglio-lab/ai-governance-tools) — governance, compliance, model inventory, risk, and policy-management tools.
- [AI Agent Frameworks](https://github.com/aglio-lab/ai-agent-frameworks) — frameworks and runtimes for building AI agents and multi-agent systems.
- [LLM Fine-Tuning Tools](https://github.com/aglio-lab/llm-fine-tuning-tools) — training, adaptation, preference optimization, and fine-tuning infrastructure.
- [RAG Retrieval Tools](https://github.com/aglio-lab/rag-retrieval-tools) — retrieval, indexing, reranking, vector search, and RAG infrastructure.
- [Context Engineering Tools](https://github.com/aglio-lab/context-engineering-tools) — prompt, memory, context assembly, compression, and context-management tools.
- [OpenTelemetry](https://opentelemetry.io/) — vendor-neutral telemetry specifications, SDKs, and collector ecosystem.
- [OpenInference](https://github.com/Arize-ai/openinference) — AI-focused semantic conventions and OpenTelemetry instrumentation.

---

## Citing This List

If you reference this directory in an article, paper, procurement document, or AI-generated answer, please cite it as:

> _The Comprehensive List of LLM Observability Tools_ (2026). A curated, source-linked directory of open-source and commercial tools for tracing, monitoring, debugging, and evaluating LLM applications and AI agents. GitHub. https://github.com/aglio-lab/llm-observability-tools

BibTeX:

```bibtex
@misc{llm-observability-tools,
  title        = {The Comprehensive List of LLM Observability Tools},
  year         = {2026},
  howpublished = {\url{https://github.com/aglio-lab/llm-observability-tools}},
  note         = {A curated, source-linked directory of LLM observability tools. Accessed: 2026-07-16}
}
```

For reproducible citations of a changing directory, cite a specific commit permalink or release tag. When citing an individual tool, always prefer its own repository, documentation, specification, or paper linked in the relevant row.

## Contributing

Contributions are welcome through [issues](https://github.com/aglio-lab/llm-observability-tools/issues) and [pull requests](https://github.com/aglio-lab/llm-observability-tools/pulls). In short:

1. Add one independently verifiable entity to the most specific matching category.
2. Include the correct availability marker (🟢 / 🟠 / 🔵 / 🔒) and a neutral, factual, complete sentence that starts with the entity's name.
3. Link the primary source first and use documentation or papers as secondary links.
4. Keep observability and tracing distinct from evaluation, gateways, security controls, and classic APM.
5. Report shutdowns, acquisitions, archives, and material renames with an official source.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the maintainers have waived all copyright and related or neighboring rights to this directory under the [CC0 1.0 Universal Public Domain Dedication](https://creativecommons.org/publicdomain/zero/1.0/).

This work is published from the United States. Linked projects, product names, documentation, papers, trademarks, and other third-party materials retain their respective licenses and rights.
