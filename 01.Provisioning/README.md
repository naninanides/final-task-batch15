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










