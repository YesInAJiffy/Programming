# Domain Driven Design
Domain-Driven Design (DDD) is a software development approach created by Eric Evans in his 2003 book that focuses on building complex software by closely aligning it with the business domain it serves.

## Core Philosophy

The central idea is that the most critical complexity in software projects is understanding the business domain itself, not the technical implementation. DDD provides strategies for managing this complexity through modeling and collaboration.

## Key Concepts

**Ubiquitous Language**
A shared vocabulary between developers and domain experts that's used in code, documentation, and conversations. For example, if business people call something an "Order," the code should have an Order class, not a "Transaction" or "Purchase."

**Bounded Contexts**
Different parts of the system where terms and models have specific meanings. For instance, "Customer" in a sales context might mean something different than "Customer" in a support context. Each bounded context maintains its own model.

**Building Blocks**

- **Entities**: Objects defined by their identity (e.g., a Customer with ID #12345)
- **Value Objects**: Objects defined by their attributes, not identity (e.g., an Address or Money amount)
- **Aggregates**: Clusters of related entities and value objects treated as a unit, with one root entity controlling access
- **Repositories**: Mechanisms for retrieving and storing aggregates
- **Services**: Operations that don't naturally belong to entities or value objects
- **Domain Events**: Something significant that happened in the domain

Think of this like a **Patient** in a large hospital system. If you tried to build one single "Patient" model for the entire hospital, it would be a chaotic mess of data. Instead, different departments (domains) see that same human being through very different lenses.

### The "Patient" Example

Just like the Product example in your image, a Patient is modeled differently depending on the **Context**:

---

### 1. The Admissions Domain

When a patient first walks in, the staff cares about **Identity and Logistics**.

* **Attributes:** Name, Home Address, Insurance Provider, Next of Kin.
* **Goal:** Ensure the hospital gets paid and knows who to contact in an emergency.
* **Relationships:** Linked to a **Bed** or a **Room**.

### 2. The Clinical/Medical Domain

Once the patient is in the exam room, the doctor doesn't care about their home address or their insurance deductible. They care about **Vitals and History**.

* **Attributes:** Blood Type, Allergies, Current Heart Rate, Medical History.
* **Goal:** To treat the illness safely.
* **Relationships:** Linked to **Lab Results** and **Prescriptions**.

### 3. The Billing Domain

After the treatment, the finance department looks at the patient as a **Financial Account**.

* **Attributes:** Patient ID, Total Cost of Procedures, Amount Covered by Insurance.
* **Goal:** To issue an invoice and track payments.
* **Relationships:** Linked to **Invoices** and **Payment Gateways**.

---

### Why this is better than one big "Patient" model:

* **Privacy & Security:** The billing clerk doesn't need to see the patient’s sensitive medical history (Clinical Domain). By separating the models, you naturally enforce data privacy.
* **Performance:** The Admissions screen doesn't have to load 10 years of medical lab results just to update a phone number.
* **Simplified Logic:** If the Clinical team wants to change how "Blood Pressure" is recorded (e.g., from a string to a complex object), the Billing team’s code remains completely untouched.

### Comparison Summary

| Domain | Focus | Key Entity Relationships |
| --- | --- | --- |
| **Admissions** | Identity | Patient  Insurance Policy |
| **Clinical** | Health | Patient  Medical Record |
| **Billing** | Finance | Patient  Outstanding Balance |

> **The Big Idea:** Even though it's the same person in the real world, in software, it's better to have three small, specialized models than one "God Model" that tries to do everything.

Would you like to see how these different models "talk" to each other when a patient moves from Admissions to the Exam room?

DDD works best for complex business domains with intricate rules and logic. It's often overkill for simple CRUD applications or technical infrastructure projects. The approach requires significant collaboration with domain experts and ongoing refinement of the model.

Would you like me to explain any of these concepts in more detail?
