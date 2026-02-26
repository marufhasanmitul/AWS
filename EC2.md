🟢 Step 2: EC2 Instance Create (Step-by-Step)
1️⃣ AWS Console → EC2 → Launch Instance
2️⃣ Name দাও

যেমন: my-api-server

3️⃣ AMI নির্বাচন করো

👉 Ubuntu Server 22.04 (Beginner friendly)

4️⃣ Instance Type

👉 t2.micro বা t3.micro (Free Tier)

5️⃣ Key Pair তৈরি করো

👉 RSA
👉 .pem file download করো (এটা খুব গুরুত্বপূর্ণ)

6️⃣ Network Settings

Security Group এ:

Type	Port
SSH	22
HTTP	80
HTTPS	443

👉 SSH source = My IP (security জন্য)

7️⃣ Launch Instance 🚀
🟢 Step 3: EC2 তে SSH দিয়ে Connect

Windows হলে:

Git Bash বা PowerShell ব্যবহার করো।

chmod 400 mykey.pem
ssh -i mykey.pem ubuntu@your-public-ip

Connected হলে তুমি এখন AWS server এ আছো 🎉

🟢 Step 2: Server Update

sudo apt update
sudo apt upgrade -y



🟢 Step 3: Apache + PHP Install
sudo apt install apache2 -y
sudo apt install php libapache2-mod-php php-mysql -y







🎯 তোমার Learning Goal (7 Days Plan)

Day 1 → EC2 launch
Day 2 → SSH + Linux basic
Day 3 → Nginx setup
Day 4 → Node API deploy
Day 5 → Domain connect
Day 6 → SSL setup
Day 7 → Restart automation (PM2)

🔥 Production Level এ যেতে চাইলে

শিখতে হবে:

Amazon VPC

Amazon RDS

Docker

তুমি এখন কোথায় আছো বলো:

1️⃣ Account নেই
2️⃣ Account আছে কিন্তু EC2 launch করিনি
3️⃣ EC2 launch করেছি কিন্তু connect পারছি না
4️⃣ Deploy করতে চাই

বললেই আমি তোমাকে direct guide করবো 💪

