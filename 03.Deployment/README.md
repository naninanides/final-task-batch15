![image](https://user-images.githubusercontent.com/68781074/221351296-db8c84d6-7da4-4924-859e-66987acbcf60.png)

# Deployment

## Application

### Build Images Frontend & Backend For Production

1. Create Dockerfile for frontend 

![Screen Shot 2023-02-27 at 23 45 40](https://user-images.githubusercontent.com/68781074/221626176-3a01b29b-f506-4ddb-a24a-bbd450455e53.png)

2. build dockerfile for just to docker images frontend

![Screen Shot 2023-02-27 at 22 03 35](https://user-images.githubusercontent.com/68781074/221626910-997ca31b-7b67-4967-ae28-21c89c951111.png)

3. Create Images for backend

![Screen Shot 2023-02-27 at 22 19 13](https://user-images.githubusercontent.com/68781074/221627298-97a7533a-8905-4a17-942a-f57a2feca173.png)

4. Processing build for docker images

![Screen Shot 2023-02-27 at 22 20 14](https://user-images.githubusercontent.com/68781074/221627421-afeebb85-aa9b-43ec-9991-6ad7732766ca.png)

5. Result for docker images frontend & backend

![Screen Shot 2023-02-27 at 23 52 13](https://user-images.githubusercontent.com/68781074/221627816-6b761caa-ff49-4cb1-9385-a7e15382aa10.png)

### Make Docker compose for running the images

1. create docker-compose.yml for frontend

![Screen Shot 2023-02-27 at 23 53 46](https://user-images.githubusercontent.com/68781074/221628258-38b7bd51-96b5-4369-9691-9e65c33a5f35.png)

2. create docker-compose.yml for backend

![Screen Shot 2023-02-27 at 23 55 57](https://user-images.githubusercontent.com/68781074/221628760-75b688ba-176e-4ae7-902e-a9a4fb628fbb.png)

3. create docker-compose.yml for database

![Screen Shot 2023-02-27 at 23 56 36](https://user-images.githubusercontent.com/68781074/221628863-33d7eaf2-0391-477f-ab2d-0682a168764c.png)

### Running Docker Container with image was build before

1. first we could run database

![Screen Shot 2023-02-28 at 0 09 19](https://user-images.githubusercontent.com/68781074/221631738-6b41da97-3c76-4e1b-b0ed-b58ef0da500d.png)

2. and then we can run docker container frontend & backend

![Screen Shot 2023-02-28 at 0 11 11](https://user-images.githubusercontent.com/68781074/221632127-f253e755-b5bb-466e-ba14-9e1f987a9b20.png)

3. we can check if docker container is running with command
> docker ps -a

![Screen Shot 2023-02-28 at 0 11 54](https://user-images.githubusercontent.com/68781074/221632275-9b703238-0eba-4ea7-b9a5-038fafd71805.png)

4. now we can access application we just deploy from docker

![Screen Shot 2023-02-28 at 0 12 40](https://user-images.githubusercontent.com/68781074/221632461-1a7b07e9-c4b2-41e8-9aad-b45cb287e0aa.png)

![Screen Shot 2023-02-27 at 21 33 39](https://user-images.githubusercontent.com/68781074/221632524-6c1ba724-b5b4-45f7-935f-d85b6494ef1d.png)

![Screen Shot 2023-02-27 at 21 34 16](https://user-images.githubusercontent.com/68781074/221632556-4d5af302-e8aa-45e5-a900-3389edb6aac0.png)


## CICD

### Setup Jenkins

1. pertama kita masuk terlebih dahulu ke dalam jenkin melalui port yang sudah kita atur

![Screen Shot 2023-02-28 at 0 21 35](https://user-images.githubusercontent.com/68781074/221641242-7381a07d-5452-4c85-98ae-bd06b30acea5.png)

2. untuk login kita bisa mengecek password admin lewat logs didalam docker container

![Screen Shot 2023-02-28 at 0 22 42](https://user-images.githubusercontent.com/68781074/221641387-5cc28f4d-b385-4ba8-b68f-6c88c3c06b6b.png)

3. untuk halaman setelah login kita bisa memilih custom plugin untuk penginstallan pertama dan yang akan kita tambahkan adalah plugin sshagent

![Screen Shot 2023-02-28 at 0 23 02](https://user-images.githubusercontent.com/68781074/221641992-4f6233ce-5952-4667-b021-7d9d7c740824.png)

![Screen Shot 2023-02-28 at 0 23 55](https://user-images.githubusercontent.com/68781074/221642063-1352dcde-9dd4-4d0f-b57d-ad9a6b060e7c.png)

4. Proses installasi Jenkins

![Screen Shot 2023-02-28 at 0 25 13](https://user-images.githubusercontent.com/68781074/221643224-3976dcad-993b-48fc-b14a-53ca7e9b6d90.png)

5. Lalu kita setup untuk create admin user

![Screen Shot 2023-02-28 at 0 29 10](https://user-images.githubusercontent.com/68781074/221644060-e866bacc-b31f-418b-8217-2929d4962d9c.png)

![Screen Shot 2023-02-28 at 0 29 37](https://user-images.githubusercontent.com/68781074/221644105-aad47e82-6057-4247-9208-2ba3433799fa.png)

6. lalu kita masukan domain untuk jenkins

![Screen Shot 2023-02-28 at 0 29 56](https://user-images.githubusercontent.com/68781074/221644295-9c49f210-f115-4a75-b82b-06c03eb7029c.png)

7. kurang lebih jika proses installasi selesai maka akan seperti ini

![image](https://user-images.githubusercontent.com/68781074/218250548-fd9a4bc3-fa10-44da-ba6a-aa57e92c0955.png)

8. dashboard jenkin seperti ini

![Screen Shot 2023-02-28 at 0 30 26](https://user-images.githubusercontent.com/68781074/221644508-2d658d50-9a87-45b6-8e29-8ef7e80594df.png)



















