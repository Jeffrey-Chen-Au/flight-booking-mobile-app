# Flight Booking Mobile App

> 📱 Production-grade mobile application for flight search and booking,
> built with React Native (Expo) and integrated with a legacy backend
> system.

------------------------------------------------------------------------

## 🚀 Overview

This project is a **real-world flight booking application** designed for
a travel business (name anonymized).

The app supports:

-   unified flight search\
-   mixed inventory (internal deals + agent tickets)\
-   multi-path booking flows\
-   passenger management\
-   order tracking

------------------------------------------------------------------------

## 🏗️ System Architecture

![Architecture Diagram](./docs/architecture_level2.png)

------------------------------------------------------------------------

## ✈️ Features

-   🔍 Flight search (origin, destination, date, passengers)\
-   💰 Mixed results (internal deals + agent tickets)\
-   📄 Flight details with branching logic\
-   🧾 Multi-step booking flows\
-   👤 Passenger management\
-   📦 Order tracking

------------------------------------------------------------------------

## 🔄 User Flow

Search → Results → Details → (Branch)

-   Internal Deal → Web Checkout\
-   Agent Ticket → Native Booking Flow

------------------------------------------------------------------------

## 🔀 Booking Flow Overview

- Shared search experience
- Branching at detail stage:
  - Internal Deals → Web Checkout
  - Agent Tickets → Native Booking Flow

------------------------------------------------------------------------

## 🧩 Booking Architecture

### Shared Discovery Flow

`flightresults → flightdetails`

-   Results include both internal deals and agent-backed tickets\
-   Branching occurs at the detail screen

------------------------------------------------------------------------

### 1. Internal Deal Flow (Gdeals)

`flightresults → flightdetails → webview checkout`

-   Native browsing experience\
-   Checkout handled via WebView\
-   Shared session between app and web\
-   Uses existing backend + database

------------------------------------------------------------------------

### 2. Agent API Flow (Ypsilon)

`flightresults → flightdetails → flightbooking → flightpassenger → flightconfirm`

-   Fully native booking experience\
-   App communicates with backend\
-   Backend communicates with agent APIs\
-   Multi-step validation and passenger input

------------------------------------------------------------------------

## 🔄 Data Flow (Agent Booking Example)

1.  User selects flight → app creates booking payload\
2.  App sends request → backend API\
3.  Backend:
    - validates request\
    - calls external agent API\
    - transforms and normalizes provider responses
4.  Response normalized into unified format\
5.  Booking stored in database\
6.  Confirmation returned → app updates UI

------------------------------------------------------------------------

## 🧠 Key Design Decisions

### WebView vs Native Checkout

-   Reused existing web checkout to avoid duplicating complex business
    logic\
-   Ensured consistency with web platform\
-   Reduced development risk

### Backend-Mediated API Integration

-   Prevented direct client-to-provider communication\
-   Centralized API logic and error handling

### Branching Architecture

-   Unified search experience\
-   Deferred complexity to detail stage

------------------------------------------------------------------------

## ⚠️ Engineering Challenges

### Mixed Inventory Handling

-   Unified UI across different ticket types\
-   Preserved different booking behaviors

### Flow Branching

-   Managed routing and state across divergent flows

### Hybrid Web + Native Checkout

-   Maintained session continuity across app and WebView

### Backend-Mediated APIs

-   Centralized provider integration in backend

------------------------------------------------------------------------

## ⚠️ Failure Handling

-   Prevented duplicate submissions using request locking\
-   Managed API failures with retry and error states\
-   Preserved state across navigation steps\
-   Handled partial failures with clear user feedback

------------------------------------------------------------------------

## 📊 Production Considerations

-   Real transaction handling\
-   API latency management\
-   UX loading states\
-   Consistency with web platform

------------------------------------------------------------------------

## 🔧 Future Improvements

-   Introduce BFF layer\
-   Add caching for search results\
-   Improve analytics tracking\
-   Add offline handling

------------------------------------------------------------------------

## 🔍 Retrospective

-   Would introduce BFF earlier\
-   Improve backend response standardization\
-   Reduce frontend normalization complexity

------------------------------------------------------------------------

## ⚠️ Notes

-   Architecture-focused repository\
-   Sensitive logic removed\
-   Backend not included

------------------------------------------------------------------------

## 👤 Author

Mobile engineer specializing in:

-   React Native (Expo)\
-   Firebase integration\
-   Booking systems\
-   Legacy backend integration

