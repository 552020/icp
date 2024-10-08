# Build on Internet Computer with ICP Rust CDK

## Course Introduction

- Course Introduction

## Introduction to Internet Computer and Rust

- Introduction
- Overview of the IC ecosystem and core differences

  - Canisters
  - Nodes and Subnets
  - Chain Key Cryptography
  - Doatabase vs Blockchain
  - Conclusion

- Overview of the IC architecture and its components

  - Explanation of the Traditional Network // Web2
  - ICP vs Traditional Network
  - Core IC Protocol
  - Architecture of the Internet Computer
  - Conclusion

- Setting up the development environment for IC
  - Introducing the IC SDK
  - Installing the IC SDK
  - Installed Components
  - IC SDK, CDK and dfx
  - Conclusion

## Building Smart Contracts with Rust and Working with Canisters

- Introduction
- Creating Smart Contracts
- State Managment 1
- State Managment 2
- Update and Query Functions
- Updating the Candid File
- Testing the Contract

## Varia

### **ICP Nodes Run at Web Speed**

The Internet Computer Protocol (ICP) achieves "web speed" by delivering decentralized applications with the same low-latency performance as traditional web services. This is made possible by ICP’s innovations like Chain-Key Technology, which allows for ultra-fast transaction processing—query calls (reads) complete in about 200 milliseconds and update calls (writes) in roughly 2 seconds. While other blockchains prioritize security and decentralization at the cost of speed, ICP combines web-level performance with decentralized infrastructure, enabling it to host and execute smart contracts and web applications directly on the blockchain without off-chain services.

### Hezner, Ethereum and ICP

In August 2022, **Hetzner**, a major European cloud provider, reinforced its policy against using its infrastructure for blockchain-related activities, including Ethereum node hosting, staking, and mining. This affected around 15-16% of **Ethereum** nodes hosted on Hetzner, raising concerns about the dependence of decentralized networks on centralized providers like Hetzner, AWS, and Google Cloud. This reliance creates centralization risks for blockchains such as **Ethereum**, **Solana** (where Hetzner hosted 34% of validators), and **Bitcoin**, which have a significant portion of their nodes running on public cloud services. In comparison, the **Internet Computer Protocol (ICP)** is built to avoid these risks by utilizing a global network of **independent data centers**, which are not controlled by any single entity. This decentralized infrastructure enhances ICP’s resilience to centralized decisions, making it better suited to the vision of a censorship-resistant, fully decentralized internet. Unlike other blockchains, ICP does not rely on cloud providers, making it less vulnerable to policy changes like those from Hetzner.

### Subnet Types

In the **Internet Computer Protocol (ICP)**, **subnets** are crucial components of its architecture that enable scalability, security, and interoperability. Each subnet functions as a mini-blockchain, hosting nodes that collectively process and store data. There are different types of subnets based on their role within the ICP network:

1. **System Subnets**: These are responsible for critical network functions, such as the Network Nervous System (NNS), which governs the Internet Computer. System subnets manage tasks like upgrades, governance proposals, and overall network coordination.

2. **Application Subnets**: These subnets host decentralized applications (dApps) and smart contracts (known as canisters). Application subnets scale horizontally, meaning new subnets can be added to the network to handle increased load, enabling seamless scaling for large-scale dApps.

3. **Verified Subnets**: These subnets offer extra security and validation by being verified for specific use cases, such as handling sensitive data or applications that require higher security guarantees.

By using different subnets, ICP achieves a balance between scalability, decentralization, and performance, allowing applications to run at web speed while maintaining robust security.

### Key Chain Cryptography

**Chain Key Cryptography** is a core innovation in the **Internet Computer Protocol (ICP)** that allows the network to maintain security and efficiency while operating at scale. It enables the network to process transactions rapidly, handle cross-subnet communication, and perform key management in a decentralized way. The core innovation here lies in how ICP splits cryptographic keys across nodes using **threshold cryptography**, enabling nodes to collectively sign transactions without any single node holding the full private key. This ensures security, scalability, and high performance.

#### What’s Innovative About Chain Key Cryptography?

**Chain Key Cryptography** stands out for several reasons:

1. **Threshold Cryptography**: ICP uses threshold cryptography, where the private key is divided among multiple nodes. No single node holds the complete key, but a threshold number of nodes can collaborate to perform cryptographic operations. This is innovative because it enhances security and resilience against attacks, as no single node can compromise the system.
2. **Efficient Key Management**: The cryptographic key for a subnet is collectively held by the nodes, but only a single **public key** represents the entire subnet. This key management system allows the Internet Computer to perform cryptographic operations like transaction validation efficiently, without requiring every node to process the full blockchain.

3. **Cross-Subnet Communication**: Chain Key Cryptography enables seamless communication between subnets on the Internet Computer. Smart contracts (canisters) on one subnet can call functions on other subnets securely and efficiently without needing to trust external bridges, which are often points of vulnerability in other blockchain ecosystems.

#### How Other Blockchains Differ

Most blockchains, like Bitcoin, Ethereum, Solana, and others, use **elliptic curve cryptography (ECC)**, which relies on a single private-public key pair for each transaction or account. Here's how they differ from ICP's approach:

1. **Bitcoin**: Uses **Elliptic Curve Digital Signature Algorithm (ECDSA)**. Each transaction on the Bitcoin blockchain is verified using a single private-public key pair, which is held by the individual user. This cryptography is secure but does not support advanced features like threshold cryptography or decentralized key management.
2. **Ethereum**: Also uses **ECDSA** for its transactions and smart contracts. Ethereum relies on individual nodes to manage keys and verify transactions, and while it’s secure, Ethereum does not incorporate the kind of cross-node collaboration and threshold cryptography that ICP uses for decentralization.

3. **Solana**: Uses **Ed25519**, another elliptic curve-based cryptography system. Like Bitcoin and Ethereum, Solana's cryptography is highly efficient but focuses on speed and scalability, without the unique threshold cryptography of ICP. Solana does not use decentralized key management like ICP does with its subnets.

#### How Chain Key Cryptography Differs

- **Decentralized Key Control**: Unlike other blockchains that rely on a single private-public key pair, ICP uses **threshold cryptography** to split private keys across many nodes. This enhances security by ensuring that no single node can control the cryptographic operations.

- **Seamless Subnet Interaction**: Other blockchains require external bridges to connect different blockchain networks, which introduces additional risks and inefficiencies. ICP’s Chain Key Cryptography enables **subnets** to interact directly and securely, facilitating seamless cross-network communication without needing external trust layers.

- **Single Public Key for Subnets**: While traditional blockchains assign individual keys for transactions or accounts, ICP introduces a single public key for entire subnets, which optimizes network operations and ensures scalability across multiple subnet blockchains.

In summary, **Chain Key Cryptography** sets ICP apart from other blockchains by enabling decentralized, secure, and scalable cryptographic operations, whereas other blockchains rely on more traditional elliptic curve cryptography (ECC) without the same level of distributed key management and cross-network capabilities.

### The Network Nervous System

The **Network Nervous System (NNS)** in the **Internet Computer Protocol (ICP)** is a decentralized, autonomous system responsible for governing and managing the entire network. It is one of the key innovations of ICP, allowing the network to evolve and operate without centralized control. Here’s a breakdown of how it works and its importance:

#### Key Functions of the NNS:

1. **Governance**: The NNS allows ICP token holders to participate in the decision-making process for network upgrades, protocol changes, and governance proposals. This means the community controls how the Internet Computer evolves over time.

2. **Node Management**: It oversees the management of nodes, including adding or removing data centers and node machines. The NNS monitors the health of the network and ensures it operates smoothly by adjusting node participation as needed.

3. **Subnet Creation and Management**: The NNS can create new subnets (which are individual blockchains within ICP) to scale the network. It dynamically allocates nodes to these subnets, ensuring efficient load distribution and network resilience.

4. **Security**: The NNS plays a critical role in ensuring the security of the network by approving upgrades and controlling cryptographic parameters. This helps keep the network robust and resistant to attacks.

5. **Tokenomics**: The NNS manages the economic aspects of ICP, including converting ICP tokens into **cycles**, which power smart contract (canister) execution. Token holders can also stake their tokens in neurons, which allows them to vote on governance proposals and earn rewards for doing so.

#### How It Works:

- **Neurons**: Token holders create **neurons**, which are essentially locked-up ICP tokens used for governance. These neurons can vote on proposals, and the more neurons a participant controls, the more voting power they have. Neurons can also follow other neurons for voting, which is similar to a form of delegated voting.

- **Proposals**: Any participant with neurons can submit a proposal to the NNS, whether it’s about adding new features, making technical upgrades, or altering governance rules. The community of neuron holders then votes on these proposals.

- **Autonomous Operation**: The NNS operates autonomously. Once a decision is made through a proposal and voting process, the NNS can automatically implement changes, such as adding new nodes, upgrading the protocol, or adjusting network parameters. This decentralized nature ensures the network continues to operate efficiently without needing centralized oversight.

#### Why It’s Innovative:

- **Decentralized Governance**: Unlike traditional blockchains where governance might be influenced by a small group of developers or miners, the NNS gives **all token holders** a voice in the decision-making process, making governance more transparent and decentralized.
- **Self-Updating**: The NNS allows ICP to update itself autonomously, meaning that new features or upgrades can be implemented without hard forks, which are common in other blockchains like Bitcoin and Ethereum. This makes the Internet Computer more adaptable and easier to evolve.

- **Scalability and Efficiency**: By managing the addition of nodes and subnets, the NNS ensures that ICP can scale seamlessly to handle more transactions and applications as the network grows.

In summary, the **Network Nervous System (NNS)** is the backbone of ICP’s decentralized governance and operation, providing a democratic and automated way for the network to manage itself, upgrade, and scale【10†source】【12†source】【11†source】.

## Developer Environemnt Setup

Here’s a short primer for setting up a developer environment for **ICP (Internet Computer Protocol)** development using **Rust** on both **Linux** and **macOS**:

### Step 1: Install Rust

You'll need **Rust** as it's the primary language for building canisters (smart contracts) on ICP.

#### For Linux and macOS:

1. Install Rust using `rustup`, the recommended installation method:

   ```bash
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
   ```

   Follow the instructions to complete the installation.

2. After installation, ensure Rust is added to your path:

   ```bash
   source $HOME/.cargo/env
   ```

3. Verify that Rust is installed:
   ```bash
   rustc --version
   ```

### Step 2: Install DFX (Internet Computer SDK)

DFX is the development tool for building and deploying canisters on the Internet Computer.

#### For Linux and macOS:

1. Download and install DFX:

   ```bash
   sh -ci "$(curl -fsSL https://internetcomputer.org/install.sh)"
   ```

2. Verify installation:
   ```bash
   dfx --version
   ```

### Step 3: Install the `wasm32-unknown-unknown` Target

Rust canisters need to be compiled to WebAssembly (Wasm). For this, you need to add the WebAssembly target for Rust:

1. Add the WebAssembly target:
   ```bash
   rustup target add wasm32-unknown-unknown
   ```

### Step 4: Set Up a Project

1. Create a new directory for your ICP project:

   ```bash
   mkdir my_icp_project && cd my_icp_project
   ```

2. Initialize the project with DFX:

   ```bash
   dfx new my_project
   cd my_project
   ```

3. Compile the Rust canister to WebAssembly:

   ```bash
   cargo build --target wasm32-unknown-unknown --release
   ```

4. Start the local DFX environment:
   ```bash
   dfx start
   ```

### Step 5: Deploy and Test

1. Deploy the canisters to the local network:

   ```bash
   dfx deploy
   ```

2. Interact with the deployed canisters using DFX commands.

### Additional Tools

- **VSCode**: Recommended IDE for Rust development. Install it via `brew install --cask visual-studio-code` on macOS or from your Linux package manager.
- **Rust Analyzer**: Add the Rust Analyzer plugin to VSCode for better Rust support.

With this setup, you're ready to start developing and deploying canisters on the Internet Computer!

## DFX

**DFX** is the command-line interface (CLI) tool for **Internet Computer Protocol (ICP)** development, designed to help developers manage canisters, local environments, identities, and the deployment of applications. The name **DFX** is derived from **"DFINITY Framework for Execution,"** reflecting its role as a comprehensive tool for managing both the development and execution of applications on the Internet Computer.

### Key Features of DFX:

- **Local Replica**: A **replica** is a local instance of the Internet Computer that developers can run on their machine. This allows them to test and interact with their canisters (smart contracts) without deploying to the public network. It’s a sandbox environment that mimics the behavior of the Internet Computer, enabling testing in a controlled space.

  - Command: `dfx start` launches the local replica, simulating the Internet Computer network on your machine.

- **Identity Management**: An **identity** in the context of ICP refers to a user's cryptographic key pair, which is used to authenticate actions, sign transactions, and interact with canisters on the Internet Computer. DFX allows you to manage these identities, including creating multiple identities and switching between them during development.
  - Command: `dfx identity new <identity_name>` creates a new identity, and `dfx identity use <identity_name>` switches between them.

### Main DFX Commands:

1. **Starting a Local Replica**:

   - Command: `dfx start`
   - This command spins up a local instance of the Internet Computer, allowing developers to test their applications without deploying them to the public network.

2. **Creating a New Project**:

   - Command: `dfx new <project_name>`
   - Initializes a new project, setting up the necessary directories and configuration files for canister development.

3. **Building Canisters**:

   - Command: `dfx build`
   - This command compiles the code into WebAssembly (Wasm) format, which is required for deployment on the Internet Computer.

4. **Deploying Canisters**:

   - Command: `dfx deploy`
   - Deploys the compiled canisters to the local replica or the live Internet Computer network. You can also specify a particular network using flags like `--network ic`.

5. **Calling Canister Methods**:

   - Command: `dfx canister call <canister_name> <method_name>`
   - Interacts with a deployed canister by invoking one of its methods, allowing developers to test the functionality of their smart contracts.

6. **Managing Identities**:

   - Command: `dfx identity new <identity_name>` creates a new identity.
   - Command: `dfx identity use <identity_name>` switches between existing identities.

7. **Checking Wallet Balance**:

   - Command: `dfx wallet balance`
   - This command lets you check the balance of ICP tokens or cycles associated with the current identity’s wallet.

8. **Stopping the Local Replica**:
   - Command: `dfx stop`
   - Shuts down the local replica when it’s no longer needed.

### What a Replica Is:

A **replica** in the ICP context refers to a local version of the Internet Computer that runs on your machine. It replicates the behavior of the main network, allowing developers to deploy, test, and interact with canisters without needing to use real resources (like cycles) or expose their code to the public Internet. The replica is crucial for the development cycle because it enables debugging and testing in an isolated environment.

### What an Identity Is:

An **identity** in DFX is a cryptographic key pair (public/private key) that represents a developer or user within the Internet Computer ecosystem. These identities are used to sign transactions, authorize actions, and manage canisters. DFX allows developers to create, manage, and switch between multiple identities, which is useful when working on different projects or testing interactions under various accounts.

In summary, **DFX** serves as a complete framework for developing, testing, and deploying applications on the Internet Computer. It enables local testing via replicas, handles identity and wallet management, and automates the process of compiling and deploying smart contracts (canisters). Its decentralized nature, combined with the use of local and public networks, makes DFX a powerful tool for ICP developers.

Here are similar descriptions for **moc** and **Motoko**, **network binary**, **uninstall.sh**, and **versions** in the context of the Internet Computer (ICP) development environment:

---

### **moc and Motoko**

**Motoko** is a programming language developed specifically for building canisters (smart contracts) on the **Internet Computer**. It is designed to make it easier to write, deploy, and maintain decentralized applications (dApps) on ICP, providing type safety, actor-based concurrency, and integration with ICP-specific features.

The **moc** tool is the **Motoko compiler** that converts Motoko source code into **WebAssembly (Wasm)** format, which can then be deployed on the Internet Computer. Similar to how Rust projects are compiled into Wasm, **moc** serves the same purpose for Motoko, converting the high-level language into executable code that can run on ICP.

- **Command to compile Motoko code**:
  ```bash
  moc <filename>.mo
  ```

**Motoko’s Key Features**:

1. **Actor-Based Model**: Motoko uses actors to handle concurrency, which maps well to the Internet Computer’s model of canisters that run isolated, concurrent programs.
2. **Type Safety**: Motoko’s strong type system prevents many common programming errors at compile time.
3. **Seamless ICP Integration**: Motoko has built-in functions and libraries to work directly with ICP’s environment, making it easier to interact with cycles, canisters, and identities.

### **network binary**

The **network binary** in ICP refers to the compiled binary files of canisters or applications that are prepared to run on the Internet Computer network. Once code is compiled, either in Rust or Motoko, it is turned into **WebAssembly (Wasm) binaries**, which are then deployed to the network. These binaries are what the Internet Computer actually executes when running applications.

In a typical development cycle, the steps are:

1. Write code in **Rust** or **Motoko**.
2. Use the compiler (Rust `cargo build` or Motoko `moc`) to produce **Wasm binaries**.
3. Deploy these binaries to the Internet Computer via **DFX**.

- **Deploying the binary**:
  ```bash
  dfx canister install <canister_name>
  ```

### **uninstall.sh**

The **uninstall.sh** script is a common tool provided by many command-line tools, including those for the Internet Computer (such as DFX), to completely remove the software from your machine. This script is typically used to reverse all changes made during the installation process, including removing files, binaries, and configurations.

For DFX, the **uninstall.sh** script is used to clean up all DFX-related files, settings, and dependencies, ensuring a clean removal of the development environment from your system.

- **Running the uninstall.sh**:
  ```bash
  ./uninstall.sh
  ```

It’s helpful if you need to reset your environment or if you encounter issues and want to start fresh.

### **versions**

**Versions** in the context of ICP development typically refer to the versions of various tools like **DFX**, **moc** (Motoko compiler), and libraries used in canister development. Keeping these tools up-to-date is important to ensure compatibility with the latest features and security improvements in the Internet Computer environment.

You can manage and view the versions of these tools as follows:

- **Checking the DFX version**:

  ```bash
  dfx --version
  ```

- **Specifying a DFX version**: When initializing a project, you can specify a DFX version to ensure compatibility:

  ```bash
  dfx new <project_name> --version <dfx_version>
  ```

- **Motoko compiler version**:
  ```bash
  moc --version
  ```

Using the correct versions is crucial when developing for specific ICP environments, especially in collaborative projects where multiple developers need consistency across their tools.

---

These tools are essential parts of the Internet Computer development ecosystem, each providing a specific function from compilation, deployment, cleanup, and version control to ensure a smooth development workflow for decentralized applications.
