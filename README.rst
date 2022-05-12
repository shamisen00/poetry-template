# プロジェクト開始時

コンテナに入ってから

poetry init --name [project name] --dependency ipykernel --dev-dependency pre-commit black isort flake8

poetry run poetry config virtualenvs.in-project true

or

docker-compose run --entrypoint "poetry init --name [project name] --dependency ipykernel" dev

# build後

# activate env

poetry shell

# activate pre-commit

pre-commit install
