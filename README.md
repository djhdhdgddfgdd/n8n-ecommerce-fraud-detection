# 🛒 n8n E-commerce Order Monitoring & Fraud Detection

Production-ready **n8n workflow** for secure e-commerce order monitoring and fraud risk detection using webhook security, data validation, and rule-based risk scoring.

هذا المشروع مصمم كـ **Demo احترافي** يعكس طريقة بناء أنظمة أتمتة حقيقية تُستخدم في بيئات الإنتاج (Production)، مع التركيز على **الأمان، القابلية للتوسع، وسهولة التكامل**.

---

## 🚀 Features

- 🔐 **Secure Webhook Authentication**
  - التحقق من الطلبات عبر `x-webhook-secret`
- 🧹 **Data Normalization**
  - توحيد شكل بيانات الطلبات الواردة
- ✅ **Input Validation**
  - التأكد من صحة المبلغ والبيانات الأساسية
- 🧠 **Fraud Risk Scoring Logic**
  - تصنيف الطلبات إلى: `LOW / MEDIUM / HIGH`
- 📤 **External Audit Logging**
  - إرسال السجلات إلى endpoint خارجي (Webhook.site) لأغراض الاختبار
- 🧪 **Production-like Demo**
  - بدون استخدام أي مفاتيح حقيقية أو بيانات حساسة

---

## 🧱 Workflow Overview

**Flow:**

1. Secure Webhook  
2. Verify Webhook Secret  
3. Normalize Order Data  
4. Validate Order  
5. Fraud Risk Logic  
6. Send Audit Log  

Client
↓
Secure Webhook
↓
Secret Verification
↓
Data Normalization
↓
Validation
↓
Fraud Risk Scoring
↓
Audit / Ops Notification


---

## 🛡️ Security Design

- لا يتم تخزين أي مفاتيح حقيقية داخل المشروع
- جميع القيم الحساسة مستخدمة لأغراض **Demo فقط**
- التحقق من الهوية يتم قبل أي معالجة للبيانات
- في بيئة Production يُنصح باستخدام:
  - Environment Variables
  - API Gateway
  - Rate Limiting
  - IP Whitelisting

> راجع ملف [`SECURITY.md`](./SECURITY.md) لمزيد من التفاصيل.

---

## 📦 Project Structure

n8n-ecommerce-fraud-detection/
│
├─ workflows/
│ └─ ecommerce-fraud-detection.json
│
├─ scripts/
│ └─ test-webhook.sh
│
├─ README.md
├─ SECURITY.md
├─ ARCHITECTURE.md
└─ .gitignore


---

## 🧪 Testing the Workflow

### Example cURL Request

```bash
curl -X POST http://localhost:5678/webhook-test/ecom-orders-secure ^
-H "Content-Type: application/json" ^
-H "x-webhook-secret: DEMO_SECRET_456" ^
-d "{\"order_id\":\"ORD-1001\",\"amount\":1200,\"country\":\"SA\",\"new_customer\":true}"

Expected Result
الطلب يمر على جميع العقد

يتم تصنيفه كـ HIGH risk

يتم إرسال Log إلى endpoint خارجي للاختبار

🔧 Tech Stack
n8n – Workflow Automation

Webhook API

Rule-based Fraud Detection

HTTP Integrations

🌍 Use Cases
E-commerce Platforms

Payment Monitoring Systems

Order Risk & Fraud Detection

Operations Alerting

Backend Automation Pipelines

📌 Notes
هذا المشروع Demo للعرض فقط

جميع الروابط الخارجية مستخدمة للاختبار

لا يحتوي على أي بيانات حقيقية

