![image](https://user-images.githubusercontent.com/68781074/221351233-51fb59ca-a56b-4d82-88cc-137be7d38a61.png)


# Provisioning

## Setup terraform

1. first we can setup our VM with terraform, in this task i will create 4 VM for Appserver, gateway, CICD, and monitoring

![Screen Shot 2023-02-25 at 16 32 45](https://user-images.githubusercontent.com/68781074/221365301-97d09d6c-1fe5-4d63-95d6-5a15e1e327ad.png)

![Screen Shot 2023-02-25 at 16 32 49](https://user-images.githubusercontent.com/68781074/221365311-a81c167c-4c48-4a48-bfe2-0697ff199a9f.png)

![Screen Shot 2023-02-25 at 16 32 52](https://user-images.githubusercontent.com/68781074/221365314-c40b2329-9095-47f5-9db8-73d7e5f1a0a3.png)

![Screen Shot 2023-02-25 at 16 32 57](https://user-images.githubusercontent.com/68781074/221365318-b5123333-c4e2-4563-823c-be6bae96991f.png)

2. The next step is to run the Terraform script by executing the "terraform init" command.

![Screen Shot 2023-02-25 at 16 52 24](https://user-images.githubusercontent.com/68781074/221365510-f3bd7f54-1c10-4ced-ba03-d58d87ec7ba5.png)

3. After running "terraform init", we use the "terraform plan" command to see what configurations we have entered in the Terraform script.

![Screen Shot 2023-02-25 at 16 52 37](https://user-images.githubusercontent.com/68781074/221365520-046e9ac2-ecb0-4f3c-964a-f729695a2c55.png)

![Screen Shot 2023-02-25 at 16 52 40](https://user-images.githubusercontent.com/68781074/221365526-dea32190-edb7-4f67-a6f0-38bde3388730.png)

![Screen Shot 2023-02-25 at 16 52 43](https://user-images.githubusercontent.com/68781074/221365531-6b7573a1-3de9-4f52-bda6-5fd637696989.png)

![Screen Shot 2023-02-25 at 16 52 47](https://user-images.githubusercontent.com/68781074/221365545-a256392b-c255-4846-8830-52477c43a5b5.png)

4. Then, to start the process of creating a virtual machine, we can use the "terraform apply" command.

![Screen Shot 2023-02-25 at 22 58 22](https://user-images.githubusercontent.com/68781074/221366841-245fa4a8-41e3-40e2-9613-7331049f577a.png)

![Screen Shot 2023-02-25 at 16 53 02](https://user-images.githubusercontent.com/68781074/221366869-40791fd9-e075-4734-b9b8-9dea77650bd2.png)

![Screen Shot 2023-02-25 at 16 54 55](https://user-images.githubusercontent.com/68781074/221366880-061569d4-56ca-4285-9b3d-dc4379c3c953.png)

![Screen Shot 2023-02-25 at 16 56 11](https://user-images.githubusercontent.com/68781074/221366894-94d3e1a8-0d54-4ef6-9e76-03d491a5aad0.png)

5. Now our virtual machine has been successfully created using Terraform.

![Screen Shot 2023-02-25 at 23 12 09](https://user-images.githubusercontent.com/68781074/221367471-5bc23960-9c3c-4134-bfdf-d4bf9de9abac.png)

![Screen Shot 2023-02-25 at 23 12 15](https://user-images.githubusercontent.com/68781074/221367474-125ed62f-a020-4ebc-a707-5d2d65000fdb.png)

![Screen Shot 2023-02-25 at 23 12 22](https://user-images.githubusercontent.com/68781074/221367478-3d4852a4-994f-4abd-b64e-6732d16690ab.png)

![Screen Shot 2023-02-25 at 23 12 29](https://user-images.githubusercontent.com/68781074/221367482-96a3517d-26f0-4979-be68-683f2e4d006c.png)

## Setup Ansible

1. The first step to set up Ansible is to create the hosts and inventory files.

![Screen Shot 2023-02-25 at 23 48 00](https://user-images.githubusercontent.com/68781074/221369169-c37e3305-c1d5-4a14-af67-5fe56ffe4354.png)

![Screen Shot 2023-02-25 at 23 48 12](https://user-images.githubusercontent.com/68781074/221369173-40c94440-438e-4c18-aec8-881a54a2a684.png)

2. After that, we can create the Ansible playbook file based on our needs for the installation inside the virtual machine. 
 
### Install Docker

1. To install Docker, we need to create the Ansible playbook first.

![Screen Shot 2023-02-26 at 10 08 46](https://user-images.githubusercontent.com/68781074/221390134-8ace1ecf-4dca-4ec3-be8c-71a9370342b0.png)

![Screen Shot 2023-02-26 at 10 08 51](https://user-images.githubusercontent.com/68781074/221390140-54457436-a78f-4f67-8fff-07de925a8cbb.png)

2. then we can use command ansible-playbook "name-file.yml" for start the process.

![Screen Shot 2023-02-26 at 10 15 57](https://user-images.githubusercontent.com/68781074/221390484-75bfe643-db97-4f60-b779-15e38218e816.png)

![Screen Shot 2023-02-26 at 10 18 30](https://user-images.githubusercontent.com/68781074/221390487-c98d32fc-bbd5-4c0e-a436-255135e06be3.png)

3. Docker done installing in all Virtual machine.

![Screen Shot 2023-02-26 at 10 44 10](https://user-images.githubusercontent.com/68781074/221391223-2563dcbb-dba6-4a9b-8dc9-6f771c22fe0c.png)

![Screen Shot 2023-02-26 at 10 45 08](https://user-images.githubusercontent.com/68781074/221391229-8db82016-69f1-4a1e-b1fe-c6c7d28c3c08.png)

![Screen Shot 2023-02-26 at 10 45 35](https://user-images.githubusercontent.com/68781074/221391236-a4bd468f-67c3-45b4-9ce5-44c85aa733c8.png)

![Screen Shot 2023-02-26 at 10 44 42](https://user-images.githubusercontent.com/68781074/221391239-9f88d680-b3cb-46d4-ae82-1aae8e923cdd.png)

### Install Nginx

1. after we install docker, next we will need to install nginx for gateway server. i'll install native nginx not on top docker.

![Screen Shot 2023-02-26 at 10 53 14](https://user-images.githubusercontent.com/68781074/221391427-e557cff7-0f61-486e-aa34-3c79c9413056.png)

![Screen Shot 2023-02-26 at 10 53 25](https://user-images.githubusercontent.com/68781074/221391431-d01d9fc8-989b-433e-9504-e335e69a63a2.png)

2. process installing nginx with ansible.

![Screen Shot 2023-02-26 at 10 55 42](https://user-images.githubusercontent.com/68781074/221391505-3cb10875-8de3-41c2-8bc1-706a9a11343f.png)

3. we can check if docker was install in virtual machine with.
> sudo systemctl status nginx

![Screen Shot 2023-02-26 at 10 57 08](https://user-images.githubusercontent.com/68781074/221391542-3ec62f62-15f1-41df-925b-e92a80d84562.png)

![Screen Shot 2023-02-26 at 11 00 41](https://user-images.githubusercontent.com/68781074/221391618-800a68b8-bba9-44f2-867b-ffad761e38e9.png)


4. The reverse proxy is working well, but an error occurred because we haven't yet executed the application that we want to deploy.

![Screen Shot 2023-02-26 at 10 59 53](https://user-images.githubusercontent.com/68781074/221391653-f8266b17-cd42-4e94-89c7-1f1517fc14f9.png)


### Install Jenkins

1. we'll setup ansible playbook for installing jenkins.

![Screen Shot 2023-02-26 at 12 43 54](https://user-images.githubusercontent.com/68781074/221394451-8b7c5ae8-fc7f-4052-a475-747839c509ad.png)

2. after that we can start ansible-playbok for installing jenkins.

![Screen Shot 2023-02-26 at 12 43 20](https://user-images.githubusercontent.com/68781074/221394441-01b39c62-f42a-4f60-ba8e-20bcacc7e30f.png)

3. jenkins now running on top docker.

![Screen Shot 2023-02-26 at 12 41 42](https://user-images.githubusercontent.com/68781074/221394381-a1a19f2c-10c4-4911-93be-151a0776f5bd.png)


### Install Monitoring App

1. first we'll install a node exporter for appserver, gateway and monitoring server

![Screen Shot 2023-02-26 at 15 13 14](https://user-images.githubusercontent.com/68781074/221399560-a5449836-7794-424e-a727-87b1a0b92505.png)

![Screen Shot 2023-02-26 at 15 16 11](https://user-images.githubusercontent.com/68781074/221399659-c4275f38-8d34-4de6-9a95-88f116a68cb6.png)

2. After installing the node exporter, we can check it by accessing the port that we previously configured.

![Screen Shot 2023-02-26 at 15 21 17](https://user-images.githubusercontent.com/68781074/221399889-0a59765d-53a1-456a-85e4-bbf6c4a22ef8.png)

![Screen Shot 2023-02-26 at 15 21 29](https://user-images.githubusercontent.com/68781074/221399893-c76b3686-4000-415c-a48a-696eeac7d915.png)

![Screen Shot 2023-02-26 at 15 21 42](https://user-images.githubusercontent.com/68781074/221399900-30cf6bdc-03f3-4268-8e82-1e2283bee0b7.png)

3. After that we can install prometheus and grafana, but before that i'll create config for prometheus.

![Screen Shot 2023-02-26 at 15 23 30](https://user-images.githubusercontent.com/68781074/221399980-935ac48c-0f26-4949-9b9e-ec6d218cdf68.png)

4. and for Ansible-playbook for installing prometheus and grafana like this.

![Screen Shot 2023-02-26 at 15 22 51](https://user-images.githubusercontent.com/68781074/221400009-2dfeccfa-975a-4b09-b929-e33ccaf6bc33.png)

5. installing process for prometheus and grafana.

![Screen Shot 2023-02-26 at 15 27 08](https://user-images.githubusercontent.com/68781074/221400143-1a3a4b7b-b041-41f7-aeb3-63fd6995cc39.png)

6. We can access it by using the port that we previously configured.

![Screen Shot 2023-02-26 at 15 28 49](https://user-images.githubusercontent.com/68781074/221400218-62d69c19-b3f1-4498-ad3a-262e051fd0eb.png)

![Screen Shot 2023-02-26 at 15 29 00](https://user-images.githubusercontent.com/68781074/221400227-2365a381-5a40-4b2c-b4a6-fe5cdbc3fdca.png)






