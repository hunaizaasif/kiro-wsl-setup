# kiro-wsl-setup

🔧 Kiro Gateway Configuration & Troubleshooting Guide
❌ Configuration Error – No Kiro Credentials
📌 Problem

Agar server run karte waqt yeh error aaye:

<img width="380" height="158" alt="image" src="https://github.com/user-attachments/assets/8c6f4c5a-ad11-423d-a514-1e813e5590dc" />


ERROR | No kiro credentials configured!
CONFIGURATION ERROR


To iska matlab hai ke .env file properly configure nahi hui ya credentials missing hain.

✅ Solution Step-by-Step
🧾 Step 1: .env File Create Karein

Terminal open karein aur yeh commands run karein:

cd ~/kiro-openai-gateway
cp .env.example .env


Yeh command example environment file ko copy karke actual .env file bana degi.

✏️ Step 2: .env File Edit Karein
nano .env

🔓 Step 3: Required Variables Uncomment Karein

.env file ke andar yeh lines dhoondhein:

# KIRO_CREDS_FILE="~/.aws/sso/cache/kiro-auth-token.json"
# PROXY_API_KEY="my-super-secret-password-123"


Inhe uncomment karke is tarah likhein:

KIRO_CREDS_FILE="~/.aws/sso/cache/kiro-auth-token.json"
PROXY_API_KEY="my-super-secret-password-123"

💾 Step 4: File Save Karein

Nano editor mein:

Ctrl + O   → Save
Enter
Ctrl + X   → Exit

⚠️ Step 5: Kiro IDE Login Verify Karein

Yeh step bohat important hai.

✔ Ensure Karein:

Kiro IDE open ho

User login ho

Credits available ho

📌 Note:
Agar Kiro IDE login nahi hoga to gateway server kaam nahi karega.

🚀 Server Testing & Verification
▶️ Server Start Karein
python3 main.py

✅ Successful Server Start Output

Agar setup sahi hai to yeh messages nazar aayenge:

INFO | Starting Uvicorn server...
INFO | Credentials loaded...
INFO | Model cache ready
INFO | Uvicorn running on http://0.0.0.0:8000

🌐 Browser Test Karein

Browser mein open karein:

http://localhost:8000


⚠️ 0.0.0.0 browser mein use nahi karna.

✅ Expected Success Response
{
  "status": "ok",
  "message": "Kiro Gateway is running"
}

❌ Agar Browser Error De

Server stop karein:

Ctrl + C


Phir server ko local host par run karein:

python3 main.py --host 127.0.0.1


Phir browser mein open karein:

http://127.0.0.1:8000

🧩 Final Setup Workflow
🖥 Terminal 1 – Gateway Server
cd ~/kiro-openai-gateway
python3 main.py


⚠️ Important:
Yeh terminal band nahi karna.

🖥 Terminal 2 – Claude Code Router

Naya terminal open karein:

ccr restart
ccr status
ccr code

💬 Test Message
Hi! Can you confirm you're working?

🤖 Model Verification
ccr model

🔄 Agar Setup Kaam Na Kare

Yeh troubleshooting steps try karein:

✔ System Restart Karein
✔ Kiro IDE Login Check Karein
✔ Gateway Server Running Check Karein
✔ Environment Variables Verify Karein
cat .env

📌 Common Mistakes

❌ .env file create na karna
❌ Credentials path galat hona
❌ Kiro IDE login na hona
❌ Server terminal band kar dena
❌ Browser mein 0.0.0.0 open karna

✅ Final Checklist

 .env file configured

 Kiro IDE login verified

 Gateway server running

 Browser test successful

 CCR working


create by Amber

