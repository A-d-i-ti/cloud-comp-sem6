fist we create topic :
aws sns--> topic ---> create topic 
<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/698efe7f-c75b-4e40-8e2f-b85ff5c45473" />
now we create subscription :
<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/c6c2164c-30a6-498c-a2c0-12c8bf7f5d07" />
now we go to AWS CLOUDWATCH --->METRICS--> ALL METRICS--->EC2--> CPU UTILISATION 
<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/b1d04cbb-8bf3-4a08-b10e-d12143233f1b" />
and the alarm is created :
<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/59e73b7e-84a2-4329-9a65-72570ea8e61e" />
now we will increse the cpu utilization to check :
connect the instance and run the following commands -
sudo apt update -y
sudo apt install stress -y
stress --cpu 2 --timeout 300
