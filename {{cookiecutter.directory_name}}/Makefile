default: test


test: env
	.env/bin/py.test --cov=slash --cov-report=html tests

env: .env/.up-to-date

.env/.up-to-date: setup.py Makefile
	python -m virtualenv .env
	.env/bin/pip install -e .[testing]
	touch .env/.up-to-date

doc: env
.env/bin/sphinx-build -a -E doc build/sphinx/html

.PHONY: doc

release: test
python scripts/make_release.py
