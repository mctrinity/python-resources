# 📌 Machine Learning Engineering for Production (MLOps)

## **1️⃣ Introduction to MLOps**
Machine Learning Operations (**MLOps**) is an emerging discipline that integrates best practices from **software engineering, DevOps, and ML** to streamline the lifecycle of ML projects. 

MLOps aims to: 
- Bridge the gap between ML development and production.
- Improve model reproducibility, reliability, and scalability.
- Ensure continuous monitoring, updating, and retraining of models.

---
## **2️⃣ The Machine Learning (ML) Project Lifecycle**
1. **Scoping**
    - Define project objectives and key success metrics.
    - Understand business goals and constraints.
    - Assess feasibility and potential risks.
2. **Data**
    - Define, label, and organize data.
    - Establish baseline performance.
    - Handle missing data and outliers.
3. **Modeling**
    - Select, train, and optimize models.
    - Perform error analysis and hyperparameter tuning.
    - Ensure robustness and fairness in predictions.
4. **Deployment**
    - Deploy models to production.
    - Monitor, maintain, and improve models over time.
    - Establish CI/CD pipelines for model updates.

---
## **3️⃣ Case Study: Speech Recognition System**
### **Scoping Stage**
- Define project scope: **Voice search using speech recognition**.
- Identify key metrics:
    - **Accuracy, latency, throughput**.
    - Estimate **resources** and **timeline**.
    - Assess user needs and expectations.

### **Data Stage**
#### Define Data:
- Ensure consistent data labeling.
- Define data preprocessing strategies:
    - **Silence trimming** before/after clips.
    - **Volume normalization**.
- Address **edge cases** like background noise, accents, and speech impairments.
- Evaluate data biases and mitigate their impact on the model.

### **Modeling Stage**
Key components for ML model:
- **Code** (algorithm/model architecture).
- **Hyperparameters**.
- **Data** (training and validation sets).
- **Regularization techniques** to avoid overfitting.
- Consider **transfer learning** for improved performance on small datasets.

### **Deployment Stage**
- **Edge Device (Mobile Phone)**:
    - Local software captures microphone input.
    - **Voice Activity Detection (VAD)** module.
- **Cloud-based Speech API**:
    - Sends audio input to **Prediction Server**.
    - Returns **transcript and search results**.
- **Monitoring & Maintenance**:
    - Detect and mitigate **concept drift & data drift**.
    - Implement **logging and anomaly detection**.

---
## **4️⃣ Deployment Challenges & Strategies**
### **Concept Drift & Data Drift**
- **Training Set:** Purchased data & historical transcripts.
- **Test Set:** Recent data samples.
- **Data Degradation:**
    - **Gradual change**: Slow shifts in data distribution.
    - **Sudden shock**: Drastic data change.
- **Software Engineering Considerations:**
    - Real-time vs batch processing.
    - Cloud vs edge/browser deployment.
    - Compute resources: 
    - **CPU, GPU, memory**.
    - **Latency, throughput (QPS - queries per second)**.
    - **Logging, security, and privacy**.
    - Implement **feature stores** for reproducibility and consistency.

### **Deployment Patterns**
#### **Common Deployment Cases:**
- **New Product/Capability**
- **Automation or assistance for manual tasks**
- **Replacing an existing ML system**

#### **Best Practices:**
- **Gradual rollout with monitoring**.
- **Rollback mechanisms** in case of failure.
- **A/B testing to evaluate model performance in production**.

#### **Shadow Mode (Human vs ML):**
- ML system runs alongside human operators **without impacting real decisions**.
- Used for **evaluation before full deployment**.
- Helps compare **ML vs human accuracy**.

#### **Canary Deployment:**
- Roll out model to a **small fraction (5%)** of traffic initially.
- Gradually increase traffic while monitoring performance.
- Ensures smooth transition without disrupting users.

#### **Blue-Green Deployment:**
- **Router directs traffic** to either old (**blue**) or new (**green**) version.
- Allows **seamless rollback** if issues occur.
- Ensures **high availability with minimal downtime**.

#### **Degrees of Automation (Spectrum)**
- **Human-only** decision making.
- **Shadow mode** (ML runs in parallel but doesn’t act).
- **AI Assistance** (ML suggests but humans decide).
- **Partial Automation** (ML takes some actions).
- **Full Automation** (ML fully controls the decision-making process).
- 🚨 **Note:** You can choose to **stop at any stage** before full automation.

---
## **5️⃣ Monitoring & Maintenance**
### **Monitoring Dashboard**
- **Server Load**
- **Fraction of non-null outputs**
- **Fraction of missing input values**
- **Data pipeline health metrics**

### **How to Set Up Monitoring Effectively:**
1. **Brainstorm potential issues** in production.
2. **Define key metrics** to detect issues early.
3. **Start with multiple metrics** and refine over time.
4. **Set thresholds for alerts**.
5. **Continuously adapt metrics and thresholds**.

### **Examples of Monitoring Metrics:**
#### **Software Metrics:**
- **Memory usage**
- **Compute power**
- **Latency**
- **Throughput (QPS)**
- **Server load**

#### **Input Metrics:**
- **Average input length**
- **Average input volume**
- **Number of missing values**
- **Average image brightness (for vision models)**
- **User interaction statistics**

#### **Output Metrics:**
- **# of times empty results (`""`) are returned**
- **# of times user redoes a search**
- **# of times user switches from voice to typing**
- **Click-through rate (CTR)**
- **Feedback from real-world usage**

---
## **6️⃣ Iterative Deployment & Model Maintenance**
### **ML Deployment as an Iterative Process:**
1. **Model Training & Data Collection**
2. **Experimentation & Error Analysis**
3. **Deployment & Continuous Monitoring**
4. **Analyze Traffic & Performance**
5. **Refine Monitoring Metrics**

### **Model Maintenance Strategies:**
- **Manual Retraining** (On-demand updates when needed).
- **Automatic Retraining** (Scheduled or triggered by performance degradation).
- **Active Learning** (Use human feedback to improve the model continuously).
- **Automated Testing** to catch regression issues.

🚀 **Machine Learning deployment is not a one-time event but an ongoing process of optimization and refinement.**

---
### **📌 Next Steps:**
⏭️ **Stopped at Section 7** – Resume at **Section 8** next time!
