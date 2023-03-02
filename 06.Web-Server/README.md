![image](https://user-images.githubusercontent.com/68781074/221351341-ca262a3f-4737-40f4-8bb2-8840342288ec.png)

# Web-Server

## Create domain for Virtual Machine

1. membuat semua domain menggunakan platform cloudflare, dan semua ip akan di arahkan ke public IP dari server Gateway.

![Screen Shot 2023-03-03 at 1 21 46](https://user-images.githubusercontent.com/68781074/222517861-d6eba723-08f0-459e-ab93-c9b66b5ce9b4.png)

2. membuat reverse proxy untuk tiap server

![Screen Shot 2023-03-01 at 22 05 11](https://user-images.githubusercontent.com/68781074/222518034-314e13ca-eb7d-45f5-a95e-4c56dbfe20a5.png)

![Screen Shot 2023-03-01 at 22 05 19](https://user-images.githubusercontent.com/68781074/222518066-0ea942fd-cd83-4b6a-b0b8-b269e2a6620e.png)

## SSL Certificates with certbor

1. langkah pertama yang dilakukan adalah untuk menginstall certbot terlebih dahulu, untuk proses installasi certbot kita bisa mengikuti dokumentasi yang sudah disediakan dan apa saja yang di install

![Screen Shot 2023-03-01 at 22 39 17](https://user-images.githubusercontent.com/68781074/222518733-71fdf809-d641-48fe-ac54-0d37b9083448.png)

2. lalu kita bisa setup credential dengan membuat sebuah filenya seperti ini 

![Screen Shot 2023-03-01 at 22 42 39](https://user-images.githubusercontent.com/68781074/222519204-d14ee2a4-15cc-4ebf-962d-b7b1eeeaaa13.png)

3. untuk mendapatkan cloudflare api key kita bisa














