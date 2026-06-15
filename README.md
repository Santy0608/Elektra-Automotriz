# Elektra Automotriz — ERP + E-commerce Platform

> **Status: Live in Production** — Actively used daily by a Costa Rican auto parts business.

A full-scale enterprise solution built for a small-to-medium auto parts retailer, combining a complete ERP system and an AI-powered e-commerce platform connected to the same backend — eliminating 100% of manual spreadsheet-based tracking and streamlining customer quoting through WhatsApp.

---

## 🧩 System Overview

The solution consists of two interconnected applications sharing the same Spring Boot backend:

| Component | Stack |
|---|---|
| ERP (Back-office) | Angular + Spring Boot + MySQL |
| E-commerce (Storefront) | Next.js + Spring Boot + MySQL |
| AI Search | Anthropic API + Prompt Engineering + Token Caching |
| Infrastructure | Docker + Digital Ocean + Vercel + Cloudinary |
| Testing | JUnit + Mockito |
| Security | Spring Security + JWT + Role-based access control |

---

## 🏗️ Architecture

<img width="1282" height="1061" alt="Arquitectura Elektra Automotriz drawio" src="https://github.com/user-attachments/assets/1b4a93c3-da88-4ef7-a611-1cde2487ea5b" />


## 🏗️ ERP — Back-office System (Angular + Spring Boot + MySQL)

### Modules

**Sales Management**
- Complete sales flow with product selection, customer assignment, and automatic total calculation.
- Automated electronic invoicing integrated with the Ministerio de Hacienda CR *(integration developed, pending activation)*.
- Sales reports with PDF export filtered by date range.

**Quotations**
- Full quotation module with PDF generation using iTextPDF.
- Vehicle and parts detail included in each quotation.

**Inventory Management**
- Inventory entries and returns with full traceability.
- Auto parts management with image upload via Cloudinary.
- Logical deletion (soft delete) across all CRUD modules.
- Audit logs tracking creation and modification events across the entire system.

**Auto Parts Compatibility Module** ⭐
- Core feature of the system: allows adding compatibility per auto part by brand, model, year, and engine.
- Compatibility data stored in a composite relational table (`repuesto_vehiculo`) in MySQL.
- Filters available across the ERP and e-commerce by brand, model, year, and engine.

**Configuration Module**
- CRUD management for brands, models, engines, and vehicles used in the compatibility system.

**Categories & Suppliers**
- Full CRUD for product categories and suppliers with logical deletion.

**Accounts Receivable & Payable**
- Complete module for tracking incoming and outgoing financial obligations.

**Analytics Dashboard**
- 5 Chart.js visualizations covering sales trends, inventory status, and business performance metrics.

**Security**
- Spring Security with JWT authentication.
- Role-based access control protecting all API endpoints.

---

## 🛒 E-commerce — Customer Storefront (Next.js + Spring Boot + MySQL)

### Features

**Homepage**
- Vehicle compatibility filter (brand, model, year, engine) on the landing page.
- Category browsing and company information section.

**Catalog Page**
- Same vehicle compatibility filter available on the catalog.
- **AI-powered natural language search** — allows customers to find exact parts using natural language. Built with LLM-based entity extraction, prompt engineering, and token caching for cost control.
- AI API integrated directly in Next.js server-side routes — never exposed to the client.

**Shopping Cart & Checkout**
- Full shopping cart with part selection and vehicle association.
- Final quotation sent directly via WhatsApp, including vehicle details, selected parts, and total amount — eliminating back-and-forth customer inquiries.

**Single Product Page**
- Detailed product view with images, compatibility information, and add-to-cart functionality.

---

## 📸 Screenshots

### ERP

**Dashboard**
<img width="1877" height="911" alt="Dashboard ERP" src="https://github.com/user-attachments/assets/399c5c1e-7124-4209-a5c6-c6f9208381da" />

**Auto Parts Compatibility Module**
<img width="1901" height="912" alt="Compatibilidad Modulo Repuestos" src="https://github.com/user-attachments/assets/76bea43a-92f1-4dde-b884-b74e722cd52a" />

**Sales Form**
<img width="1912" height="907" alt="Registrar Venta" src="https://github.com/user-attachments/assets/1fb6a83b-cc44-4d31-8a71-6ad11e296d13" />

**Invoice PDF**
<img width="996" height="852" alt="Factura PDF" src="https://github.com/user-attachments/assets/6ad12bba-396f-4432-a1be-96aaf5678f56" />

**Quotation PDF**
<img width="990" height="852" alt="Cotizacion PDF" src="https://github.com/user-attachments/assets/11d04700-c216-4d61-bc5a-b01d18d32977" />

**Quotation Details**
<img width="1906" height="907" alt="Resumen Cotización" src="https://github.com/user-attachments/assets/28dd0019-ce93-4dfa-bcb3-aedf87c906e6" />

**Login**
<img width="1897" height="907" alt="Login ERP" src="https://github.com/user-attachments/assets/327c3777-4475-4ebc-8cb8-310b5a171dd1" />

### E-commerce


---

## 🚀 Deployment

| Service | Platform |
|---|---|
| Spring Boot Backend | Docker + Digital Ocean |
| Next.js E-commerce | Vercel |
| Image Storage | Cloudinary |

---

## 🔒 Repository Notice

The source code for this project is private due to client confidentiality.

**Available upon request:**
- Architecture overview
- Database schema (ERD)
- Code walkthrough session

📹 **ERP Demo** — *(coming soon)*

📹 **E-commerce + AI Search Demo** — *(coming soon)*

🌐 **Live E-commerce:** *(URL here)*

---

## 📐 Database Design

> Normalized relational MySQL database (3NF) with composite table for auto parts compatibility.

<img width="1708" height="1821" alt="Diagrama DER Elektra drawio" src="https://github.com/user-attachments/assets/faf3c811-3f20-4e92-b241-b264045e2280" />


---

## 🛠️ Full Tech Stack

- **Backend:** Java, Spring Boot, Spring Security (JWT), Spring Data JPA, Spring Web, RESTful APIs
- **Frontend:** Angular, Next.js, TypeScript, Chart.js, HTML, CSS
- **Database:** MySQL — advanced normalization, composite relational tables
- **AI:** Anthropic API, LLM-based entity extraction, Prompt Engineering, token caching
- **DevOps:** Docker, Digital Ocean, Vercel, Git, GitHub
- **Storage:** Cloudinary
- **PDF Generation:** iTextPDF
- **Other:** WhatsApp API integration, PDF Invoicing
