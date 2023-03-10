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

3. create docker-compose.yml for database we use PosgresSQL for database

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

### Build docker images for production

1. First, we create a Dockerfile for production, but here I am not using 'npm start'.

![Screen Shot 2023-02-28 at 23 29 09](https://user-images.githubusercontent.com/68781074/221916205-3d9ed751-4a32-4df2-9191-9028ede47629.png)

```
FROM node:16-alpine3.11 as staging
WORKDIR /home/app
COPY . .
RUN npm install
RUN npm run build

FROM node:16-alpine3.11
WORKDIR /home/app
COPY --from=staging /home/app /home/app
RUN npm install -g server
EXPOSE 3000
CMD ["npx","serve","build","-l","3000"]
```
![Screen Shot 2023-02-28 at 23 34 29](https://user-images.githubusercontent.com/68781074/221917588-47c1da95-8070-4029-9a62-b9d19c101a94.png)

```
FROM golang:1.18-alpine as distroless
WORKDIR /home/app
COPY . .
RUN CGO_ENABLED=0  go build

#distroless
FROM gcr.io/distroless/cc-debian11
WORKDIR /home/app
COPY --from=distroless /home/app /home/app
CMD ["/home/app/dumbmerch"]
```

2. Then, we first change the Git from staging to production.

![Screen Shot 2023-02-28 at 23 33 47](https://user-images.githubusercontent.com/68781074/221917352-ab3bd94a-add4-43d0-b01b-7040f85e5af3.png)

3. After that, we build the production image.

![Screen Shot 2023-02-28 at 23 31 45](https://user-images.githubusercontent.com/68781074/221918042-7ba8dddf-bc87-45ed-9ed2-e0e6051835a2.png)

![Screen Shot 2023-02-28 at 23 37 07](https://user-images.githubusercontent.com/68781074/221918236-695881e1-5df7-4987-ac45-64d20718394e.png)

4. The image for production is now complete. For the database, I am using distroless images for production.

![Screen Shot 2023-02-28 at 23 38 46](https://user-images.githubusercontent.com/68781074/221918618-c0507cb1-a1c2-4b09-97ec-c8b7f4e1c72f.png)

5. Before running container we create docker-compose.yml for frontend and backend.

![Screen Shot 2023-02-28 at 23 59 59](https://user-images.githubusercontent.com/68781074/221924108-e82baca1-cf43-4734-b668-9014bf3d8dd7.png)

![Screen Shot 2023-03-01 at 0 00 54](https://user-images.githubusercontent.com/68781074/221924309-ffefc073-0c80-4e2c-8fa4-331e5011a493.png)

6.now we can running the container.

![Screen Shot 2023-03-01 at 0 04 24](https://user-images.githubusercontent.com/68781074/221925166-39580d10-f1fb-4408-9164-51f34dc3c800.png)

![Screen Shot 2023-03-01 at 0 04 39](https://user-images.githubusercontent.com/68781074/221925397-329cb10c-9592-4ad6-b135-42cfa0f49632.png)

![Screen Shot 2023-03-01 at 0 05 02](https://user-images.githubusercontent.com/68781074/221925412-c03cbaa9-f175-43ce-8fa7-bb6c14a88238.png)

![Screen Shot 2023-03-01 at 0 05 17](https://user-images.githubusercontent.com/68781074/221925452-9ba385f4-7600-45dc-ada3-e50f7ed1420c.png)

## CICD

### Install Jenkins

1. First, we need to enter Jenkins by accessing the port that we have configured.

![Screen Shot 2023-02-28 at 0 21 35](https://user-images.githubusercontent.com/68781074/221641242-7381a07d-5452-4c85-98ae-bd06b30acea5.png)

2. To log in, we can check the admin password through the logs inside the Docker container.

![Screen Shot 2023-02-28 at 0 22 42](https://user-images.githubusercontent.com/68781074/221641387-5cc28f4d-b385-4ba8-b68f-6c88c3c06b6b.png)

3. For the page after login, we can choose a custom plugin for the initial installation, and the plugin we will add is sshagent.

![Screen Shot 2023-02-28 at 0 23 02](https://user-images.githubusercontent.com/68781074/221641992-4f6233ce-5952-4667-b021-7d9d7c740824.png)

![Screen Shot 2023-02-28 at 0 23 55](https://user-images.githubusercontent.com/68781074/221642063-1352dcde-9dd4-4d0f-b57d-ad9a6b060e7c.png)

4. The Jenkins installation process involves setting up an admin user and entering the domain for Jenkins.

![Screen Shot 2023-02-28 at 0 25 13](https://user-images.githubusercontent.com/68781074/221643224-3976dcad-993b-48fc-b14a-53ca7e9b6d90.png)

![Screen Shot 2023-02-28 at 0 29 10](https://user-images.githubusercontent.com/68781074/221644060-e866bacc-b31f-418b-8217-2929d4962d9c.png)

![Screen Shot 2023-02-28 at 0 29 37](https://user-images.githubusercontent.com/68781074/221644105-aad47e82-6057-4247-9208-2ba3433799fa.png)

![Screen Shot 2023-02-28 at 0 29 56](https://user-images.githubusercontent.com/68781074/221644295-9c49f210-f115-4a75-b82b-06c03eb7029c.png)

5. If the installation process is complete, it should look like this.

![image](https://user-images.githubusercontent.com/68781074/218250548-fd9a4bc3-fa10-44da-ba6a-aa57e92c0955.png)

6. The Jenkins dashboard will appear as shown.

![Screen Shot 2023-02-28 at 0 30 26](https://user-images.githubusercontent.com/68781074/221644508-2d658d50-9a87-45b6-8e29-8ef7e80594df.png)

### Setup Jenkins

1. The first step we will take is to set up the SSH credentials for Jenkins, and we can generate the SSH key first.

![Screen Shot 2023-02-28 at 0 58 34](https://user-images.githubusercontent.com/68781074/221645296-da8445e5-c092-428b-b508-2f52122733c7.png)

2. We will take the key from the ssh-keygen that we generated earlier.

![Screen Shot 2023-02-28 at 0 59 58](https://user-images.githubusercontent.com/68781074/221645634-3d9f9c22-46db-45a8-8cfe-76292a65e37b.png)

3. Then, on the dashboard, click 'Manage Jenkins', select 'Manage Credentials', and add the credentials for Jenkins.

![Screen Shot 2023-02-28 at 1 00 36](https://user-images.githubusercontent.com/68781074/221646268-bd2db535-e702-4de1-96ff-7a033258ce1e.png)

![Screen Shot 2023-02-28 at 1 00 51](https://user-images.githubusercontent.com/68781074/221648858-0c710341-a277-47ac-9ba3-e2c7db1a331d.png)

![Screen Shot 2023-02-28 at 1 00 54](https://user-images.githubusercontent.com/68781074/221648884-aea24cff-2c2b-4698-b2cf-6842bde539e1.png)

![Screen Shot 2023-02-28 at 1 01 26](https://user-images.githubusercontent.com/68781074/221648906-bdbf225b-d9b3-4725-b2db-53536864cbfb.png)

4. Next, we enter the key that we generated earlier.

![Screen Shot 2023-02-28 at 1 17 58](https://user-images.githubusercontent.com/68781074/221649378-346b4102-2317-44bb-adf9-4f7440a62046.png)

![Screen Shot 2023-02-28 at 1 18 00](https://user-images.githubusercontent.com/68781074/221649397-358492b4-9816-48d9-90be-31828b79bfaa.png)

5. We have now added the credentials.

![Screen Shot 2023-02-28 at 1 19 00](https://user-images.githubusercontent.com/68781074/221649718-90064ba4-8dcb-4b89-9d94-e8c5baa5d341.png)

6. After that, we insert the key.pub into Github.

![Screen Shot 2023-02-28 at 1 20 36](https://user-images.githubusercontent.com/68781074/221650099-97a8f5b3-0e42-462f-91c5-3ef819fa2166.png)

![Screen Shot 2023-02-28 at 1 21 12](https://user-images.githubusercontent.com/68781074/221650125-4b62e9de-9836-4d08-8726-49fce4ec0b3b.png)

![Screen Shot 2023-02-28 at 1 21 33](https://user-images.githubusercontent.com/68781074/221650162-36a4801a-4c42-4458-b1da-2ed264e2b361.png)


### Create Pipeline

1. To create a pipeline, we can click on 'New Item' and select the type of pipeline that we want.

![Screen Shot 2023-02-28 at 1 29 10](https://user-images.githubusercontent.com/68781074/221651656-aa5ab7b2-1efe-4465-9645-eefe0cf72215.png)

![Screen Shot 2023-02-28 at 1 29 07](https://user-images.githubusercontent.com/68781074/221651745-ba30046a-aae7-4238-8e12-3dc6963ab398.png)

2. To configure it, we can click on 'GitHub hook trigger' to integrate it with GitHub.

![Screen Shot 2023-02-28 at 1 33 28](https://user-images.githubusercontent.com/68781074/221652472-d0fe3e23-7e90-4b01-bd90-4ee2d103b76f.png)

3. Then, the Pipeline configuration will look something like this.

![Screen Shot 2023-02-28 at 1 37 49](https://user-images.githubusercontent.com/68781074/221653760-e5e6a4c6-d19e-4f95-826d-dea2de9ffb51.png)

![Screen Shot 2023-02-28 at 1 41 19](https://user-images.githubusercontent.com/68781074/221653959-0ea4a00a-f772-4aa8-986d-f2cb7c095a3e.png)

![Screen Shot 2023-02-28 at 1 40 03](https://user-images.githubusercontent.com/68781074/221653778-f18b833c-903e-4e7e-835c-28b36c2872d0.png)

4. After that, we need to prepare the Jenkinsfile inside Git.

![Screen Shot 2023-03-01 at 1 34 38](https://user-images.githubusercontent.com/68781074/221947347-1caaf70d-bf10-40ff-a804-8e23e1549b33.png)

```
pipeline {
    agent any

    environment{
        def branch = "Production"
        def nama_repository = "origin"
        def directory = "~/dumbmerch-fe"
        def credential = 'bhq'
        def server = 'bhq@103.37.124.141'
        def docker_image = 'naninanides/dumbmerch-fe-production'
        def nama_container = 'backend'
    }

    options {
        disableConcurrentBuilds()
        timeout(time: 30, unit: 'MINUTES')
    }

    stages {

        stage('Notif nih BOS') {
            steps {
                discordSend description: '', footer: '', image: '', link: '', result: '', scmWebUrl: '', thumbnail: '', title: 'Mulai jalan nih ', webhookURL: 'https://discord.com/api/webhooks/1073903280893202502/FwVTY2tdIp9qekgj3qLn-ta-PuBst9FRg3lqmqFyu0yG_3dYFs5mB7SRCVBFiQACf4ua'
            }
        }

        stage('pull repository dari github ') {
            steps {
                sshagent([credential]){
                    sh"""
                    ssh -o StrictHostKeyChecking=no ${server} << EOF
                    cd ${directory}
                    git pull ${nama_repository} ${branch}
                    exit
                    EOF"""
                }
            }
        }

        stage('docker compose down') {
            steps {
                sshagent([credential]){
                    sh"""
                    ssh -o StrictHostKeyChecking=no ${server} << EOF
                    cd ${directory}
                    docker compose down
                    exit
                    EOF"""
                }
            }
        }

        stage('build image frontend') {
            steps {
                sshagent([credential]){
                    sh"""ssh -o StrictHostKeyChecking=no ${server} << EOF
                    cd ${directory}
                    docker build -t ${docker_image}:latest .
                    exit
                    EOF"""
                }
            }
        }

        stage('jalankan docker compose') {
            steps {
                sshagent([credential]){
                    sh"""ssh -o StrictHostKeyChecking=no ${server} << EOF
                    cd ${directory}
                    docker compose up -d
                    exit
                    EOF
                    """
                }
            }
        }
        
        stage('push image ke dockerhub') {
            steps {
                sshagent([credential]){
                    sh"""
                    ssh -o StrictHostKeyChecking=no ${server} << EOF
                    cd ${directory}
                    docker image push ${docker_image}:latest
                    exit
                    EOF"""
                }
            }
        }
    }
    post {

        aborted {
            discordSend description: '', footer: '', image: '', link: '', result: '', scmWebUrl: '', thumbnail: '', title: 'Kok di cancel sih???', webhookURL: 'https://discord.com/api/webhooks/1073903280893202502/FwVTY2tdIp9qekgj3qLn-ta-PuBst9FRg3lqmqFyu0yG_3dYFs5mB7SRCVBFiQACf4ua'
        }
        failure {
            discordSend description: '', footer: '', image: 'https://giphy.com/gifs/theoffice-y9gcCOXpNX8UfZrp0X', link: '', result: '', scmWebUrl: '', thumbnail: '', title: 'Yah gagal', webhookURL: 'https://discord.com/api/webhooks/1073903280893202502/FwVTY2tdIp9qekgj3qLn-ta-PuBst9FRg3lqmqFyu0yG_3dYFs5mB7SRCVBFiQACf4ua'
        }

        success {
            discordSend description: '', footer: '', image: '', link: '', result: '', scmWebUrl: '', thumbnail: '', title: 'Berhasil nih boss', webhookURL: 'https://discord.com/api/webhooks/1073903280893202502/FwVTY2tdIp9qekgj3qLn-ta-PuBst9FRg3lqmqFyu0yG_3dYFs5mB7SRCVBFiQACf4ua'
        }
        
    }
    
}
```
![Screen Shot 2023-02-28 at 19 29 48](https://user-images.githubusercontent.com/68781074/221854609-7d20c17f-a3df-4e59-bfa6-6484915fab46.png)

![Screen Shot 2023-02-28 at 19 29 51](https://user-images.githubusercontent.com/68781074/221854625-f1c38b72-9609-41f2-940b-bd559100e2c8.png)

![Screen Shot 2023-02-28 at 19 29 53](https://user-images.githubusercontent.com/68781074/221854644-c07a949c-9bf7-43cf-a4ab-34a57c6b25df.png)


5. After that, we can build the pipeline. 

![Screen Shot 2023-03-01 at 1 35 48](https://user-images.githubusercontent.com/68781074/221947517-bbf43a8e-fd8d-4516-b3a0-0053bb9b7e00.png)

6. If the pipeline process is successful, it will look like this.

![Screen Shot 2023-02-28 at 3 00 29](https://user-images.githubusercontent.com/68781074/221947633-b596f426-9735-4049-b926-75b91d2f3e9c.png)

7. Then, we can integrate it into GitHub using a webhook. The webhook function will automatically rebuild the pipeline if there is an update to the Jenkinsfile.

![Screen Shot 2023-02-28 at 18 33 59](https://user-images.githubusercontent.com/68781074/221948201-9cc835bc-a604-4c99-b929-d319d222d394.png)

![Screen Shot 2023-03-01 at 1 38 43](https://user-images.githubusercontent.com/68781074/221948047-75238f77-2e85-40c4-b0e0-68bc954db79d.png)

![Screen Shot 2023-03-01 at 1 39 11](https://user-images.githubusercontent.com/68781074/221948128-c3fb5129-bc7e-48e1-aee6-247b211edb13.png)

![Screen Shot 2023-02-28 at 19 04 05](https://user-images.githubusercontent.com/68781074/221948240-b2b52b81-fad3-44bc-943a-4cbc959f1402.png)







