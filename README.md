# Enterprise Accounting RPA & Document Intelligence

## Overview
This repository serves as an architectural showcase for an end-to-end Robotic Process Automation (RPA) system designed for accounting departments. The system automates the ingestion, standardization, data extraction, and reconciliation of supplier invoices. 

By integrating Intelligent Document Processing (IDP) with enterprise accounting software (QuickBooks), the pipeline eliminates manual data entry and accelerates financial reconciliation.

*Note: Source code is restricted under NDA. This document outlines the system architecture and business logic.*

## System Architecture

The pipeline is split into two primary phases: Data Standardization and Reconciliation.

### Phase 1: Ingestion & Intelligent Document Processing
1. **Multi-Format Ingestion:** The automation monitors a shared OneDrive folder where suppliers upload invoices in various formats (raw phone images, PDFs, Excel sheets).
2. **Format Recognition & Standardization:** The system identifies the file type. All incoming documents are standardized into a unified PDF format.
3. **Vision AI / OCR Extraction:** For unstructured data (e.g., photos of receipts taken via mobile phone), the system utilizes Vision AI / OCR to extract key-value pairs (Invoice Number, Total Amount, Vendor Name, Date) and transforms them into structured data.

### Phase 2: Automated Reconciliation
1. **Data Syncing:** The extracted structured data is cross-referenced with internal records via the QuickBooks API.
2. **Reconciliation Engine:** The logic matches supplier invoices against existing purchase orders and payment logs in QuickBooks.
3. **Discrepancy Reporting:** 
   - The system categorizes invoices into states (e.g., Paid, Unpaid, Discrepancy).
   - A detailed reconciliation report highlighting unmatched amounts or errors is automatically generated and exported to an Excel spreadsheet for the finance team.

## Technical Capabilities
- **Document AI:** Optical Character Recognition (OCR), Layout parsing, Vision Models.
- **Workflow Automation:** Multi-step routing based on file MIME types.
- **Integrations:** Microsoft OneDrive API, QuickBooks API, Excel data manipulation.
- **Data Engineering:** Transformation of unstructured image data into structured tabular datasets.

## Business Value
- Eliminated hours of manual data entry for unstructured supplier receipts.
- Reduced human error in financial reconciliation.
- Created a centralized, standardized audit trail for all incoming invoices.