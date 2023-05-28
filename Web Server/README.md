
## Nginx
- Saya akan menginstall web server, yaitu NGINX dengan menggunakan ansible-playbook. Berikut script yang saya gunakan:
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

- Berikut konfigurasi DNS serta IP nya dan beberapa sudah di SSL menggunakan certbot..

<img width="810" alt="Screenshot 2023-05-29 at 01 00 15" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/08c02f66-60db-4a0f-bbdf-50fad97d51db">
<img width="811" alt="Screenshot 2023-05-29 at 01 00 24" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/b7ec17df-ba2e-4300-91f2-fd7a33297849">
<img width="820" alt="Screenshot 2023-05-29 at 01 00 35" src="https://github.com/angellaviory/DevOps16-dw-AngellaAvioryRotinsulu/assets/102456153/b1ad2fd2-50a6-44f1-a857-17d2a77f77fe">

