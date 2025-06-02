# Blockchain Technology in Farmer’s Portal

## Introduction

In this project, I have addressed the lack of transparency and trust in agricultural supply chains by designing a secure Farmer’s Portal using blockchain technology. The portal allows farmers, distributors, and retailers to record transactions and product provenance on an immutable ledger, reducing fraud and improving traceability.
The business problem is ensuring food safety and fair trade by enabling stakeholders to verify every step of produce from farm to market.

## Dataset

I have used a synthetic dataset representing farm produce shipments (e.g., crop variety, quantity, timestamps). The dataset was organized in CSV format with fields like `ProductID`, `OriginFarmID`, `DestinationID`, `Timestamp`, and `QualityMetrics`. If available, historical market data from the USDA or Kaggle could augment this (e.g., farm yields, prices, and certifications). The size of the simulated dataset is on the order of thousands of records to demonstrate scalability.

## Methodology

I have implemented a private blockchain network to record each transaction. The step-by-step workflow included:
- **Data Ingestion:** Load farm shipment data from CSV/SQL into a staging database.
- **Blockchain Setup:** Use Python and a blockchain framework (e.g., Hyperledger Fabric or Ethereum with Python wrappers) to create a network of nodes.
- **Smart Contracts:** Write smart contracts (Solidity or Chaincode) to validate transactions (e.g., new harvest entry, shipment sent).
- **Consensus & Storage:** Use a consensus algorithm (e.g., Proof of Authority) to append verified transactions to blocks.
- **Query Interface:** Develop Python scripts or a simple API for users to query provenance data.

At each step, data engineering and ETL (Extract-Transform-Load) tasks were scripted in Python; for example, cleaning input data and preparing it for blockchain recording.

## Tools & Techniques

- **Blockchain Framework:** Hyperledger Fabric (Go/Node) or Ethereum (Solidity) for ledger and smart contracts.  
- **Programming Languages:** Python (for data processing, integration) and Solidity (for contracts).  
- **Libraries:** Pandas/Numpy for data handling; `web3.py` or Hyperledger SDK for blockchain interaction.  
- **Data Management:** PostgreSQL or SQLite for interim data storage.  
- **Version Control:** Git for code and smart contract tracking.  
- **Concepts:** Decentralized ledgers, immutability, distributed consensus.

## Results & Insights

The deployed system successfully logged all simulated transactions on-chain. Key insights include:
- > **Traceability:** Each product batch can be traced back to its origin farm, ensuring accountability.
- > **Fraud Reduction:** Smart contract checks (e.g., requiring digital signatures from farms) help prevent unauthorized data entry.
- > **Efficiency:** Dashboard visualizations (e.g., in Tableau) can display real-time supply-chain flows.
  
For example, I have demonstrated that a late shipment annotated in the blockchain ledger could be quickly identified and traced, highlighting potential processing bottlenecks. Preliminary tests showed that transaction throughput and latency met real-time requirements for moderate loads (hundreds of transactions per minute).

## Setup & Running Instructions

To run this project:

1. **Install Dependencies:** Use `pip install -r requirements.txt` to install Python libraries (e.g., web3, pandas).  
2. **Blockchain Network:** Install and configure Hyperledger Fabric (v2.x) or Ganache/Ethereum. Ensure Docker is running if needed.  
3. **Smart Contracts:** Compile and deploy contracts using Truffle or Fabric tools.  
4. **Data Load:** Populate the database with sample CSV data (`farm_portal_data.csv`) via the provided `load_data.py` script.  
5. **Execution:** Run `python start_portal.py` to launch the API and interface.  
6. **View Dashboard:** Open `dashboard.html` or access the Tableau public dashboard for visualization.  

Detailed instructions and sample config files are included in the `docs/` directory.


## Credits

This project was supervised by Professor Dr. Sasikumar P. and is based on collaborative research in blockchain applications for agriculture.
