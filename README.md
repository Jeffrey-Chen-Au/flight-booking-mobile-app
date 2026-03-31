# Flight Booking Mobile App

> 📱 A production mobile application for flight search and booking,
> built with React Native Expo and integrated with an existing backend
> system.

------------------------------------------------------------------------

## 🚀 Overview

This project is a **mobile flight booking application** designed for a
real-world travel business (name anonymized for confidentiality).

The app supports:

-   flight search\
-   price-based result listing\
-   booking flow\
-   passenger management\
-   order tracking

It integrates with an existing backend system to handle flight data,
bookings, and payments.

------------------------------------------------------------------------

## 🏗️ System Architecture

Mobile App (React Native) ↓ API Layer (PHP Backend) ↓ MySQL Database

Additional services: - Firebase Authentication → user identity\
- Firebase Analytics → event tracking\
- Expo Notifications → push notifications

------------------------------------------------------------------------

## ✈️ Features

-   🔍 Flight search (origin, destination, date, passengers)\
-   💰 Sorted flight results (price-based)\
-   📄 Flight details (layovers, baggage, airline info)\
-   🧾 Multi-step booking flow\
-   👤 Passenger management (adults, children, infants)\
-   📦 Order history and tracking

------------------------------------------------------------------------

## 🔄 User Flow

Search → Results → Details → Booking → Passenger → Confirmation

-   Users can browse flights without logging in\
-   Authentication is required before completing a booking\
-   Booking flow follows validation + step-based input

------------------------------------------------------------------------

## 🔄 Data Flow (Booking Example)

1.  User searches flights\
    → request sent to backend API

2.  Backend aggregates:

    -   internal deals\
    -   external APIs

3.  Response normalized → sent to app

4.  User selects flight\
    → booking payload created

5.  Backend validates + creates order

6.  Confirmation returned → UI updated

------------------------------------------------------------------------

## ⚙️ Tech Stack

### Frontend

-   React Native (Expo)\
-   Expo Router\
-   Expo Notifications

### Backend (External System)

-   PHP-based backend (existing system)\
-   MySQL database\
-   Shared with web platform

### Authentication & Analytics

-   Firebase Authentication (Email, Phone, Google, Apple)\
-   Google Analytics

### Build & Deployment

-   Expo EAS Build

------------------------------------------------------------------------

## 🧠 Technical Highlights

### 1. Unified Flight Data Handling

-   Integrated multiple flight data sources\
-   Normalized inconsistent schemas into unified model

### 2. Booking Flow Integration

-   Aligned mobile flow with existing web system\
-   Maintained backend compatibility

### 3. Authentication Strategy

-   Optional login for browsing\
-   Required before booking\
-   Synced Firebase identity with backend

### 4. Environment Management

-   Separate dev & production environments\
-   .env configuration\
-   EAS build profiles

------------------------------------------------------------------------

## ⚠️ Engineering Challenges

### Legacy Backend Constraints

-   Backend not mobile-first\
-   Required adaptation of APIs

### Data Normalization

-   Multiple inconsistent provider schemas\
-   Built unified frontend model

### State Consistency

-   Prevented invalid booking states\
-   Managed multi-step flow reliability

### Auth Boundary

-   Firebase vs backend session mismatch\
-   Implemented identity synchronization

------------------------------------------------------------------------

## 📊 Production Considerations

-   Handled real booking transactions\
-   Prevented duplicate submissions\
-   Managed API latency and loading states\
-   Ensured consistency with web system

------------------------------------------------------------------------

## 🔧 Future Improvements

-   Introduce BFF (Backend-for-Frontend) layer\
-   Improve caching strategy\
-   Add offline support\
-   Enhance analytics tracking

------------------------------------------------------------------------

## ⚠️ Notes

-   Architecture and implementation overview only\
-   Backend system not included\
-   Sensitive data removed

------------------------------------------------------------------------

## 👤 Author

Mobile engineer experienced in: - production mobile applications\
- booking systems\
- React Native + Firebase\
- legacy backend integrations
