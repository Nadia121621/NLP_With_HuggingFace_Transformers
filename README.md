<h1 align="center"> NLP With HuggingFace Transformers </h1>
<p align="center"> Berisi tentang pipeline dari HuggingFace Transformers untuk keperluan NLP (Natural Language Processing)  </p>

<div align="center">

<img src="https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue">

<img src="https://img.shields.io/badge/Jupyter-F37626.svg?&style=for-the-badge&logo=Jupyter&logoColor=white">


</div>

<h2 align="center"> Analisis </h2>
*   Kode pipeline zero-shot classification dari pustaka Transformers untuk mengklasifikasikan teks tanpa pelatihan ulang pada label khusus. Pipeline dikonfigurasi untuk menentukan kategori teks yang berbunyi "This is a course about the Transformers library" di antara label kandidat "education," "politics," dan "business."

*   Kode ini menggunakan pipeline zero-shot classification dari pustaka Transformers untuk mengklasifikasikan teks `"Segitiga Bermuda adalah sebuah wilayah di bagian barat Samudra Atlantik Utara"` dengan label kandidat tunggal, yaitu `"education"`. Meskipun konteks teks ini lebih berkaitan dengan geografi atau pengetahuan umum, model tetap akan mencoba mengaitkannya dengan label `"education"` karena itu satu-satunya pilihan yang diberikan.
Alasannya adalah zero-shot classification bekerja dengan mencoba menemukan hubungan antara teks dan label yang disediakan, bahkan jika label tersebut tidak langsung berkaitan dengan topik teks. Dalam kasus ini, meskipun teks mengenai Segitiga Bermuda lebih terkait dengan informasi geografis, model dapat menganggapnya sebagai bagian dari "education" dalam konteks pengetahuan umum. Karena hanya ada satu label, hasilnya mungkin menampilkan skor tinggi untuk "education," meskipun kecocokannya dengan topik pendidikan mungkin tidak terlalu kuat.
*   Input Teks dan Label Kandidat
Pipeline menerima teks "Pak Prabowo menjadi presiden ke-8 Republik Indonesia" dengan satu label kandidat, yaitu ["politics"]. Karena topik teks berkaitan dengan politik, model diprediksi akan memberikan skor tinggi pada label ini.
*   generator = pipeline("text-generation")
Baris ini membuat pipeline untuk tugas text generation, yang bertujuan menghasilkan teks yang melanjutkan teks awal yang diberikan. Model ini biasanya menggunakan model pre-trained seperti GPT-2 atau model lain yang dilatih untuk memprediksi kata atau frasa berikutnya dalam suatu kalimat atau paragraf.
*   generator("In this course, we will teach you how to")
Pipeline ini digunakan untuk menghasilkan teks lanjutan dari frasa "In this course, we will teach you how to". Model akan mencoba melanjutkan teks ini dengan kata-kata atau frasa yang dianggap paling mungkin mengikuti konteks kalimat awal.
*   Teks Input dan Parameter Lanjutan
1.   "In this course, we will teach you how to": Frasa ini menjadi teks awal yang akan dilanjutkan oleh model.
2.   max_length=30: Membatasi panjang teks yang dihasilkan hingga maksimal 30 token, termasuk teks input. Ini mengontrol seberapa panjang keluaran yang diinginkan.
3.  num_return_sequences=2: Menentukan bahwa model harus menghasilkan 2 teks lanjutan yang berbeda. Ini berguna untuk melihat variasi hasil dari model.
*   Pipeline Text Generation dengan Model DistilGPT-2
Pipeline dibuat untuk menghasilkan teks, dengan menggunakan model DistilGPT-2. DistilGPT-2 adalah versi ringan dari GPT-2 yang tetap mempertahankan performa baik dalam menghasilkan teks, namun lebih efisien dan cepat.
*   Pipeline Fill-Mask
Pipeline fill-mask digunakan untuk memprediksi kata atau frasa yang tersembunyi dalam teks. Pipeline ini memanfaatkan model seperti BERT atau RoBERTa, yang dilatih untuk memahami konteks kalimat dan memprediksi kata yang paling cocok untuk menggantikan mask.
*   Pipeline Named Entity Recognition (NER)
Pipeline ner digunakan untuk melakukan named entity recognition, yaitu tugas NLP yang mengidentifikasi dan menandai entitas penting dalam teks, seperti nama orang, lokasi, organisasi, dll.
*   Parameter grouped_entities=True
Parameter ini menginstruksikan pipeline untuk mengelompokkan entitas yang terkait dalam satu kategori. Misalnya, jika suatu nama terdiri dari dua kata seperti "Infinite Learning," pipeline akan mengelompokkan keduanya sebagai satu entitas tunggal untuk kategori organisasi.
*   Pipeline Question Answering
Pipeline question-answering digunakan untuk menjawab pertanyaan berdasarkan konteks yang diberikan. Model yang digunakan adalah DistilBERT, yang terlatih untuk memahami teks dan menjawab pertanyaan dengan akurat.
*   Input Konteks dan Pertanyaan
- context: Teks yang menjelaskan tentang air.
- question: Pertanyaan "Apa itu air?" yang ditujukan untuk mendapatkan informasi dari konteks.
*   Eksekusi Pipeline
Kode memanggil pipeline dengan memberikan question dan context. Model kemudian akan mencari jawaban yang relevan dari konteks.
*    Input Teks
Teks yang dianalisis adalah "The model was so great! I think I'm going to choose other". Kalimat ini berisi ekspresi positif terhadap suatu model, tetapi bagian "I think I'm going to choose other" dapat menunjukkan keraguan atau pertimbangan untuk memilih alternatif.
*    Pipeline Summarization
Pipeline summarization digunakan untuk menghasilkan ringkasan dari teks panjang. Model ini dilatih untuk memahami konten dan mengidentifikasi informasi penting yang dapat disampaikan dalam bentuk ringkasan yang lebih pendek.
*    Pipeline Translation
Pipeline translation digunakan untuk menerjemahkan teks dari satu bahasa ke bahasa lain. Dalam hal ini, model yang digunakan adalah Helsinki-NLP/opus-mt-id-en, yang dirancang untuk menerjemahkan dari bahasa Indonesia (ID) ke bahasa Inggris (EN).

