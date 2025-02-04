# AI-Powered Outbound Voice Agent

## 📌 Overview
This guide explains the **AI-powered outbound voice agent** that automates calling customers for overdue payments. The system **makes calls, understands customer responses, processes payments, and routes calls intelligently.**

## 🔧 Tech Stack
| Component        | Technology Used |
|-----------------|----------------|
| Backend        | Flask (Python) |
| Voice Calling  | Asterisk (FreePBX) |
| AI Processing  | Google Dialogflow |
| Text-to-Speech | Google Cloud TTS |
| Payment Processing | Stripe API |
| Keypad Input (DTMF) | Asterisk DTMF Capture |
| Database (optional) | PostgreSQL / Firebase |

## 🎯 Workflow & Architecture

1️⃣ **AI Calls the Customer** using **Asterisk** & plays a **Text-to-Speech (TTS)** message.  
2️⃣ Customer **responds using voice or keypad (DTMF input).**  
3️⃣ **AI Processes the Input**: 
   - **If spoken response**, it is transcribed & analyzed using **Dialogflow AI.**
   - **If keypad response (DTMF input)**, the system routes actions accordingly.  
4️⃣ **AI Responds & Takes Action**:
   - ✅ **Press 1** → AI **triggers Stripe payment API** to collect payment.
   - ✅ **Press 2** → Call is **transferred to a live agent** via Asterisk.
   - 🚨 **Invalid input** → AI plays a retry message.  
5️⃣ **AI Logs & Tracks Interactions** in a database (if required).  

## 🛠 System Components

### 1️⃣ **Voice Calling System**
- **Replaces Twilio** with Asterisk (Free, Open-Source VoIP system).
- Uses Asterisk to **initiate calls** & manage call flow.
- Uses **DTMF Keypad input** to capture customer responses.

### 2️⃣ **AI Understanding (Natural Language Processing - NLP)**
- **Google Dialogflow** analyzes **spoken responses**.
- AI **understands phrases like "I want to pay"** or "I need more time".
- Generates **dynamic AI responses**.

### 3️⃣ **Text-to-Speech (TTS) Integration**
- Uses **Google Cloud TTS** to convert AI responses into human-like speech.
- Supports **SSML for more natural-sounding AI voices.**

### 4️⃣ **DTMF (Dual-Tone Multi-Frequency) Input Handling**
- Customers can **press phone keys** to interact with the AI.
- **Press 1** → AI initiates a **Stripe payment request**.
- **Press 2** → AI **routes the call to a live agent**.
- **Pressing invalid keys** triggers an error message with retries.
- Captured using **Asterisk DTMF processing** in `extensions.conf`:
  ```ini
  [default]
  exten => 1001,1,Answer()
      same => n,Playback(/var/lib/asterisk/sounds/output)
      same => n,Read(choice,beep,1)  ; Wait for user input
      same => n,GotoIf($["${choice}"="1"]?pay)
      same => n,GotoIf($["${choice}"="2"]?agent)
      same => n,Hangup()

  exten => pay,1,Playback(/var/lib/asterisk/sounds/payment_processing)
      same => n,AGI(payment_script.py)  ; Calls the payment API
      same => n,Hangup()

  exten => agent,1,Dial(SIP/agent123)  ; Transfers to a live agent
      same => n,Hangup()
  ```

### 5️⃣ **Payment Handling with Stripe**
- **AI asks if customer wants to pay**.
- **Press 1** → AI triggers **Stripe PaymentIntent API**.
- **Customer confirms payment** via in-call or a payment link.
- AI plays **success/failure messages.**

### 6️⃣ **Call Routing (Human Escalation)**
- **Press 2** → Asterisk transfers the call to a live agent.
- Uses **SIP trunking** for call handling.
- Logs interactions & escalates critical cases.

## 🚀 Deployment & Scalability
✅ **Dockerized Flask API** for easy deployment.  
✅ **Can be deployed on AWS/GCP** using **Cloud Functions or EC2.**  
✅ **Future Enhancements**: Multi-language support, WhatsApp/SMS reminders.

---
## 📌 Next Steps
- 🔹 Deploy Asterisk on your server.
- 🔹 Set up Google Dialogflow for AI conversation handling.
- 🔹 Test voice agent workflow using real-world scenarios.

🚀 **This AI-driven call system can reduce human workload & automate payment collections efficiently!**
