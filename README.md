# Second-Hand PC Parts App

https://pcmarket.app

## Table of Contents

- [Introduction](#introduction)
- [Problem Statement](#problem-statement)
- [Solution Overview](#solution-overview)
- [Development Process](#development-process)
	- [Initial Design](#initial-design-microservices-architecture)
	- [Iteration 1 (Extension)](#iteration-1-extension)
	- [Final Design](#final-design-monolithic-architecture)
- [Deployment](#deployment)
	- [Infrastructure](#infrastructure)
	- [Dockerised Services](#dockerised-services)
	- [Cloudflare Integration](#cloudflare-integration)

## Introduction

This is a personal project that aimed to bridge the gap between broader platforms like eBay and Facebook Marketplace in Australia by creating a dedicated marketplace for buying and selling pre-owned computer components. The primary goal of this project was to learn the entire full-stack development lifecycle, from conception to production deployment, while exploring potential startup ideas.

## Problem Statement

The current market lacks a dedicated platform for purchasing and selling second-hand PC parts. This results in:

- Inefficiencies in finding rare or specific components
- Difficulty in verifying the authenticity of items being sold
- Limited opportunities for buyers to connect with sellers directly

## Solution Overview

- A curated marketplace for buying and selling pre-owned PC parts
- User profiles and ratings system for credibility and trust
- Search filters and categorization for easy discovery
- Real-time chat functionality, enabling users to communicate with each other directly within the platform

## Development Process

Throughout this project, I prioritized learning the full stack development lifecycle, from initial design to production deployment, while also exploring a viable startup concept. I deliberately structured the development process in iterations to manage complexity and gain focused experience.

### Initial Design (_Microservices Architecture_)

My initial design focused on a _Microservices Architecture_ to leverage the benefits of scalability, modularity, and deeper understanding of common architectural patterns. This was implemented with the following services:

- **_Frontend Service_**: Built using Next.js, Tailwind CSS, and TypeScript – chosen for their widespread adoption and suitability for larger-scale applications.
- **_Orchestrator Service_**: Utilized Next.js SSR BFF (Backend for Frontend) to facilitate efficient data shaping and service orchestration, leveraging shared types for improved developer productivity.
- **_API Service_**: Implemented using C# .NET ASP.NET with EF Core to gain familiarity with the flip side of Spring Boot, an enterprise backend framework I already had exposure to.
- **_Auth Service_**: Developed a custom FastAPI JWT authentication service to understand the implementation details of pre-built authentication solutions.
- **_Database Service_**: PostgreSQL – selected for its reliability and established ecosystem.
- **_Cache Service_**: Redis – employed for optimizing data retrieval.

### Iteration 1 (Extension)

- **_Chat Service_**: Built using GoLang with the Gorilla library and Jackc PGX, prioritizing performance and concurrency through a high-performance language.
- **_Orchestrator Service_**: Replaced the Next.js SSR BFF with a decoupled Node.js Fastify orchestrator to reduce load on the frontend server and gain experience with Node.js.

### Final Design (Monolithic Architecture)

As the project grew and its complexity increased, I realized managing multiple microservices alone became unsustainable. Maintaining a microservices architecture as a solo developer demanded excessive time and resources. I therefore refactored the project into a streamlined, monolithic architecture to simplify maintenance, reduce overhead, and improve development efficiency by doing the following:

- Restored the initial Next.js SSR BFF backend for the frontend layer, eliminating the Node.js orchestrator service.
- Unified all backend operations (API, Auth, and Chat) into a single FastAPI service.
- Simplified authentication by utilizing Firebase’s reliable authentication solution.

## Deployment

### Infrastructure

- Server: Self-hosted Debian server
- Containerization: Docker for containerizing applications and services
- Reverse Proxy: Dockerised Nginx gateway for routing incoming traffic

### Dockerised Services

- Environment Setup: Set up two separate environments (Dev and Prod) on the same server to enable efficient deployment and testing
- Docker Compose: Utilize Docker Compose to define and manage services, configurations, and dependencies across both environments

### Cloudflare Integration

- Tunneling: Cloudflare tunnel used for routing incoming traffic from the public internet to the self-hosted server
- Security and Performance Optimization: Leveraged Cloudflare's security features (e.g., WAF, SSL/TLS encryption) and performance optimization tools to protect and accelerate the application