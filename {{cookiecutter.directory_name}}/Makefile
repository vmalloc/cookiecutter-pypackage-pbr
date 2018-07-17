default: test


test: env
	.env/bin/pytest tests

env: .env/.up-to-date

.env/.up-to-date: setup.py Makefile requirements.txt
	python3 -m virtualenv .env
	.env/bin/pip install -e .[testing]
	touch .env/.up-to-date
