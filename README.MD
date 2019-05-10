```
#install system dependencies
sudo apt-get install chromium-chromedriver
sudo apt-get install redis-server
#start redis server
sudo redis-server --port 6379
#create virtual environment
virtualenv --python=python3 venv
#activate virtual environment
source venv/bin/activate
#install requirements
pip install -r requirements.txt
#initialize db
python manage.py migrate
#create users
python manage.py createsuperusers
#starts celery
celery -A challenge worker -l info
```
