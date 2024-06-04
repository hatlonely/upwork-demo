FROM python:3.12.0rc2-alpine3.18

COPY . /app
WORKDIR /app

RUN pip3 install -r requirements.txt

COPY --from=public.ecr.aws/awsguru/aws-lambda-adapter:0.6.2 /lambda-adapter /opt/extensions/lambda-adapter
ENV PORT=8000

EXPOSE 8000
CMD [ "gunicorn", "-c", "config.py", "main:app" ]
