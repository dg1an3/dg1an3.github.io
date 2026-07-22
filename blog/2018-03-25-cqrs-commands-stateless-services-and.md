---
layout: default
title: "CQRS Commands, stateless services, and thin clients"
date: 2018-03-25
original_url: http://www.dg1an3.net/2018/03/cqrs-commands-stateless-services-and.html
---

Looking at the CQRS architectural pattern, there are interactions that maybe I didn’t fully understand. Like if the target of queries/commands are the Managers from the IDesign methodology, this kinda has a direct implication on the statefulness of the Manager vs the statelessness of the client. So you need a thin client with little state, and commands are routed to the Manager in the backend, and any updates then come back to the thin client as a response object or update message.
