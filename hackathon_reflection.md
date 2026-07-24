
# Hackathon Reflection - PipeGuard AI

## Project Title

PipeGuard AI: Real-Time Pipeline Loss Detection & Anomaly Monitoring System

## Team

AVENGERS GROUP

## Hackathon Domain

Domain A - Pipeline Integrity & Product Loss

# 1. Project Overview

PipeGuard AI is an AI-powered pipeline monitoring and product loss detection platform designed to improve pipeline integrity management for petroleum transportation networks.

The system focuses on detecting abnormal pipeline behaviour by analyzing sensor data such as:

- Flow rates
- Pressure readings
- Temperature measurements
- Pipeline operational status
- Product loss indicators

The goal is to provide real-time monitoring, anomaly detection, operational insights, and AI-assisted support for pipeline operators.

---

# 2. Problem Understanding

Petroleum pipeline networks experience challenges such as:

- Product leakage
- Illegal tapping
- Equipment failures
- Meter inaccuracies
- Pressure abnormalities
- Operational inefficiencies

Traditional monitoring approaches often rely on manual inspections and periodic analysis of SCADA data. This creates delays in detecting problems, leading to:

- Increased product losses
- Revenue impact
- Environmental risks
- Safety concerns
- Higher operational costs

PipeGuard AI addresses these challenges by introducing automated data processing, intelligent monitoring, and real-time decision support.

---

# 3. Solution Approach

The project implements a complete data-to-insight pipeline:

## Data Collection and Ingestion

The system is designed to support multiple data sources including:

- Pipeline sensor devices
- SCADA systems
- IoT monitoring devices
- External APIs
- Historical datasets

For the hackathon prototype, the system uses the KPC pipeline sensor dataset as the primary data source.

The ingestion pipeline:

1. Collects raw pipeline sensor data
2. Validates incoming records
3. Cleans and transforms data
4. Stores processed information in PostgreSQL
5. Exposes data through FastAPI services
6. Visualizes operational insights through the frontend dashboard

---

# 4. Technical Architecture

The system architecture was designed with scalability and future AI integration in mind.

## Frontend

**Angular**

Responsibilities:

- Real-time operational dashboard
- Pipeline monitoring visualization
- Alert management
- Analytics views
- AI assistant interface

Design principles:

- Modern enterprise UI
- Responsive layout
- Blue and purple theme representing technology, intelligence, and reliability

---

## Backend

**FastAPI**

Responsibilities:

- REST API services
- Data processing endpoints
- Authentication services
- Dashboard data delivery
- AI integration layer

FastAPI was selected because of:

- High performance
- Easy integration with AI models
- Python ecosystem support
- Automatic API documentation

---

## Database

**PostgreSQL**

Stores:

- Pipeline readings
- Sensor history
- Detected anomalies
- Alerts
- User interactions
- AI recommendations

---

## Data Engineering Pipeline

The ingestion layer supports:

### Current Prototype

CSV-based ingestion:
