### frontend
- Pertama buatlah file YAML yang berisikan script untuk deployment frontend.
<img width="580" alt="Screenshot 2023-05-29 at 16 08 41" src="https://github.com/angellaviory/final-task-batch16/assets/102456153/a2378e0b-9dea-46d9-b8f4-6d9fed245966">

- Setelah itu, jalankan dengan command ``minikube kubectl -- apply -f frontend.yml``. 
<img width="661" alt="Screenshot 2023-05-29 at 16 20 37" src="https://github.com/angellaviory/final-task-batch16/assets/102456153/7ddfddfc-760f-4b41-8891-d5f0c344ea1b">


- Kemudian buatlah file YAML yang berisikan script service frontend.
<img width="663" alt="Screenshot 2023-05-29 at 16 40 51" src="https://github.com/angellaviory/final-task-batch16/assets/102456153/8f7cc2ad-7df4-46d2-bf64-6b83c6e75628">

- Setelah itu, jalankan dengan command ``minikube kubectl -- apply -f frontend-svc.yml`` .
<img width="661" alt="Screenshot 2023-05-29 at 16 41 41" src="https://github.com/angellaviory/final-task-batch16/assets/102456153/2bfe67cf-fafe-4a02-a057-4143772c4047">

- Selanjutnya untuk memastikan file tersebut sudah berhasil dibuat menggunakan command ``minikube kube -- get all``.
<img width="662" alt="Screenshot 2023-05-29 at 16 46 32" src="https://github.com/angellaviory/final-task-batch16/assets/102456153/6e62f664-f0b6-4879-b650-c7a932293e1b">

- Sekarang saya akan manjalankan aplikasi di browser. Saya telah berhasil menjalankannya di browser.
<img width="1325" alt="Screenshot 2023-05-29 at 16 50 13" src="https://github.com/angellaviory/final-task-batch16/assets/102456153/e23fdf0c-9bf9-43a9-b209-c79cb083f8f3">


### backend
- Pertama buatlah file YAML yang berisikan script untuk deployment backend.
<img width="657" alt="Screenshot 2023-05-29 at 22 06 47" src="https://github.com/angellaviory/final-task-batch16/assets/102456153/4cd5f99c-ac62-420a-af3b-e0c7fcf26274">

- Setelah itu, jalankan dengan command ``minikube kubectl -- apply -f backend.yml``. 
<img width="653" alt="Screenshot 2023-05-29 at 22 07 58" src="https://github.com/angellaviory/final-task-batch16/assets/102456153/83f7cd3a-9432-4bff-8f79-74d819a5d5a1">

- Kemudian buatlah file YAML yang berisikan script service frontend.

- Setelah itu, jalankan dengan command ``minikube kubectl -- apply -f backend-svc.yml`` .

- Selanjutnya untuk memastikan file tersebut sudah berhasil dibuat menggunakan command ``minikube kube -- get all``.
