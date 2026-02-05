I have started a new jurney with Wazuh, because I just investigated some SIEM and XDR stuff and find this tool really interesting. Wazuh its a powerfull tool that monitores infrastructure.

I´m going to use AWS too because I want apply it an scalable structures and in general everyone are hosting their websites or web apps on cloud. So lets get started.

First of all we need to create an EC2 instance. I´m going to try t3.small (bc its free tier) instance but they recommend at least t3.medium, also wee need to configure ports the right way:


224,TCP/UDP,Comunication with agents (logs) 
1515 and 1514 Authentication for new agents
55000,TCP, Wazuh API
Https
22 ssh

After the instalation using this command line, I ran out of resources so yeah, its better listening to recommendations sometimes. 
curl -sO https://packages.wazuh.com/4.7/wazuh-install.sh && sudo bash wazuh-install.sh -a

Now we connect to public ip thru https and we can see login panel. We need to introduce the password from our console:


<img width="518" height="429" alt="image" src="https://github.com/user-attachments/assets/cd4da8d5-9426-446d-8b2e-ebc171ef685d" />


<img width="1899" height="774" alt="image" src="https://github.com/user-attachments/assets/168cc1fd-e5a4-4310-9a67-e150b3aa59ff" />

Deploy new agent

So for now we need to create another EC2 Instance where we can practice with our agent.
In wazuh interface, we choose "Create new agent" and follow instructions (like installing agent, adding public ip, etc)
After completing evetithing, we need to add our wazuh ip to agent-auth.

sudo /var/ossec/bin/agent-auth -m (PUBLIC WAZUH IP)

We have everithing mounted, so lets simulate some allerts. Let´s try an ssh connection with false user, after trying a bit, we can find that our agent just captured "auth fail" log.

 <img width="1903" height="793" alt="image" src="https://github.com/user-attachments/assets/9b0db95c-d50e-495e-98cb-821a6aa9ee93" />

We can see that there is all the information of our attemps.

Now lets try integrity monitoring test, lets modify hosts file.
After modifiyng the file, wazuh registered a new event

<img width="1902" height="720" alt="image" src="https://github.com/user-attachments/assets/3ed9085c-4f03-41ba-9027-d48dbde251f9" />

<img width="1908" height="903" alt="image" src="https://github.com/user-attachments/assets/02cecd84-af79-4c5b-8212-cb99a83114fc" />



