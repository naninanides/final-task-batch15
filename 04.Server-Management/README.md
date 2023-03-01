![image](https://user-images.githubusercontent.com/68781074/221351317-ffdae604-edfa-4ec8-aed2-24bf98b15c8f.png)

# Server Management

## Server login with SSH

1. I have prepared an SSH key to be inserted into the VM that we need during the provisioning process in Terraform.

![Screen Shot 2023-03-01 at 1 57 10](https://user-images.githubusercontent.com/68781074/222067588-6d567408-fe99-4de3-84e6-883436c1124d.png)

![Screen Shot 2023-03-01 at 1 57 15](https://user-images.githubusercontent.com/68781074/222067609-5cb10125-1865-4315-adc9-46e0a990a5d4.png)

![Screen Shot 2023-03-01 at 1 57 19](https://user-images.githubusercontent.com/68781074/222067623-4318aeea-c582-4a51-9cb6-accfccde2854.png)

2. Each server has received the SSH key that we entered during provisioning.

![Screen Shot 2023-03-01 at 14 05 25](https://user-images.githubusercontent.com/68781074/222068926-780fabc1-0d4c-43cf-80c4-ceb402b24aac.png)

![Screen Shot 2023-03-01 at 14 05 46](https://user-images.githubusercontent.com/68781074/222068946-c640fb87-9d05-4cdc-91e1-b2aec0df80a9.png)

![Screen Shot 2023-03-01 at 14 06 35](https://user-images.githubusercontent.com/68781074/222068969-7a86848f-6c58-4009-a5cb-f8ed3ec59948.png)

![Screen Shot 2023-03-01 at 14 07 10](https://user-images.githubusercontent.com/68781074/222068990-705b732d-d76d-40c5-8555-c5b088b73330.png)

3. If you want to login but did not insert the local SSH key into the server, it will look like this.

![image](https://user-images.githubusercontent.com/68781074/221952708-efab048a-59db-46f5-b754-9c7c340f722b.png)

## Password Login Disable

1. For setup, I use an ansible-playbook to disable password login on each server.

![Screen Shot 2023-03-01 at 14 16 15](https://user-images.githubusercontent.com/68781074/222069884-ec817a8e-0907-4eeb-aeab-14cf8bf6082e.png)

2. Password Authentication has been disabled.

![Screen Shot 2023-03-01 at 1 53 54](https://user-images.githubusercontent.com/68781074/222069528-48c4e3d0-e297-447a-9de5-8ac4071027ca.png)

![Screen Shot 2023-03-01 at 1 54 13](https://user-images.githubusercontent.com/68781074/222069620-9688d3c4-4ecd-4037-af78-99356f5146dd.png)

![Screen Shot 2023-03-01 at 1 55 02](https://user-images.githubusercontent.com/68781074/222069635-1a29ba36-3778-48de-bbf5-c25f3c009d11.png)

![Screen Shot 2023-03-01 at 1 55 48](https://user-images.githubusercontent.com/68781074/222069656-0980c5f2-eb11-4a2e-95c0-b453968c1d51.png)


## Add ssh config

1. I have created an SSH config for local and also for the VM gateway where we can log in using a private IP on the VM gateway.

![Screen Shot 2023-03-01 at 14 17 51](https://user-images.githubusercontent.com/68781074/222070200-d1b6d1f2-865c-44a1-ac5b-cc0a5235e0d9.png)

![Screen Shot 2023-03-01 at 14 18 11](https://user-images.githubusercontent.com/68781074/222070255-52c02a3c-c6db-4da9-b6c3-84d49e68dc8b.png)

2. I only use one SSH key from local. Here, I send one SSH key to all VMs and use it for login, CICD, and also for repository to Github.

![Screen Shot 2023-03-01 at 14 23 12](https://user-images.githubusercontent.com/68781074/222071241-7d9454c4-a2ce-4127-8546-52c446a93876.png)

![Screen Shot 2023-03-01 at 14 30 24](https://user-images.githubusercontent.com/68781074/222072766-11fc2cd9-220a-4381-a13a-ea732baeeb32.png)

## Add Firewall for only Port used allowed

1. I have created an ansible-playbook to add firewall on each server and enter the ports we need.

![Screen Shot 2023-03-01 at 1 45 54](https://user-images.githubusercontent.com/68781074/222072893-e369a1c4-3252-4731-a10c-a310ed5060ee.png)

2. Running the ansible-playbook for UFW enable.

![Screen Shot 2023-03-01 at 14 44 21](https://user-images.githubusercontent.com/68781074/222076312-3375ed86-e6af-40e4-9f63-bb2bcab86032.png)

![Screen Shot 2023-03-01 at 14 46 54](https://user-images.githubusercontent.com/68781074/222076332-96ed8f10-3ed5-4bbe-9633-7ccb19601f06.png)

3. The firewall is now active on each virtual machine.

![Screen Shot 2023-03-01 at 14 48 20](https://user-images.githubusercontent.com/68781074/222076546-4f7abc0d-81af-4a3d-92f2-ea9664fdc893.png)

![Screen Shot 2023-03-01 at 14 48 40](https://user-images.githubusercontent.com/68781074/222076611-96f2f5dd-f820-457a-a445-d6a9383581d9.png)

![Screen Shot 2023-03-01 at 14 48 56](https://user-images.githubusercontent.com/68781074/222076667-c45aeae0-4b06-49ec-8748-a14c52e15750.png)

![Screen Shot 2023-03-01 at 14 49 10](https://user-images.githubusercontent.com/68781074/222076724-8e094e61-4464-49ae-8e44-28394620a433.png)


