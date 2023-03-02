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

3. untuk mendapatkan cloudflare api key yaitu menggunakan global token yang di sediakan oleh cloudflare

![Screen Shot 2023-03-03 at 1 30 07](https://user-images.githubusercontent.com/68781074/222519952-55d2bf40-51f4-44b7-8cb1-c5b6bb7d49db.png)

![Screen Shot 2023-03-03 at 1 30 16](https://user-images.githubusercontent.com/68781074/222519969-cb2d0814-3be4-472e-92dd-5013b25cd23b.png)

![Screen Shot 2023-03-03 at 1 30 34](https://user-images.githubusercontent.com/68781074/222520012-26596bd2-3162-40a8-864d-a3f78e8aa65c.png)

3. setelah kita membuat file credential kita dapat menjalankan perintah untuk melakukan ssl certificate

![Screen Shot 2023-03-01 at 22 58 14](https://user-images.githubusercontent.com/68781074/222520528-91c55bd2-86fb-4da5-b077-8eaf863ef6d8.png)

4. kita bisa mengecek SSL certificate di dalam configurasi reverse proxy

![Screen Shot 2023-03-03 at 1 36 10](https://user-images.githubusercontent.com/68781074/222520831-8d9eeb1c-dcc1-467f-b55a-067d91184c41.png)

![Screen Shot 2023-03-03 at 1 36 15](https://user-images.githubusercontent.com/68781074/222520856-c03cbb6a-85b5-42c9-a618-6fdadff6c612.png)

![Screen Shot 2023-03-03 at 1 36 20](https://user-images.githubusercontent.com/68781074/222520890-e283d925-2eb2-435a-a462-c218e7b8ba4e.png)

5. semua domain sudah terproteksi dengan SSL certificate

![Screen Shot 2023-03-03 at 1 39 14](https://user-images.githubusercontent.com/68781074/222521496-1157675f-dacc-4881-8580-2df3a1483b6e.png)

![Screen Shot 2023-03-01 at 23 27 46](https://user-images.githubusercontent.com/68781074/222521263-d5d78ec6-9f82-4429-aa3a-7e9765179c8b.png)

![Screen Shot 2023-03-01 at 23 27 54](https://user-images.githubusercontent.com/68781074/222521289-b42e5f01-637e-41b5-8bda-f15d54a3590d.png)

![Screen Shot 2023-03-01 at 23 28 04](https://user-images.githubusercontent.com/68781074/222521323-0993f390-abda-4b5b-b839-83126174430e.png)

![Screen Shot 2023-03-01 at 23 28 19](https://user-images.githubusercontent.com/68781074/222521342-24adb136-913d-4ce8-8852-c62d7d3ab8af.png)

![Screen Shot 2023-03-01 at 23 28 42](https://user-images.githubusercontent.com/68781074/222521367-c45745a1-354d-4e2b-9bc9-67c0a92cc6f0.png)

![Screen Shot 2023-03-01 at 23 29 03](https://user-images.githubusercontent.com/68781074/222521390-d70d4ce4-f727-4953-8f08-d2dfff4c7f40.png)

![Screen Shot 2023-03-01 at 23 29 23](https://user-images.githubusercontent.com/68781074/222521433-6998c0f3-5810-4f96-95e2-1cf7f3e3c8d3.png)










