.DEFAULT_GOAL := all

all: install test run deploy

install:
	echo "Встановлення залежнотей..."
	pip3 install pipenv
	pipenv --python 3.8
	pipenv install requests
	pipenv install ntplib
	pipenv install pytest

test:
	echo "Початок тестів..." >> results.txt
	pipenv run pytest tests/tests.py >> results.txt

run:
	echo "Запуск додатку..." >> results.txt
	pipenv run python3 app.py >> results.txt

deploy:
	echo "Завантаження на гіт..."
	git add results.txt
	git commit -m "lab2"
	git push origin main lab2
	echo "Завантаження успішне..."
