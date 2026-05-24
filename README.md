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

<img width="1282" height="1061" alt="elektra_arquitectura drawio" src="https://github.com/user-attachments/assets/d0ed8449-6e9e-4bb9-a8cf-d5bbb35d9491" />


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


### E-commerce


## 🧪 Testing

- Unit tests written with **JUnit** and **Mockito** covering core business logic.

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

<img width="1708" height="1821" alt="Diagrama DER Elektra drawio" src="https://github.com/user-attachments/assets/e882c1f5-0341-4325-98ec-9b1d6e598afa" />

---

## 🛠️ Full Tech Stack

- **Backend:** Java, Spring Boot, Spring Security (JWT), Spring Data JPA, Spring Web, RESTful APIs
- **Frontend:** Angular, Next.js, TypeScript, Chart.js, HTML, CSS
- **Database:** MySQL — advanced normalization, composite relational tables
- **AI:** Anthropic API, LLM-based entity extraction, Prompt Engineering, token caching
- **DevOps:** Docker, Digital Ocean, Vercel, Git, GitHub
- **Storage:** Cloudinary
- **PDF Generation:** iTextPDF
- **Testing:** JUnit, Mockito
- **Other:** WhatsApp API integration, Electronic Invoicing (Hacienda CR)
