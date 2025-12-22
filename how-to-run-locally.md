# Apache Fineract - Local Testing Guide

This guide provides comprehensive instructions for running local API tests within the Apache Fineract repository. Follow these steps to ensure your environment is correctly configured and your tests run efficiently.

---

## Table of Contents

1. [Local Development Setup](#local-development-setup)
2. [Integration Tests](#integration-tests)
3. [Cucumber E2E Tests](#cucumber-e2e-tests)
4. [API Testing with curl](#api-testing-with-curl)
5. [View API Documentation](#view-api-documentation)
6. [Troubleshooting](#troubleshooting)

---

## Local Development Setup

### Prerequisites

Before starting, ensure your local machine meets the following hardware and software requirements:

* **Java:** Java 21 (Azul Zulu JDK recommended).
* **Database:** * MariaDB ≥ 11.5.2
    * PostgreSQL ≥ 17.0
    * MySQL ≥ 9.1
* **Hardware:** Minimum **16GB RAM** and **8-core CPU**.
* **Git:** Required for source code management.
* **Gradle:** Version 8.14.3 (managed via the included Gradle wrapper).

### Starting Fineract Locally

Follow these commands to initialize your databases and launch the application in development mode.

**1. Create the required databases:**
```bash
./gradlew createDB -PdbName=fineract_tenants
./gradlew createDB -PdbName=fineract_default