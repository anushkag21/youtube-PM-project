# YouTube Teen Consent Flow — India

> An interactive Product Management prototype for a privacy-first parental consent experience for YouTube users aged 13–17 in India.

## Overview

**YouTube Teen Consent Flow** is an interactive clickable prototype that explores how YouTube could design a smooth, verifiable parental-consent journey for teenagers under 18 in India.

The prototype focuses on balancing three goals:

- **Regulatory compliance** — obtain verifiable parental consent before processing a minor's personal data.
- **Privacy by default** — disable behavioral profiling and personalized advertising for under-18 users.
- **Low-friction UX** — make the consent journey understandable, reversible, and easy for both teenagers and parents.

The experience follows a complete happy path from **age detection → parental approval → identity verification → consent configuration → ongoing parental control → protected YouTube experience → PM compliance monitoring**.

> **Note:** This is a product/design prototype using mock data. It does not connect to YouTube, Google Family Link, DigiLocker, Aadhaar, or any production backend.

---

## Product Concept

The prototype follows a fictional 15-year-old user, **Aarav**, and his parent/guardian, **Meera**.

### Core user journey

```text
Teen signs up
     ↓
Age detected as under 18
     ↓
Parent/guardian approval requested
     ↓
Guardian identity & relationship verification
     ↓
Consent preferences configured
     ↓
Consent granted
     ↓
Parent gets ongoing controls
     ↓
Teen accesses protected YouTube experience
     ↓
Product team monitors compliance & funnel health
```

---

## Key Product Features

### 1. Age-Aware Onboarding

The flow begins by using the date of birth associated with the user's account to determine whether the user is under 18.

Instead of treating age as a simple checkbox, the prototype presents an age-aware onboarding experience.

**Product principle:**  
> Age verification should be a meaningful control point rather than a self-declared form field.

---

### 2. Under-18 Consent Routing

When a minor is detected, the experience clearly explains why parental approval is required.

The teenager can:

- Request parental approval
- Continue watching general content while approval is pending

This avoids turning compliance into a hard dead-end.

---

### 3. Parent-Centric Consent

The consenting party is explicitly shifted from the teenager to the parent/guardian.

The parent receives a request containing:

- Child's identity
- Application/service requesting access
- Type of account being requested
- Guardian confirmation requirement

This makes the consent relationship explicit.

---

### 4. Verifiable Parental Consent

The prototype introduces a simulated **DigiLocker-based verification flow**.

The mock verification experience demonstrates:

- Adult identity verification
- Guardian relationship verification
- OTP interaction
- Consent record creation
- Timestamped/auditable consent

The prototype intentionally makes the verification step more meaningful than a simple:

> "I am the parent" checkbox.

**Important:** DigiLocker/Aadhaar verification is simulated and does not make any real government or identity-service calls.

---

### 5. Privacy by Default

After verification, the parent can configure account permissions.

#### Parent-controlled settings

- Watch history & playlists
- Comments & community posts
- Break and bedtime reminders

#### Locked privacy protections

The prototype keeps the following protections enabled for under-18 users:

- Personalized advertising — **Off**
- Behavioral profiling — **Off**
- Contextual recommendations — **On**

Recommendations are framed around the user's current viewing context rather than a persistent behavioral profile.

---

### 6. Consent Withdrawal

Consent is designed to be reversible.

The parent dashboard provides a one-tap withdrawal interaction demonstrating the principle:

> Consent should be as easy to withdraw as it was to provide.

When consent is withdrawn, the prototype updates the account state and communicates that data processing is no longer active while allowing basic video watching to continue.

---

### 7. Protected Teen Experience

Once approved, Aarav enters a protected YouTube experience.

The prototype communicates:

- Parent approval status
- Active privacy protections
- Non-personalized advertising
- Contextual recommendations
- No behavioral profiling

The experience also demonstrates a future-state concept where the account can transition into a normal adult experience when the user turns 18.

---

## Product Analytics Dashboard

The final screen demonstrates how a PM could monitor the system after launch.

### Key metrics

| Metric | Example Value | Purpose |
|---|---:|---|
| VPC Coverage Rate | 59% | Measures consent coverage among eligible users |
| Verified Teen Accounts | 26.4M | Tracks adoption |
| DigiLocker Success | 92% | Measures verification reliability |
| Protections Enabled | 99.8% | Compliance/correctness guardrail |
| Consent Complaints | 1.9K | Detects trust and UX issues |

### Funnel

```text
12.4M
Started
   ↓
10.8M
Verified
   ↓
10.2M
Completed
```

### Platform segmentation

The dashboard also compares consent coverage across:

- iOS
- Android
- Web
- Android TV

This helps identify platform-specific friction rather than relying only on an aggregate conversion metric.

---

## PM Thinking Behind the Prototype

The prototype is designed around a few core product principles.

### Compliance should not become friction

Instead of placing a compliance wall in front of users, the experience guides teenagers and parents through a clear sequence of actions.

### Privacy should be the default

Sensitive processing decisions are not presented as optional parental toggles when they are intended to remain restricted for minors.

### Consent should be reversible

The parent receives ongoing control rather than providing consent once and losing visibility afterward.

### Measure the entire funnel

A successful consent system cannot be evaluated only by the number of users who start verification.

The product team should monitor:

```text
Eligible Users
      ↓
Consent Started
      ↓
Verification Started
      ↓
Verification Successful
      ↓
Consent Completed
      ↓
Protections Correctly Applied
      ↓
Consent Retained
```

---

## Interactive Prototype

The prototype contains **8 navigable stages**:

| Step | Experience |
|---|---|
| 0 | Product introduction |
| 1 | Age check |
| 2 | Under-18 routing |
| 3 | Parent approval request |
| 4 | DigiLocker verification |
| 5 | Consent & privacy configuration |
| 6 | Parent dashboard |
| 7 | Protected YouTube experience |
| 8 | PM compliance dashboard |

### Interactive elements

The prototype includes:

- Step-by-step navigation
- Previous/Next controls
- Keyboard navigation using `←` and `→`
- Clickable progress indicators
- Toggle interactions
- Consent withdrawal interaction
- OTP input auto-advance
- Simulated DigiLocker verification
- Animated screen transitions
- Responsive layouts for smaller screens

---

## Tech Stack

This prototype intentionally keeps the implementation lightweight.

**Frontend**

- HTML5
- CSS3
- Vanilla JavaScript
- Inline SVG

**Dependencies**

- No frameworks
- No npm packages
- No build system
- No backend
- No external APIs

The entire prototype is contained in:

```text
index.html
```

---

## Project Structure

```text
youtube-PM-project/
│
├── index.html
└── README.md
```

The current implementation is deliberately self-contained, making it easy to run, demonstrate, or deploy as a static webpage.

---

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/youtube-PM-project.git
cd youtube-PM-project
```

### 2. Open the prototype

Because the project has no build dependencies, you can simply open:

```text
index.html
```

in a browser.

### Optional: Run with a local server

Using Python:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

---

## Prototype Limitations

This repository represents a **PM/product prototype**, not a production implementation.

The following are simulated:

- YouTube account data
- Google/Familly Link interaction
- DigiLocker verification
- Aadhaar verification
- OTP verification
- Consent records
- Analytics data
- Compliance metrics
- Video recommendations
- Parent dashboard data

No real user data is collected or processed.

---

## Potential Production Architecture

A production implementation could evolve into a service-oriented architecture:

```text
                    ┌─────────────────────┐
                    │  YouTube Client     │
                    │ Web
