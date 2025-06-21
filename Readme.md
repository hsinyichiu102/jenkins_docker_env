# Jenkins-Docker environment settings

* Structure

```text
    jenkins_docker_ENV/
    ├── Dockerfile
    ├── docker-compose.yml         #（可選）
    ├── jenkins_home/              # Jenkins volume（自動產生）
    └── README.md                  # 使用說明（選配）
```

1. Run Dockerfile:

    ```Bash
        docker build -t myjenkins .
        docker run -d \
        --name jenkins \
        -p 8080:8080 -p 50000:50000 \
        -v jenkins_home:/var/jenkins_home \
        -v /var/run/docker.sock:/var/run/docker.sock \
        myjenkins
    ```

2. Run docker-compose.yaml:

    ```Bash
        docker compose up -d
    ```

3. enter to docker container

    ```Bash
        docker exec -it jenkins bash
    ```