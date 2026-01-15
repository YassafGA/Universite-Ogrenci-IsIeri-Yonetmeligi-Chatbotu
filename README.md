# 🎓 Üniversite Öğrenci İşleri Yönetmeliği Chatbotu  
### RAG • Fine-Tuning (LoRA) • Hybrid Karar Destek Sistemi

Bu proje, **Karar Destek Sistemleri** dersi kapsamında geliştirilmiş bir **doğal dil tabanlı karar destek chatbotudur**.  
Chatbot, üniversite **Öğrenci İşleri Yönetmeliği** dokümanını temel alarak öğrenci sorularına **doğru, kontrollü ve açıklanabilir** cevaplar üretir.

Projede **açık kaynak büyük dil modeli (Gemma)** kullanılmış;  
**RAG**, **Fine-Tuning (LoRA)** ve **Hybrid** yaklaşımlar **aynı soru üzerinde karşılaştırmalı** olarak uygulanmıştır.

---

# 🚀 Proje Özeti

- 📌 Tek Jupyter Notebook içinde geliştirilmiştir  
- 📌 Harici API (GPT, Gemini vb.) **kullanılmamıştır**
- 📌 Tüm veriler notebook içinde tanımlıdır (dosyadan okuma yok)
- 📌 Web arayüzü Gradio ile notebook içinde çalışmaktadır
- 📌 Aynı soru **3 farklı model yaklaşımı** ile cevaplanmaktadır

---

# 🧠 Kullanılan Modeller ve Yaklaşımlar

### 1️⃣ RAG (Retrieval Augmented Generation)
- Yönetmelik metni parçalara (chunk) ayrılır
- Sentence-Transformers ile embedding üretilir
- Cosine similarity ile en ilgili parçalar bulunur
- Model yalnızca bu bağlamı kullanarak cevap üretir

### 2️⃣ Fine-Tuning (LoRA)
- Gemma-2B-IT modeli LoRA (PEFT) ile fine-tune edilmiştir
- Eğitim verisi QA (Soru–Cevap) formatındadır
- Model, yönetmeliğe özel cevap üretmeyi öğrenir
- Bilgi olmayan sorular için “bilgi yok” cevabı öğretilmiştir

### 3️⃣ Hybrid (RAG + Fine-Tuning)
- Önce RAG ile bağlam getirilir
- Ardından fine-tuned model bu bağlam üzerinden cevap üretir
- En kontrollü ve en doğru yaklaşımı temsil eder

# 🛠️ Kullanılan Teknolojiler

- **Python 3**
- **HuggingFace Transformers**
- **Gemma-2B-IT (Open Source LLM)**
- **PEFT (LoRA)**
- **Sentence-Transformers**
- **Gradio**
- **PyTorch**
