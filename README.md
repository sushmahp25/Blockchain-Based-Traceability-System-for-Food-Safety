# Blockchain
Title: "Blockchain Based Traceacbility System for Food Safety".
Abstract— Food industry professionals and consumers alike take food safety seriously. The complexity of the food supply chain makes it difficult to trace the provenance and quality of food products, which can result in contamination, fraud, and ineffective recalls. To improve transparency, traceability, and accountability throughout the food supply chain, blockchain technology has emerged as a possible alternative. It examines how blockchain technology and food safety interact, highlighting how it could fundamentally alter how we monitor, confirm, and protect the quality of our food. This work proposes a Blockchain based food traceability system provides a safe and tamper-proof platform for tracking each step of the food journey by establishing an immutable and decentralized ledger of transactions. It has been implemented with the essential characteristics of blockchain, such as data immutability, transparency, smart contracts, and decentralized consensus and could successfully trace the food chain steps.

# Methodolgy
The Solidity smart contract, named "Food Safety," aims to establish a blockchain-based system for ensuring food safety. It allows producers to register food products with details like product name, production date, and origin. Producers can then request certification from trusted entities, marking the product as certified if approved. The contract includes modifiers to restrict certain actions to producers and certified entities only. Users can interact with this system through Ethereum and the MetaMask wallet. To test the functionality, we deploy the contract on a local Ethereum network using tools like Ganache, allowing producers to register products, request certifications, and consumers to verify product certifications, thereby enhancing food safety and transparency in the supply chain.

Techniques adopted in the Methodology used are:
1.	Blockchain: A distributed ledger system known as a blockchain keeps track of transactions among a network of computers. It is renowned for its immutability, traceability, security, and transparency. One of the most widely utilized blockchains for developing smart contracts is Ethereum.
2.	Smart Contracts: Smart contracts are pieces of programmable, self-executing code that run on the blockchain and do predetermined actions when specific criteria are satisfied. These contracts automate procedures and eliminate the need for middlemen in a variety of industries, including finance, supply chain, healthcare, and more.
3.	 Ethereum: The decentralized Ethereum blockchain platform facilitates the development of smart contracts. Smart contracts are agreements that automatically carry out their obligations because they are encoded in code. Ether (ETH), a money created by Ethereum, is used to power network transactions and computations.
4.	Metamask: Metamask is a gateway to blockchain apps and a bitcoin wallet. Users can manage their Ethereum wallets with this browser extension. Through Metamask, users may communicate with smart contracts and transfer and receive Ether.
5.	Ganache: Ganache is a development tool for building and managing personal Ethereum test networks. It makes it simpler to test and create smart contracts without connecting with the main Ethereum network by enabling developers to replicate an Ethereum environment locally. For Ethereum development, Ganache offers both a graphical user interface and a CLI (Command Line Interface) version.

# System Components
![image](https://github.com/user-attachments/assets/586140c9-74a4-4767-842f-e9f494486d23)

Figure 1 illustrates the System Components of the food safety system:
A.	Product Verification:
a)	Producers (Food Producers or Manufacturers): Producers initiate the process by registering food products on the blockchain. They provide information such as product details, production date, and origin. This data is recorded on the blockchain using smart contracts.
b)	Smart Contracts: Smart contracts are utilized to automate and manage product registration. When producers register their products, a smart contract creates a new block on the blockchain, containing all the product information. The smart contract ensures that this data is immutable and transparent.
c)	User Interfaces: User-friendly interfaces are provided to producers for registering their products on the blockchain. Producers interact with these interfaces to input their product data, which is then processed by the smart contracts.
d)	Consumers: Consumers can use user interfaces to verify the authenticity and safety of food products. They do this by inputting the product's unique identifier (e.g., QR code) into the system, which queries the blockchain to retrieve the product's certification status and details.

B.	Certificate Issuance:
a)	Producers (Food Producers or Manufacturers): Producers can request certification for their products from certifiers, indicating their intention to have their products certified for safety and quality.
b)	Certifiers: Certifiers review the product data provided on the blockchain. If necessary, they may perform physical inspections to ensure compliance with safety and quality standards.
c)	Smart Contracts: Smart contracts play a crucial role in the certification process. When a product successfully meets the required standards, the certifier issues a certification transaction via a smart contract. This certification transaction is recorded on the blockchain, indicating that the product is certified.
d)	User Interfaces: User-friendly interfaces are provided to certifiers for reviewing product data, conducting inspections, and issuing certifications. These interfaces streamline the certification process and ensure that it is transparent and tamper-proof.  

Figure 2 illustrates System Workflow of the food safety system:
A.	Product Verification:
a)	Data Entry and Recording: Producers initiate the process by registering food products on the blockchain. They do this through a user interface, providing essential information such as producer details, product specifications, production date, and origin.
b)  Blockchain Recording: Smart contracts, which are self- executing contracts with the terms of the agreement directly written into code, create a new block for the product data. This block contains all the information related to the product. This information is recorded on the blockchain in a tamper- resistant manner.
c)  Notification: After the data is successfully added to the blockchain, the producer is notified. This step ensures that the producer is aware that their product's information has been securely recorded on the blockchain.

C.	Certificate Issuance:
a)	Request for Certification: Producers can request certification from certifiers. Certification may be needed to prove that the product meets safety standards or specific quality requirements.
b)	Certification Review: Certifiers, who are typically third- party entities with expertise in food safety and quality, review the product data provided on the blockchain. If necessary, they may also conduct physical inspections or audits of the production process to ensure compliance with safety and quality standards.
c)	Update and Notification: The certification status is updated on the blockchain, indicating that the product is certified. This updated status is accessible to relevant parties. Notifications are sent to inform stakeholders, including the producer, that the product has been certified.

D.	 Data Validation:
a)	Regulatory Oversight: Regulators play a crucial role in maintaining the integrity of the blockchain-based traceability system. They conduct periodic audits and oversee compliance with food safety regulations.
b)	Audit and Cross-Referencing: Regulators audit the blockchain data, cross-referencing it with physical inspections when necessary. This cross-referencing ensures that the data on the blockchain accurately represents the real- world conditions and that products are meeting the safety and quality standards as claimed.

![image](https://github.com/user-attachments/assets/b865668b-6b1b-4ac9-876a-4fa29fb3aa02)

# ALGORITHM
1.	Create a Solidity contract named ‘Food Safety.’
2.	Define a struct called `Product` to represent individual food products with the following properties:
•	productId: A unique identifier for the product.
•	producer: Address of the producer who registered the product.
•	productName: Name of the product.
•	productionDate: Date when the product was produced.
•	origin: The origin of the product.
•	isCertified: A boolean flag to indicate whether the product is certified for safety.
3.	Create a mapping to store product information using
`uint256` productId as the key and `Product` struct as the value.
4.	Declare a public state variable `totalProducts` to keep track of the total number of registered products.
5.	Define two events:
•	`ProductRegistered`: Triggered when a new product is registered, containing productId and producer's address.
•	`ProductCertified`: Triggered when a product is certified, containing productId and the certifier's address.
6.	Define two modifiers:
•	`onlyProducer`: Ensures that only the producer of a product can call certain functions.
•	`onlyCertified`: Ensures that only a certified entity can call certain functions.
7.	Implement a function `registerProduct` that allows a producer to register a new product by providing product details.
•	Increment `totalProducts`.
•	Create a new `Product` struct with the provided details and set
`isCertified` to `false`.
•	Store the   product   in   the   `products`   mapping   with  
•	`totalProducts` as the productId. - Emit the `ProductRegistered` event.
•	Implement a function `certifyProduct` that allows the producer to certify their product's safety.
•	Check if the caller is the producer of the product using the
•	`onlyProducer` modifier.
•	Set the `isCertified` flag of the product to `true`.
•	Emit the `ProductCertified` event.
•	The producer initiates the transaction to certify their product's safety. Inside the `certifyProduct` function, check if the caller of the function ‘msg.send’ (the sender of the transaction) is the producer of the product. The `onlyProducer` modifier is used to ensure this condition is met.
•	If the condition is met (i.e., the caller is the producer of the product), proceed to the next step i.e set the `isCertified` flag of the   product   with   the given `productId` to `true`. This marks the product as certified for safety. If the condition is not met, revert the transaction with an error message indicating that only the producer can perform this action. The function execution completes. caller is the producer of the product), proceed to the next step, i.e set the `isCertified` flag of the   product   with   the given `productId` to `true`. 
•	This marks the product as certified for safety. If the condition is not met, revert the transaction with an error message indicating that only the producer can perform this action. The function execution completes.

# Algorithm 1: To certify product
Whenever a producer initiates the transaction to certify their product,
1: For [k=1, k≤ L, k++]
2: if [‘msg.send’ == ‘productId’] 3: set (‘isCertified’ == true)
4: return true
5: else
7: set ("Only the producer can perform this action.") 8: return false
9: endif
10: endfor
8.	Implement a function `getProductDetails` to retrieve product details based on the given productId.
•	Fetch the product information from the `products` mapping.
•	Return the product's producer, name, production date, origin,
and certification status.
9.	Implement a function `isProductCertified` to check if a product is certified for safety.
•	Retrieve the `isCertified` flag from the `products` mapping for
the given productId.
•	Return the certification status (boolean).

Whenever a customer or stakeholder wants to check whether the product id is certified or not, `isProductCertified’ function is called, which will use the ‘isCertified’ flag from the products mapping for the given ‘productId’. The function will return the certification status which is a Boolean value (true or false). This function will return true if the product is certified and false otherwise. If the productId does not exist in the products mapping, it returns false.
 
 # Algorithm 2: To validate the product certification
 
Whenever a customer wants to check whether product is certified or not,
1: For [k=1, k≤ L, k++]
2: call ‘isCertified’, which maps for ‘productId’ 3: if [‘productId’ == ‘isCertified’]
4: return true
5: else if [‘productId’ ≠ ‘isCertified’] 6: return false
7: else [‘productId’ not in products] 8: return false
9: endif
10: endfor.

# IMPLEMENTATION

To establish a secure and efficient food safety blockchain network, it is imperative to connect vital components, such as Metamask and Ganache, in a manner analogous to the protocols observed in blockchain development. Much like Metamask serves as a crucial interface for seamless interaction with the Ethereum network, ensuring interconnection among diverse stakeholders holds paramount importance in the domain of food safety. The creation of a transparent and traceable food supply chain hinges on the seamless connectivity of all participants, spanning from producers to regulatory bodies. The role of Metamask, as a conduit for users to access Ethereum's blockchain, resonates within the context of food safety by aligning with the imperative of establishing robust links between the multifarious actors within the food safety blockchain ecosystem. Analogous to the configuration wherein Metamask is linked to Ganache to gain access to localized Ethereum networks for testing and development purposes, forging connections among producers, certifiers, regulators, and consumers becomes a pivotal aspect of fortifying the food safety framework. This web of connectivity enables real-time data exchange and validation, thereby enhancing the security and dependability of our food supply chain. It also facilitates efficient oversight and validation processes, akin to Metamask's role in enabling seamless transaction processing on the Ethereum network. Lastly, the assurance of secure data transfer from Ganache to Metamask mirrors the critical need for robust data transmission mechanisms in the food safety sector, guaranteeing the reliable dissemination of vital information, including certifications and product data, among stakeholders.

![image](https://github.com/user-attachments/assets/98010ca3-2dc8-4d9a-9603-028c97ba8a17)
Fig.3. Blockchain structure for food safety.

# RESULT AND DISCUSSION

![image](https://github.com/user-attachments/assets/7a41b357-1e01-4dab-81bf-799bc82af101)
Fig.4.Product deployment details.

Fig 4 illustrates how a producer registers a new product by providing its name, production date, and origin. Then product is certified by the certifier. Further, the product is transferred to another address, capturing the traceability information. Finally, the certified product is shipped to its destination, capturing the destination information.

![image](https://github.com/user-attachments/assets/30d665ed-108b-4f3b-b103-18aba376d577)
Fig 5: Information of the products.
Fig 5 illustrates how a consumer or retailor can get the detailed information about a product based on its product ID and can check whether the product is certified or not.

![image](https://github.com/user-attachments/assets/4a2200c6-6522-4d7c-9b4b-811dba3babfc)
Fig.6. Inject remix IDE and get the result from MetaMask.

Fig 6 shows how Ethereum IDE is connected to MetaMask, ensuring that food safety transactions are initiated from our local IDE and confirmed through the MetaMask extension, all while maintaining network consistency and control over gas fees. This integration streamlines the development and execution of blockchain-based food safety solutions.
 
![Screenshot 2024-10-15 144857](https://github.com/user-attachments/assets/94a4030f-d172-46e6-b882-78ee45ae3551)
Fig.7. Metamask contract interaction

Every transaction detail and log offer visibility into gas efficiency, the contract's address, and activity updates, facilitating effective management and monitoring of blockchain- based food safety traceability solution as shown in fig 7.

# FUTURE WORK
By all this work, it focuses on scaling the system to accommodate a growing number of participants and transactions, fostering user adoption through user-friendly interfaces and outreach, conducting real-world testing to validate the system's performance, integrating IoT devices for real-time data, ensuring regulatory compliance and standards adherence, establishing sustainable governance models, enhancing security and privacy measures, optimizing the food supply chain using blockchain data, fostering community engagement among stakeholders, and maintaining a commitment to ongoing research and development to keep the system aligned with emerging technologies and industry best practices. This comprehensive approach will further strengthen the food safety blockchain network's security, efficiency, and reliability, ultimately benefiting all participants and ensuring the transparency and traceability of the food supply chain.

# CONCLUSION
Incorporating blockchain for food safety can revolutionize the food industry by ensuring trust, transparency, and traceability throughout the supply chain. By addressing existing problems, we contribute to a safer and healthier society, promotes fair trade, and fosters sustainable practices. Embracing blockchain's potential in this context can significantly improve food safety and reshape the way we interact with the food we consume. By leveraging blockchain technology, it enables producers to register their products and seek certifications from trusted entities, ensuring that consumers can make informed choices about the food they consume. This system empowers producers to demonstrate the quality and safety of their products while giving consumers confidence in the products they purchase. When implemented on a broader scale and integrated into real- world supply chains, such a system has the potential to significantly improve food safety standards, reduce fraud, and ultimately protect the health and well-being of consumers.
