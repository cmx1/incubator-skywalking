# Observability Analysis Platform
OAP(Observability Analysis Platform) is a new concept, which starts in SkyWalking 6.x. OAP replaces the 
old SkyWalking whole backend. The capabilities of the platform are following.

## OAP capabilities
<img src="https://skywalkingtest.github.io/page-resources/6_overview.png"/>

In SkyWalking 6 series, OAP accepts data from more sources, which belongs two groups: **Tracing** and **Metric**.

- **Tracing**. Including, SkyWalking native data formats. Zipkin v1,v2 data formats and Jaeger data formats.
- **Metric**. SkyWalking integrates with Service Mesh platforms, such as Istio, Envoy, Linkerd, to provide observability from data panel 
or control panel. Also, SkyWalking native agents can run in metric mode, which highly improve the 
performance.

At the same time by using any integration solution provided, such as SkyWalking log plugin or toolkits, 
SkyWalking provides visualization integration for binding tracing and logging together by using the 
trace id and span id.

As usual, all services provided by gRPC and HTTP protocol to make integration easier for unsupported ecosystem.

## Tracing in OAP
Tracing in OAP has two ways to process.
1. Traditional way in SkyWalking 5 series. Format tracing data in SkyWalking trace segment and span formats, 
even for Zipkin data format. The AOP analysis the segments to get metrics, and push the metric data into
the streaming aggregation.
1. Consider tracing as some kinds of logging only. Just provide save and visualization capabilities for trace. 

## Metric in OAP
Metric in OAP is totally new feature in 6 series. Build observability for a distributed system based on metric of connected nodes.
No tracing data is required.

Metric data are aggregated inside AOP cluster in streaming mode. See about [Observability Analysis Language](oal.md),
which provides the easy way to do aggregation and analysis in script style. 