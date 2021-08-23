# Instruction
- Python 3.8
- Django 3.1
- NodeJS 12
- Angular 9
- Postgres 12
- Celery 5
- Nginx 1.19.0

# Prerequisites
 - Docker
 - Docker-compose
 - tmux and tmuxinator (optional)

# สร้าง Username
- `cd poc-certificate_management`
- `cd django`
- คำสั่งสำหรับการสร้าง Username `docker-compose exec django python manage.py createsuperuser`
  ```ตัวอย่าง
     Username (leave blank to use 'root'): <ชื่อผู้ใช้งาน>
     Email address: <อีเมล>
     Password: <รหัสผ่าน>
     Password (again): <ยืนยันรหัสผ่าน>
     Superuser created successfully.
  ```
![alt text](https://www.img.in.th/images/9644b6166504079ad991ba643abba0d2.png)
- คำสั่งสำหรับการเปลี่ยน Password `docker-compose exec django python manage.py changepassword`
  ```ตัวอย่าง
     Changing Password for user 'root'
     Password: <รหัสผ่าน>
     Password (again): <ยืนยันรหัสผ่าน>
     Password success for user 'root'
  ```
![alt text](https://www.img.in.th/images/f13cefff15fc4831540326bb4f053b8e.png)
