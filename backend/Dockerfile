# استخدم صورة Python
FROM python:3.10-slim

# تعيين مسار العمل داخل الحاوية
WORKDIR /app

# نسخ متطلبات المشروع وتثبيتها
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# نسخ بقية ملفات المشروع
COPY . .

# فتح المنفذ 8000 لتشغيل Django
EXPOSE 8000

# تشغيل التطبيق باستخدام gunicorn
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi:application"]
