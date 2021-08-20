# Instruction
# Stack
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

# Runserver
- `chmod +x ./scripts/wait-for-it.sh`
- `chmod +x ./scripts/wait-for-postgres.sh`
- Change file 'docker-compose.override.yml' file this line
  ```yml
    django:
      ...
      extra_hosts:
      - hsm1.codium.co:<YOUR COMPUTER IP>
      - hsm2.codium.co:<YOUR COMPUTER IP>
  ```
- Open file 'django/main/apps/grpc/connector.py' and change GRPC_SERVER port to 50051
  ```py
  self.GRPC_SERVER = f'{settings.GRPC_SERVER_IP}:50051'
  ```
- Open 4 terminals and follow command in '.tmuxinator.yml' file or run `mux .` (if you have tmux and tmuxinator)

# Deployment
You have to deploy manually because it need VPN access.
https://coda.io/d/DDoc_dwheJPuKQwm/POC-EGAT_suMHo#_luILu

# backend shell
`docker run -it --expose 8000 -w /opt/app -v $(pwd)/django:/opt/app python:3.8-alpine sh`

# frontend shell
`docker run -it --expose 4200 -w /opt/app -v $(pwd)/angular:/opt/app node:12.18.1-alpine sh`

