# Celery with RabbitMQ in Django (Python)
Implementing Celery with RabbitMQ in python

## Setting up django project
- Start the virtual environment
    ```
    source venv/bin/activate
    ```
- Install the packages
    ```
    pip install -r requirements.txt
    ```

## Setting up RabbitMQ server
- Install RabbitMQ server
    ```
    sudo apt-get install rabbitmq-server -y
    ```
- Enabling rabbitmq server
    ```
    sudo systemctl enable rabbitmq-server
    ```
- Starting the rabbitmq server
    ```
    sudo systemctl start rabbitmq-server
    ```
- Checking rabbitmq server status
    ```
    systemctl status rabbitmq-server
    ```
- Stopping RabbitMQ server
    ```
    sudo rabbitmqctl stop
    ```

## Testing app1 task
- starting Celery
    ```
    celery -A proj worker -l info
    ```
- Open interactive shell
    ```
    python manage.py shell
    ```
- Import the task
    ```
    from app1.tasks import add
    ```
- Running the task
    ```
    add.delay(2, 4)
    ```
    ```
    add.apply_async((3,3), countdown=5)
    ```