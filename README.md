"# QA_Automation_Project_Finding_Hospitals_-practo.com-" 


# 🏥 Healthcare QA Automation Framework: Practo.com

[![Java](https://img.shields.io/badge/Language-Java_11%2B-orange?style=for-the-badge&logo=java)](https://www.oracle.com/java/)
[![Selenium WebDriver](https://img.shields.io/badge/Automation-Selenium_4.x-green?style=for-the-badge&logo=selenium)](https://www.selenium.dev/)
[![TestNG](https://img.shields.io/badge/Framework-TestNG-purple?style=for-the-badge&logo=testng)](https://testng.org/)
[![Maven](https://img.shields.io/badge/Build_Tool-Maven-blue?style=for-the-badge&logo=apachemaven)](https://maven.apache.org/)

An enterprise-grade, robust End-to-End UI Automation Framework designed for the healthcare domain, specifically target testing the workflows of **Practo.com**. This framework is engineered using **Java**, **Selenium WebDriver**, and **TestNG**, incorporating the **Page Object Model (POM)** architectural pattern to ensure modularity, high maintainability, and clean separation of concerns.

---

## 🗺️ Framework Architecture

The framework decouples raw UI actions, configurations, test data management, and validation layers to streamline automated testing lifecycles.


┌────────────────────────────────────────────────────────┐
│             Layer 1: External Inputs                   │
│   - config.properties        - Apache POI (Excel)      │
└───────────────────────────┬────────────────────────────┘
▼
┌────────────────────────────────────────────────────────┐
│             Layer 2: Test Execution Layer              │
│   - TestNG Test Suites       - Assertions & Validation │
└───────────────────────────┬────────────────────────────┘
▼
┌────────────────────────────────────────────────────────┐
│             Layer 3: Page Object Model (POM)           │
│   - BasePage (Explicit Waits) - Page Factory (@FindBy) │
└───────────────────────────┬────────────────────────────┘
▼
┌────────────────────────────────────────────────────────┐
│             Layer 4: Target Infrastructure             │
│   - Chrome Driver            - Firefox Driver          │
└────────────────────────────────────────────────────────┘

### 🖼️ Core Architecture Diagram
For a deep dive into the complete conceptual layer breakdown, please refer to our primary structural blueprint below:

![Healthcare Framework Architecture Diagram](41425679470262845.jpeg)
*Figure 1: Full schematic layout mapping data pipelines, synchronization loops, and validation modules.*

> 🛠️ **GitHub Display Setup:** 
> To ensure the diagram is visible to everyone browsing this repository, download your architecture image as **`41425679470262845.jpeg`** and save it directly in the root directory (alongside `pom.xml`). The markdown is optimized with a relative path to render natively without breaking!

---

## 🏗️ Technical Directory Breakdown

The codebase keeps test verification script suites cleanly isolated from locator web-element repositories:

```text
QA_Automation_Project_Finding_Hospitals/
│
├── src/
│   ├── main/java/              # ⚙️ Business Logic & POM Layers
│   │   └── pages/
│   │       ├── BasePage.java            # WebDriver conditional sync wrappers (Explicit Waits)
│   │       ├── PractoHomePage.java      # Geolocation settings, city search bar handlers
│   │       ├── HospitalResultsPage.java # Hospital search grid, filter checks, rating extractors
│   │       └── DiagnosticsPage.java     # Lab tests page components & booking forms
│   │
│   └── test/java/              # 🧪 Test Verification Layer
│       └── tests/
│           ├── BaseTest.java            # Global Hooks (@BeforeClass initialization, Driver quit)
│           ├── FindHospitalsTest.java   # Core validation suites for location filtering & scores
│           └── DiagnosticsFlowTest.java # Functional tests verifying diagnostic booking pipelines
│
├── src/test/resources/         # 📦 Configuration & Parameter Files
│   ├── testng.xml               # Suite execution engine parameters & groupings
│   └── config.properties        # Global browser toggles, timeout rules, app URLs
│
├── target/                     # 📊 Compilation Artifacts
│   └── surefire-reports/        # Auto-generated HTML execution report metrics
│
├── pom.xml                     # Maven project configuration file containing dependencies
└── README.md                   # Main documentation file
