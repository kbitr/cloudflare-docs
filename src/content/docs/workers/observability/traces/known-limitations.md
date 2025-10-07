---
pcx_content_type: navigation
title: Known limitations 
sidebar:
  order: 3
  group:
    hideIndex: false
---

Workers tracing is currently in open beta. This page documents current limitations and any upcoming features on our roadmap. To provide more feedback and feature requests please [reach out to us](link).

### Trace context propagation not yet supported
One of the key aspects of distributed tracing is ensuring trace context flows across service boundaries and automatically linking spans together to create complete, end-to-end visibility. When fully implemented, our automatic trace context propagation will follow [W3C standards](https://www.w3.org/TR/trace-context/) to ensure compatibility across your existing tools and services. 

Without trace context propagation, you will also see an additional trace whenever your Worker is making a call to another Worker via service bindings or to a Durable Object. 

### Missing instrumentation for some spans and attributes 
We are adding more automatic instrumentation for every part of the Workers platform. While we first want to give you visibility into the duration of every operation within your request, we also planning to add more detailed attributes on each span. You can find a complete list of what is already instrumented [here](/workers/observability/traces/spans-and-attributes). Your feedback on what’s missing will help us prioritize accordingly.

### Support for custom spans and attributes: 
While automatic instrumentation covers the platform interactions, we know you need visibility into your own application logic too. We're working to support the [OpenTelemetry API](https://www.npmjs.com/package/@opentelemetry/api) to make it easier for you to instrument custom spans within your application. 

### 