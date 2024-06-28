FROM python

WORKDIR /app

# I can use . here because the WORKDIR changed the context to /app so after the WORKDIR: . = /app
COPY . .

CMD ["python", "bmi.py"]