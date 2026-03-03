# Praktikum 1 - User Management API

Praktikum ini adalah implementasi API sederhana menggunakan Spring Boot dan Java untuk mengelola data pengguna (Create, Read, Update, Delete). 

## Dokumentasi Web

1. Hasil ditampilan Web
   <img width="1920" height="1200" alt="Screenshot 2026-03-03 151559" src="https://github.com/user-attachments/assets/3ba0602d-7f5a-418d-ae09-445926c8957f" />
   
## Dokumentasi API

Base URL: http://localhost:8080  
   
1. Tambah User/Data(Create)
Menambahkan data user baru. ID akan *digenerate* secara otomatis dalam bentuk UUID.

* URL: /api/users
* Method: POST
* Request Body:
    

```json
    {
        "name": "Faris Naufal",
        "age": 21
    }
```
* Success Response (201 Created):


```json
    {
        "status": "success",
        "data": {
            "id": "e76af37e-8c0c-4ead-a191-94d57118d171",
            "name": "Faris Naufal",
            "age": 21
        }
    }
```

2. Ambil Semua Data User (Read All)
Menampilkan daftar seluruh user yang ada di dalam *database*.

* URL: /api/users
* Method: GET
* Success Response (200 OK):
    

```json
    {
        "status": "success",
        "data": [
            {
                "id": "db970f67-4689-422d-acc4-c4d8dca62eae",
                "name": "Sandi Ardhian",
                "age": 21
            },
            {
               "id": "e76af37e-8c0c-4ead-a191-94d57118d171",
                "name": "Faris Naufal",
                "age": 69
            }
        ]
    }
``` 

3. Ambil Detail User Spesifik (Read Detail)
Mencari dan menampilkan detail satu user berdasarkan ID.

* URL: /api/users/{db970f67-4689-422d-acc4-c4d8dca62eae}
* Method: GET
* URL Params: id=[String]
* Success Response (200 OK):
    
```json
    {
        "status": "success",
        "data": {
            "id": "db970f67-4689-422d-acc4-c4d8dca62eae",
            "name": "Sandi Ardhian",
            "age": 69
        }
    }
```   

4. Ubah Data User (Update)
Memperbarui data nama dan/atau umur dari user yang sudah ada.

* URL: /api/users/{db970f67-4689-422d-acc4-c4d8dca62eae}
* Method: PUT
* URL Params: id=[String]
* Request Body:
    
```json
    {
        "name": "Sando Mendo",
        "age": 69
    }
``` 
* Success Response (200 OK):



```json
    {
        "status": "success",
        "data": {
            "id": "db970f67-4689-422d-acc4-c4d8dca62eae",
            "name": "Sando Mendo",
            "age": 69
        }
    }
```   

5. Hapus Data User (Delete)
Menghapus data user secara permanen dari *database*.

* URL: /api/users/{db970f67-4689-422d-acc4-c4d8dca62eae}
* Method: DELETE
* URL Params: id=[String]
* Success Response (200 OK):
    

```json
    {
        "status": "success delete user with id db970f67-4689-422d-acc4-c4d8dca62eae"
    }
```
