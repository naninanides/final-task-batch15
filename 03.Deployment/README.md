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

1. langkah pertama yang kita akan lakukan adalah setup untuk ssh credential jenkinsnya, kita bisa menggenerate ssh keynya terlebih dahulu

![Screen Shot 2023-02-28 at 0 58 34](https://user-images.githubusercontent.com/68781074/221645296-da8445e5-c092-428b-b508-2f52122733c7.png)

2. kita akan mengambil key dari ssh-keygen yang sudah kita generate tadi

![Screen Shot 2023-02-28 at 0 59 58](https://user-images.githubusercontent.com/68781074/221645634-3d9f9c22-46db-45a8-8cfe-76292a65e37b.png)

3. Lalu pada dashboard klik manage jenkins lalu pilih manage credentials dan akan menambahkan credential untuk jenkins

![Screen Shot 2023-02-28 at 1 00 36](https://user-images.githubusercontent.com/68781074/221646268-bd2db535-e702-4de1-96ff-7a033258ce1e.png)

![Screen Shot 2023-02-28 at 1 00 51](https://user-images.githubusercontent.com/68781074/221648858-0c710341-a277-47ac-9ba3-e2c7db1a331d.png)

![Screen Shot 2023-02-28 at 1 00 54](https://user-images.githubusercontent.com/68781074/221648884-aea24cff-2c2b-4698-b2cf-6842bde539e1.png)

![Screen Shot 2023-02-28 at 1 01 26](https://user-images.githubusercontent.com/68781074/221648906-bdbf225b-d9b3-4725-b2db-53536864cbfb.png)

4. lalu kita masukan key yang sudah kita generate tadi

![Screen Shot 2023-02-28 at 1 17 58](https://user-images.githubusercontent.com/68781074/221649378-346b4102-2317-44bb-adf9-4f7440a62046.png)

![Screen Shot 2023-02-28 at 1 18 00](https://user-images.githubusercontent.com/68781074/221649397-358492b4-9816-48d9-90be-31828b79bfaa.png)

5. kita sudah menambahkan credential

![Screen Shot 2023-02-28 at 1 19 00](https://user-images.githubusercontent.com/68781074/221649718-90064ba4-8dcb-4b89-9d94-e8c5baa5d341.png)

6. lalu setelah itu kita masukan key.pub ke dalam github

![Screen Shot 2023-02-28 at 1 20 36](https://user-images.githubusercontent.com/68781074/221650099-97a8f5b3-0e42-462f-91c5-3ef819fa2166.png)

![Screen Shot 2023-02-28 at 1 21 12](https://user-images.githubusercontent.com/68781074/221650125-4b62e9de-9836-4d08-8726-49fce4ec0b3b.png)

![Screen Shot 2023-02-28 at 1 21 33](https://user-images.githubusercontent.com/68781074/221650162-36a4801a-4c42-4458-b1da-2ed264e2b361.png)


### Create Pipeline

1. Untuk membuat sebuah pipeline kita bisa mengklik new item dan kita pilih jenis pipeline apa yang kita inginkan

![Screen Shot 2023-02-28 at 1 29 10](https://user-images.githubusercontent.com/68781074/221651656-aa5ab7b2-1efe-4465-9645-eefe0cf72215.png)

![Screen Shot 2023-02-28 at 1 29 07](https://user-images.githubusercontent.com/68781074/221651745-ba30046a-aae7-4238-8e12-3dc6963ab398.png)

2. untuk di konfigurasi kita bisa mengklik Github hook triger bertujuan agar terintegerasi oleh github

![Screen Shot 2023-02-28 at 1 33 28](https://user-images.githubusercontent.com/68781074/221652472-d0fe3e23-7e90-4b01-bd90-4ee2d103b76f.png)

3. Lalu pada Pipeline kurang lebih seperti ini untuk konfigurasinya

![Screen Shot 2023-02-28 at 1 37 49](https://user-images.githubusercontent.com/68781074/221653760-e5e6a4c6-d19e-4f95-826d-dea2de9ffb51.png)

![Screen Shot 2023-02-28 at 1 41 19](https://user-images.githubusercontent.com/68781074/221653959-0ea4a00a-f772-4aa8-986d-f2cb7c095a3e.png)

![Screen Shot 2023-02-28 at 1 40 03](https://user-images.githubusercontent.com/68781074/221653778-f18b833c-903e-4e7e-835c-28b36c2872d0.png)

4. lalu kita siapkan untuk jenkinsfilenya di dalam git

![Screen Shot 2023-02-28 at 1 57 52](https://user-images.githubusercontent.com/68781074/221657213-2f9c2a5e-f8c4-4e03-876a-64746c3dbd6a.png)

```
My Drive
pipeline {
    agent any

    environment{
        def branch = "Production"
        def nama_repository = "origin"
        def directory = "~/dumbmerch-fe"
        def credential = 'bhq'
        def server = 'bhq@10.84.198.151'
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
            discordSend description: 'kok di gagalin', footer: '', image: '', link: '', result: '', scmWebUrl: '', thumbnail: '', title: 'proses yang berjalan', webhookURL: 'https://discord.com/api/webhooks/1073903280893202502/FwVTY2tdIp9qekgj3qLn-ta-PuBst9FRg3lqmqFyu0yG_3dYFs5mB7SRCVBFiQACf4ua'
        }
        failure {
            discordSend description: 'gagal nih bosss', footer: '', image: '', link: '', result: '', scmWebUrl: '', thumbnail: '', title: 'proses yang berjalan', webhookURL: 'https://discord.com/api/webhooks/1073903280893202502/FwVTY2tdIp9qekgj3qLn-ta-PuBst9FRg3lqmqFyu0yG_3dYFs5mB7SRCVBFiQACf4ua'
        }

        success {
            discordSend description: 'berhasil nih bos', footer: '', image: '', link: '', result: '', scmWebUrl: '', thumbnail: '', title: 'proses yang berjalan', webhookURL: 'https://discord.com/api/webhooks/1073903280893202502/FwVTY2tdIp9qekgj3qLn-ta-PuBst9FRg3lqmqFyu0yG_3dYFs5mB7SRCVBFiQACf4ua'
        }
        
    }
}
```

5. 






