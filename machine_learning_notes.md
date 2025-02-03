# 📌 Machine Learning Engineering for Production (MLOps)

## **1️⃣ Introduction to MLOps**
Machine Learning Operations (**MLOps**) is an emerging discipline that integrates best practices from **software engineering, DevOps, and ML** to streamline the lifecycle of ML projects.

---
## **2️⃣ The Machine Learning (ML) Project Lifecycle**
1. **Scoping**
    - Define project objectives and key success metrics.
2. **Data**
    - Define, label, and organize data.
    - Establish baseline performance.
3. **Modeling**
    - Select and train models.
    - Perform error analysis.
4. **Deployment**
    - Deploy models to production.
    - Monitor, maintain, and improve models over time.

---
## **3️⃣ Case Study: Speech Recognition System**
### **Scoping Stage**
- Define project scope: **Voice search using speech recognition**.
- Identify key metrics:
    - **Accuracy, latency, throughput**.
    - Estimate **resources** and **timeline**.

### **Data Stage**
#### Define Data:
- Ensure consistent data labeling.
- Define data preprocessing strategies:
    - **Silence trimming** before/after clips.
    - **Volume normalization**.

### **Modeling Stage**
Key components for ML model:
- **Code** (algorithm/model architecture).
- **Hyperparameters**.
- **Data** (training and validation sets).

### **Deployment Stage**
- **Edge Device (Mobile Phone)**:
    - Local software captures microphone input.
    - **Voice Activity Detection (VAD)** module.
- **Cloud-based Speech API**:
    - Sends audio input to **Prediction Server**.
    - Returns **transcript and search results**.
- **Monitoring & Maintenance**:
    - Detect and mitigate **concept drift & data drift**.

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

### **Deployment Patterns**
#### **Common Deployment Cases:**
- **New Product/Capability**
- **Automation or assistance for manual tasks**
- **Replacing an existing ML system**

#### **Best Practices:**
- **Gradual rollout with monitoring**.
- **Rollback mechanisms** in case of failure.

#### **Shadow Mode (Human vs ML):**
- ML system runs alongside human operators **without impacting real decisions**.
- Used for **evaluation before full deployment**.

#### **Canary Deployment:**
- Roll out model to a **small fraction (5%)** of traffic initially.
- Gradually increase traffic while monitoring performance.

#### **Blue-Green Deployment:**
- **Router directs traffic** to either old (**blue**) or new (**green**) version.
- Allows **seamless rollback** if issues occur.

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

#### **Output Metrics:**
- **# of times empty results (`""`) are returned**
- **# of times user redoes a search**
- **# of times user switches from voice to typing**
- **Click-through rate (CTR)**

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

🚀 **Machine Learning deployment is not a one-time event but an ongoing process of optimization and refinement.**

---
### **📌 Next Steps:**
⏭️ **Stopped at Section 7** – Resume at **Section 8** next time!
