### **Part 1: Tech Stack for the SWRP Curriculum Service**

A robust and scalable SWRP (Software, Robotics, and Programming) platform requires a modern, cloud-native tech stack designed for real-time interaction, 3D rendering, and data analytics.

Our SWRP platform is architected around a suite of best-in-class open-source solutions, orchestrated as a cohesive set of microservices. This ensures transparency, flexibility, and provides an authentic technology experience for students.

Here is a breakdown of our core backend services and how they integrate:

**1\. Identity & Access Management (Powered by Keycloak)**

* **Core Technology:** **Keycloak**.  
* **Purpose:** This service is the central hub for all user authentication and authorization. Keycloak manages user identities, roles (student, teacher, admin), and permissions across the entire platform.  
* **Integration:** It provides Single Sign-On (SSO) for all other services (Moodle, JupyterHub, GitBucket, etc.). It can also integrate with a school's existing identity provider (e.g., LDAP, SAML, or Google Workspace) for seamless user onboarding.

**2\. Learning Management & Curriculum (Moodle Integration Layer)**

* **Core Technology:** **Moodle**, accessed via a custom **Node.js/Python** microservice.  
* **Purpose:** Moodle serves as the authoritative source for our standards-aligned curriculum. It hosts courses, lessons, assignments, and grades.  
* **Integration:** Our custom microservice acts as an API gateway. It uses Moodle's Web Services and LTI (Learning Tools Interoperability) standards to:  
  * Sync class rosters from Keycloak into Moodle.  
  * Display curriculum content within our main platform UI.  
  * Push grades and progress from the simulation lab back into the Moodle gradebook.

**3\. Collaborative Metaverse (Powered by Mozilla Hubs)**

* **Core Technology:** A self-hosted instance of **Mozilla Hubs**.  
* **Purpose:** Provides the immersive, multi-user 3D environment for our Virtual Robotics Lab and collaborative spaces.  
* **Integration:** We have a dedicated **Metaverse Management Service** that programmatically interacts with our Hubs instance. This service:  
  * Creates private, persistent virtual rooms for each class or project team.  
  * Authenticates users via Keycloak before granting them access.  
  * Spawns 3D models of student-designed robots and curriculum-specific environments into the Hubs rooms.

**4\. Code & Version Control (Powered by GitBucket)**

* **Core Technology:** A self-hosted instance of **GitBucket**.  
* **Purpose:** To teach students professional software development practices, all robot programming code is stored and managed in Git repositories.  
* **Integration:** When a student starts a new project, our platform automatically creates a new repository for them in GitBucket. The in-browser code editor directly commits code to this repository, allowing for version history, branching, and collaboration. This provides an authentic development workflow.

**5\. Simulation**

* **Purpose:** This service runs the high-fidelity physics simulations. Crucially, it also acts as a bridge between the virtual and physical worlds.  
* **Framework:** **React.js**/**Vue.js** with **TypeScript**. This provides a reactive, component-based user interface that is highly maintainable and type-safe.  
* **3D Rendering Engine:** **Three.js**. These are powerful WebGL-based libraries that run directly in the browser, allowing us to render the 3D robotics simulations and Metaverse environments without requiring users to install special software.  
* **State Management:** Redux (for React) or Vuex (for Vue) to manage complex application states, such as the position of a robot, sensor data, and user interactions.  
* **Real-time Communication:** **WebSockets** for instant, two-way communication between the user and the server. This is critical for live collaboration and real-time updates in the virtual lab.

**6\. IoT & Data Visualization Platform (integrating OpenRemote)**

This track focuses on the "Internet of Things"—connecting physical hardware, collecting data, and creating automated systems.

* **Core Technology:** A self-hosted **OpenRemote** instance.  
* **Purpose:** To serve as a professional-grade IoT platform where students can connect, manage, and analyze data from real-world sensors and devices. It is the bridge between the physical world and our data analytics tools.  
* **Integration and Workflow:**  
  1. **Hardware Connection:** Students learn to connect Leanbot with various IoT sensors (temperature, light, motion, etc.) to the network.  
  2. **Data Ingestion:** Using standard protocols like MQTT, students configure their devices to send data to the IoT platform.  
  3. **Dashboarding and Visualization:** Students use IoT Platform's built-in designer to create custom web-based dashboards. They can build real-time graphs, gauges, maps, and alerts to visualize the data from their physical sensors.  
  4. **Automation with Rules Engine:** The core of this pathway is learning automation. Students use the IoT Platform rules engine to create "if-this-then-that" logic (e.g., "IF the temperature sensor reads \> 25°C, THEN send a command to turn on the fan"). This teaches the fundamentals of control systems and smart environments.

**7\. Data Analytics & Insights (Powered by JupyterHub)**

* **Core Technology:** **JupyterHub**.  
* **Purpose:** Provides a powerful data science environment for teachers and advanced students to analyze simulation data, student performance metrics, and IoT sensor logs.  
* **Integration:** JupyterHub is connected to our **PostgreSQL** database and data warehouse. We provide pre-configured notebooks to help teachers visualize class-wide progress or identify students who need support. Students in advanced courses can use it to perform data analysis on their robot's sensor logs.

**8\. The Mobile Application Development (Powered by MIT App Inventor)**

This track focuses on pure software development, teaching students how to design, build, and deploy their own mobile applications that can interact with web-based services.

* **Core Technology:** **MIT App Inventor**.  
* **Purpose:** To provide an accessible, block-based environment for students to create fully functional mobile apps for Android and iOS. This pathway emphasizes UI/UX design, event-driven programming, and interaction with APIs.  
* **Integration and Workflow:**  
  * **Standalone Development:** Students learn the fundamentals by building standalone apps, such as calculators, quizzes, or simple games.

**9\. User workspace, Public Content & Documentation (Powered by WordPress)**

* **Core Technology:** **WordPress**, accessed via its REST API.  
* **Purpose:** WordPress manages all public-facing content, including the marketing website, blog posts, case studies, and the knowledge base/support documentation.  
* **Integration:** Our main platform can pull relevant help articles or blog posts directly from WordPress to display within the user interface, providing contextual support to students and teachers. This separates marketing content from the core curriculum managed in Moodle.

**10\. Database:**

* **Primary Database:** **MySQL**/**PostgreSQL**. A powerful, open-source relational database for storing structured data like user profiles, curriculum content, and student progress.  
* **Caching Layer:** **Redis**. Used for caching frequently accessed data and managing real-time session information to reduce latency.  
* **Data Warehouse:** **PostgreSQL** for aggregating and analyzing large volumes of student performance data to provide insights to teachers and administrators.

**11\. Infrastructure & DevOps:**

Our platform is deployed on a strategic **hybrid model**, combining dedicated self-hosted servers with any public cloud. This architecture is purposefully designed to give us the best of both worlds: the raw performance and data control of on-premises infrastructure, combined with the global scalability and cost-effectiveness of a flexible cloud provider.

* **Public Cloud:** **Amazon Web Services (AWS)** or **Google Cloud Platform (GCP)** for their scalability, global reach, and rich set of managed services.  
* **Containerization:** **Docker**. All our microservices are containerized for consistency across development, testing, and production environments.  
* **Orchestration:** **Docker swarm**. Manages our containerized applications, enabling auto-scaling, self-healing, and zero-downtime deployments.  
* **CI/CD Pipeline:** **GitHub Actions** to automate our build, testing, and deployment processes, ensuring we can release new features and fixes safely and quickly.  
* **Content Delivery Network (CDN):** **LightCDN** to cache static assets (like 3D models, videos, and images) closer to users globally, dramatically improving load times.

---

### **Part 2: Metaverse Integration into the Curriculum**

Our Metaverse integration is built on a **self-hosted instance of Mozilla Hubs**, providing an unparalleled level of control, security, and customization. 

This is a complete creative ecosystem designed to guide students through the entire modern digital creation pipeline. It starts with building worlds and avatars and culminates in breathing life into intelligent, interactive AI characters.

Here’s how the Metaverse is woven into the SWRP curriculum:

**1\. Creating an AI Mind (The AI Character Creator):**

* **What it is:** The AI Character Creator is a guided, no-code interface that allows students to build their own conversational AI agent. This agent is powered by a foundational **OpenAI model (like GPT-4)** but is customized and "taught" by the student.  
* **How it Works: A Simplified Workflow**  
  * **Choose a Foundation:** Students start with the powerful, general-purpose OpenAI base model.  
  * **Define the Persona (The "Brain"):** In a simple text interface, students write the AI's "system prompt" or "constitution." This defines its personality, role, and rules. For example: *"You are 'Unit 734', the lead engineer for the Mars rover project. You will only answer questions related to robotics, physics, and Mars exploration. You are helpful, precise, and have a slightly robotic tone."*  
  * **Provide a Knowledge Base (Optional, Advanced):** For advanced projects, students can upload documents (like technical manuals for their robot, historical texts, or project research notes). The AI will use this private information to answer questions with specific, factual data, a technique known as Retrieval-Augmented Generation (RAG).  
  * **Embody the Character:** The student assigns their newly created "AI brain" to a 3D avatar, which can be one they designed in the AI Avatar Lab.  
  * **Deploy into a Hubs Room:** The student spawns their AI character into their private Mozilla Hubs room. The character appears as an interactive Non-Player Character (NPC).  
* **The Result: An Interactive AI Agent**  
  Other students can now approach this character in the Metaverse, ask it questions via voice or text, and the AI will respond in real-time, adhering to the personality and knowledge it was given.

**2\. Collaborative Project Spaces:**

* **What it is:** Shared virtual environments where students, represented as avatars, can meet, communicate, and work together on projects.  
* **How it's used:**  
  * **Team-Based Challenges:** Students from the same class (or even different schools) can collaborate on building a single, complex robot. They can see each other's changes in real-time.  
  * **Virtual Whiteboards & 3D Models:** Teams can brainstorm on virtual whiteboards, import 3D models of their designs, and co-debug code on a shared virtual screen. This enhances remote and hybrid learning.

**3\. Immersive Conceptual Learning:**

* **What it is:** Using the virtual environment to take students "inside" the technology.  
* **How it's used:**  
  * **Visualize Data Flow:** Students can "see" data flowing from a sensor, through the robot's processor, to an actuator.  
  * **Explore Mechanical Systems:** Students can explode a virtual gearbox to see how the gears interact or walk through a large-scale model of a CPU to understand its components. This makes abstract engineering and computer science concepts concrete and memorable.

**Curriculum Integration & Learning Outcomes**

This feature is not just for fun; it is a core part of the advanced Software and AI curriculum.

* **Project Example: The "Virtual Expert"**  
  1. **Task:** After completing a major robotics project, a student team is tasked with creating a "Virtual Expert" AI character. This AI must be able to explain the robot's design, the function of its code, and the challenges the team faced.  
  2. **Process:**  
     1. The team writes a clear persona for their expert.  
     2. They upload their project documentation, code files (with comments), and design diary as the AI's knowledge base.  
     3. They deploy the expert into a Hubs room alongside their virtual robot.  
  3. **Assessment:** Other students (or the teacher) can then "interview" the AI expert. The team is graded on how accurately and coherently their AI can answer questions, demonstrating their deep understanding of their own project.  
* **Key Learning Outcomes:**  
  1. **AI Literacy:** Students learn firsthand how LLMs work, moving beyond the "magic" to understand the concepts of system prompts, knowledge bases, and model behavior.  
  2. **Prompt Engineering:** The core of the task is writing clear, unambiguous instructions, a critical skill for working with any modern AI.  
  3. **Data Curation:** In advanced projects, students learn the importance of providing clean, well-organized data to get good results from their AI.  
  4. **Ethical AI:** This opens up classroom discussions about AI bias, personality, and the responsibility of the creator for their AI's output.  
  5. **Systems Thinking:** Students learn to design and integrate a complete system: a world, an avatar, and an AI brain, all working together to serve a specific purpose.
