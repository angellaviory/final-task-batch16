
# fe-dumbmerch
- Hal pertama saya lakukan adalah mengclone aplikasi dari repository github.
<img width="579" alt="Screenshot 2023-05-19 at 03 14 32" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/83450932-d901-4253-ac22-ee1969c7ab1e">

- Selanjutnya saya akan membuat file **.env** (environment), dimana saya akan memasukkan IP sehingga aplikasi dapat diakses.
```
REACT_APP_BASEURL=http://api.angel.studentdumbways.my.id/api/v1
```

- Kemudian saya akan membuat **Dockerfile** untuk mem-build image dumbmerch-frontend.
```
#staging
ROM node:16.16-alpine AS staging
WORKDIR /app
COPY . .
RUN npm install
EXPOSE 3000
CMD ["npm","start"]

#production
ROM node:16.16-alpine AS staging
WORKDIR /app
COPY . .
RUN npm install

FROM staging
WORKDIR /app
COPY --from=staging /app /app
EXPOSE 3000
CMD ["npm","start"]
```
- Saya akan mem-build Dockerfile tersbut. 
<img width="680" alt="Screenshot 2023-05-21 at 17 11 11" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/cb2c48e0-3a14-4dde-b239-6bc1717cbe09">

- Berikut menggunakan branch production.
<img width="561" alt="Screenshot 2023-05-27 at 00 44 00" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/9fb1ca85-23a3-4299-8a92-4a31cf67531d">



# be-dumbmerch
- Hal pertama saya lakukan adalah mengclone aplikasi dari repository github.
<img width="579" alt="Screenshot 2023-05-19 at 03 14 32" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/c8b5dffd-905b-4de9-b844-6eb6bb21cbfd">

- Selanjutnya saya akan membuat file **.env** (environment), dimana saya akan memasukkan IP sehingga aplikasi dapat diakses.
```
DB_HOST=10.52.49.248
DB_USER=ang
DB_PASSWORD=Dumbways1
DB_NAME=dumbmerch
DB_PORT=5423
PORT=5000
```
- Kemudian saya akan membuat **Dockerfile** untuk mem-build image dumbmerch-backend
```
#stagiing dan production
FROM golang:1.16
WORKDIR /app
COPY . .
RUN go get ./ && go build && go mod download
EXPOSE 5000
CMD ["go", "run", "main.go"]
```
- Saya akan mem-build Dockerfile tersbut. 
<img width="633" alt="Screenshot 2023-05-21 at 22 48 37" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/3335139d-3cf8-428c-bc0a-d906e63693c8">
<img width="563" alt="Screenshot 2023-05-27 at 00 47 24" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/0bce5030-2517-4303-a4ed-fbf1ebd0e6d4">

# Deployment
- Saya telah membuat image docker untuk dumbmerch-frontend dan dumbmerch-backend. Sekarang saya sudah bisa meng-compose aplikasi dumbmerch. Berikut script docker-compose.yml:
```
version: "3.8"
services:
  db:
    image: postgres:latest
    container_name: postgres
    ports:
      - 5432:5432
    volumes:
      - ~/postgresql:/var/lib/postgresql/data
    environment:
      - POSTGRES_USER=ang
      - POSTGRES_PASSWORD=dumbways1
      - POSTGRES_DB=dumbmerch

  be:
    depends_on:
      - db
    image: angellaviory/dumbmerchbe-production:latest
    container_name: be-dumbmerch
    stdin_open: true
    restart: unless-stopped
    ports:
      - 5000:5000

  fe:
    image: angellaviory/dumbmerchfe-production:latest
    container_name: fe-dumbmerch
    stdin_open: true
    restart: unless-stopped
    ports:
      - 3000:3000
```
<img width="608" alt="Screenshot 2023-05-27 at 00 51 14" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/3223a1f1-ecfa-4833-ba1c-07fe39b71cfb">

- Sekarang saya akan mencoba mengakses aplikasi Dumbmerch menggunakan browser. Saya telah berhasil mengakses aplikasi Dumbmerch.
<img width="1323" alt="Screenshot 2023-05-22 at 13 25 56" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/2e5d3be6-02d5-4eaa-8bde-2e4701ec8be9">
<img width="1319" alt="Screenshot 2023-05-22 at 13 35 30" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/9341d09f-2ac7-4a29-ae1b-d445c2ba91ca">
<img width="1323" alt="Screenshot 2023-05-22 at 13 36 06" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/0f75eebc-8285-4f87-90c2-1308d5369d9a">

# CI/CD: Jenkins
- Agar bisa mengakses jenkins, pertama-tama masukkan password untuk meng-unlock jenkins.
<img width="1323" alt="Screenshot 2023-05-22 at 00 00 37" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/113300cf-9b45-46ce-a6da-2d697a477380">

- Kemudian saya memilih menginstall dengan menambah plugin tambahan, yaitu **ssh agent**. Setelah itu jenkins akan mulai mendownload.
<img width="1322" alt="Screenshot 2023-05-22 at 00 01 14" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/37a171cc-2c0a-4085-928f-3a267bacbfe2">

- Sekarang saya akan meng-create user untuk jenkins.
<img width="1322" alt="Screenshot 2023-05-22 at 00 07 45" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/8d138061-c93b-4e65-8b44-6f9c0964f002">

- Setelah itu saya memasukkan IP public saya.
<img width="1324" alt="Screenshot 2023-05-22 at 00 07 52" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/efb2d11b-d6bb-4157-9464-c2194401ef2e">

- Jenkins telah berhasil di install dan siap digunakan.
<img width="1325" alt="Screenshot 2023-05-22 at 00 07 58" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/bb76d916-398a-496c-8c07-70f6f128d0ee">

- Hal selanjutnya yang saya lakukan adalah membuat **cridentials** dan memasukkan **private-key** local ke jenkins. 
<img width="1310" alt="Screenshot 2023-05-22 at 00 09 38" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/5460255a-fdfc-496c-9b22-291f83cd2207">
<img width="1321" alt="Screenshot 2023-05-22 at 00 09 40" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/6b90f4a8-328f-4b31-85cf-7819f1918ba7">

- Sekarang saya akan memulai membuat pipeline jenkins. Saya memilih project menggunakan pipeline dan setiap memulai project baru, lakukan configurasi seperti berikut:
<img width="1324" alt="Screenshot 2023-05-22 at 00 10 21" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/82a1077a-8770-4245-9014-ca49bf603e1a">
<img width="1312" alt="Screenshot 2023-05-22 at 14 13 05" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/c3402345-4723-4a51-8bb7-d99fdef0fd7a">
<img width="1308" alt="Screenshot 2023-05-22 at 14 12 56" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/99853265-c35a-4218-96e9-abec5bff71e3">
<img width="1313" alt="Screenshot 2023-05-22 at 14 13 13" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/b201279e-ed5f-4b97-bd4d-a6be31edbc32">


- Kemudian, membuat Jenkinsfile untuk menjalankan CI/CD. Berikut script file **Jenkinsfile** dumbmerch-frontend:
```
def branch = "cicd"
def repo = "git@github.com:angellaviory/fe-dumbmerch.git"
def cred = "ang"
def dir = "~/fe-dumbmerch"
def server = "ang@103.31.38.155"
def imagename = "dumbmerch-fe"

pipeline {
    agent any
    stages {
        stage('Repository pull') {
            steps {
                sshagent([cred]) {
                    sh """ssh -o StrictHostKeyChecking=no ${server} << EOF
		    mkdir ${dir}
                    cd ${dir}
		    git init
                    git remote add origin ${repo}
		    git pull origin master
		    git branch ${branch}
		    git checkout ${branch}
		    git pull origin ${branch}
                    exit
                    EOF
                    """
                }
            }
        }
    
        stage('Image Build') {
            steps {
                sshagent([cred]) {
                    sh """ssh -o StrictHostKeyChecking=no ${server} << EOF
                    mkdir ${dir}
                    cd ${dir}
                    docker build -t ${imagename}:latest .
                    exit
                    EOF
                    """
                    }
               }
         }

         stage('Image Push') {
            steps {
                sshagent([cred]) {
                    sh """ssh -o StrictHostKeyChecking=no ${server} << EOF
                    mkdir ${dir}
                    cd ${dir}
                    docker tag ${imagename}:latest angellaviory/dumbmerchfe-staging:latest
                    docker push angellaviory/dumbmerchfe-staging:latest
                    exit
                    EOF
                    """
                    }
               }
         }

         stage('Docker Run') {
            steps {
                sshagent([cred]) {
                    sh """ssh -o StrictHostKeyChecking=no ${server} << EOF
                    mkdir ${dir}
                    cd ${dir}
                    docker run -d -p 3300:3000 ${imagename}:latest
                    exit
                    EOF
                    """
                    }
               }
         }

    }
}
```
- Berikut **Jenkinsfile** dumbmerch-backend:
```
def branch = "cicd"
def repo = "git@github.com:angellaviory/be-dumbmerch.git"
def cred = "ang"
def dir = "~/be-dumbmerch"
def server = "ang@103.31.38.155"
def imagename = "dumbmerch-be"

pipeline {
    agent any
    stages {
        stage('Repository pull') {
            steps {
                sshagent([cred]) {
                    sh """ssh -o StrictHostKeyChecking=no ${server} << EOF
		    mkdir ${dir}
                    cd ${dir}
		    git init
                    git remote add origin ${repo}
		    git pull origin master
		    git branch ${branch}
		    git checkout ${branch}
		    git pull origin ${branch}
                    exit
                    EOF
                    """
                }
            }
        }
    
        stage('Image Build') {
            steps {
                sshagent([cred]) {
                    sh """ssh -o StrictHostKeyChecking=no ${server} << EOF
                    mkdir ${dir}
                    cd ${dir}
                    docker build -t ${imagename}:latest .
                    exit
                    EOF
                    """
                    }
               }
         }

         stage('Image Push') {
            steps {
                sshagent([cred]) {
                    sh """ssh -o StrictHostKeyChecking=no ${server} << EOF
                    mkdir ${dir}
                    cd ${dir}
                    docker tag ${imagename}:latest angellaviory/dumbmerchbe-staging:latest
                    docker push angellaviory/dumbmerchbe-staging:latest
                    exit
                    EOF
                    """
                    }
               }
         }

         stage('Docker Run') {
            steps {
                sshagent([cred]) {
                    sh """ssh -o StrictHostKeyChecking=no ${server} << EOF
                    mkdir ${dir}
                    cd ${dir}
                    docker run -d -p 5500:5000 ${imagename}:latest
                    exit
                    EOF
                    """
                    }
               }
         }

    }
}
```
- Kemudian push file Jenkinsfile dumbmerch-frontend dan dumbmerch backend ke GitHub.
<img width="568" alt="Screenshot 2023-05-22 at 00 59 41" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/252f75d0-9782-41fa-a09f-eca858950712">
<img width="655" alt="Screenshot 2023-05-22 at 06 38 22" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/65b4c1cc-3c7f-46dd-9019-ff8cfab03ef6">

- Setelah itu, saya sudah bisa menjalankan pipeline jenkins. Dapat dilihat, saya telah berhasil melakukan **Pull Repository**, **Build image**, **Push Image**, dan **Run Image**.
<img width="1324" alt="Screenshot 2023-05-22 at 10 07 40" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/faf86a93-d6e6-4cb4-9ea6-9688866e1edc">
<img width="1322" alt="Screenshot 2023-05-22 at 14 19 56" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/855ada11-ecdd-4349-ae6d-e923c9db8f17">
