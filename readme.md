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

## Creating Your First App - Writing Views

Django dibangun di atas _app_. Setiap _app_ menyajikan sebuah fungsionalitas yang spesifik. Sebuah project Django bisa memiliki banyak _app_.

Untuk menginisiasi sebuah app baru, jalankan command `python manage.py appstart <nama app>`. Sebuah direktori baru akan dibuat yang bernama `<nama app>`. Direktori ini adalah sebuah modul dengan struktur berikut.

![app_structure](writeup/image/app_structure.PNG)

Direktori ini berisikan hal berikut:
1. Folder _migrations_, berfungsi untuk men-setup database
2. File \_\_init\_\_.py, digunakan sebagai penanda untuk Python bahwa direktori ini adalah sebuah modul
3. File admin.py, digunakan untuk mengatur interface administrator dari app tersebut
4. File apps.py, berfungsi sebagai pusat konfigurasi app
5. File models.py, berisi definisi struktur data (i.e. model dalam MVC) dalam bentuk class
6. File tests.py, berisi unit test untuk app tersebut
7. File views.py, berisi bagaimana app digunakan untuk memberikan respon atas request yang datang

"View" pada framework Django tidak sama dengan "view" pada konsep arsitektur sistem pada umumnya (e.g. MVC, MVVM). "View" pada framework Django lebih tepat disebut dengan "Response Handler", sedangkan "view" pada konsep arsitektur pada umumnya adalah sebuah interface yang dapat dilihat oleh pengguna.

View dibuat dengan mendefinisikan sebuah fungsi pada file _views.py_. Fungsi ini akan me-return response yang akan dikirim ke client. Salah satu nilai yang bisa digunakan sebagai nilai return fungsi view adalah class `django.http.HttpResponse`

![](writeup/image/playground_views.PNG)