---
layout: post
title: "Instalasi Rouge untuk Highligter Jekyll "
date: 2018-08-08 10:47:00 +0900
categories: Jekyll Web
img_path: assets/img/post/080818.svg
---

Rouge highlighter merupakan pewarna potongan kode program bawaan jekyll yang mengenali kurang lebih 135 bahasa komputer. Tulisan ini merupakan dokumentasi bagaimana cara menginstal, mengkonfigurasi dan menggunakan rouge highlighter.   

_coba perhatikan potongan kode program dibawah ini. Tanpa rouge highlighter_ : 
{:.my-1}
<pre>
statusApp() {
	if [[ $APP_STATUS = 1 ]]; then 
		echo "$APP_NAME is running with PID : $OLD_PID, OLD_PID : `cat $FILE_PID` ."
	else 
		echo "$APP_NAME is not running."
	fi
}
</pre>

_bedakan dengan yang menggunakan rouge highlighter_ : 
{:.my-1}
{% highlight BASH %}
statusApp() {
	if [[ $APP_STATUS = 1 ]]; then 
		echo "$APP_NAME is running with PID : $OLD_PID, OLD_PID : `cat $FILE_PID` ."
	else 
		echo "$APP_NAME is not running."
	fi
}
{% endhighlight %}

Selain potongan kode program terlihat lebih indah dengan warna, tujuan lain dari menggunakan kode higlighter adalah untuk kemudahan dalam mengidetifikasi bagian-bagian program seperti _function_, _variabel_, _kondisi_ dan _data_.     

##### Instalasi rouge 
Instalasi dilakukan melalui _command line interface_, dengan menggunakan perintah :  
{:.my-1}
{% highlight POWERSHELL %}
gem install rouge 
{% endhighlight %}

##### Konfigurasi
Ubah konfigurasi yang ada pada fail `_config.yml` dengan menambahkan baris berikut : 
{:.my-1}
{% highlight YAML %}
highlighter: rouge
{% endhighlight %}

Setelah `highlighter: rouge` ditambahkan, langkah selanjutnya adalah memilih tema atau style rouge sesuai dengan yang diinginkan. 

Untuk melihat daftar tema atau style rouge yang tersedia gunakan perintah : 
{:.my-1}
{% highlight POWERSHELL %}
rougify help style
{% endhighlight %}

`tema yang tersedia : base16, base16.dark, base16.light, base16.monokai, base16.monokai.dark, base16.monokai.light, base16.solarized, base16.solarized.dark, base16.solarized.light, colorful, github, gruvbox, gruvbox.dark, gruvbox.light, igorpro, molokai, monokai, monokai.sublime, pastie, thankful_eyes, tulip`

Pilih salah satu tema yang tersedia kemudian konfersi menjadi fail css ke dalam folder asset.  
{:.my-1}
{% highlight POWERSHELL %}
rougify style pastie > assets/css/syntax.css
{% endhighlight %}

Setelah fail css dari tema rouge dikonfersi, tambahkan tema tersebut ke dalam kode html diantara tag `<head>` dan `</head>`. 
{:.my-1}
{% highlight HTML %}
<link rel="stylesheet" href="{{site.baseurl}}/assets/style/css/syntax.css">
{% endhighlight %}

##### Menggunakan rouge 
Untuk menggunakan rouge highlitter tulisan code, seperti contoh kode berikut :
{:.my-1}

{% highlight LIQUID %}
{% raw %}
{% highlight HTML %}
    //kodenya masukkan disini
{% endhighlight %}
{% endraw %}
{% endhighlight %}

##### Daftar Pustaka 
[1. Jekyllrb](https://jekyllrb.com/docs/templates/#code-snippet-highlighting){:target="new"}<br>
[2. Syntax Highlighting in Jekyll With Rouge](https://sacha.me/articles/jekyll-rouge/){:target="new"}<br>
[3. Add Syntax Highlighting to your Jekyll site with Rouge](https://bnhr.xyz/2017/03/25/add-syntax-highlighting-to-your-jekyll-site-with-rouge.html){:target="new"}<br>
[](){:target="new"}<br>