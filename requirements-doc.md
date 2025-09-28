# CSCE 4901 Requirements Document

## Product Requirements  
**Project:** Express Towing App  
**Team:** Keyboard Warriors<br>
Michael Romero, Jorge Sandoval Ruiz, Andres Ojeda, Saiyam Bhakta, Ibrahim Chaudhry  

---

## Problem Statement  
The goal of this project is to develop a product that the client will be able to utilize for their company as well as market the app to partnered businesses/organizations.  

The Express Towing App is designed to streamline the process of requesting roadside assistance and towing services. Users can quickly request help with just a few taps, choosing from services such as towing, lockouts, fuel delivery, tire changes, and jump starts. The app connects drivers directly with tow truck operators, cutting out delays often caused by third-party insurance processes. With features like account creation, scheduling options, and real-time service updates, the app provides customers with faster, more reliable roadside support.  

Currently, many people face long wait times when requesting roadside assistance through insurance companies or traditional hotlines. These delays can be frustrating and unsafe, especially when drivers are stranded on the road. The Express Towing App aims to solve this problem by creating a direct connection between customers and towing providers, eliminating unnecessary middlemen. By offering a fast, user-friendly platform, the app enables towing companies to serve more customers efficiently while giving users an easy way to request help with their roadside problems.  

---

## System Requirements & Tech Stack  
*What system configuration needs to run your proposed system (including anything third party that is needed to run your system).*
### Mobile App (Customer & Driver)  
- **Operating Systems:** iOS 17+, Android 10+  
- **Hardware & Software:**  
  - GPS/location services enabled  
  - Reliable internet connection  
  - Camera for verification photos  

### Front-End  
- Mobile App: Developed using **React Native** (iOS & Android)  
- Web App: Developed using **React.js**

### Back-End  
- Server and backend implemented using **Node.js + Express.js**  
- **REST API** for communication with the front-end
- WebSockets for real-time updates (driver location, ETA, request acceptance)

### Database  
- **MySQL (or Supabase)** to store users, drivers, driver service logs, service request data, etc.

### Deployment  
- AWS  
- App Store / Play Store  

### Authentication  
- **Firebase Authentication or Auth0** for user login and authentication

### Third Party  
- **Stripe** for in-app payments
- Some GPS API for location services

---

## User Profile
*Who is the system intended for? What characteristics should the users have (this can also be a range of things such as reading level, etc.).*
### Primary Users:
- **Customers/Vehicle Owners:** Vehicle owners in need of quick roadside service and help, not wanting long wait times.
- **Tow Drivers:** Must sign up with verification (VIN, ID, insurance, etc.). Can include independent drivers or drivers associated with a towing company. Drivers can accept and fulfill customer requests.
- **Dispatchers/Admins:** Track drivers, see logs, manage requests, assign jobs, configure pricing, and approve sign-ups.

### Other Characteristics:
- Age Range: 18 or older (Drivers with a valid license)
- Motivations: Fast, safe, and transparent help for customers. Operational efficiency.
- Service Range: About a 10-15-mile radius.
- Digital literacy, able to navigate a simple UI

---

## List of Features  
*Provide a numbered list of features (F1, F2, etc.) that concisely, clearly, and accurately describe that which constitutes your project.*
| No. | Feature | Description | Priority |
|-----|---------|-------------|----------|
| F1  | Service Request | Customers instantly request roadside assistance; drivers pick, customer approves. | 1 |
| F2  | Range of Services | Towing, lockouts, fuel delivery, tire changes, jump starts (this is the baseline) | 1 |
| F3  | Scheduling | Option to schedule car tows | 3 |
| F4  | User Registration/Accounts | Login and profile management, storing vehicle information, driver information and verification | 1 |
| F5  | Real-Time Updates/GPS Tracking | Track driver acceptance and ETA; customers track drivers on a GPS | 1 |
| F6  | Secure Payments | In-app payment system using Stripe with receipts and service history; drivers/companies give quotes, then customer accepts the best quote (or base rate + per-mile for pricing) | 1 |
| F7  | Ratings/Reviews | Customers rate drivers/companies (only drivers/companies can see the reviews; they’re not visible to clients) | 2 |
| F8  | Driver Dashboard on Separate Driver App | Dedicated interface for drivers to accept, manage, and navigate to service requests, and an availability toggle | 1 |
| F9  | Notifications | Enable push/sms notifications for job completion, ETA, etc. | 1 |
| F10 | Admin Interface | Administrators can access dispatcher view, manage jobs, tasks, and pricing; they have a service log of all their drivers | 1 |
| F11 | Request Cancellation | Customers can cancel, but will be charged a fee if they cancel after 5 minutes of accepting a request | 1 |
| F12 | Tips | Customers can tip drivers | 1 |
| F13 | Chat/Phone Calls | Customers can call dispatchers/admins while drivers are on the way. Customers can send messages to drivers and dispatchers through an in-app chat. Drivers can call customers when they’re close to the destination. | 2 |
| F14 | Report | Customers can report drivers and vice versa for inappropriate behavior. | 1 |

---

## Functional Requirements / User Stories  
*List the Priority as 1 (High Priority - Critical) to 3 (Low Priority – Would be nice if we have time)*
### 1. Service Request Flow  
| No. | User Story Name | User Story | Priority |
|-----|-----------------|------------|----------|
| R1  | Send Request | As a user, I can send a roadside service request so that drivers can respond. | 1 |
| R2  | Pick Service Type | As a user, I can pick a service type (towing, tire fix, fuel delivery, jump start, lockout) depending on my needs. | 1 |
| R3  | Service Descriptions | As a user, I can see a short description for each service type. | 1 |
| R4  | Driver Quotes | As a driver, I can see incoming requests and provide quotes for them. | 1 |
| R5  | Approve Quote | As a user, I can approve a driver’s bid/quote so that I can get service at the price I want. | 1 |
| R6  | Scheduling | As a user, I can schedule service requests ahead of time. | 3 |
| R7  | Driver Info | As a user, I can see drivers’ information (name, profile picture, license plate). | 2 |

### 2. Registration  
| No. | User Story Name | User Story | Priority |
|-----|-----------------|------------|----------|
| R1  | Sign Up | As a user, I can sign up using email/password, Google, or Facebook to save my information. | 1 |
| R2  | Save Vehicle | As a user, I can save my vehicle details (make/model/license plate). | 2 |
| R3  | Company Driver Verification | As a company driver, I can submit VIN, license, insurance, ID, etc. for account verification. | 1 |
| R4  | Independent Driver Verification | As an independent driver, I can submit VIN, license, insurance, ID, etc. for account verification. | 3 |

### 3. Location/Tracking  
| No. | User Story Name | User Story | Priority |
|-----|-----------------|------------|----------|
| R1  | Share Location | As a user, I can share my location via GPS or pin my location so drivers can find me. | 1 |
| R2  | Driver Location Visibility | As a driver, both company admins and users can see my current location and ETA. | 2 |
| R3  | Manual Address Entry | As a user, I can enter my address manually if GPS tracking fails. | 1 |
| R4  | Tracking Warnings | As a user, I should receive a warning flag if live tracking or personal driver is incorrect. | 1 |
| R5  | Live Location/ETA | As a user, I can see drivers’ live location and ETA so I know when help arrives. | 1 |
| R6  | Driver Status Updates | As a user, I can be updated on driver status (assigned route, cancellation, on-site, completed). | 1 |

### 4. Pricing  
| No. | User Story Name | User Story | Priority |
|-----|-----------------|------------|----------|
| R1  | Accept Bid | As a user, I can accept bid options from a driver of my choice. | 2 |
| R2  | Set Rates | As a company/driver, I can pick the fixed rate + per mile pricing. | 2 |
| R3  | Price Breakdown | As a user, I can see the breakdown (base fee + mileage + bid + additional fees). | 1 |

### 5. Payment  
| No. | User Story Name | User Story | Priority |
|-----|-----------------|------------|----------|
| R1  | Secure Payment | As a user, I can pay securely within the app via Stripe. | 1 |
| R2  | Tips | As a user, I can give drivers tips that go directly to them. | 2 |

### 6. Driver Dashboard  
| No. | User Story Name | User Story | Priority |
|-----|-----------------|------------|----------|
| R1  | View Jobs | As a driver, I can view the service I need to provide and its location. | 1 |
| R2  | View Reviews | As a driver, I can see reviews left by customers after a service has been done. | 2 |

### 7. Admin Dashboard  
| No. | User Story Name | User Story | Priority |
|-----|-----------------|------------|----------|
| R1  | Manage Vehicles | As an admin, I can manage company vehicles and assign them to employees. | 1 |
| R2  | Set Prices | As an admin, I can set prices per service. | 1 |
| R3  | See Reviews | As an admin, I can see reviews left by customers after a service has been done. | 2 |

### 8. User Interaction  
| No. | User Story Name | User Story | Priority |
|-----|-----------------|------------|----------|
| R1  | Talk to Dispatcher | As a user, I can talk to my driver’s admin/dispatcher via phone or in-app chat to give important information. | 1 |
| R2  | Talk to Driver | As a user, I can talk to my driver via in-app chat to give important information. | 1 |
| R3  | Driver Calls User | As a driver, I can call my customer to let them know I’ve arrived. | 1 |
| R4  | Cancel Request | As a user, I can cancel a request after approval, but I will be charged a fee if I cancel too late. | 1 |
| R5  | Report Driver | As a user, I can report drivers for inappropriate behavior. | 1 |
| R6  | Report Customer | As a driver, I can report customers for inappropriate behavior. | 1 |

---

## Non-Functional Requirements  
*Describe any constraints or cross-cutting characterstics of the system in a manner that is clear,
specific, and testable. Each requirement should have a unique identifier (e.g. NF1, NF2,..). Only
present those which are applicable to your system. Categories include but are not limited to:<br>
Security<br>
Reliability<br>
Usability<br>
Cross-Platform Compatibility<br>
Accuracy*
| No.  | Name | Description | Priority |
|------|------|-------------|----------|
| NF1  | Security | User and driver data (logins, licence, VIN, insurance, etc.) must be stored securely in the database; the app shall support user authentication. | 1 |
| NF2  | Reliability | The system should handle real-time GPS + driver bidding with minimal downtime. | 2 |
| NF3  | Usability | The app should have a clean and simple UI that’s easily accessible. Target is “simple like Uber;” new users should understand core features within 5 minutes. The core flow (client request -> driver bid -> approve -> track) should take no longer than a minute. | 1 |
| NF4  | Cross-Platform Compatibility | Both Customer App and Driver App must work on iOS and Android; installable via the App Store and the Play Store. | 1 |
| NF5  | Performance | GPS tracking should update every couple of seconds; chat messages should have a latency under 200ms in normal conditions. | 2 |
| NF6  | Accessibility | The app should support dark mode, readable fonts, basic screen-reader compatibility, and multi-language support. | 3 |
| NF7  | Scalability | The app should handle multiple concurrent requests without major slowdown. | 2 |
| NF8  | Observability | The app should gather info on error logging and crash tracking. | 2 |
