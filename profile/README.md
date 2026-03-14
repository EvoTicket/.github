<!--
EvoTicket Organization Profile README
Place this file at: .github/profile/README.md
-->

<p align="center">
  <img src="https://img.shields.io/badge/Status-Active%20Development-2563eb?style=for-the-badge" alt="Status" />
  <img src="https://img.shields.io/badge/Architecture-Microservices-0f766e?style=for-the-badge" alt="Architecture" />
  <img src="https://img.shields.io/badge/Domain-E%20Ticketing-7c3aed?style=for-the-badge" alt="Domain" />
  <img src="https://img.shields.io/badge/Stack-Spring%20Boot%20%7C%20Next.js%20%7C%20Blockchain-f59e0b?style=for-the-badge" alt="Stack" />
</p>

<h1 align="center">EvoTicket</h1>

<p align="center">
  A hybrid event ticketing platform that combines modern Web2 usability with Blockchain-based ownership control and AI-powered user assistance.
</p>

<p align="center">
  Graduation Thesis Project • Online Event Ticket Distribution and Management System
</p>

---

## Quick Links

<p align="center">
  <a href="https://github.com/EvoTicket">Organization</a> •
  <a href="https://github.com/EvoTicket/EvoTicket_FE">Frontend</a> •
  <a href="https://github.com/EvoTicket/Order-Service">Order Service</a> •
  <a href="https://github.com/EvoTicket/Inventory-Service">Inventory Service</a> •
  <a href="https://github.com/EvoTicket/Payment-Service">Payment Service</a> •
  <a href="https://github.com/EvoTicket/IAM-Service">IAM Service</a> •
  <a href="https://github.com/EvoTicket/Api-Gateway">API Gateway</a> •
  <a href="https://github.com/EvoTicket/Notification-Service">Notification Service</a> •
  <a href="https://github.com/EvoTicket/Server-Discovery">Server Discovery</a>
</p>

> **Private repositories**
> - `blockchain-contracts`
> - `web3-worker-service`

---

## About the Organization

**EvoTicket** is the official GitHub organization for our graduation thesis project.

The project focuses on building a **hybrid online ticketing system** that addresses three major challenges in event ticketing:

1. **Ticket scalping and uncontrolled resale**
2. **Ticket authenticity and secure check-in**
3. **Poor user support and discovery experience**

To address these issues, EvoTicket combines:

- **Web2 usability** for seamless browsing, ordering, and payment
- **Blockchain-based ticket ownership** for controlled ticket lifecycle management
- **Custodial wallet architecture** for better control over transfer and resale constraints
- **AI-powered chatbot and recommendation features** to improve user interaction and event discovery

---

## Thesis Scope

EvoTicket is designed as an **online event ticket distribution and management platform** with two major perspectives:

### 1. Buyer side
For end users who want to:
- browse events
- view event details
- select tickets or seats
- complete payment
- view owned tickets
- verify on-chain proof
- access resale under platform-controlled rules
- use AI support features

### 2. Organizer side
For event organizers who need to:
- create and manage events
- manage ticket types and ticket availability
- monitor sales
- view simplified operational dashboards
- handle payout-related views at a basic level

### 3. Checker side
For staff members responsible for:
- scanning dynamic QR codes
- validating ticket entry
- preventing reused or invalid tickets
- handling fast, low-friction check-in operations

---

## Core System Goals

EvoTicket is built around the following system goals:

### Controlled ticket lifecycle
Tickets are not treated as simple static database records.  
Instead, the system aims to manage ticket ownership more strictly across:
- purchase
- payment confirmation
- minting
- controlled resale
- check-in

### Anti-scalping support
The platform is designed to reduce speculative ticket resale through:
- custodial wallet control
- constrained ownership transfer
- marketplace-based resale flow
- price-cap-aware resale rules

### Ticket authenticity and secure entry
The platform improves ticket verification using:
- dynamic QR generation
- TOTP-based validation
- controlled check-in flow
- used/invalid ticket blocking

### Practical hybrid architecture
Rather than building a pure Web3 experience, EvoTicket follows a **hybrid approach**:
- users interact through familiar Web2 flows
- blockchain operations are executed underneath by the system
- on-chain proof is preserved without exposing unnecessary wallet complexity to end users

---

## System Architecture Overview

EvoTicket follows a **microservices-oriented architecture** with a hybrid Web2–Web3 design.

### Main backend services
- **IAM-Service**  
  Authentication, authorization, user profile, organization profile

- **Inventory-Service**  
  Event management, ticket types, reviews, favorites, event-facing content

- **Order-Service**  
  Order creation, booking flow, voucher application, downstream event production

- **Payment-Service**  
  Payment link generation, callback/webhook handling, payment verification

- **Notification-Service**  
  Notification-related flow and asynchronous user communication

- **Api-Gateway**  
  Unified entry point for backend services

- **Server-Discovery**  
  Service registration and discovery

### Web3-related components
- **blockchain-contracts** *(private)*  
  Smart contracts for ticket ownership and controlled marketplace flow

- **web3-worker-service** *(private)*  
  Worker responsible for hybrid event consumption, wallet integration, and minting flow

### Frontend
- **EvoTicket_FE**  
  Main frontend repository that contains the user-facing experience across:
    - buyer flows
    - organizer flows
    - checker flows

### Documentation
- **documentation**  
  Architecture notes, planning artifacts, WBS, integration notes, and technical documentation

---

## Repository Map

| Repository | Purpose | Visibility |
|---|---|---|
| [`IAM-Service`](https://github.com/EvoTicket/IAM-Service) | Identity, authentication, authorization | Public |
| [`Api-Gateway`](https://github.com/EvoTicket/Api-Gateway) | Gateway and routing layer | Public |
| [`Notification-Service`](https://github.com/EvoTicket/Notification-Service) | Notification-related processing | Public |
| [`Server-Discovery`](https://github.com/EvoTicket/Server-Discovery) | Service discovery | Public |
| [`Payment-Service`](https://github.com/EvoTicket/Payment-Service) | Payment provider integration and callback handling | Public |
| [`Order-Service`](https://github.com/EvoTicket/Order-Service) | Order, booking, voucher, downstream event generation | Public |
| [`Inventory-Service`](https://github.com/EvoTicket/Inventory-Service) | Events, ticket types, reviews, favorites | Public |
| `blockchain-contracts` | Smart contracts for ticketing and marketplace | Private |
| `web3-worker-service` | Minting and hybrid Web2–Web3 integration worker | Private |
| [`EvoTicket_FE`](https://github.com/EvoTicket/EvoTicket_FE) | Frontend application | Public |
| [`documentation`](https://github.com/EvoTicket/documentation) | Project documentation and technical notes | Public |

---

## Technology Stack

### Backend
- Java
- Spring Boot
- Spring Cloud
- PostgreSQL
- Redis

### Frontend
- TypeScript
- Next.js
- Modern component-based UI architecture

### Blockchain
- TypeScript
- Hardhat
- Solidity
- Polygon Amoy
- ERC-1155

### AI
- Gemini-based integration
- Chatbot and recommendation-oriented flow

---

## Current Direction

The current implementation direction focuses on the following critical flows:

- organizer creates and manages events
- buyer selects tickets or seats and places an order
- payment is confirmed through provider callback/webhook
- hybrid event flow triggers minting
- user can view ticket ownership proof
- dynamic QR check-in validates entry
- controlled resale is executed through the platform marketplace
- AI assists users with event-related support and discovery

---

## Notes

- This organization is maintained as the central technical workspace for the EvoTicket graduation thesis project.
- Some repositories are intentionally private due to implementation sensitivity and integration boundaries.
- Public repositories may still be under active development and subject to ongoing refactoring.

---

<p align="center">
  <sub>
    Built and maintained for the EvoTicket Graduation Thesis Project.<br/>
    Hybrid Ticketing • Controlled Ownership • Secure Check-in • AI Assistance
  </sub>
</p>