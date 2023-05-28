
## Server Login dengan SSH Key dan Password Disabled.
- Berikut saya dapat mengakses server tanpa menggunakan password.
<img width="737" alt="Screenshot 2023-05-17 at 19 28 39" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/424c13cb-8199-43f7-b186-79b41b101860">
<img width="773" alt="Screenshot 2023-05-17 at 19 29 23" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/95148f96-bd9d-4797-b555-73e980ec62d9">
<img width="701" alt="Screenshot 2023-05-17 at 19 30 42" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/9f0ec57c-2adb-4783-9e34-9cdfc3370c59">
<img width="745" alt="Screenshot 2023-05-17 at 19 31 37" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/9cecb490-fdb8-458a-974d-7f6a208b696b">

## SSH-KEYGEN
- Saya menggunakan 2 **ssh-keygen**, yaitu di server **"appserver"** dan **"cicd"**.
<img width="626" alt="Screenshot 2023-05-21 at 17 27 50" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/39f1eff7-7120-4b0b-b843-a39327a758c7">
<img width="1324" alt="Screenshot 2023-05-21 at 17 30 17" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/252cb672-a3c2-4ade-8d5d-4b1ef0a3f93e">
<img width="584" alt="Screenshot 2023-05-22 at 01 22 31" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/1bd35b47-b892-4cb6-99d1-2cd1ab237220">

## UFW Enabled
- Pertama-tama yang saya lakukan adalah menginstall firewall terlebih dahulu.
<img width="581" alt="Screenshot 2023-05-29 at 00 36 29" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/7f9d4bb8-e28f-4545-984b-ad7f20cd926d">

- Kemudian saya men-deny incoming, dimana memblokir akses yang mau masuk. 
<img width="582" alt="Screenshot 2023-05-29 at 00 36 46" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/43c13643-4574-4325-b45d-3494e98aaea7">

- Kemudian saya meng-allow outgoing, dimana saya dapat mengakses keluar.
<img width="579" alt="Screenshot 2023-05-29 at 00 36 58" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/55026c3a-8e57-4991-8a57-8f66154e3710">

- Berikut menunjukkan list.
<img width="584" alt="Screenshot 2023-05-29 at 00 37 08" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/6742a5ca-1c0d-4835-891a-8f21d94110ce">

- Berikut meng-allow Nginx.
<img width="582" alt="Screenshot 2023-05-29 at 00 37 28" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/03ab724e-f034-4ed2-9b6c-5e5c9b577548">

- Kemudian meng-allow akses untuk port 22.
<img width="583" alt="Screenshot 2023-05-29 at 00 52 04" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/4483ac18-61e0-4d64-a4db-30d371ee59d7">

- Setelah itu meng-allow 22/TCP, yaitu **http://**
<img width="584" alt="Screenshot 2023-05-29 at 00 38 14" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/0f4147a7-80ab-443b-9ca3-39ed97ed641b">

- Setelah itu meng-allow 22/UDP, yaitu **https://**
<img width="582" alt="Screenshot 2023-05-29 at 00 38 31" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/5ff999ab-b8b7-4411-9f60-7327cffd5982">
