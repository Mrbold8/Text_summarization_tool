# Монгол хэлний Text Summarization Model -ууд

Монгол хэл дээр **Text Summarization**, **Title Generation**, **Keywords Extraction** task -уудад зориулан fine-tuning хийсэн 5 model -ийг энэхүү repo -д оруулсан. Model -уудыг **PEFT / LoRA** аргачлалаар өөрийн бэлдсэн монгол хэлний dataset дээр fine-tuning хийж, гүйцэтгэлийг сайжруулсан.

---

## 📄 Судалгааны ажлын тайлан

[![Тайланг харах (PDF)](https://github.com/Mrbold8/Text_summarization_tool/blob/main/%D0%A1%D1%83%D0%B4%D0%B0%D0%BB%D0%B3%D0%B0%D0%B0%D0%BD%D1%8B_%D0%B0%D0%B6%D0%B8%D0%BB.pdf)

---

## Dataset

Монгол хэлний бичвэр болон хураангуйгаас бүрдэх dataset боловсруулж, CNN/DailyMail dataset -ийг Google Batch Translate ашиглан монгол хэл рүү хөрвүүлэн хэмжээг нэмэгдүүлсэн. Дараа нь гарчиг болон түлхүүр үг үүсгэн dataset -ээ баяжуулсан.

Dataset холбоосууд:

- https://huggingface.co/datasets/amaraaa/mn_translated_cnn_extended  
- https://huggingface.co/datasets/amaraaa/multi-task_mn_cnn_v02  

---

## Fine-tuned Model-ууд

### 1. mT5-small summarization (LoRA)
Encoder–Decoder architecture бүхий model.  
**RougeLsum:** ~13.8  
**HF:** https://huggingface.co/amaraaa/mt5-small-summarization-mn-v1  

---

### 2. mT5-base summarization (LoRA)
Илүү том model тул монгол текстийн утга, найруулгыг илүү сайн гаргана.  
**RougeLsum:** ~18.57  
**HF:** https://huggingface.co/amaraaa/mt5-base-summarization-mn-v1  

---

### 3. mBART-50-large summarization (LoRA)
Монгол хэл дээр хамгийн өндөр гүйцэтгэл үзүүлсэн model.  
**RougeLsum Test:** ~31.47  
**HF:** https://huggingface.co/amaraaa/mbart50-mn-summarization_v2  

---

### 4. mongolian-gpt2 summarization (LoRA)
Decoder-only architecture бүхий туршилтын summarization model.  
**HF:** https://huggingface.co/amaraaa/gpt2-summarization-mn-v1  

---

### 5. Multitask mT5-base (Summarization + Title + Keywords)
Summarization, Title generation, Keywords extraction task -уудыг нэг model дээр зэрэг сургаж fine-tuning хийсэн хувилбар.  
**HF:** https://huggingface.co/amaraaa/multitask-mt5-base-mn-v1  

---

## Ашигласан технологи

- HuggingFace, Google Colab
- Transformers, Datasets, PEFT-LoRA  
- Google Batch Translate  
- Hugging Face Inference Endpoint  
- Next.js, React, TypeScript  
- AWS Deployment  

---

## Товч дүгнэлт

Model -уудаас **facebook/mBART-50-large** болон **google/mT5-Base** Монгол хэл дээр хамгийн өндөр чанартай хураангуй үүсгэсэн. Бусад model -ууд мөн сайн гүйцэтгэлтэй бөгөөд Multitask хувилбар нь нэг model -оор олон task гүйцэтгэх боломжтой.

---
