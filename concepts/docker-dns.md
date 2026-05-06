---
title: "Docker DNS"
category: concepts
tags: [infrastructure, docker, networking]
sources: [deployment-guide]
updated: 2026-05-06
---

# Concept: Docker DNS

## Definition
An embedded DNS server provided by Docker for containers attached to a user-defined bridge network (e.g., `travery-network`).

## Mechanism
- **Service Discovery**: Allows containers to resolve each other by their **container names** instead of ephemeral IP addresses.
- **Example**: The [[Spring-Boot]] app connects to the database using `jdbc:postgresql://postgres:5432` where `postgres` is the container name.

## Benefits
- **Plug-and-Play**: Eliminates the need for manual IP configuration.
- **Isolation**: Internal communication remains within the private bridge network, invisible to the public internet.

## References
- [[deployment-guide]]
- [[travery-backend]]
