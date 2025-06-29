# CS-230 Portfolio - Operating Platforms Coursework by Ian
# Project Reflection: “Draw It or Lose It” Design

**1. Client & Software Requirements**  
**Client:** The studio behind _Draw It or Lose It_—a gaming startup aiming to launch a real-time, browser-based multiplayer drawing game.  
**Software Goal:** Architect a cross-platform web application that supports low-latency drawing events over WebSockets, RESTful player/account services, horizontal scaling under peak loads, and secure user management.

---

**2. What I Did Particularly Well**  
- Translated high-level business goals (“engaging, competitive, shareable”) into crisp functional requirements and nonfunctional constraints (latency, availability, data privacy).  
- Applied OOP rigor: drafted a UML domain model with a reusable Entity base class and clear aggregation/inheritance relationships.  
- Compiled a thorough platform evaluation matrix (macOS, Linux, Windows, mobile) to guide technology choices.  
- Crafted targeted recommendations (microservices + Docker/Kubernetes, hybrid SQL/NoSQL + cache, service mesh, TLS + OAuth2) that align with industry best practices.

---

**3. How the Design Document Guided Coding**  
- **Architectural Clarity:** Defining logical tiers (UI → API Gateway → microservices → data stores) up front meant I scaffolded packages and modules to match real system boundaries.  
- **Constraint-Driven Development:** Specifying sub-100 ms round-trip requirements and security protocols ahead of time forced me to benchmark WebSocket libs and integrate JWT auth before feature code.  
- **Traceability:** Every class, REST endpoint, and WebSocket event was traceable back to a business requirement or performance constraint, minimizing guesswork and rework.

---

**4. One Part to Revise & Improvement Plan**  
**Section:** _System Architecture View_ (left blank in the template)  
**Improvements:**  
1. Add a logical topology diagram (client ↔ API gateway ↔ service mesh ↔ data stores).  
2. Annotate inter-service protocols (REST vs. WebSocket) and failover paths.  
3. Include capacity-planning notes (pod counts, CPU/memory quotas per microservice).

---

**5. Interpreting & Implementing User Needs**  
- **User Research:** Mapped “casual vs. enthusiast” personas to prioritize real-time sketch accuracy, shareable results, and quick reconnections.  
- **Feature Translation:** Turned “social share” into a REST endpoint for exporting PNG snapshots and OAuth2-mediated posting to social networks.  
- **Importance:** Centering on real user workflows drives adoption—without low latency, intuitive reconnects, and seamless sharing, players drop off and churn spikes.

---

**6. Software Design Approach & Future Techniques**  
- **Current Strategy:**  
  1. Capture personas & user stories → define functional/nonfunctional requirements  
  2. Model domain (UML classes, aggregation, inheritance) → sketch sequence flows  
  3. Select architecture (microservices + container orchestration) → enumerate APIs/protocols  
  4. Evaluate platforms → recommend dev toolchain and deployment pipeline  
- **Future Enhancements:**  
  - **Event Storming** workshop to uncover nuanced domain events (e.g., “player timeout,” “replay request”).  
  - **User Journey Mapping** for end-to-end flows (account creation → matchmaking → replay → share).  
  - **Behavior-Driven Development** (Cucumber/Gherkin) to lock feature specifications to automated tests.  
  - **Infrastructure as Code** (Terraform/Helm charts) to version-control and templatize deployments from day one.
