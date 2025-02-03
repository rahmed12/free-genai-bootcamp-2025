# Architecture Document: AI-Powered Bengali Language Learning Portal

## 1. Business Requirements

### 1.1 Business Goals and Objectives

#### Goals:
The primary goal of this project is to develop an AI-powered language portal that helps students learn Bengali effectively while providing teachers with tools to enhance their lesson plans.

#### Objectives:
1. **Gamify Learning:** Implement an interactive "Choose Your Own Adventure" feature where students make choices using the Bengali words they are learning.
2. **Visual Flash Card Generation:** Automatically generate flashcards with AI-driven visuals, adapted to the student's proficiency level.
3. **Sentence Constructor:** Provide a guided tool to help students form sentences correctly using Bengali grammar.
4. **Writing Practice App:** Develop a handwriting recognition tool where students can practice writing Bengali characters and words.
5. **Speak to Learn:** Incorporate speech recognition to enable learning through verbal practice and pronunciation feedback.
6. **Light Visual Novel Immersion:** Introduce immersive storytelling where students engage in reading and comprehension through AI-powered visual novels.

---

## 2. Tooling: GenAI vs ML

### 2.1 Overview
The choice between **Generative AI (GenAI)** and **Traditional Machine Learning (ML)** is crucial for different components of the Bengali language learning portal. Each approach has its strengths and trade-offs that must be considered.

### 2.2 Generative AI (GenAI)
GenAI models, such as large language models (LLMs) and AI-powered visual generators, create text, images, and speech dynamically based on user input.

#### **Benefits of GenAI:**
- **Personalization:** Can generate adaptive learning content, including flashcards, story-driven lessons, and customized writing prompts.
- **Creativity:** Enables the creation of engaging content, such as interactive storytelling and AI-generated visual novel elements.
- **Natural Language Understanding:** Can generate coherent sentence examples and provide explanations for grammatical structures.
- **Low Development Effort:** Pre-trained models (e.g., GPT, DALL·E, TTS models) can be leveraged with minimal customization.

#### **Cons of GenAI:**
- **Higher Computational Costs:** Running large generative models requires substantial processing power.
- **Unpredictability:** Outputs may sometimes be incorrect or inconsistent, requiring additional validation layers.
- **Limited Training Customization:** While adaptable, fine-tuning GenAI models for niche applications (e.g., Bengali grammar) can be complex.

---

### 2.3 Traditional Machine Learning (ML)
ML techniques use structured training datasets to make predictions, recognize patterns, and provide intelligent feedback.

#### **Benefits of ML:**
- **Accuracy and Reliability:** More deterministic than GenAI when trained on well-labeled datasets (e.g., Bengali pronunciation classification).
- **Lower Resource Consumption:** Smaller models, such as decision trees or neural networks, are less resource-intensive.
- **Data-Driven Insights:** Can analyze student progress, predict learning gaps, and suggest targeted exercises.

#### **Cons of ML:**
- **Requires Large Labeled Datasets:** Training effective ML models for tasks like handwriting recognition or pronunciation correction requires high-quality datasets.
- **Less Adaptive:** Unlike GenAI, ML models do not dynamically generate new content; they rely on pre-existing labeled data.
- **More Development Effort:** ML pipelines need feature engineering, training, and continuous data curation.

---

### 2.4 Choosing the Right Approach for Each Feature

| Feature                         | Best Approach | Justification |
|--------------------------------|--------------|--------------|
| **Gamified Learning (Choose Your Own Adventure)** | **GenAI** | Generates dynamic storylines based on user input. |
| **Visual Flashcards** | **GenAI** | AI-generated images adapt to different learning levels. |
| **Sentence Constructor** | **GenAI + ML** | GenAI for generating examples, ML for grammatical accuracy checks. |
| **Writing Practice App** | **ML** | ML models recognize and assess handwritten Bengali characters. |
| **Speak to Learn (Pronunciation Practice)** | **ML** | ML-based speech recognition and feedback for phonetic accuracy. |
| **Light Visual Novel Immersion** | **GenAI** | AI creates personalized stories and dialogues. |

By strategically leveraging **both** GenAI and ML, we can optimize learning experiences while maintaining efficiency and accuracy.

---
## 3. Non-Functional Requirements

To ensure the Bengali language learning portal operates efficiently, the following non-functional requirements must be met.

### 3.1 Performance
- **Fast Response Times:** The system should respond to user inputs (e.g., sentence construction, pronunciation analysis) within a reasonable time to ensure a smooth user experience.
- **Efficient AI Model Execution:** Optimized AI models or smaller modles should be used to prevent latency, especially for real-time interactions such as pronunciation feedback.


### 3.2 Scalability
- **Horizontal Scalability:** The system should support an increasing number of users by dynamically scaling backend services.
- **Efficient Caching Mechanisms:** Frequently accessed resources (e.g., pre-generated flashcards, grammar rules) should be cached to reduce redundant computation.
- **Microservices-Based Architecture:** Deploy AI models, database services, and UI components independently for greater scalability.

### 3.3 Security
- **AI Model Protection:** Ensure **AI-generated content validation** to prevent inappropriate or incorrect learning material from being displayed.

### 3.4 Usability
- **Intuitive UI/UX Design:** Ensure the interface is **easy to navigate**, with clear instructions and visual feedback.
- **Multi-Device Compatibility:** The platform should be **fully responsive**, supporting desktop, tablet, and mobile usage.

