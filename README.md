# Coursetro Smart Contract DApp

A simple **Ethereum Smart Contract** and **Web3 frontend application** built using **Solidity, Remix IDE, and JavaScript**.

This project demonstrates how to build, deploy, and interact with a smart contract that stores and updates instructor information on the Ethereum blockchain.

---

# Project Overview

This decentralized application (DApp) allows users to:

- Store an instructor name and age on-chain
- Retrieve instructor information from the blockchain
- Update instructor data through a Web3-enabled web interface
- Listen to contract events emitted when the instructor is updated

The project was developed and deployed using **Remix IDE (web version)** and connected to a **local Ethereum blockchain node**.

---

# Smart Contract

The smart contract is written in **Solidity (version 0.8.20)** and stores instructor data in the blockchain state.

It also emits an event every time the instructor data changes.

```solidity
pragma solidity ^0.8.20;

contract Coursetro {

    string fName;
    uint age;

    event Instructor(string name, uint age);

    function setInstructor(string memory _fName, uint _age) public {
        fName = _fName;
        age = _age;

        emit Instructor(_fName, _age);
    }

    function getInstructor() public view returns (string memory, uint) {
        return (fName, age);
    }

}
```

---

# Architecture

The application consists of three main components:

## 1. Smart Contract (Solidity)

Handles blockchain storage and logic.

Responsibilities:

- Store instructor data
- Update instructor data
- Emit blockchain events
- Provide read access to stored data

---

## 2. Frontend Interface (HTML + JavaScript)

The frontend interacts with the blockchain through **Web3.js**.

Capabilities:

- Connect to Ethereum provider
- Read smart contract data
- Send transactions to update instructor information
- Listen for smart contract events

---

## 3. Blockchain Environment

The project was tested using a **local Ethereum network**.

Possible environments:

- Hardhat local node (`localhost:8545`)
- Ganache
- Remix VM

---

# Development Tools

This project was developed using the following tools:

| Tool | Purpose |
|-----|------|
| Solidity | Smart contract programming language |
| Remix IDE | Smart contract development and deployment |
| Web3.js | Frontend blockchain interaction |
| JavaScript | Client-side DApp logic |
| HTML/CSS | User interface |
| Hardhat Node | Local Ethereum blockchain |

---

# Deployment Process

The smart contract was deployed using **Remix IDE Web**.

Steps followed:

1. Open Remix IDE in the browser
2. Create the smart contract file
3. Compile the contract using Solidity `0.8.20`
4. Deploy the contract to a local Ethereum node
5. Copy the deployed contract address
6. Connect the frontend JavaScript application using the contract ABI and address

---

# Example DApp Interface

The frontend application allows users to:

- View the current instructor stored in the blockchain
- Update the instructor name and age
- Send a transaction to the smart contract
- Display loading indicators while transactions are processed

Example UI components:

- Instructor display
- Input fields for name and age
- Transaction button
- Loading spinner during blockchain interaction

---

# Example Interaction Flow

1. User enters instructor name and age
2. The frontend sends a transaction using Web3
3. The smart contract updates the blockchain state
4. The `Instructor` event is emitted
5. The frontend updates the UI with the new data

---

# Event System

The smart contract emits an event when the instructor is updated.

```solidity
event Instructor(string name, uint age);
```

Events allow the frontend to listen to blockchain changes and update the UI automatically.

---

# Running the Project

## Start Local Ethereum Node

Example using Hardhat:

```bash
npx hardhat node
```

This starts a local blockchain at:

```
http://127.0.0.1:8545
```

---

## Run the Frontend

Open the project folder and start a local web server.

Example using **VS Code Live Server**.

Then open:

```
http://127.0.0.1:5500/index.html
```

---

# Example Output

```
Coursetro Instructor

Franco (55 years old)
```

Users can update the instructor data and see the result stored on-chain.

---

# Educational Purpose

This project demonstrates the fundamental concepts required to build a **basic Ethereum DApp**:

- Smart contract development
- Blockchain deployment
- Web3 frontend integration
- Event-driven UI updates
- Transaction handling

---

# Future Improvements

Possible improvements include:

- MetaMask wallet integration
- Deployment to public testnets (Sepolia / Holesky)
- Ethers.js instead of Web3.js
- React or Next.js frontend
- Smart contract access control
- Gas optimization
- Contract verification on Etherscan

---

# License

MIT License
