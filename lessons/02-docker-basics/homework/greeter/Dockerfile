#ייבוא פייטון לקונטיינר
FROM FROM python:3.11-slim
#עובדים מתוך התקיה APP
WORKDIR /app
#מעתיק את הדרישות קודם כל
COPY requirements.txt .
# מתקין את כל התלויות המוגדרות בקובץ ה-requirements
RUN pip install --no-cache-dir -r requirements.txt 
# מעתיק את שאר קבצי האפליקציה אל הקונטיינר
COPY app.pt .
#חושף את פורט 8000
EXPOSE 8000

CMD ["python", "app.py"]




