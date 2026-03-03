DOKUMEN API

Proyek ini adalah implementasi RESTful API sederhana menggunakan Spring Boot dan Java untuk mengelola data pengguna (Create, Read, Update, Delete). 

## 🛠️ Teknologi yang Digunakan
* Backend: Spring Boot, Spring Web
* Database Access: Spring Data JPA
* Utility: Lombok
* Format Data: JSON

## 🚀 Cara Menjalankan Aplikasi
1.  Pastikan koneksi *database* (seperti MySQL) sudah berjalan dan sesuai dengan pengaturan di application.properties.
2.  Buka proyek menggunakan IDE (IntelliJ IDEA / Eclipse / VS Code).
3.  Jalankan *file* utama Praktikum1Application.java.
4.  Secara bawaan (*default*), *server* akan berjalan di http://localhost:8080.

*(Catatan: Endpoint di bawah ini sudah dikonfigurasi dengan CORS sehingga aman untuk diakses dan dihubungkan langsung dengan antarmuka Frontend seperti HTML/AJAX).*

---

## 📚 Dokumentasi API

Base URL: http://localhost:8080  
Content-Type: application/json

### 1. Tambah Data User Baru (Create)
Menambahkan data user baru. ID akan *digenerate* secara otomatis dalam bentuk UUID.

* URL: /api/users
* Method: POST
* Request Body:

```json
    {
        "name": "Sandy A",
        "age": 19
    }
```
* Success Response (201 Created):
  
```json
    {
        "status": "success",
        "data": {
            "id": "f8f81155-caf3-482c-83b6-55f5c07f1a73",
            "name": "Sandy A",
            "age": 19
        }
    }
```

### 2. Ambil Semua Data User (Read All)
Menampilkan daftar seluruh user yang ada di dalam *database*.

* URL: /api/users
* Method: GET
* Success Response (200 OK):
  
```json
    {
        "status": "success",
        "data": [
            {
                "id": "a528ca8f-94a4-42a5-bb20-2a828ee4ad46",
                "name": "Sandy A",
                "age": 19
            }
        ]
    }
```

### 3. Ambil Detail User Spesifik (Read Detail)
Mencari dan menampilkan detail satu user berdasarkan ID.

* URL: /api/users/{id}
* Method: GET
* URL Params: id=[String]
* Success Response (200 OK):
```json
    {
        "status": "success",
        "data": {
            "id": "a528ca8f-94a4-42a5-bb20-2a828ee4ad46",
            "name": "Farez Kopling",
            "age": 20
        }
    }
```

### 4. Ubah Data User (Update)
Memperbarui data nama dan/atau umur dari user yang sudah ada.

* URL: /api/users/{id}
* Method: PUT
* URL Params: id=[String]
* Request Body:
```json
    {
        "name": "Farez Kopling Update",
        "age": 20
    }
``` 
* Success Response (200 OK):

```json
    {
        "status": "success",
        "data": {
            "id": "a528ca8f-94a4-42a5-bb20-2a828ee4ad46",
            "name": "Farez Kopling Update",
            "age": 22
        }
    }
```

### 5. Hapus Data User (Delete)
Menghapus data user secara permanen dari *database*.

* URL: /api/users/{id}
* Method: DELETE
* URL Params: id=[String]
* Success Response (200 OK):

``` json
    {
        "status": "success delete user with id 123e4567-e89b-12d3-a456-426614174000"
    }

Scrrenshot Web :
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8f32165d-83f7-4ad8-a347-43447a3aa61b" />
