
# Getting Started Guide for Serey API and Services

## 1. Setting Up Nodes

### a. Testnet Node
1. **Overview**: Testnet nodes are used for development and testing without affecting the main network.
2. **Steps**:
   - Install the blockchain software for Serey.
   - Configure the node for testnet mode:
     - Update the configuration file with testnet parameters.
   - Start the testnet node:
     ```bash
     ./serey-node --testnet
     ```
   - Verify synchronization by checking logs or status commands.
3. **Troubleshooting**:
   - Common issues like network sync errors and resolutions.

### b. Production Node
1. **Overview**: Production nodes are used for live blockchain operations.
2. **Steps**:
   - Follow the same setup as for testnet, but configure for mainnet mode.
   - Use the mainnet configuration file.
   - Start the node in production mode:
     ```bash
     ./serey-node --mainnet
     ```
   - Set up monitoring and alerts to ensure uptime.
3. **Security Tips**:
   - Use firewalls and secure network configurations.
   - Enable backups for node data.

---
**Note**:<font color="red"> we provide the document to setup the nodes , with information like 
- configuration file
- IP address to sync
- backup blockchain file for central points(reduce sync time) 
- monitoring tools to check node is fully synced
- options for fullnode and witness nodes

</font>

---

## 2. Deploy Serey Services as Docker
1. **Overview**: Docker simplifies deployment by packaging the application and its dependencies.
2. **Steps**:
   - Clone the Docker repository:
     ```bash
     git clone https://github.com/serey-org/docker-services.git
     ```
   - Build the Docker images:
     ```bash
     docker-compose build
     ```
   - Start the services:
     ```bash
     docker-compose up -d
     ```
   - Verify services are running:
     ```bash
     docker ps
     ```
3. **Custom Configuration**:
   - Modify `docker-compose.yml` for environment-specific variables.

---
**Note**:<font color="red"> this part we will build a docker images thats can able to run the services of 
- api services
- database
- seeding data to tranform to their own basic website (like a clone of serey with basic features)
  
this is enough to run a website based on serey api and blockchain.
User won't able to customize the code or add on more feature.

</font>

---

## 3. Build from Scratch

### a. Clone Serey API and Frontend Repositories
1. **Clone the Repositories**:
   - API:
     ```bash
     git clone https://github.com/serey-org/serey-api.git
     ```
   - Frontend:
     ```bash
     git clone https://github.com/serey-org/serey-frontend.git
     ```
2. **Setup Environment Variables**:
   - Create `.env` files for API and frontend with appropriate values.

### b. Setup Database and Install Schema
1. **Database Setup**:
   - Install PostgreSQL or the required database system.
   - Create a new database for Serey.
     ```sql
     CREATE DATABASE serey;
     ```
2. **Install Schema**:
   - Use provided SQL scripts:
     ```bash
     psql -U username -d serey -f schema.sql
     ```
3. **Verify Database Connectivity**:
   - Test connections using tools like `psql` or database management systems.

### c. Deploy the Services
1. **API Deployment**:
   - Navigate to the API repository:
     ```bash
     cd serey-api
     ```
   - Install dependencies:
     ```bash
     npm install
     ```
   - Start the API service:
     ```bash
     npm start
     ```
2. **Frontend Deployment**:
   - Navigate to the frontend repository:
     ```bash
     cd serey-frontend
     ```
   - Install dependencies:
     ```bash
     npm install
     ```
   - Start the frontend service:
     ```bash
     npm run dev
     ```
3. **Verify Deployment**:
   - Access the frontend and API endpoints to confirm they are operational.

---
**Note**:<font color="red"> this part we provide all source code and database structure.
  
this is enough to run a website based on based on our own existing code, they can customize the api or change completely interface, but still posts data to Blockchain.

for this we need developer team or community to support development.

</font>

---


## 4. Developer Documentation
1. **Purpose**:
   - Provide clear guidance on contributing to and using Serey services.
2. **Structure**:
   - **Introduction**: Overview of Serey services.
   - **Getting Started**:
     - Setting up the development environment.
     - Key dependencies and versions.
   - **API Documentation**:
     - Endpoint descriptions.
     - Sample requests and responses.
   - **Frontend Documentation**:
     - File structure and build instructions.
   - **Troubleshooting**:
     - Common issues and solutions.
3. **Tools**:
   - Use Markdown for documentation.
   - Host on platforms like GitHub Pages, ReadTheDocs, or Notion.
---
**Note**:<font color="red"> we need team to build the documents for development, developers need to read documents , so they able to understand the structure.
- provide all possible resource
- all SDK
- all frameworks

</font>

---
