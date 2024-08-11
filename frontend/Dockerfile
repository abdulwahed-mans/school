# استخدم صورة Node.js
FROM node:16

# تعيين مسار العمل داخل الحاوية
WORKDIR /app

# نسخ package.json وتثبيت التبعيات
COPY package*.json ./
RUN npm install

# نسخ بقية ملفات المشروع
COPY . .

# بناء مشروع Next.js
RUN npm run build

# فتح المنفذ 3000 لتشغيل Next.js
EXPOSE 3000

# تشغيل التطبيق
CMD ["npm", "start"]
