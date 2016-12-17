# Klausurvorbereitung 3

<!-- TOC depthFrom:2 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Transaction Processing Systems](#transaction-processing-systems)
	- [Key Functions](#key-functions)
	- [Different types](#different-types)
- [Functional Area Information System](#functional-area-information-system)
	- [Problems](#problems)
- [Enterprise Resource Planning Information Systems](#enterprise-resource-planning-information-systems)
	- [Enterprise Resource Planning](#enterprise-resource-planning)
	- [Core ERP Modules](#core-erp-modules)
- [Extended ERP](#extended-erp)
	- [Benefits](#benefits)
	- [Limitations](#limitations)
	- [Approaches](#approaches)
		- [Vanilla](#vanilla)
		- [Custom Approach](#custom-approach)
		- [Best of Breed Approach](#best-of-breed-approach)
		- [SaaS](#saas)
			- [Advantages](#advantages)
			- [Disadvantages](#disadvantages)
	- [Cause of ERP Implementation Failures](#cause-of-erp-implementation-failures)
- [CRM](#crm)
	- [Key features](#key-features)
	- [Architecture](#architecture)
- [Supply chain](#supply-chain)
	- [Structure & components](#structure-components)
	- [Supply Chain Management](#supply-chain-management)
	- [Value chain](#value-chain)
	- [Interorganizational](#interorganizational)
		- [Types of frictions](#types-of-frictions)
	- [Push/Pull model](#pushpull-model)
	- [Problems](#problems)
	- [Solutions](#solutions)
	- [Technology Support](#technology-support)

<!-- /TOC -->

## Transaction Processing Systems
* Supports the monitoring, collection, storage and processing of data
* Data comes from the organization's basic business transactions
  * Each basic business transaction generates data
* Must be dependable, reliable and support high processing capacity
* Supports core operations
* Collects data continuously and *in real time*

### Key Functions
* Efficiently handle high volumes of data
* Avoid errors
  * Overlapping updates
  * Inconsistencies
* Reverse erroneous transactions
* Maintain privacy and security

### Different types
* Batch processing
  * Data is collected and accumulated in batches
  * Updates per batch (e. g. over night)
* Online transaction processing (OTP)
  * Business transactions are processed as soon as they occur
  * Updates in real time

## Functional Area Information System
* Supports a particular functional area in the organization
* Increases each area's internal efficiency and effectiveness

### Problems
* Isolated systems
* Lack of communication between the systems
* Data inconsistency
* Lack of integration on an organizational level
* Difficult and inefficient decision making
* Increasing cost to perform an activity/operation

## Enterprise Resource Planning Information Systems
* Are an evolution of FAISs
* Correct lack of communication of FAISs
* Contain one common database
* Adopt a business process view of the overall organization
* Seamless information flow between functions
* Managing and fulfillment of end-to-end cross-departmental processes
* Either commercially purchased or internally developed

### Enterprise Resource Planning
* Technological backbone of e-business
* Cross-functional system
* Integrates modules that support internal business processes
* Real-time view of business processes
* Track business resources
  * Cash, production, inventory etc.
* Make sure commitments are met (e. g. customer deliveries)
* Help in
  * Automating business processes
  * Reducing inventories
  * Shortening lifecycles
  * Lowering costs
  * Improving operations

### Core ERP Modules
* Sales, Distribution, Order Management
* Production Planning
* Integrated Logistics
* Accounting and Finances
* Human Resources

## Extended ERP
* Also called "ERP II"
* Web-enabled links to customers, suppliers, business partners
* Functions as e-business suites

### Benefits
* Organizational flexibility
* Decision support
* Quality and efficiency
* Provides an opportunity to improve and redesign outdated business processes

### Limitations
* Predefined business processes as best practices might not fit organization
* Complex, expensive and time-consuming to implement
* Implementation challenges (on-time, scope, fit, trainings etc)

### Approaches
#### Vanilla
* Standard ERP package
* Built-in configuration options
* Quick Implementation
* **Limited adaption of organizational business processes**
#### Custom Approach
* Customized ERP system
* Development of new customized functions to fit the firm
* Careful examination of existing business processes
* **Customization is expensive and risky**
#### Best of Breed Approach
* Combining benefits of both approaches
* Avoiding extensive costs and risks of customization
* Mixing and mathcing core business processes of different vendors
#### SaaS
* Cloud-based ERP system
* Renting from Application Service Provider (ASP)
* Relationship regulated via Service Level Agreements (SLAs)
##### Advantages
* Good for companies not able to invest a lot
* Prevent initial hardware and software expenses
* Can be used from any location through the Internet
* Systems are easily expandable
##### Disadvantages
* Security issues are unclear
* Unavailability of control over the system
* Lack of maintenance facilities when system is slow or unavailable
* Business continuity issues if provided system is slow

### Cause of ERP Implementation Failures
* Affected employees not involved enough in planning and development phases
* Too much and too fast change
* Insufficient training in new work practices
* Failure to perform proper data conversion and testing

## CRM
* Customer-focues and customer-driven organizational strategy
* Customer-centric
* Personal marketing
* Customer intimancy
* More time with customers

### Key features
* Build sustainable long-term customer relationships
* Acquire new customers
* Support retaining existing customers
* Expand relationships with proftiable customers
* Real-time access to customer information
* 360-degree view of consolidated customer data

### Architecture
* Analytical CRM
  * Customer database
  * Data analysis
* Operative CRM
  * Marketing automation
  * Sales automatoin
  * Service automation
* Collaborative CRM
  * Face-to-face contact
  * Internet
  * E-Mail
  * Call center


## Supply chain
* Flow of materials, information, money and services
  * From raw suppliers, through factories and warehouses, to end customers
* Tight integration of business to suppliers, business partners and customers
* Supply of necessary gods and services from supplier to organization
* Defines how business partners are linked together
* Leaves organization to focus on core competencies
* Imrpoves supply chain visiblitiy
* Improves inventory velocity

### Structure & components
* Upstream: Sourcing from external suppliers
* Internal: Packaging, assembling, manufacturing activities
* Downstream: Distribution
* Flows: Material, financial

### Supply Chain Management
* Process of planning, organizing and optimizing the various activities performed along the supply chain
* Improves how to find raw materials to produce a product or service and deliver it to customers

### Value chain
* Plan
  * Strategic component of SCM
  * Development of a set of metrics to minitor supply chain
  * Target is high quality and low cost
* Source
  * Choice of suppliers
  * Development of pricing, delivery & payment processes
  * Development of good management processes
  * Monitor and improve supplier relationships
* Make
  * Product manufacturing
  * Scheduling activities for production, testing, packaing, and preparation
  * Measure quality, production output, worker productivity
* Deliver
  * Logistics
  * Coordinate receiving of customer orders
  * Develop warehouse networks
  * Arrange transportatoin methods to customer
  * Set up customer invoicing
* Return
  * Return process for defective or excess products from customers
  * Customer support with problems with delivered products

### Interorganizational
* Reduce costs of routine business transactions
* Improve quality of information flow by eliminating errors
* Compress cycle time involved in fulfulling business transactions
* Eliminate paper processing and associated inefficiencies and costs
* Make transfer and processing of information easier for users
* Reduce problems or frictions along supply chain

#### Types of frictions
* Poor customer services
* Late deliveries of customer products/service
* Problems associated with high inventory costs and loss in revenue

### Push/Pull model
* Push: Make-to-stock (mass production)
  * Forecast customer demand
* Pull: Make-to-order
  * Via customer order

### Problems
* Uncertainties
  * Demand forecasting
  * Delivery times influenced by failures in machines or traffic jams
* Need of collaborating activities with internals and business partners

### Solutions
* Just-in-time inventory
  * Minimize inventories
  * Assembling of finished product at the right time
* Information sharing
  * Improve demand forecasting
  * Electronic data interchange
* Vendor-managed inventory
  * Supplier, rather than retailer, manages the whole supply chain process

### Technology Support
* Electronic Data Interchange (EDI)
  * Communication standard to exchange documents electronically
  * Pre-defined EDI format standards
* Extranets
  * Access to authorized business partners
  * Collaboration using VPNs
* Portals & Exchanges
  * Collaboration between companies and suppliers
  * Procurement portals (for suppliers) (upstream)
  * Distribution portals (for customers) (downstream)
