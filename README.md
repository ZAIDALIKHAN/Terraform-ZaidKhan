# Terraform-Zaid

Networking
CIDR:
10.0.0.0/24 -- First three places are locked, and fourth place can only be changed – 256 ip’s
10.0.0.0/16 – First two places are locked,third and fourth place can be changed– 65536 ip’s
10.0.0.0/8 – First one places is locked, second, third and fourth place can be changed-16,777,216 ip’s

SUBNET – CREATION – issues i faced:
🌐 Given:
Your VPC CIDR = 10.0.0.0/24
That means:
Total IPs = 256 (from 10.0.0.0 → 10.0.0.255)
🎯 Goal:
You want two subnets that don’t overlap within this /24 VPC.
So you must split the /24 range into two smaller CIDR blocks.
🧮 Step-by-step subnetting
Each time you increase the prefix length by 1 (e.g., /24 → /25),
you split the range into 2 equal subnets.
Split /24 into /25 subnets:
Subnet CIDR Range IP Range Total IPs
Subnet 1 10.0.0.0/25 10.0.0.0 → 10.0.0.127 128 IPs
Subnet 2 10.0.0.128/25 10.0.0.128 → 10.0.0.255 128 IPs
✅ These two subnets do not overlap and fit perfectly inside 10.0.0.0/24.
Another Example below:10.0.0.0/16 split this for subnets: 
(10.0.0.0/17) covers 10.0.0.0 → 10.0.127.255. and (10.0.128.0/17) covers 10.0.128.0 → 10.0.255.255. These two blocks are adjacent and do not overlap.
