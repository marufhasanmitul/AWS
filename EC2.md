দারুন 🔥 তুমি যদি EC2 শিখতে চাও, তাহলে আমরা একদম practical ভাবে শিখবো।

☁️ Amazon EC2 শেখার Complete Guide (Beginner Friendly)
🟢 Step 1: AWS Account তৈরি

👉 আগে Amazon Web Services এ Free Tier account তৈরি করো
👉 Billing alert চালু করো (খুব গুরুত্বপূর্ণ)

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

🟢 Step 4: Basic Server Setup
sudo apt update
sudo apt upgrade -y
🟢 Step 5: Nginx Install (Test করার জন্য)
sudo apt install nginx -y

Browser এ public IP দাও →
Nginx default page দেখাবে ✅

🟢 Step 6: Node.js API Deploy (Example)
sudo apt install nodejs npm -y

Simple test server:

nano server.js

Paste:

const http = require('http');

http.createServer((req, res) => {
  res.write("Hello from EC2 🚀");
  res.end();
}).listen(3000);

Run:

node server.js

Browser এ:

http://your-public-ip:3000
🧠 Important Concept বুঝতে হবে
🔹 Public IP

Internet থেকে access করার জন্য।

🔹 Security Group

Firewall (port control করে)

🔹 Elastic IP

Static IP (production এর জন্য ভালো)

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

USing Php

দারুন 🔥 তাহলে আমরা PHP দিয়ে EC2 তে backend deploy করবো step-by-step।

☁️ Amazon EC2 + PHP Setup Guide
🟢 Step 1: EC2 Launch

Ubuntu 22.04

Instance type: t2.micro / t3.micro

Port open করো:

22 (SSH)

80 (HTTP)

443 (HTTPS)

SSH দিয়ে connect করো:

ssh -i yourkey.pem ubuntu@your-public-ip
🟢 Step 2: Server Update
sudo apt update
sudo apt upgrade -y
🟢 Step 3: Apache + PHP Install
sudo apt install apache2 -y
sudo apt install php libapache2-mod-php php-mysql -y

Check:

php -v
🟢 Step 4: Apache Test

Browser এ দাও:

http://your-public-ip

Apache default page দেখাবে ✅

🟢 Step 5: PHP Test File বানাও
sudo nano /var/www/html/info.php

Paste:

<?php
phpinfo();
?>

Browser এ:

http://your-public-ip/info.php

PHP info page দেখালে সব ঠিক আছে 🎉

🟢 Step 6: Simple API Example (Flutter এর জন্য)
sudo nano /var/www/html/api.php

Paste:

<?php
header("Content-Type: application/json");

$data = [
    "status" => true,
    "message" => "Hello from EC2 PHP 🚀"
];

echo json_encode($data);
?>

Browser এ:

http://your-public-ip/api.php

JSON response দেখাবে ✅

🟢 Step 7: MySQL Database Setup

Local install করতে পারো:

sudo apt install mysql-server -y

অথবা production এর জন্য ভালো:

👉 Amazon RDS

🟢 Step 8: Permission Fix (Important)
sudo chown -R www-data:www-data /var/www/html
sudo chmod -R 755 /var/www/html
🎯 Production Ready করতে চাইলে

পরের ধাপে শিখতে হবে:

SSL (HTTPS)

Domain connect

Firewall secure করা

PM2 দরকার নেই (PHP Apache handle করে)

Database private রাখা (VPC ব্যবহার)

🧠 Final Architecture (Recommended)
Flutter App
     ↓
EC2 (Apache + PHP)
     ↓
RDS (MySQL)

তুমি এখন বলো:

1️⃣ শুধু local MySQL ব্যবহার করবো
2️⃣ RDS দিয়ে production setup চাই
3️⃣ Domain + SSL setup করতে চাই
4️⃣ Full production secure architecture চাই

আমি তোমাকে next level এ নিয়ে যাব 💪
