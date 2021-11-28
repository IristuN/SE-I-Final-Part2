# Software Engineering I Chapter 11 : Physical Architecture Layer Design
---

## Physical Architecture Layer Design
#### Architectural components
- **Software components**
	- Data storage
	- Data access logic
	- Application logic
	- Presentation logic
- **Hardware components**
	- Client computers
	- Servers
	- Networks

---
## Computing Architecture
#### Server-based architecture
- Server peforms all
- One point of control: server can overload
- Upgrade in large "increment" and expensive
```mermaid
classDiagram
class Client{
	(terminal)
}
class Server_Host{
	- Data Storage
	- Data Access Logic
	- Application Logic
	- Presentation Logic
	(mainframe computer)
}
Client -- Server_Host
```

#### Client-based architecture
- Clients are personal computers on <u>network</u>
- Server stores data on same <u>network</u>
- Simple to develop
- quickly overloaded
	- data downloaded to client
	- <u>Network</u> traffic may excessive
	- Bottleneck at client

```mermaid
classDiagram
class Client{
	- Data Access Logic
	- Application Logic
	- Presentation Logic
	(microcomputer)
}
class Server{
	- Data Storage
	(microcomputer)
}
Client -- Server
```

#### Client-server architecture
- Balance betwwen client and server
- Predominant architecture
- Amont of client
	- Thin clients: presentation logic
	- Thick clients: presentation and application logic
- Highly scalable at incremental cost
- More complex

##### Two-tiered architecture
```mermaid
classDiagram
class Client{
	- Application Logic [Thick client]
	- Presentation Logic
	(microcomputer)
}
class Server{
	- Data Storage
	- Data Access Logic
	- Application Logic [Thin client]
	(micro,mini, or mainframe)
}
Client -- Server 
```

##### Three-tiered architecture
```mermaid
classDiagram
class Client{
	- Presentation Logic
	(microcomputer)
}
class Application_Server{
	- Application Logic
	(microcomputer)
}

class Database_Server{
	- Data Storage
	- Data Access Logic
	(micro,mini, or mainframe)
}
Client -- Application_Server
Application_Server -- Database_Server

```

##### N-tier architecture 
- Application logic split
- Common in e-commerce
- Better load balancing
- More scalable
- Higher demands on network
```mermaid
classDiagram
class Client{
	- Presentation Logic
	[Web browser]
	(microcomputer)
}
class Web_Server{
	- Web-realated 
	Application Logic
	[HTML & graphics]
	(micro,mini, or mainframe)
}

class Application_Server{
	- Non-Web-related
	Application Logic
	(micro,mini, or mainframe)
}

class Database_Server{
	- Data Storage
	- Data Access Logic
	(micro,mini, or mainframe)
}
Client -- Web_Server
Web_Server -- Application_Server
Application_Server -- Database_Server

```

#### Factors
- **Cost of infrastructure** (initial acquisition and future growth)
	- hardware, software, network
- **Cost of development**
	- Complexity / GUI dev. tools
- **Ease of development**
	- Requirment of skills
- **Interface capabilities**
	- character-based vs GUI
- **Control and security**
	- One point vs many points of contol
- **Scalability **(increase or decrease in capacity; upgrades)
	- Cost/limitation of capacity change or upgrade

|                        | Server-Based | Client-Based | Client-Server |
|------------------------|:------------:|:------------:|:-------------:|
| Cost of infrastructure |      VH      |       M      |       L       |
| Cost of development    |       M      |       L      |       H       |
| Ease of development    |       L      |       H      |      L-H      |
| Interface capabilities |       L      |       H      |       H       |
| Control and security   |       H      |       L      |       M       |
| Scalability            |       L      |       M      |       H       |

---
## Cloud Computing
- pay-as-you-go
- **Deployment model**
	- Private
	- Public
	- Hybrid
- **Service model**
	- <u>SaaS</u> (Software as a Service) - Hosted apps
		- <u>PaaS</u> (Platform as a Service) - Dev. tools, OS
			- <u>IaaS</u> (Infrastructure as a Service) - Servers & storage, Networking firewalls, Data center

--- 
## Ubiquitous Computing and IoT
- Ubiquitous computing
- Internet of things
- Computing devices

---
## Green IT
#### Topic
- E-waste
- Energy consumption of data centers and desktops
- Paperless office

---
## Nonfunctional Requirements Revisited
#### Operational
- Technical environment 
- System integration 
-  Portability 
-  Maintainability

#### Performance
- Speed  
- Capacity
- Availability & reliability

#### Security
- System value 
- Access control
- Encryption & authentication
- Virus control

#### Cultural & Political influence
- Centralized vs. local control
- Language differences (keyboard 
requirements)

#### Legal implications
- Laws & government regulations
- Global presence requires scrutiny of 
local laws

|                                | Server-Based | Client-Based | Thin Client-Server | Thick Client-Server |
|--------------------------------|:------------:|:------------:|:------------------:|:-------------------:|
| __Operational__              	 |              |              |                    |                     |
| System Integration             |       ✓      |              |          ✓         |          ✓          |
| Portability                    |              |              |          ✓         |                     |
| Maintainability                |       ✓      |              |          ✓         |                     |
| __Performance__                |              |              |                    |                     |
| Speed                          |              |              |          ✓         |          ✓          |
| Capacity                       |              |              |          ✓         |          ✓          |
| Availability/Reliability       |       ✓      |              |          ✓         |          ✓          |
| __Security__                   |              |              |                    |                     |
| High System Value              |       ✓      |              |          ✓         |                     |
| Access Control                 |       ✓      |              |                    |                     |
| Encryption/Auth                |              |              |          ✓         |          ✓          |
| Virus Control                  |       ✓      |              |                    |                     |
| __Cultural & Political__       |              |              |                    |                     |
| Multilingual                   |              |              |          ✓         |                     |
| Customization                  |              |              |          ✓         |                     |
| Making Unstated Norms Explicit |              |              |          ✓         |                     |
| Legal Requirement              |       ✓      |              |          ✓         |          ✓          |

---
## Infrastructure Design
utilize hardware, software, and communication
- Change or improve the existing infrastructure 
- Coordination of infrastructure components
	- Deplyment diagram
	- Network model


#### Deployment Diagram
- A node
- An artifact
- A node with a deployed artifact
- A communication path

#### Components and Deployment Diagram
- ** Logical components**
	- business components
	- process components
- **Physical components**
	- tech components (.NET, Node.js)
	- web sevices
	- APIs
	- executables

#### Network Model
- major components and their geographic locations
- Purposes
	- convey the complexity
	- show how components will fit together

---

## Hardware & Software Specifications
Utilize <u>network diagram</u>  and <u>deployment diagram</u>
#### Software requirments
- Operating System
- Special purpose software (e.g. DBMS)
- Include training needed, maintenance, warranties and licensing agreements

#### Hardware requirements
- type and quantity of
	- servers
	- peripherals
	- storage
	- backup devices
- Descibe <u>minimum requirements</u>
- Use an **alternative matrix** to evaluate vendor proposals
#### Factors
**1. Funtions and Features**
**2. Performance** 
**3. Legacy Databases and Systems** - How well hardware and software interact
**4. Hardware and OS Strategy** - future migration plans
**5. Cost of Ownership** -costs beyond purchase
**6. Political Preferences** - changes should be minimized
**7. Vendor Performance** - different future prospects

---
## Verifying and Validating the Physical Architecture Layer
- deployment diagram and network diagram are consistent
	- same architecture
	- low-level network & deployment diagram for each nodes of top-level network diagram
- Consistent with low-level network model
- Test nonfunctional requirement

---