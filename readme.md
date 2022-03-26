# Introduction to Django - HSI Sandbox

Repositori ini sebagai dokumentasi progress pembelajaran melalui materi (Introduction to Django)[https://www.youtube.com/watch?v=rHux0gMZ3Eg]

## Creating Your First Django Project

Bagian ini menjelaskan bagaimana menginisiasi _scaffolding_ server menggunakan Django. Tahap ini membutuhkan pengguna untuk telah menginstall Python (pemateri menyatakan supaya menggunakan versi terbaru). Di tahap ini pemateri menyarankan agar menggunakan editor VS Code supaya mampu mengikuti materi yang akan disampaikan.

Untuk membuat _web server_ dengan Django, langkah berikut ini perlu dijalankan:
1. _Install_ `pipenv` dengan `pip install pipenv`
2. Buat direktori untuk menampung _source code web server_. Selanjutnya direktori ini akan disebut dengan _base directory_
3. _Install_ `django` untuk virtual environment di _base directory_ dengan menjalankan `pipenv install django` di _base directory_
    ![django](writeup/image/django_installation.png)

4. Untuk selanjutnya, versi python yang digunakan untuk pengembangan _web server_ adalah versi yang tersimpan di virtual environment (venv) yang telah dibuat. Selanjutnya, versi python ini akan disebut dengan _versi lokal_. Di VS Code, ini bisa dilakukan dengan men-_setting_ Python Interpreter yang digunakan dengan versi yang tersimpan di venv. Caranya dengan membuka _command palette_ dan pilih `Python: Select Interpreter` kemudian mengisi/memilih versi Python di direktori venv. Apabila tidak menggunakan VS Code (atau memilih untuk tidak menggunakan fitur dari VS Code), hal ini bisa dilakukan dengan menjalankan `pipenv shell` di _base directory_.
5. Pastikan Django telah terinstall dengan menjalankan `django-admin`
6. Buat _scaffolding_ server di _base directory_ dengan menjalankan `django-admin startproject <nama project> <base directory>`. Misalkan, `django-admin startproject storefront .` Apabila langkah ini dijalankan dengan benar, sebuah file bernama _manage.py_ dan folder bernama sesuai dengan nama project yang dientrikan akan muncul di _base directory_. File _manage.py_ berisi _command_ yang sama dengan `django-admin` dan beberapa _command_ lainnya
7. Pastikan semua berjalan dengan baik dengan menjalankan `python manage.py runserver [<port>]`. Secara default `port` akan bernilai 8000. Setelah menjalankan command tersebut, buka browser ke alamat `127.0.0.1:8000`. Jika semua proses berjalan dengan benar, sebuah laman yang mengatakan instalasi Django telah berhasil akan muncul
![first_page](writeup/image/run_development_server.PNG)