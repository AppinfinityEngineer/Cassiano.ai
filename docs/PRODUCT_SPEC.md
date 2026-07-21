# Cassiano.ai V1 Product Specification

## Promise

Cassiano.ai turns a business into a trained, tested, ready-to-use AI employee without requiring a sales call or technical knowledge.

## Positioning

Primary message: **Your AI employee, trained on your business.**

Lead with business outcomes rather than terms such as GPT, LLM, RAG, prompt engineering, or agent framework.

## V1 commercial model

- One configurable package
- Full payment upfront through Stripe Checkout
- One custom AI employee
- Human-reviewed build
- Structured QA
- One included revision
- No subscription, deposit, balance-payment, token-billing, or multiple-package complexity in V1

## User roles

### Customer
- register and authenticate
- purchase the package
- access one project created from the paid order
- complete and resume onboarding
- upload business knowledge securely
- submit the project
- track simplified progress
- receive information requests
- view final delivery
- request one revision

### Admin
- view customers, orders, projects, submissions, and files
- manage the project workflow
- request missing information
- create and version the build brief and GPT build record
- run structured QA
- release delivery
- manage the included revision
- view audit history

A separate builder role is excluded from V1.

## Public pages

- Home
- How It Works
- Pricing
- What It Can Do
- FAQ
- Contact
- Privacy placeholder
- Terms placeholder
- Refund Policy placeholder
- Login
- Registration

The public website must include sound SEO foundations: unique metadata, canonical URLs, sitemap, robots.txt, semantic HTML, structured data where appropriate, accessibility, performance, and internal linking. Do not create fake testimonials or unsupported claims.

## Customer journey

1. Visitor understands the offer.
2. Visitor creates an account.
3. Customer pays in full through Stripe Checkout.
4. Verified Stripe webhook records payment and creates exactly one project.
5. Customer completes guided multi-step onboarding with autosave.
6. Customer securely uploads knowledge documents.
7. Customer reviews and submits the project.
8. Admin reviews the submission and requests missing information if required.
9. Admin manually builds the final Custom GPT and records its configuration.
10. Admin executes structured QA.
11. Critical failures block delivery.
12. Admin releases delivery.
13. Customer receives access, instructions, recommended prompts, limitations, and third-party cost guidance.
14. Customer may request one included revision.
15. Admin completes the revision and closes the project.

## Onboarding scope

### Business
- business name
- website
- industry
- location/service area
- company description
- target customer

### Products and services
- products
- services
- prices where applicable
- benefits
- differentiators

### Brand voice
- tone attributes
- formality
- preferred terminology
- words to use and avoid
- example writing

### Responsibilities
- customer support
- sales support
- email writing
- proposal writing
- marketing
- social content
- internal knowledge
- policy/process explanation

### FAQs and scenarios
- common customer questions
- common staff questions
- objections
- complaints
- escalation scenarios
- difficult edge cases

### Guardrails
- prohibited topics
- claims not to make
- confidential information restrictions
- discount/pricing rules
- mandatory disclaimers
- regulated or high-risk subjects
- human escalation rules

### Review and submission
- complete summary
- required confirmations
- locked submission after final submit

## Knowledge uploads

Initially support PDF, DOCX, TXT, CSV, XLSX, and PPTX. Files must be stored privately outside MongoDB with metadata in MongoDB. Use signed access, server-side ownership checks, file limits, MIME/extension validation, filename sanitisation, delete/replace support, and a local development adapter.

## Project states

Internal states:

- onboarding
- submitted
- needs_information
- ready_for_build
- building
- qa
- ready_for_delivery
- delivered
- revision_requested
- revision_in_progress
- complete
- cancelled

All transitions must be validated server-side and recorded in status history. Customers see a simplified timeline.

## Admin build workspace

Tabs or equivalent sections:

- Overview
- Customer and order
- Onboarding
- Files
- Build brief
- GPT configuration
- QA
- Delivery
- Revision
- Status and audit history

The build brief must be editable and versioned. V1 may generate it deterministically from onboarding fields. The application must function without an AI provider.

## GPT build record

Record:

- employee name
- platform
- version
- system instructions
- conversation starters
- knowledge files used
- capabilities
- guardrails
- known limitations
- preview/final URL or access instructions
- build notes
- revision history

Do not store customer API keys in plaintext.

## QA harness

Each test stores:

- category
- prompt
- expected behaviour
- actual response pasted by admin
- pass, fail, or review
- severity
- reviewer
- notes
- timestamp

Categories include company knowledge, product/service accuracy, brand voice, support, sales, guardrails, refusal behaviour, escalation, and hallucination risk.

Required tests must be complete. Critical failures must block delivery. Browser automation against Custom GPTs is excluded from V1.

## Delivery

Delivery includes:

- AI employee name
- access link/instructions
- setup guidance
- recommended prompts
- capabilities
- known limitations
- privacy and review guidance
- explanation of third-party ChatGPT/API/seat costs
- delivery date
- revision entitlement

## Revision

One revision is included. Collect the issue, desired behaviour, example, priority, and supporting files. Enforce one active revision and one entitlement, with admin override and out-of-scope handling. Retain history.

## Notifications and auditing

Provide transactional email abstraction and lifecycle notifications for registration, payment, onboarding, submission, missing information, build start, delivery, revision submission, and revision completion.

Audit sensitive actions including authentication events, payments, status changes, file access, admin changes, delivery release, and revision actions.

## V1 exclusions

- automatic Custom GPT creation or transfer
- subscriptions
- deposits and remaining balances
- multiple AI employees per customer
- builder role
- live chat
- voice or phone agents
- WhatsApp
- CRM integrations
- website chat widget
- customer token billing
- autonomous tool execution
- SEO CMS
- automatic website scraping
- public API
- mobile app
- reseller/affiliate systems
- production deployment without owner approval

## Release definition

The complete test-mode customer and admin journey must pass end-to-end. Tenant isolation, payment integrity, private file access, state-transition enforcement, QA delivery blocking, revision entitlement, accessibility, and production build viability must be verified.
