# Standards & API Reference

> Project: Contractor Management Platform · Generated: 2026-05-06

## Industry Standards & Specifications

### ISO Standards

**ISO 45001:2018 — Occupational Health & Safety Management Systems**
- URL: https://www.iso.org/standard/63787.html
- Directly relevant to contractor safety compliance. Requires organisations to coordinate procurement with contractors, identify risks arising from contractor activities, and ensure outsourced processes with safety impact are appropriately controlled. A key certification demanded in construction and field-services tendering.

**ISO 9001:2015 — Quality Management Systems (Clause 8.4 Externally Provided Processes)**
- URL: https://www.iso.org/standard/62085.html
- Clause 8.4 defines requirements for controlling externally provided products and services, covering contractor evaluation, selection, monitoring, and performance review. A platform supporting ISO 9001 workflows must store documented criteria for supplier approval and maintain evidence of ongoing evaluation.

**ISO/IEC 27001:2022 — Information Security Management Systems**
- URL: https://www.iso.org/standard/27001
- Mandates protection of confidentiality, integrity, and availability of information held about third parties. A contractor management platform storing identity documents, tax forms, insurance certificates, and payment data must implement controls aligned with ISO 27001 Annex A, particularly access control, cryptography, and incident management domains.

**ISO 37001:2025 — Anti-Bribery Management Systems**
- URL: https://www.iso.org/standard/37001
- Covers transparency, misconduct prevention, conflict-of-interest management, and due-diligence procedures in supply chains. Especially relevant for platforms serving government contractors or organisations operating across high-risk jurisdictions. The 2025 revision adds enhanced provisions on compliance culture and climate change impacts.

### W3C & IETF Standards

**RFC 6350 — vCard Format Specification (IETF)**
- URL: https://www.rfc-editor.org/rfc/rfc6350.html
- Defines the standard data format for representing contractor contact information (name, address, phone, email, organisation). Relevant for contact import/export, directory integrations, and interoperability with HR systems. vCard 4.0 supports extensible property types and internationalisation.

**RFC 7519 — JSON Web Tokens (JWT)**
- URL: https://datatracker.ietf.org/doc/html/rfc7519
- JWTs are the standard token format for stateless authentication and claims exchange between contractor management APIs and integrated systems (payroll, ERP, identity providers). Used within OAuth 2.0 and OpenID Connect flows.

**RFC 7231 — HTTP/1.1 Semantics and Content**
- URL: https://datatracker.ietf.org/doc/html/rfc7231
- Foundation for RESTful API design. Defines HTTP methods (GET, POST, PUT, PATCH, DELETE), status codes, and content negotiation; foundational to any REST API exposed by a contractor management platform.

**RFC 8288 — Web Linking**
- URL: https://datatracker.ietf.org/doc/html/rfc8288
- Defines the `Link` header used for pagination in REST APIs. Relevant for APIs returning large contractor lists, document records, and audit log entries.

### Data Model & API Specifications

**OpenAPI Specification 3.1 / 3.2**
- URL: https://spec.openapis.org/oas/v3.1.0.html / https://spec.openapis.org/oas/v3.2.0.html
- The de-facto standard for describing RESTful APIs. OAS 3.1 introduced full JSON Schema compatibility. OAS 3.2 (released September 2025) adds first-class streaming support (SSE and JSON Lines) and structured tag navigation. All public-facing contractor management APIs should be described with an OAS document to enable client code generation and documentation tooling.

**JSON Schema (Draft 2020-12)**
- URL: https://json-schema.org/specification
- Used to define and validate contractor data models (contractor profiles, onboarding documents, contract terms, payment records). Directly embedded in OpenAPI 3.1 Schema Objects. Enables runtime validation and developer tooling for API consumers.

**GraphQL Specification**
- URL: https://spec.graphql.org/
- An alternative query language used by some contractor/HR platforms (notably Greenhouse Onboarding API). Enables clients to request precisely the fields they need, useful for complex contractor profile objects with optional fields across different engagement types.

### Security & Authentication Standards

**RFC 6749 / RFC 6750 — OAuth 2.0 Authorization Framework**
- URL: https://datatracker.ietf.org/doc/html/rfc6749
- The standard protocol for delegated authorisation used across all major contractor management platforms (Procore, Bullhorn, Greenhouse, Deel, Coupa). Required for secure third-party integrations and partner-built apps accessing contractor data on behalf of users.

**OpenID Connect 1.0 (OIDC)**
- URL: https://openid.net/connect/
- Authentication layer built on OAuth 2.0. Provides identity tokens (JWTs) enabling SSO across contractor portals, payroll systems, and ERP integrations. Used by Coupa, ADP, and Workday for their contractor API access.

**OWASP API Security Top 10 (2023 Edition)**
- URL: https://owasp.org/API-Security/editions/2023/en/
- The authoritative checklist for API security risk in SaaS applications. Key risks applicable to contractor management APIs include: Broken Object-Level Authorization (contractor data leakage across tenants), Broken Authentication, Excessive Data Exposure in responses, and Unrestricted Resource Consumption. Any contractor platform with multi-tenant architecture must implement controls against all top-10 risks.

**NIST SP 800-63B — Digital Identity Guidelines**
- URL: https://pages.nist.gov/800-63-3/sp800-63b.html
- Defines authentication assurance levels. Relevant for contractor identity verification workflows; platforms collecting government ID, I-9 documents, or biometric data should implement authentication at NIST AAL2 or above.

**SOC 2 (AICPA Trust Service Criteria)**
- URL: https://www.aicpa-cima.com/resources/landing/system-and-organization-controls-soc-suite-of-services
- The standard security attestation expected by enterprise buyers of contractor management SaaS. Type II reports (covering a 6–12 month observation window) are the market norm. Covers security, availability, processing integrity, confidentiality, and privacy Trust Service Criteria.

### Regulatory Frameworks

**GDPR (EU General Data Protection Regulation)**
- URL: https://gdpr.eu/
- Governs collection, storage, and processing of personal data for contractors who are EU data subjects. Key obligations: lawful basis for processing, data minimisation, right to erasure, data subject access requests (DSARs), breach notification within 72 hours. Platforms must implement Data Processing Agreements (DPAs) with customers who are EU data controllers.

**IRS Form W-9 / 1099-NEC (US Tax)**
- URL: https://www.irs.gov/forms-pubs/about-form-w-9
- US tax collection standard for independent contractors. Platforms operating in the US must collect and validate W-9 data (TIN/EIN) and generate 1099-NEC filings. Electronic delivery of 1099 forms requires contractor consent and IRS-compliant formatting.

**Form I-9 / E-Verify (US Employment Eligibility)**
- URL: https://www.e-verify.gov/
- Federal requirement for verifying work authorisation for US contractors (mandatory for federal contractors under the FAR E-Verify clause). E-Verify+ (launched 2024) merges the I-9 and E-Verify process into one digital workflow. Third-party API solutions (e.g., Sterling, DISA) offer I-9/E-Verify API integration for onboarding platforms.

---

## Similar Products — Developer Documentation & APIs

### Deel — Contractor Lifecycle API

- **Description:** Global contractor management platform covering contract creation, signing, amendments, terminations, timesheets, milestones, invoice adjustments, and off-cycle payments. Supports 150+ countries.
- **API Documentation:** https://developer.deel.com/api/contractors/introduction
- **Developer Portal:** https://developer.deel.com/docs/introduction-gp
- **SDKs/Libraries:** Not publicly listed; REST API with JSON payloads; Postman collections available via developer portal.
- **Developer Guide:** https://help.letsdeel.com/hc/en-gb/articles/8801712601233-How-To-Use-Deel-API
- **Standards:** REST/JSON; OpenAPI-described endpoints
- **Authentication:** OAuth 2.0; Org Admin or IT Developer Admin role required to generate API credentials; sandbox environment available for testing.
- **Key Contractor Entities:** Contracts, Amendments, Terminations, Timesheets, Milestones, Invoice Adjustments, Off-cycle Payments.

### SAP Fieldglass — Contingent Workforce VMS API

- **Description:** Enterprise Vendor Management System (VMS) for contingent workforce, contractors, and services procurement. Integrates with SAP S/4HANA, SAP SuccessFactors, and SAP Ariba.
- **API Documentation:** https://api.sap.com/products/SAPFieldglass/apis/packages
- **SAP Business Accelerator Hub:** https://api.sap.com/package/FieldglassAPI
- **SDKs/Libraries:** Available via SAP Integration Suite connectors; OData V2 API format.
- **Developer Guide:** https://help.sap.com/docs/SAP_FIELDGLASS
- **Standards:** OData V2 (REST-compatible); SAP proprietary integration standards; SOAP available for legacy integrations.
- **Authentication:** OAuth 2.0 via SAP Identity Authentication Service.
- **Key Contractor Entities:** Work Orders, Service Entries, Statements of Work, Worker Profiles, Suppliers, Timesheets, Expense Reports.

### Procore — Construction Contractor Management API

- **Description:** Construction project management platform with contractor management modules covering subcontractors, compliance documents, bidding, and site access.
- **API Documentation:** https://developers.procore.com/reference/rest/docs/rest-api-overview
- **Developer Portal:** https://developers.procore.com/
- **SDKs/Libraries:** Ruby, Python, JavaScript/Node.js SDKs; Postman and Insomnia collections; API Explorer tool.
- **Developer Guide:** https://developers.procore.com/documentation/introduction
- **Standards:** REST/JSON; RESTful API Concepts documented; Swagger/OpenAPI for endpoint navigation.
- **Authentication:** OAuth 2.0; supports both client credentials (service accounts) and authorization code flows; sandbox environment available.
- **Key Contractor Entities:** Companies (subcontractors), Compliance Documents, Observations, RFIs, Submittals, Budgets, Purchase Orders, Prime Contracts.

### Bullhorn — Staffing & Contractor ATS API

- **Description:** CRM and ATS for staffing agencies managing contractor/contingent worker placements. Supports the full lifecycle from sourcing to timesheet and payroll.
- **API Documentation:** https://bullhorn.github.io/rest-api-docs/
- **Entity Reference:** https://bullhorn.github.io/rest-api-docs/entityref.html
- **GitHub Repository:** https://github.com/bullhorn/rest-api-docs
- **SDKs/Libraries:** REST API; Open API specification published; Postman collection available; Merge.dev and other unified API platforms provide abstracted access.
- **Developer Guide:** https://kb.bullhorn.com/bh4sf/Content/BH4SF/LP/developerDocumentation.htm
- **Standards:** REST/JSON; OpenAPI Specification published for the Recruitment Cloud product.
- **Authentication:** OAuth 2.0 (client credentials); session token (BhRestToken) issued after login; all subsequent requests include session token and base REST URL.
- **Key Contractor Entities:** Candidates, Placements, Job Orders, Submissions, Companies, Contacts, Timesheets, Pay/Bill records.

### Greenhouse — Recruiting & Onboarding API

- **Description:** ATS and onboarding platform used to manage candidate pipelines through to employee/contractor onboarding. Widely used as a hiring front-end before contractor management platforms.
- **API Documentation:** https://developers.greenhouse.io/
- **Harvest API Reference:** https://developers.greenhouse.io/harvest.html
- **Onboarding API:** https://developers.greenhouse.io/gho.html (GraphQL)
- **SDKs/Libraries:** REST (Harvest, Ingestion) and GraphQL (Onboarding API); Postman collections; Workato and Zapier connectors.
- **Developer Guide:** https://support.greenhouse.io/hc/en-us/articles/10568627186203-Greenhouse-API-overview
- **Standards:** REST/JSON for Harvest and Ingestion APIs; GraphQL for Onboarding API. Note: Harvest API v1 and v2 will be deprecated after August 31, 2026.
- **Authentication:** HTTP Basic Auth (Harvest); OAuth 2.0 (Onboarding); webhook HMAC signatures for event verification.
- **Key Contractor Entities:** Candidates, Applications, Job Postings, Offers, Departments, Employees (Onboarding), Custom Fields.

### Coupa — Supplier & Contractor Spend Management API

- **Description:** Total spend management platform with supplier and contractor management capabilities. Manages procurement, purchase orders, invoices, and supplier compliance.
- **API Documentation:** https://compass.coupa.com/en-us/products/product-documentation/integration-technical-documentation/the-coupa-core-api
- **Suppliers API:** https://compass.coupa.com/en-us/products/product-documentation/integration-technical-documentation/the-coupa-core-api/resources/reference-data-resources/suppliers-api-(suppliers)
- **SDKs/Libraries:** REST API with JSON and XML payloads; Celigo, Workato, and MuleSoft connectors available.
- **Developer Guide:** https://compass.coupa.com/en-us/products/product-documentation/integration-technical-documentation
- **Standards:** REST; UTF-8 XML and JSON; resource URL pattern: `https://<instance>.coupahost.com/api/<resource_name>`
- **Authentication:** OAuth 2.0 with OpenID Connect (OIDC); API key authentication also supported for older integrations.
- **Key Contractor Entities:** Suppliers, Supplier Information, Supplier Users, Contracts, Purchase Orders, Invoices, Payments.

### Workday — HCM & Extended Workforce API

- **Description:** Cloud HCM platform with Extend Workforce modules for managing contingent workers alongside full-time employees. Widely used as the system-of-record that contractor management platforms integrate against.
- **API Documentation:** https://community.workday.com/sites/default/files/file-hosting/productionapi/index.html
- **Developer Resources:** https://developer.workday.com/
- **SDKs/Libraries:** REST API and SOAP/WSDL web services; Workday Studio for custom integrations; Integration Cloud Connectors for HCM.
- **Developer Guide:** https://www.getknit.dev/blog/workday-api-integration-in-depth
- **Standards:** REST/JSON (modern APIs) and SOAP/XML (legacy WSDL); Workday Web Services (WWS) Directory documents all SOAP endpoints.
- **Authentication:** OAuth 2.0; API Client registration in Workday tenant required; refresh token flow for long-lived integrations.
- **Key Contractor Entities:** Workers (Contingent), Positions, Job Profiles, Compensation Elements, Organizations, Cost Centers, Time Off.

### Beeline — Contingent Workforce VMS API

- **Description:** Vendor Management System focused on enterprise contingent workforce. Maintains a library of 350+ APIs and connectors. Used by large enterprises to manage high contractor volumes across global supply chains.
- **API Documentation:** https://developer.beeline.com/ (access requires Beeline client, MSP, or partner credentials)
- **Developer Portal:** https://www.beeline.com/integrations
- **SDKs/Libraries:** REST APIs; most are self-service with no custom configuration required.
- **Standards:** REST/JSON; most REST APIs are self-service and do not require Beeline configuration.
- **Authentication:** OAuth 2.0; API keys for legacy integrations.
- **Key Contractor Entities:** Workers, Work Orders, Supplier Companies, Timesheets, Expenses, Compliance Documents, Requisitions.

### Merge.dev / Finch — Unified HRIS & Payroll API Abstraction

- **Description:** Unified API platforms that abstract multiple HRIS, payroll, and ATS systems behind a single normalised API. Merge supports 200+ HRIS integrations; Finch covers 250+ employment systems. Useful for contractor management platforms that need to sync data to/from a customer's existing HR stack without building individual integrations.
- **Merge API Documentation:** https://docs.merge.dev/hris/
- **Finch API Documentation:** https://developer.tryfinch.com/
- **SDKs/Libraries:** Merge: JavaScript/TypeScript, Python, Ruby, Java, Go; Finch: JavaScript, Python, Java.
- **Standards:** REST/JSON; unified data model normalised across providers; OpenAPI-described.
- **Authentication:** OAuth 2.0 (Merge Link for end-user authorisation); API keys for server-to-server calls.
- **Key Unified Entities (HRIS):** Employees, Employments, Locations, Pay Groups, Time-off, Payroll Runs, Bank Info, Benefits.

### DocuSign — eSignature & Intelligent Agreement Management API

- **Description:** Leading e-signature and contract lifecycle management platform. Contractor agreements, SOWs, NDAs, and compliance documents are commonly sent through DocuSign in contractor onboarding workflows.
- **API Documentation:** https://developers.docusign.com/
- **Developer Portal:** https://developers.docusign.com/
- **SDKs/Libraries:** JavaScript/Node.js, Python, Java, PHP, Ruby, C#/.NET, Go.
- **Developer Guide:** https://www.docusign.com/blog/developers/streamline-end-to-end-agreement-management-with-docusign-a-developer
- **Standards:** REST/JSON; OpenAPI-described; eSignature composite template model; document generation from data fields.
- **Authentication:** OAuth 2.0 (authorization code and JWT grant flows); Integration Key required for all applications.
- **Key Entities:** Envelopes, Documents, Recipients, Tabs (form fields), Templates, Webhooks (Connect), Web Forms.

---

## Notes

**Emerging Standards to Watch**

- **HR Open Standards (formerly HR-XML):** The HR Open Standards Consortium maintains XML and JSON schema specifications for HR data exchange including contingent worker data models. Less dominant than proprietary platform APIs but relevant for organisations requiring vendor-neutral data portability. See https://hropenstandards.org/.

- **MCP (Model Context Protocol):** Anthropic's open protocol for connecting AI assistants to data sources. An AI-native contractor management platform could expose an MCP server enabling AI assistants to query contractor status, compliance gaps, and payment records. No domain-specific MCP specification exists yet for contractor management; this is an open opportunity.

- **OpenAPI 3.2 Streaming Support:** The September 2025 release adds native streaming semantics (SSE and JSON Lines). Relevant for a contractor management platform that delivers real-time compliance alerts, payment confirmations, and onboarding status updates to integrated clients.

- **EU Platform Work Directive (effective 2026):** Creates a legal rebuttable presumption of employment for platform workers. Platforms operating in the EU will need to implement algorithmic transparency reporting, which implies new API endpoints and data export formats to comply with regulatory audit requirements.

**Gaps and Areas Still Evolving**

- No universal open standard exists for contractor classification scoring or misclassification risk data models; current implementations are proprietary.
- I-9/E-Verify API access is tightly controlled by the US government (USCIS); third-party vendors (Sterling, DISA) mediate access but there is no public developer API.
- Background check APIs (Checkr, Sterling) are adjacent to contractor onboarding but are governed by FCRA (Fair Credit Reporting Act) compliance requirements that constrain what data can be returned and retained.
