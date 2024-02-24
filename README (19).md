
# Open API security among Web Services ad Machine Learning

Google's Android OS, widely used in smartphones, faces security vulnerabilities due to its open-source nature, leading to a rise in malicious apps. Our study proposes an innovative approach using machine learning to detect such apps by analyzing permissions and API calls. This static analysis method is effective and applicable across mobile platforms.

## ABSTRACT

The Android mobile operating system, developed by Google, stands as a highly anticipated 
platform in the contemporary smartphone market. Its open-source nature allows developers to 
maximize the benefits of the mobile OS. However, this openness also introduces significant 
vulnerabilities regarding malicious applications.As Android's prominence rises, it inevitably 
becomes the focal point for a vast number of developers, thereby resulting in a surge of 
applications. This burgeoning application landscape, in turn, offers a conducive environment for malicious actors to develop and disseminate malware, camouflaging them as benign apps in both the Google Play Store and alternative third-party markets.


## OBJECTIVE

• Using machine learning for Android malware detection using permission and Api calls 

• Leveraging Healthcare API to transform Interoperability: API Security and Privacy 

• API based Security solutions for Communication among Web Services 

• API standards 

• Open API

## INTRODUCTION

The Android mobile operating system, developed by Google, stands as a highly anticipated platform in the contemporary smartphone market. Its open-source nature allows developers to maximize the benefits of the mobile OS. However, this openness also introduces significant vulnerabilities regarding malicious applications. As Android's prominence rises, it inevitably becomes the focal point for a vast number of developers, thereby resulting in a surge of applications. This burgeoning application landscape, in turn, offers a conducive environment for malicious actors to develop and disseminate malware, camouflaging 
them as benign apps in both the Google Play Store and alternative third-party markets.

In this study, we introduce an innovative approach that integrates both permission-based and API (Application Program Interface) call analytics, employing machine learning techniques to discern malicious Android applications. In our methodology, permissions are procured from an app's profile metadata, while APIs are derived from the encapsulated app file. This is accomplished by leveraging package structures and classes to epitomize API invocations. By utilizing permissions and API calls as 
distinctive features, we can efficaciously train a classifier to discern the potential malevolence of an app. A salient strength of our technique is its reliance on static analysis rather than dynamic system call tracing. This approach streamlines the detection process, focusing exclusively on inherent system 
functionalities associated with each application. Furthermore, given that both permissions and APIs are ubiquitously accessible for every app, our strategy holds potential for universal applicability across all 
mobile platforms. 

Our empirical evaluation, conducted on a dataset comprising over 1200 malware-infested and 1200 benign applications, attests to the robust efficacy of the proposed algorithm. Malware, short for malicious software, is a general term used to refer to a variety of forms of hostile or intrusive software such as viruses, worms, spyware, Trojan horses, rootkits, and backdoors  A common feature of Malware is that they are specifically designed to damage, disrupt, steal, or in general inflict some other bad or illegitimate actions. Malware can literally infect any computing machines running user programs (or applications), and the propagation and prevention of the malware have been well studied for personal computers . But for smartphone devices, our solutions for finding malware in the mobile platform are far behind the pace of the increasing popularity of the mobile applications. This popularity of the Android system has led to a huge increase in the spreading of Android malware. These malwares are mainly distributed in markets operated by third parties, but even the Google Android Market cannot guarantee that all of its listed applications are threat free. The threats for An- droid include Phishing, Banking
Trojans, Spyware, Bots, Root Exploits, SMS Fraud, Premium Dialers and Fake Installers. There have also been reports about Download-Trojans Apps that download their malicious code after installation 
which means that these Apps cannot be easily detected by Google’s technology during publication in the Google Android Market. In summary, malware applications commonly use following three types of penetration techniques for installation, activation, and running on the Android system: 

### Dataset used

d 2510 APK files where 1260 are malicious Apps which have been validated in a previous 
study  and the remaining 1250 are benign Android APK files. After the feature extraction, 
we found that many malware have identical feature values (this often happens for malware 
belonging to the same family, such as different version of one malware application). So we 
eliminate malware with exactly the same vector features and only keep one copy in the 
dataset. As a result of this process, we end up with 610 malware samples in 49 different 
malware families indicating a very complete coverage of existing Android malware. For 
each malware family we also report in the table the number of samples and the sources 
which discovered the malware, i.e., from either the official or alternative Android market. 
Malicious APKs include all varieties of the threats for Android include Phishing and 
Banking-Trojans, Spyware, Bots, Root Exploits, SMS Fraud, Premium Dialers, Fake 
Installers, etc. gathered from various sources, including Android Malware Genome Project2

### OVERVIEW OF 49 DIFFERENT MALWARE FAMILARITIES 

![App Screenshot](https://github.com/KHUSHIM02/Open-API-security-among-Web-Services-ad-Machine-Learning/blob/ee97c520b5a8b8a52d20715944aaf21af4297614/IMAGES/49%20DIFFERENT%20MALWARE.png)

#### DATASET CATEGORIZATION

• ‘Permission” dataset is created by using the requested  permissions, as defined in section 3.B, as features. The total  number of features is 
130, which is equal to the standard  permissions used in Android system  

• “API call” dataset is created by using the API call names  as the features. The total number of API we used is 1326,  which is equal to the standard Android APIs at level 17 . 

• “Com+” dataset is created by concatenating the permission  and API call features for each App. So each instance contains1456 features.

## OVERVIEW OF 49 DIFFERENT MALWARE FAMILIES AND THEIR NUMBER OF MEMBER 


![App Screenshot](https://github.com/KHUSHIM02/Open-API-security-among-Web-Services-ad-Machine-Learning/blob/3fe6e0c1f90498d623aea7417f9e41e327fcd818/IMAGES/MALWARE%20NUMBER%20CHART.png)

## The Proposed permission and API call feature based malware  detection framework

![App Screenshot](https://github.com/KHUSHIM02/Open-API-security-among-Web-Services-ad-Machine-Learning/blob/29d82bc09675af6056917a41176f2b3f469d4085/IMAGES/MALWARE%20DETECTION%20FRAMEWORK.png)

## BENIGN VS. MALICIOUS DETECTION {PERM:PERMISSION; API:API CALLS; COM+:PERMISSION+API CALLS

We analyze the algorithm performance by using different classifiers, including support vector machines, decision tress, and bagging predictor. The objective is to determine whether combining permission and API calls can provide additional 
knowledge in characterizing the behaviors of Apps. In addi- tion, we also expect to 
determine the best classification method mostly suitable for malware detection. 

Decision Tree classifiers are a type of machine-learning methods using a tree 
structure for making predictions. The internal nodes of the tree represent conditions 
regarding the variables of a problem, whereas final nodes or leaves of the tree represent the ultimate decision of the algorithm. In our experiments, we use J48, a WEKA  implementation of the C4.5 algorithm , as the decision tree algorithm. 

Bagging  is a “bootstrap” based ensemble method that creates a number of base 
classifiers for its ensemble by training each base classifier using random redistribution 
of the

| Dataset | Classifier | Accuracy | Precision | Recall | AUC |
| :---: | :---: | :---: | :---: | :---: | :---: |
| Perm | SVM | 93.54 | 92.4 | 87.5 | 0.92 |
| API | SVM | 95.75 | 91.7 | 95.7 | 0.957 |
| Com+ | SVM | 96.88 | 95.7 | 94.8 | 0.963 |
| Perm | J48 | 92.36 | 89.8 | 86.6 | 0.917 |
| API | J48 | 93.33 | 89.4 | 90.3 | 0.918 |
| Comp+ | J48 | 94.46 | 90.6 | 92.8 | 0.936 |
| Perm | Bagging | 93.60 | 92.0 | 88.2 | 0.956 |
| API | Bagging | 94.89 | 93.6 | 90.7 | 0.986 |
| Comp+ | Bagging | 96.39 | 94.9 | 94.1 | 0.991 |

## Android malicious application detection rate based on AUC. The  results show that combining permission and API calls as features (Com+)  results in noticeable performance gain. The results also show that bagging  has the best performance for malware detection. 

Due to the imbalanced class distribution  nature  of  our data, we expect that Bagging classifier may outperform other classifiers because of its characteristics including ensembling to overcome the data imbalance problems. We do not include classifiers or methods particularly designed for imbalanced data, because our objective is not to tackle the data imbalance issue but to validate whether combining permission and API calls can improve the malware detection accuracy. 

In Table  we report the classification results related to different classifiers on all three 
benchmark datasets (Permis- sion, API, and Com+. The results show that the decision tree method (J48) has the lowest detection rate and the highest detection rate in each case belongs to 
the Bagging predictor. Bagging has good performance on data with skewed class distributions. Also it is shown that Bagging has the best performance in classifying all created data sets with respect to AUC, as shown in Figure 

![App Screenshot](https://github.com/KHUSHIM02/Open-API-security-among-Web-Services-ad-Machine-Learning/blob/8f54b8f95d3c8fbbd3a225aff873c65853f0c407/IMAGES/best%20method%20for%20malware%20detection.png)

## API based Security solutions for Communication among Web Services

This paper proposes a novel approach to ensure the confidentiality and integrity of data 
transmitted via web services protocols. The approach addresses two specific security attacks: message alteration attack and XML injection attack. The proposed solution involves the use of pluggable APIs on the service provider side and security services in the middleware side. 

The paper discusses the existing literature on web service security and highlights the limitations of previous works. It then presents the proposed security solution, which includes the deployment of security services in the middleware server and the integration of pluggable APIs in the domain web service server. The security services provide encryption and decryption capabilities, while the APIs help prevent message alteration and detect XML injection attacks. 

The proposed solution is demonstrated in a composition scenario involving a middleware 
service and domain web services. The middleware service acts as a composer, integrating 
multiple domain web services. A user interacts with the system through a web browser and the 
input information is passed to the middleware service via the interface program. The 
middleware service then invokes the necessary domain web services using SOAP messages. 

To prevent message alteration attacks, the proposed solution encrypts the SOAP request 
message using encryption services in the middleware server. The entire body of the request message is encrypted, making it difficult for attackers to identify the sensitive information. The encrypted message is then communicated to the appropriate domain web service through a secure communication channel.

In addition, the proposed solution addresses XML injection attacks by implementing security 
APIs in the domain web service server. These APIs help detect and prevent XML injection 
attacks, ensuring the integrity of the data exchanged between web services. 

The paper concludes by verifying the non-vulnerability of the proposed solutions through simulated attacks. The approach presented in this paper provides a comprehensive security solution for web services, addressing both network layer and application layer security concerns.


A RESTful API (Representational State Transfer) is an architectural style for designing 
networked applications. It is commonly used in web development to provide an interface for 
different systems to communicate with each other over the internet. 

In a RESTful API, resources (such as data objects or services) are identified by unique URLs, and interactions with these resources are performed using standard HTTP methods, such as 
GET, POST, PUT, and DELETE. These methods allow clients (applications or systems consuming the API) to perform different operations on the resources. 


Key principles of a RESTful API include:

    1. Stateless: The server does not store any client state. Each request from a client contains all the necessary information to understand and process it. This allows for scalability and simplicity.

    2. Uniform interface: The API follows a consistent set of rules and conventions. It uses standard HTTP methods and status codes to communicate the state of the operation. 

    3. Client-Server architecture: The API separates the client (the system making the request) from the server (the system providing the resources). This separation allows for independent evolution and scalability of both the client and server components. 

    4. Resource-based: Resources are the fundamental concept in a RESTful API. Each resource has a unique identifier (URL), and clients interact with these resources using the available HTTP methods.

    5. Stateless communication: Each request from a client to the server must contain all the necessary information The server does not store any information about the client's state between requests. 

    6. Representation-oriented: Resources can have multiple representations (such as JSON, XML, or HTML), and the client can choose the representation it prefers by specifying the appropriate content type in the request headers.


By adhering to these principles, RESTful APIs enable interoperability, scalability, and 
simplicity in building distributed systems. They have become a popular choice for building web 
services and APIs due to their flexibility and ease of use.APIs are measured against various 
standards and criteria to assess their quality, performance, and effectiveness. Some of the 
common standards used to evaluate APIs include: 

    1.  RESTful Principles:
 Representational State Transfer (REST) is an architectural style for designing networked applications. RESTful APIs adhere to a set of principles, such as using standard HTTP methods (GET, POST, PUT, DELETE) for operations, employing resourcebased URLs, and leveraging hypermedia (HATEOAS) for navigation. APIs that follow RESTful principles are often considered more scalable, maintainable, and interoperable.

    2.  Performance and Responsiveness:
APIs are evaluated based on their response time, 
throughput, and scalability. Performance benchmarks are often established to measure how 
quickly an API responds to requests and how efficiently it handles concurrent or high-volume 
traffic. Metrics like latency, error rates, and throughput are considered to gauge an API's 
performance.

    3. Security Standards:
 APIs must adhere to established security standards to ensure the protection of data and resources. These standards include Transport Layer Security (TLS) for secure communication, OAuth and OpenID Connect for authentication and authorization, and JSON Web Tokens (JWT) for secure token-based authentication. 

    4. Documentation and Usability: 
The quality of API documentation and its ease of use are critical factors. Well-documented APIs provide comprehensive and clear documentation, 
including guides, reference documentation, code examples, and interactive API consoles. Good 
usability also involves consistency in parameter naming, error handling, and adherence to 
industry best practices. 

    5. Compatibility and Interoperability:
APIs should be designed with compatibility in mind, allowing easy integration with different systems and platforms. Standards like JSON 
(JavaScript Object Notation) and XML (eXtensible Markup Language) for data exchange, as well as support for multiple data formats and protocols, promote interoperability and enable broader adoption. 

    6. Versioning and Lifecycle Management:
APIs often undergo updates and changes over time. Versioning standards and practices ensure backward compatibility and smooth transitions 
between API versions. Proper versioning and lifecycle management help developers and API 
consumers avoid disruptions and facilitate seamless upgrades.

    7. Error Handling and Fault Tolerance:
APIs should handle errors gracefully and provide 
informative error messages. Well-designed APIs have consistent error codes, clear error 
descriptions, and guidance on how to resolve issues. Additionally, fault tolerance mechanisms, such as retry strategies and rate limiting, can enhance the reliability and resilience of APIs. 

    8. Compliance with Industry Standards:
Depending on the domain or industry, APIs may need to comply with specific standards and regulations. For example, healthcare APIs must adhere to Health Insurance Portability and Accountability Act (HIPAA) regulations, while financial APIs need to follow Payment Card Industry Data Security Standard (PCI DSS) requirements. 

It's important to note that the specific standards used to evaluate APIs may vary based on the context, industry, and requirements of the API. Different organizations may have their own internal standards and guidelines for API development and evaluation. 

## API Standards

Several organizations and consortiums are involved in designing and promoting standards for APIs. Some of the prominent organizations include: 

    1. World Wide Web Consortium (W3C):
W3C is an international community that develops web standards, including standards related to APIs. They have played a crucial role in defining standards such as the Web API specifications, including the Web API Design Principles, WebIDL, and the Fetch API. 

    2. OpenAPI Initiative (OAI):
The OpenAPI Initiative, hosted by the Linux Foundation, focuses on creating and promoting the OpenAPI Specification (formerly known as Swagger). OpenAPI Specification is a widely adopted standard for describing RESTful APIs. It provides a machine readable format to define API endpoints, request/response formats, authentication mechanisms, and more. 

    3. Internet Engineering Task Force (IETF): 
IETF is an open international community that 
develops and promotes Internet standards. They have been involved in defining standards for 
network protocols, security mechanisms, and web-related technologies. The IETF has 
contributed to API standards such as OAuth 2.0, which is widely used for authentication and 
authorization in APIs. 

    4. OAuth Community:
OAuth is an open standard for secure API authorization. It has a community-driven approach with contributors from various organizations. The OAuth community, through discussions, specifications, and implementations, helps shape and evolve the OAuth standard. 

    5. JSON Schema:
JSON Schema is a standard for specifying the structure, format, and validation rules for JSON data. While not specific to APIs, JSON Schema is often used in API  design to define the structure of API request/response payloads. 

    6. ISO (International Organization for Standardization):
ISO is an independent international organization that develops and publishes standards across various industries. Though not API specific, ISO standards like ISO/IEC 27001 (Information Security Management) and ISO/IEC 20000 (IT Service Management) provide guidelines and requirements that indirectly impact API security and management practices. 

These organizations, along with others, contribute to the development of standards and 
specifications that help establish best practices, interoperability, and consistency in API design, development, and usage.

The proposed security solution for MAA (Mobile Application Analyzer) consists of an MAAAPI installed in the web server hosting the domain web service, along with a set of security services such as encryption and decryption in the middleware web server. The solution aims to prevent message alteration attacks and ensure secure communication. 

The workflow begins with the encryption of the SOAP request message received by the 
SecurityProvider service. The entire body of the request message is encrypted to protect the 
sensitive information. The encrypted SOAP message is then transmitted via a communication 
channel to invoke the ConvertCurrency service. 

At the web server where the ConvertCurrency service is deployed, the MAAAPI intercepts the 
encrypted SOAP request message and decrypts it. The decrypted message is then passed 
through the same channel to invoke the service. Similarly, after the execution of the 
ConvertCurrency service, the response SOAP message is intercepted by MAAAPI, encrypted, 
and then passed on. 

On the middleware side, the security provider decrypts the encrypted SOAP response message 
using a decryption web service. The decrypted message is then sent to the composer service, 
which passes it on to the end user. This ensures secure transmission of the response message.

The solution effectively prevents message alteration attacks by communicating the SOAP 
messages in encrypted form. This makes it difficult for hackers to modify the message contents. The snapshot log of the middleware web server demonstrates the functioning of the solution. 

#### How API can be used in mental health .  
Open APIs can be used in various ways to facilitate and enhance mental health care. Here are a few examples: 

1. **Accessing Mental Health Resources**: Open APIs can be used to connect individuals with online databases, directories, or other resources containing information about mental health services. This could include things like treatment options, professionals and specialists in the field, available support groups, and more. 

2. **Teletherapy Platforms**: Mental health professionals can use APIs to integrate teletherapy platforms into their existing healthcare systems. This allows patients to connect with therapists or counselors remotely, which can be particularly useful for individuals who live in rural areas, have mobility issues, or prefer online counseling. 

3. **Self-Monitoring Tools**: APIs can facilitate the integration of self-monitoring tools that track user behavior, mood, stress levels, etc. This data can be used to provide individuals with insights into their mental state over time, helping them to identify triggers, notice trends, and take action when necessary. 

4. **Psychoeducation**: Open APIs can be used to provide educational resources to individuals, helping them learn more about their mental health conditions, the treatment options that are available, and ways to manage symptoms.

5. **Integrating Mental Health Assessments**: APIs can be used to integrate standardized mental health assessments into a variety of platforms, allowing users to self-assess their mental health status and professionals to screen for mental health disorders.

6. **AI-Powered Chatbots**: APIs can be used to deploy AI chatbots on various platforms. These chatbots can provide instant mental health support, engage users in cognitive behavioral therapy (CBT) exercises, and provide resources. They're not a substitute for professional help, but can provide initial assistance or supplement existing treatment. 

7. **Data Analysis and Research**: APIs can help in collecting and analyzing data regarding mental health. This data can contribute to understanding trends, prevalence, treatment outcomes, and other research aspects. 

8. **Appointment Scheduling**: APIs can help in integrating calendar services into a healthcare provider's system, allowing for easy scheduling and rescheduling of appointments, reminders for medication or therapy sessions, etc. 

9. **Emergency Services Integration**: In a crisis situation, APIs can be used to quickly connect users with emergency services or hotlines.

Please note that all applications of APIs in mental health should adhere to strict privacy and confidentiality guidelines in accordance with HIPAA or similar legislation, to protect sensitive patient data.r XIA (XML Injection Attack), a similar security solution is Proposed. It involves the deployment of a XIAAPI in the web server of the domain web service and an XML Injection service in the middleware web server. The XIAAPI intercepts and validates the decrypted SOAP request message against the SOAP_Request_DTD to detect any alterations. If 
the message is altered, a fault SOAP message is sent to indicate the attack. Otherwise, the 
request is allowed to invoke the service. 

In case of a fault message or a hacked response, the XML Injection service is used to generate 
fault messages or send a copy of the original message to ensure the integrity of the 
communication. The feasibility of the security solution is tested through experimentation, 
demonstrating its ability to detect and handle XML Injection attacks.

Overall, the proposed security solutions for MAA and XIA aim to protect the integrity and confidentiality of SOAP messages, ensuring secure communication between web services. 

This research focuses on the development of a RESTful web service and Open APIs for 
research information systems, particularly targeting smart devices such as smartphones. The 
motivation behind this research is the need for a convenient and efficient way for researchers to access information about conferences, seminars, research papers, and other related activities. By utilizing Open APIs, researchers can easily retrieve and publish conference information, search for research papers, view PDFs, and engage in mobile review systems.

The shift towards web-based architectures and mobile cloud computing has emphasized the 
importance of Open API-based development. Major community portal companies like Google, 
Naver, and Yahoo already provide Open API services for accessing their services. In the 
context of research information systems, researchers often face challenges in finding suitable conferences to publish their work, and research organizations struggle to effectively advertise their activities. Limited resources and funding make it difficult for nonprofit research organizations to promote their events through traditional means. By leveraging mobile devices and Open APIs, researchers can receive alerts for conferences, seminars, and workshops, as well as access and review research papers conveniently. 

The rise of mobile devices in education has also contributed to the popularity of using smart 
devices for learning. The South Korean Ministry of Education plans to replace traditional 
paper-based textbooks with e-books by 2015, providing students with a more convenient and 
interactive learning experience. Smart tablets offer the advantage of accessing PDF documents 
online, eliminating the need to sit at a desk. This feature differentiates PDF services on tablets from those on desktops. 

In summary, this research aims to establish a standard interface for Open APIs in research 
information systems, specifically designed for smart devices. By utilizing RESTful web 
services and Open APIs, researchers can easily access conference information, search for 
research papers, view PDFs, and engage in mobile review systems, enhancing their research 
workflow and productivity.

### Leveraging Healthcare API to transform Interoperability: API Security and Privacy

The paper discusses the challenges of interoperability in healthcare organizations and the increasing use of APIs (Application Programming Interfaces) to address these challenges. APIs allow different software applications to share data and have been used to integrate patient information across various healthcare systems and mobile apps. 

The main focus of the paper is on API security and privacy, as exposing sensitive patient data 
through APIs makes them vulnerable to potential attacks. As the need for tighter API security 
grows, managing APIs becomes crucial. 

The introduction provides an overview of interoperability in healthcare and the historical context of data exchange methods. It highlights the importance of APIs in achieving 
interoperability and complying with regulations, such as meaningful use requirements. The related work section discusses previous research in API usage, security, and identity management in healthcare. It mentions the challenges of EHR (Electronic Health Record) interoperability due to varying data standards and security concerns.

In the discussion section, the benefits of API adoption in healthcare are outlined. APIs enable 
improved data exchange, mobile app integration, and innovative solutions for clinicians and 
researchers. The potential for external interoperability and data sharing is emphasized.

The paper aims to inform healthcare providers about the advantages of API integration while 
addressing security concerns and building trust in data authority across different healthcare systems. 

In summary, the paper highlights the importance of APIs in achieving healthcare interoperability and discusses the need for stronger security measures to protect patient data. It 
presents examples of successful API implementation in healthcare and the potential benefits it offers to both providers and patients.

#### API based Security solutions for Communication among Web Services 

This paper proposes a novel approach to ensure the confidentiality and integrity of data 
transmitted via web services protocols. The approach addresses two specific security attacks: message alteration attack and XML injection attack. The proposed solution involves the use ofpluggable APIs on the service provider side and security services in the middleware side. 

The paper discusses the existing literature on web service security and highlights the limitations of previous works. It then presents the proposed security solution, which includes the deployment of security services in the middleware server and the integration of pluggable APIs in the domain web service server. The security services provide encryption and decryption capabilities, while the APIs help prevent message alteration and detect XML injection attacks. 

The proposed solution is demonstrated in a composition scenario involving a middleware 
service and domain web services. The middleware service acts as a composer, integrating 
multiple domain web services. A user interacts with the system through a web browser and the 
input information is passed to the middleware service via the interface program. The middleware service then invokes the necessary domain web services using SOAP messages. 

To prevent message alteration attacks, the proposed solution encrypts the SOAP request 
message using encryption services in the middleware server. The entire body of the request message is encrypted, making it difficult for attackers to identify the sensitive information. The encrypted message is then communicated to the appropriate domain web service through a secure communication channel.

In addition, the proposed solution addresses XML injection attacks by implementing security 
APIs in the domain web service server. These APIs help detect and prevent XML injection 
attacks, ensuring the integrity of the data exchanged between web services. 

The paper concludes by verifying the non-vulnerability of the proposed solutions through simulated attacks. The approach presented in this paper provides a comprehensive security solution for web services, addressing both network layer and application layer security concerns. 

The Android permissions are the different types of permissions an app requests from a user 
upon installation. Some permissions are necessary for the app's core functionality, while others 
may be used for data collection or potentially malicious purposes. 

    1. INTERNET: Allows the application to open network sockets. 

    2. READ_PHONE_STATE: Allows read-only access to phone state, including the phone number of the device, current cellular network information, the status of any ongoing calls, and a list of any PhoneAccounts registered on the device. 

    3. ACCESS_NETWORK_STATE: Allows applications to access information about networks. 

    4. WRITE_EXTERNAL_STORAGE: Allows an application to write to external storage.

These are commonly requested permissions by both malicious and benign (non-malicious) apps. The reason is that most apps need internet access to function properly, need to read phone state to adjust their behavior accordingly (for example, pausing a game when a call is received), 
and require access to the device's network state to ensure a stable internet connection. Writing 
to external storage is necessary for apps that need to download and store data (like images, 
videos, or other large files) on the device. 

However, the SMS-related permissions, SEND_SMS, RECEIVE_SMS, READ_SMS, and WRITE_SMS are more commonly requested by malicious apps. This could be because these apps are designed to send SMS messages without the user's knowledge, often to premium-rate numbers, leading to unexpected charges on the user's bill. They may also read incoming and outgoing SMS messages to collect sensitive information like OTPs (One-Time Passwords) for malicious purposes.
## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://khushimishprofile.netlify.app/)

[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](www.linkedin.com/in/khushimish26)

