# Terraform
- Pertama, lakukan instalasi terraform. Saya akan menjalankan command ini untuk menginstall terraform untuk OS Linux di local saya.
<img width="617" alt="Screenshot 2023-05-17 at 06 23 04" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/09825eb2-4336-4c19-860b-910361be65c5">
<img width="901" alt="Screenshot 2023-05-17 at 06 26 12" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/93d3235d-4118-425c-99ed-d994703cbce4">

- Setelah berhasil di install, untuk memastikan saya akan lakukan pengecekkan dengan command `terraform version`.
<img width="628" alt="Screenshot 2023-05-17 at 06 27 55" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/2caa0755-c0bf-43fc-9b45-d3682f222352">

- Sebelum saya membuat konfigurasi, saya akan membuat token di IDCloudHost.
<img width="1321" alt="Screenshot 2023-05-17 at 05 54 22" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/b791eefe-f760-47c4-a04f-21158651ea4c">

- Sekarang saya akan membuat VM menggunakan provider IDCloudHost. Pertama-tama, saya akan membuat directory **idch** dan file bernama **main.tf**.
<img width="582" alt="Screenshot 2023-05-17 at 05 51 25" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/b90e2acc-2219-47bc-b082-95c9b336506a">

- Kemudian saya masuk ke dalam file `main.tf` yang didalamnya akan saya isi konfigurasi pembuatan VM dan Floating IP.
<img width="613" alt="Screenshot 2023-05-18 at 02 11 35" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/2b4d3ebf-1ec8-45ec-8f9d-ec2538a3547b">
<img width="666" alt="Screenshot 2023-05-17 at 16 00 57" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/2cf86522-c302-4884-9cb1-df2baa152475">
<img width="721" alt="Screenshot 2023-05-17 at 06 21 33" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/7b06ea1e-fa50-41be-ad40-4e38a9b5d92b">

- Saatnya membuat VM dan Floating IP menggunakan terraform. Langkah pertama adalah melakukan **terraform init**, dimana file `main.tf`akan di initialized.
<img width="680" alt="Screenshot 2023-05-17 at 19 18 11" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/da738ede-99eb-404b-8dd2-99a9be460eb5">


- Jika initialized telah berhasil dilakukan, langkah selanjutnya adalah **terraform plan**, dimana akan menunjukkan rencana pembuatan VM dan Floating IP dari hasil konfigurasi file `main.tf` di IDCloudHost.
<img width="730" alt="Screenshot 2023-05-17 at 09 28 12" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/cd27ee27-7422-4d1d-b385-a7eb54043098">
<img width="660" alt="Screenshot 2023-05-17 at 09 28 29" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/cc9892e2-2e16-4de1-bb4d-66d09aa666d2">
<img width="684" alt="Screenshot 2023-05-17 at 16 20 39" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/7bfce9ba-8fb6-4cfe-9fe0-900c5476e3aa">
<img width="684" alt="Screenshot 2023-05-17 at 16 20 46" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/bb59883a-73f1-402b-be1a-d3461b089423">
<img width="685" alt="Screenshot 2023-05-17 at 16 20 51" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/0a75ee65-ff79-44ff-b7c3-65e5e71ae112">
<img width="687" alt="Screenshot 2023-05-17 at 16 20 56" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/8ec9c217-f35a-4418-859d-cca11897f8d5">


- Langkah terakhir adalah melakukan **terraform apply**, dimana setelah memberikan value **yes** maka terraform akan membuat VM dan Floating IP di IDCloudHost.
<img width="692" alt="Screenshot 2023-05-17 at 16 06 19" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/c7022353-abc5-4f03-8a87-d71643a13cac">
<img width="639" alt="Screenshot 2023-05-17 at 19 26 41" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/56766973-94e8-43ba-9eb2-b9aac9f4b902">

- Server telah berhasil dibuat dengan terraform. Berikut tampilan server IDCloudHost yang berhasil dibuat dan saya sudah bisa mengakses server tanpa memasukkan ssh.
<img width="927" alt="Screenshot 2023-05-17 at 19 47 56" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/b49845fa-2b87-42dd-ba58-30baeb540c16">
<img width="925" alt="Screenshot 2023-05-17 at 19 48 01" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/a28a7d59-137b-42d9-91a2-05cac22dd556">
<img width="925" alt="Screenshot 2023-05-17 at 19 48 04" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/11ab1c1c-30c8-4ae4-a16a-65f3330b0c1e">
<img width="927" alt="Screenshot 2023-05-17 at 19 48 08" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/7ca25f95-5d5a-43c1-b3ee-8014aa3c7b66">


<img width="737" alt="Screenshot 2023-05-17 at 19 28 39" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/424c13cb-8199-43f7-b186-79b41b101860">
<img width="773" alt="Screenshot 2023-05-17 at 19 29 23" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/95148f96-bd9d-4797-b555-73e980ec62d9">
<img width="701" alt="Screenshot 2023-05-17 at 19 30 42" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/9f0ec57c-2adb-4783-9e34-9cdfc3370c59">
<img width="745" alt="Screenshot 2023-05-17 at 19 31 37" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/9cecb490-fdb8-458a-974d-7f6a208b696b">


# Ansible

- Sebelum melakukan instalasi ansible, saya akan mendownload package manager **pip** untuk digunakan sebagai python interpreter dan python environment user.
<img width="622" alt="Screenshot 2023-05-17 at 06 28 37" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/7c6bdc62-9ac2-4ba9-ab3e-4e796a93d957">
<img width="690" alt="Screenshot 2023-05-17 at 07 28 24" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/65da208a-f03f-4b28-9141-636b0089cb83">
<img width="725" alt="Screenshot 2023-05-17 at 07 31 38" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/5867711f-9daf-42d0-b41a-a2b2bddd6347">

- Kemudian Install ansible.
<img width="725" alt="Screenshot 2023-05-17 at 07 32 25" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/b218b728-804c-44c1-8920-d110d0d8926b">

- Untuk memastikan ansible telah terinstall dengan menggunakan command `ansible --version`.
<img width="728" alt="Screenshot 2023-05-17 at 08 38 45" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/a705fbb7-e74d-4662-a5fe-2f4600dbc4c5">

- Sekarang saya akan memasukkan private-key `id_rsa` lokal saya ke VM multipass saya.
<img width="783" alt="Screenshot 2023-05-18 at 02 49 28" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/4093fc97-c7a2-4f4c-b953-b465414d3869">

- Setelah ansible sudah terinstall, saya sudah bisa membuat berbagai macam konfigurasi. Pertama-tama yang akan saya lakukan adalah membuat directory.
<img width="666" alt="Screenshot 2023-05-18 at 02 20 23" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/183e2576-f054-416e-ad33-fcdf04ee6fa8">

- Kemudian saya akan membuat file `Inventory` yang berisikan **server** dengan alamat IP nya dan **variabel** berisikan username saya dan lokasi python interpreter saya disimpan.
<img width="666" alt="Screenshot 2023-05-18 at 02 22 23" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/ca6752a8-c15d-49f4-8e8f-dd20c5ed4eae">

- Kemudian saya akan membuat file `ansible.cfg`, yang berisikan *default*. Disini invenetory akan diarahkan ke file **Inventory**, memberitahukan lokasi private-key saya berada, Meng-skip finger print dan python interpreter menjadi auto silent.
<img width="664" alt="Screenshot 2023-05-18 at 02 23 35" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/db992c59-fe83-4e96-b360-1dfd04ac3334">

## Install Docker Engine di Semua Server
- Sekarang saya akan membuat setup ansible untuk instalasi docker. Berikut isi konfigurasi file ``docker.yml``.
<img width="666" alt="Screenshot 2023-05-18 at 18 18 31" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/9e5c9e76-23eb-4c47-870a-cebb8eb35f3f">

- Selanjutnya saya akan menjalankan ansible-playbook untuk instalasi docker.
<img width="706" alt="Screenshot 2023-05-18 at 18 19 43" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/6c3c1518-1207-4950-8daf-3b06de9ca564">

- Saya masuk ke server **appserver**, **gateway**, **cicd** dan **monitoring** dan mencoba `docker version` untuk melihat apakah telah berhasil terinstall. Dapat dolihat saya telah berhasil menginstall docker.
<img width="878" alt="Screenshot 2023-05-19 at 02 44 32" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/675198d0-5804-4541-b4ba-176970ed1f94">


## Install Node Exporter di Semua Server
- Sekarang saya akan membuat setup ansible untuk instalasi node expoter. Berikut isi konfigurasi file ``node.yml``.
<img width="608" alt="Screenshot 2023-05-19 at 02 01 16" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/329de575-9bef-41d3-92d8-719f00e8d766">

- Selanjutnya saya akan menjalankan ansible-playbook untuk instalasi node exporter.
<img width="850" alt="Screenshot 2023-05-19 at 02 52 27" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/39aa9032-110b-4f94-b574-54dec2e3858b">

- Saya masuk ke server **appserver**, **gateway**, **cicd** dan **monitoring** dan mencoba `docker images` dan `docker ps -a` untuk melihat apakah berhasil mem-pull image *node exporter* dan menjalankannya di browser (mengeluarkan script metrics). Dapat dilihat saya telah berhasil menginstall node exporter.
<img width="988" alt="Screenshot 2023-05-19 at 02 57 21" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/c2271210-5ff5-486c-a7cf-d4f17abead96">
<img width="1148" alt="Screenshot 2023-05-19 at 03 03 56" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/9220b096-5d45-4b25-9404-6511bbfb1b82">

## Install NGINX di Server Gateway
- Selanjutnya saya akan menginstall web server, yaitu NGINX. Langkah pertama yang saya lakukan adalah membuat setup instalasi nginx di file YAML dengan nama `nginx.yml`. Berikut script yang saya gunakan:
```
- name: "Nginx Installation"
  hosts: gateway
  become: true
  vars:
    user: angel
  tasks:
    - name: "Instalisasi nginx"
      apt:
        name: nginx
        state: latest
    - name: "Copy Repo"
      ansible.builtin.copy:
        src: /home/ubuntu/ansible/rproxy/
        dest: /etc/nginx/sites-enabled/
    - name: "Resart Nginx"
      service:
        name: nginx
        state: restarted
```



- Sekarang saya akan membuat directory baru yang berisikan konfigurasi-konfigurasi domain server beserta IP nya.
<img width="641" alt="Screenshot 2023-05-19 at 11 25 17" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/d0190041-0239-43e8-82d4-fa0ac27ab6e9">
<img width="641" alt="Screenshot 2023-05-19 at 11 25 23" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/8155fa74-af56-4621-9adb-911cbd2a7a37">
<img width="548" alt="Screenshot 2023-05-19 at 11 26 06" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/8ef6bbef-7c4a-493b-a8a6-ee22d3f24d43">


- Setelah itu, sekarang saya akan menjalankan ansible-playbook. Saya telah berhasil menjalankan instalasi nginx di server gateway.
<img width="635" alt="Screenshot 2023-05-19 at 23 13 12" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/cf78f6b2-5ffe-460a-b507-b76af7aa1674">

## CI/CD: Jenkins
- Berikut script ansible yang digunakan untuk menginstall Jenkins:
```
- name: "Install Jenkins"
  become: true
  gather_facts: false
  hosts: cicd
  tasks:
    - name: "Jenkins On Top Docker"
      community.docker.docker_container:
        name: jenkins
        image: jenkins/jenkins:latest
        ports:
          - 8080:8080
        volumes:
          - ~/ansible/config/jenkins:/var/jenkins_home
        restart_policy: unless-stopped
```

- Kemudian jalankan script ansible tersebut. 
<img width="572" alt="Screenshot 2023-05-21 at 23 57 57" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/06bc98a2-6360-4ce4-b02e-eacb3644b8ac">

- Saya coba untuk menjalankan nya di browser. Saya telah berhasil menginstall ansible.
<img width="1324" alt="Screenshot 2023-05-25 at 16 04 10" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/fc0d518b-9c7e-4e08-9624-dbe8cb40b095">


## Prometheus dan Grafana
- Berikut script penginstallan prometheus dan grafana menggunakan ansible.
```
- name: "Install Monitoring"
  become: true
  gather_facts: false
  hosts: monitoring
  vars:
    user: ang
  tasks:
    - name: "Create Prometheus Volumes"
      file:
        path: /etc/prometheus
        state: directory
        mode: "0755"

    - name: "Copy File  Prometheus Config"
      copy:
        src: /home/ubuntu/ansible/prometheus.yml
        dest: /etc/pprometheus/
        mode: "0644"

    - name: "Create Grafana Volumes"
      file:
        path: /grafana-storage
        state: directory
        mode: "0755"

    - name: "Pull Image Prometheus"
      docker_container:
        name: prometheus
        image: prom/prometheus
        volumes:
          - /etc/prometheus/:/etc/prometheus/
        command:
          - --config.file=/etc/prometheus/prometheus.yml
        ports:
          - 9090:9090

    - name: "Pull Image Grafna"
      docker_container:
        name: grafana
        image: grafana/grafana
        ports:
          - 3000:3000
```
- Berikut script scrape_target untuk prometheus mengambil data yaitu node exporter.
```
global:
  scrape_interval: 10s
scrape_configs:
  - job_name: "prometheus"
    statiic_configs:
       - targets"
           - node-appserver.angell.studentdumbways.my.id
           - node-gate.angell.studentdumbways.my.id
           - node-cicd.angell.studentdumbways.my.id
           - node-monitoring.angell.studentdumbways.my.id
```

- Saya coba run ansible-playbook script tersebut.
<img width="743" alt="Screenshot 2023-05-22 at 17 30 08" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/d8299daf-22eb-455c-aac5-6eda6712edd0">

- Saya akan mencoba mengakses di. browser saya. Saya telah berhasil menginstall prometheus dan grafana.
<img width="1324" alt="Screenshot 2023-05-25 at 15 47 52" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/b24f6833-c688-4239-b614-29fde24970e2">

<img width="1324" alt="Screenshot 2023-05-22 at 18 00 23" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/4ec5846a-7306-4e9b-88d5-c41c3fd68780">



