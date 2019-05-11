This app was built under Ubuntu 18.04 and tested under Ubuntu and macOS.



It makes use of channels library to implement a multi-room chat with websockets. 
It also uses celery and redis to implement a bot that can check for stock prices.
  
```
#install system dependencies
sudo apt-get install chromium-chromedriver
sudo apt-get install redis-server

#also virtualenv https://gist.github.com/frfahim/73c0fad6350332cef7a653bcd762f08d

#start redis server
sudo redis-server --port 6379

#create virtual environment
virtualenv --python=python3 venv

#activate virtual environment
source venv/bin/activate

#install requirements
pip install -r requirements.txt

#initialize db
python manage.py makemigrations
python manage.py migrate

#create users
python manage.py createsuperuser

#start dev server
python manage.py runserver

#starts celery (use a different console)
celery -A challenge worker -l info
```
