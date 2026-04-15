
<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/24eede67-e3f1-4d29-a135-9367fdc13cca" />
connect it :
<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/ea29d5e8-ac3f-4dc6-bcf0-2fcded2a6eb4" />


### Now run the following commands :

sudo apt update && sudo apt upgrade -y

sudo useradd -s /bin/bash -d /opt/stack -m stack

echo "stack ALL=(ALL) NOPASSWD: ALL" | sudo tee /etc/sudoers.d/stack

sudo su - stack

git clone https://opendev.org/openstack/devstack

devstack is installed , now we navigate to devstack folder:

cd devstack

Then create the configuration file:

cat > local.conf << EOF
[[local|localrc]]
ADMIN_PASSWORD=secret
DATABASE_PASSWORD=secret
RABBIT_PASSWORD=secret
SERVICE_PASSWORD=secret
EOF

Verify the file was created:
cat local.conf

Step 5 — Start the Installation
./stack.sh
if it shows error use this : 

FORCE=yes ./stack.sh

it starts installation :
<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/bf96cfed-5569-4309-9d29-115a72ca652f" />
Step 6 — Check OpenStack is running

source openrc admin admin
openstack service list

Step 7 — Check available images

openstack image list

Step 8 — Launch your first instance

openstack server create --flavor m1.tiny --image cirros-0.6.2-x86_64-disk --network private --name my-first-vm

Step 9 — Check instance status

openstack server list

Step 10 — Access Horizon Dashboard (GUI)

http://YOUR-EC2-PUBLIC-IP/dashboard

**Login with:**
Username: admin
Password: secret
