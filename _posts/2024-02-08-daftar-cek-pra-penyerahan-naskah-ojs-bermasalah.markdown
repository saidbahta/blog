---
title: Daftar Cek Pra-Penyerahan Naskah OJS Tidak Bisa Tambah
date: 2024-02-08 17:36:31 +0900
categories: dokumentasi
img_path: assets/img/post/noimage.svg
layout: post
---

Barusan ingin menambahkan "Daftar Cek Pra Penyerahan Naskah" di OJS, sayangnya beberapa kali ditambahkan selalu tidak tersimpan. Setelah dicari, ada yang menyarankan untuk menghapus `submissionChecklist` dalam tabel `journal_settings`, namun setelah dihapus masih tetap tidak bisa menambahkan daftar cek. 

Jika tidak bisa, coba cara yang saya lakukan. Dengan menambahkan "Daftar Cek Pra Penyerahan Naskah" secara manual langsung ke database pada kolom `setting_value` setelah kolom `submissionChecklist` dengan isi seperti teks dibawah :

{% highlight MySQL %}
[{"order":1,"content":"Naskah yang disubmit belum pernah diterbitkan sebelumnya"}]
{% endhighlight %}

Setelah diisi, coba refresh kembali halaman "Daftar Cek" di browser lalu coba tambah item. Jika kasusnya sama persis dengan saya maka seharusnya sudah bisa ditambahkan. 

#### Referensi : 
[[1] &nbsp; Cannot Edit "Submission Preparation..."](https://forum.pkp.sfu.ca/t/cannot-edit-submission-preparation-checklist-in-workflow-settings/77161/4){:target="new"}<br>