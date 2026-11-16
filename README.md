# Patient-Health-Dashboard
A patient health portal/dashboard to input patient data

# SMART on FHIR — Patient Health Dashboard

A lightweight clinical web application and automated API test suite built against the **HL7 FHIR R4** standard (`hapi.fhir.org/baseR4`). This project demonstrates end-to-end healthcare interoperability—searching patient demographics, retrieving longitudinal clinical observations, visualizing vital/lab trends, and writing new observations back to a FHIR server.

## Features
- **Patient Search (`GET /Patient`):** Queries FHIR `Patient` bundles by family name and parses demographic resources.
- **Clinical Observations & Trend Visualization (`GET /Observation`):** Fetches patient vital signs and lab results, normalizes weight units (`kg` to `lbs`), and plots longitudinal trends using **Chart.js**.
- **Clinical Write-Back (`POST /Observation`):** Allows users to log new **Body Weight** (`LOINC 29463-7`) and **Blood Glucose** (`LOINC 2339-0`) observations directly to the FHIR server using standardized LOINC and UCUM coding.
- **Automated Postman API Test Suite:** Includes a complete Postman Collection (`v2.1`) and Environment file with automated `pm.test()` status and schema assertions for `Patient` and `Observation` endpoints.

## Project Structure
- `index.html` — Single-page frontend dashboard built with HTML, CSS, vanilla JavaScript (`fetch` API), and Chart.js.
- `Patient Health Dashboard.postman_collection.json` — Exported Postman collection with `GET`/`POST` workflows and post-response test scripts.
- `HAPI FHIR R4.postman_environment.json` — Postman environment variables (`baseUrl`).

## How to Run Locally
1. Clone or download this repository.
2. Open `index.html` in any modern web browser (or via VS Code Live Server).
3. Search for a test patient (e.g., `Karlinsky`, `Gonzalez`, or `Smith`) and click **View Vitals** to inspect records or log new observations.
4. Insert either patients blood sugar or body weight to view a line chart.
5. *(Optional)* Import both `.json` files into Postman, select the **HAPI FHIR R4** environment, and run the collection to verify all automated API tests pass.
