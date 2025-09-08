From python:3.9-slim

#Set working directory as app
WORKDIR /app

COPY requirements.txt . 
#Copy dependencies list 

RUN pip install --no-cache-dir -r requirements.txt 
# Installs dependencies in container 

COPY . . 

EXPOSE 5000

CMD ["python" , "app.py"]