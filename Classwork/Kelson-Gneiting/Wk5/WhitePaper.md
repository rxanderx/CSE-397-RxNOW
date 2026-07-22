# White paper Interfaces

## Title: Comparative Analysis of REST APIs, OSI Model, and Network Protocol Suites
**Name:** Kelson Gneiting  
**Course/Semester/Section**: CSE 397 Professional Career Projects: Fall 2024: Section 31  
**Instructor**: Brother Clements  
**Date**: July 21, 2026

## Summary:
This paper compares three interface layers used in modern computing: REST APIs (application interface), the OSI model (conceptual architecture), and protocol suites such as TCP/IP (operational communication rules). OSI remains a design and troubleshooting framework, while REST and TCP/IP dominate practical implementation. The central takeaway is that these are complementary, not competing, abstractions.

## Introduction:
The purpose of this research is to evaluate where APIs, OSI, and protocols overlap and where they serve distinct roles. The research focused on educational, industry, and primary technical sources to identify practical use cases for software engineering and network operations. As one source states, REST APIs are "all about communication specifically between a client and a server" (YouTube REST overview, Source 3), while OSI provides a layered model for broader system interoperability.

## Definitions:
- API (Application Programming Interface): A defined way for software systems to exchange data and operations.
- REST API: A web API style that uses HTTP methods (GET, POST, PUT, DELETE) on resource endpoints.
- OSI Model: A seven-layer conceptual framework used to describe and troubleshoot network communication.
- Protocol Suite (for example, TCP/IP): A set of networking protocols that work together to move data end to end.

## Overview:
OSI originated from ISO and ITU-T standardization work and formalized a seven-layer design for interoperable systems. Source material notes that "each layer adds encapsulation information (header) to the incoming information before it is passed to the lower layer" (Wikipedia OSI protocols, Source 2). A primary scholarly source further emphasizes that "the basic idea of layering is that each layer adds value to services provided by the set of lower layers" (Zimmermann, IEEE, Source 4).

In practice, the native OSI protocol family saw limited adoption: "the protocols originally conceived for the model did not gain popularity" (Wikipedia OSI protocols, Source 2), and operational networking converged on TCP/IP. Even so, the model remains useful because, in plain terms, "the OSI provides a standard for different computer systems to be able to communicate with each other" (Cloudflare Learning Center, Source 5).

REST APIs evolved later as web-centric interfaces over HTTP. Their interaction model is endpoint-driven and method-based, where "CRUD stands for create read update and delete" (YouTube REST overview, Source 3) and maps to HTTP verbs (POST, GET, PUT, DELETE).

## Strength and Weakness:
REST API strengths include broad tooling, cloud compatibility, and rapid integration; requests include endpoint, method, and metadata where "headers" can carry authentication context (YouTube REST overview, Source 3). A weakness is dependency on careful API design and versioning discipline.

OSI strengths include conceptual clarity, teaching value, and fault isolation: "If the problem can be narrowed down to one specific layer of the model, a lot of unnecessary work can be avoided" (Cloudflare Learning Center, Source 5). Its weakness is that it is mostly descriptive in modern deployments rather than a directly implemented full stack.

Protocol-suite strengths (e.g., TCP/IP) include real-world maturity, scalability, and deep vendor support. A common weakness appears in connectionless behavior tradeoffs: "Connectionless mode provides only best-effort service" (Wikipedia OSI protocols, Source 2) and may permit loss without guaranteed correction.

## Usage and Applicability:
- Where is it used?
REST APIs are used in web apps, mobile backends, SaaS integrations, and microservices. OSI is used in networking education, architecture documentation, and layered troubleshooting. Protocol suites are used in every IP-based network, from enterprise LANs to internet-scale services.

- When would it be used?
Use REST APIs when applications need structured service-to-service or client-to-server exchange. Use OSI when diagnosing or explaining failures across layers. Use protocol-level analysis when tuning reliability, latency, routing, and transport behavior in production networks.

## Comparison:
- REST APIs vs alternatives:
GraphQL, gRPC, SOAP.
- OSI model vs alternatives:
TCP/IP 4-layer model, vendor-specific operational reference stacks.
- Protocol suites vs alternatives:
Legacy OSI protocol suite components (e.g., X.400, X.500), specialized industrial protocols, and application-specific overlays.

REST is implementation-facing, OSI is analysis-facing, and protocol suites are operations-facing. Together they provide a complete interface perspective from application intent to packet delivery.

## Summary:
For most software teams, build with REST APIs, deploy on TCP/IP, and troubleshoot with OSI. This combined approach aligns with current industry practice while preserving conceptual rigor. The evidence shows OSI remains highly relevant as a framework even though internet protocols dominate implementation. Recommendation: treat these as layered tools in one engineering workflow rather than as mutually exclusive choices.

## References:
1. LLM (analysis support): GitHub Copilot (GPT-5.3-Codex), "Analytical synthesis of interfaces research," generated July 21, 2026.
2. Wiki: Wikipedia, "OSI protocols." https://en.wikipedia.org/wiki/OSI_protocols
3. Video: YouTube, "REST APIs Overview." https://www.youtube.com/watch?v=09od8C-Fd-A
4. Scholarly paper (primary source): Zimmermann, H. "OSI Reference Model." IEEE. https://ieeexplore.ieee.org/abstract/document/1094702
5. Website: Cloudflare Learning Center, "What is the OSI model?" https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/
