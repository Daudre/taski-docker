# Notes for myself

## Actually useful in future

* `npm cache clean --force`
* `sudo apt clean`
* `sudo journalctl --vacuum-time=1d`

* Install Docker

    ```bash
    sudo apt update
    sudo apt install curl
    curl -fSL https://get.docker.com -o get-docker.sh
    sudo sh ./get-docker.sh
    sudo apt install docker-compose-plugin
    ```

* Copy docker compose prod

    ```ps1
    scp -i "C:\Users\Me\.ssh\yas" ./docker-compose.production.yml ubuntu@81.26.191.192:~/taski/docker-compose.production.yml
    scp -i "C:\Users\Me\.ssh\yas" ./.env ubuntu@81.26.191.192:~/taski/.env
    ```

* Docker commands (with `sudo` it seems)

    ```ps1
    docker compose stop
    docker compose down
    docker compose logs
    ```

* `https://dida.myddns.me/`
* `aluerie.ddns.net`
* `81.26.191.192`

## Maybe not useful by hey

* Command to connect to Yandex VPS.

    ```ps1
    ssh ubuntu@81.26.191.192 -i "C:\Users\Me\.ssh\yas"
    ```

* Remember - we have some random notes in the previous project (taski-fork)

* `nano /etc/systemd/system/gunicorn.service` (that we killed with `sudo rm /etc/systemd/system/gunicorn.service`)

    ```ini
    [Unit]
    Description=gunicorn daemon
    After=network.target

    [Service]
    User=ubuntu
    WorkingDirectory=/home/ubuntu/taski/backend/
    ExecStart=/home/ubuntu/taski/backend/venv/bin/gunicorn --bind 0.0.0.0:8000 backend.wsgi

    [Install]
    WantedBy=multi-user.target
    ```
