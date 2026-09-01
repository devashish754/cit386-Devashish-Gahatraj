# Deployment Comparison

## Business Scenario

GreenLeaf Accounting is a small accounting firm that provides tax preparation, bookkeeping, payroll, and financial reporting services to local customers. The business has 8 employees and operates from one office. It has a technology budget of about $300 per month for hosting and infrastructure.

## Workload

### Customer and Accounting Application

The business needs a small web-based accounting application for managing customer information, invoices, and accounting records.

### Workload Requirements

- The application must be reachable from outside the office by authorized users.
- It should remain available overnight.
- It should be able to grow as the number of customers increases.
- Employees should not need physical access to the server hardware.
- The business can afford approximately $300 per month.

## Deployment Comparison

### 1. VirtualBox on a Laptop

**What works:** VirtualBox is inexpensive and easy to set up. It can run the application in a virtual machine for testing.

**What breaks:** A laptop is not designed for reliable 24/7 production use. It can be turned off or disconnected, and scaling would be difficult.

**Verdict:** Good for testing, but not suitable for production.

### 2. Hyper-V on a Workstation

**What works:** Hyper-V can run a virtual machine on a Windows workstation and provides better isolation than running the application directly.

**What breaks:** The workstation must remain powered on and maintained. It also creates a single point of failure and makes scaling difficult.

**Verdict:** Possible, but not the best production choice.

### 3. Proxmox Host

**What works:** Proxmox provides virtualization and can run the application in a dedicated virtual machine with good resource management.

**What breaks:** The business must purchase and maintain physical hardware. Hardware failure could make the application unavailable.

**Verdict:** Capable, but it requires physical server management.

### 4. Physical PC

**What works:** A dedicated PC can run the application directly and provide predictable hardware resources.

**What breaks:** The company must maintain, secure, repair, and eventually replace the hardware. Scaling is also difficult.

**Verdict:** It can work, but creates unnecessary hardware responsibilities.

### 5. Azure

**What works:** Azure provides cloud infrastructure without requiring the business to purchase physical server hardware. It supports remote access, scaling, and continuous availability.

**What breaks:** The business has a recurring cloud cost and must properly configure security and user access.

**Verdict:** Best fit because it provides remote access and scalability without requiring physical server management.

## Recommendation

I recommend **Azure** for this workload.

The deciding requirement is **reliable external access without requiring the business to physically manage server hardware**. Azure satisfies this requirement better than the other deployment options.
