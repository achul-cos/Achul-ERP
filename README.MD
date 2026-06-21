# Achul ERP

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white)

Project ini adalah proyek pembelajaran [Nasrullah (Achul)](https://www.github.com/achul-cos) pada pengembangan Aplikasi Enterprise Resource Planning (ERP) menggunakan platform [Odoo](https://www.odoo.com).

Pengembangan aplikasi ERP dengan menggunakan Odoo sebagai platformnya, menghasilkan modul-modul kostum yang dapat diinstal pada platform Odoo perusahaan.

## Table Of Contents

- [Achul ERP](#achul-erp)
    - [Table Of Content](#table-of-contents)
    - [Requirments](#requirements)
    - [Installation](#installation)
        - [Installation Achul ERP](#installation-achul-erp)
        - [Installation Odoo](#installation-odoo)
        - [Installation Python Virtual Environment and Packages](#installation-python-virtual-environment)
    - [Configuration](#configuration)
        - [Odoo Configuraion](#odoo-configuration)
    - [Usage](#usage)

## Requirements

Untuk dapat menginstall dan menggunakan projet ini, pada perangkat anda diperlukan menginstall perangkat lunak sebagai berikut:

| Nama | Versi | Keterangan |
|------|-------|------------|
| Python | 3.8 | Disarankan menggunakan pada versi ini|
| PostgresSQL| 13 | Disarankan menggunakan pada versi ini dengan locale en-us|

## Installation

Instalasi proyek ini dilakukan bertahap dimulai melakukan cloning proyek ini, serta proyek odoo sebagai platfrom dari costume model dari Achul ERP.

### Installation Achul ERP

```sh
$ npm git clone https://github.com/achul-cos/achul-erp
```

### Installation Odoo

Setelahnya masuk kedalam folder proyek:

```sh
$ cd Achul-ERP
```

Lalu cloning proyek odoo dari github odoo pada versi 14.0

```sh
$ git clone -b 14.0 https://github.com/odoo/odoo.git
```

### Installation Python Virtual Environment 

Sangat disarankan menggunakan python virtual environment untuk menjalan proyek ini, maka kita akan membuat python virtual environment pada proyek ini,

```sh
$ py -m venv venv
$ ./venv/scripts/activate
```

Setelahnya kita akan melakukan instalasi pada beberapa module atau package python untuk menjalankan Odoo. Sebenarnya dari odoo sendiri sudah menyediakan requirements.txt untuk daftar-daftar modul dan package yang perlu diinstall. Tetapi aku menyarankan kalian menginstall requirements.txt yang disediakan pada proyek ini, karena pada beberapa kondisi, requirements.txt dapat tidak kompatibel dengan versi python 3.8.

```sh
$ pip install -r requirements.txt
```

## Configuration

Setelah melakukan instalasi pada proyek ini, selanjutnya kita melakukan konfigurasi untuk dapat menjalankan proyek ini:

### Odoo Configuration

Silahkan duplikat file [Example Odoo Conf File](odoo_config.example.CONF) menjadi file odoo_config.conf.

Serta buat file log pada proyek yaitu odoo.log.

Isi konfigurasi penting ini pada file konfigurasi odoo:

```conf
addons_path = 
db_password = 
db_user = 
pg_path =
logfile = 
```

Sebagai contoh,

```conf
addons_path = C:\achul-erp\odoo\addons,C:\achul-erp\odoo\odoo,C:\achul-erp\odoo\odoo\addons, C:\achul-erp\achul-erp-module
db_password = root # password db_user postgres 
db_user = root # user postgress
pg_path = C:\Program Files\PostgreSQL\13\bin # Lokasi Postgress Di PC anda
logfile = C:\achul-erp\odoo.log
```

## Usage

Untuk menggunakan proyek ini, sebelumnya jangan lupa untuk memastikan bahwa Postgres anda sudah menyala dan anda sudah menginstall python sesuai versinya dan telah menambahkannya pada envrionment variables di PC anda.

```sh
$ py ./odoo/odoo-bin -c odoo_config.conf
```

Setelahnya akses di browser anda

htpp://localhost:8088

Silahkan lakukan manajemen database odoo anda, serta setelah melakukan login didalam aplikasi, silahkan cari apps Achul ERP.
