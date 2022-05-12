FROM python:3.9-buster

ENV PYTHONUNBUFFERED=1

# pipを使ってpoetryをインストール
RUN pip install poetry

# poetryの定義ファイルをコピー (存在する場合)
COPY pyproject.toml* poetry.lock* ./

# poetryでライブラリをインストール (pyproject.tomlが既にある場合)
RUN curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python3 - \
    && poetry config virtualenvs.in-project true

RUN if [ -f pyproject.toml ]; then poetry install; fi


