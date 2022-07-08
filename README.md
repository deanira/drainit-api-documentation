# DRAINIT

Microservices

## Acknowledgements

 - Dranit-Backend using Laravel
 - Drainit-Frontend using Laravel
 - Drainit-GIS using Laravel
 - Drainit-User using Golang
 
 
# API DOCUMENTATION




## DRAINIT USER

[Endpoint Documentation](https://documenter.getpostman.com/view/14644426/UzJJvHrY)


### API Response

#### Register masyarakat

```json
  {
    "status": 200,
    "message": "Success",
    "data": {
        "alamat": "Jalan Geso",
        "email": "joko@gmail.com",
        "id": "1e96451b-e537-4bd4-9057-8ba80a7fa7f7",
        "nama": "Indah",
        "telepon": "082392074446"
    }
  }
```

#### Login Masyarakat/Admin/Petugas
##### Masyarakat
```json
  {
    "id_masyarakat": "id",
    "token": "jwt token"
  }
```
##### Petugas
```json
  {
    "id_petugas": "id",
    "token": "jwt token"
  }
```
##### Admin
```json
  {
    "id_admin": "id",
    "token": "jwt token"
  }
```

#### Update Masyarakat/Petugas
##### Masyarakat
```json
  {
    "status": 200,
    "message": "Success",
    "data": {
        "alamat": "Jalan Geso",
        "id": "1e96451b-e537-4bd4-9057-8ba80a7fa7f7",
        "nama": "joko",
        "rows_affected": 1,
        "tanggal_lahir": "1999-12-17",
        "telepon": "088888888888"
    }
  }
```
##### Petugas
```json
  {
    "status": 200,
    "message": "Success",
    "data": {
        "alamat": "Jalan Santai",
        "email": "joko@gmail.com",
        "id": "0f869432-8e61-495b-9a68-1dd4a7137ce8",
        "nama": "Joko",
        "rows_affected": 1,
        "status": "ON_DUTY",
        "tanggal_lahir": "1975-12-05",
        "telepon": "088888888888"
    }
  }
```

#### Profile Masyarakat/Admin/Petugas

##### Masyarakat
```json
  {
    "status": 200,
    "message": "Success",
    "data": {
        "id": "1e96451b-e537-4bd4-9057-8ba80a7fa7f7",
        "nama": "Indah",
        "email": "indah@gmail.com",
        "telepon": "082392074443",
        "alamat": "Jalan Geso",
        "tanggal_lahir": "1975-12-05T00:00:00Z",
        "foto": "https://king-prawn-app-hxran.ondigitalocean.app/avatar/masyarakat/default.png"
    }
  }
```
##### Petugas
```json
  {
    "status": 200,
    "message": "Success",
    "data": {
        "id": "0f869432-8e61-495b-9a68-1dd4a7137ce8",
        "nama": "Joko",
        "telepon": "088888888888",
        "email": "joko@gmail.com",
        "status": "ON_DUTY",
        "tanggal_lahir": "1975-12-05T00:00:00Z",
        "alamat": "Jalan Santai",
        "foto": "https://king-prawn-app-hxran.ondigitalocean.app/avatar/petugas/0f869432-8e61-495b-9a68-1dd4a7137ce8.jpg"
    }
  }
```
##### Admin
```json
  {
    "status": 200,
    "message": "Success",
    "data": {
        "id": "a7451150-bd84-11ec-b1c9-005056c00001",
        "email": "admin@gmail.com",
        "nama": "admin",
        "foto": "https://king-prawn-app-hxran.ondigitalocean.app/avatar/admin/a7451150-bd84-11ec-b1c9-005056c00001.jpg"
    }
  }
```

#### Change Password Masyarakat/Admin/Petugas
```json
  {
    "status": 200,
    "message": "Success",
    "data": "Password has succesfully changed!"
  }
```

#### Change Avatar Masyarakat/Admin/Petugas
format base64: `"data:image/" . $imageFileType . ";base64," . base64_encode($data)` <br>
ex: `"data:image/jpeg;base64,/9j/4AAQSkZJRgA....."`
```json
  {
    "status": 200,
    "message": "Success",
    "data": {
        "message": "Avatar changed successfully"
    }
  }
```

## DRAINIT (LAPORAN, MENANGANI, PEMBARUAN PENGADUAN, DRAINASE, TITIK BANJIR, TITIK DRAINASE RUSAK)

[Endpoint Documentation](https://documenter.getpostman.com/view/14644426/UVsSMiTX)

### API Response

#### Post pengaduan banjir

```json
  {
    "message": "Added Successfully!",
    "data": {
        "nama_jalan": "Jalan Sudirman",
        "foto": "no-picture.png",
        "deskripsi": "banjir 2 meter",
        "geometry": "{\"type\": \"Point\", \"coordinates\": [101.415468, 0.584255]}",
        "id_masyarakat": "a40dd247-4b65-40fa-9a5a-47b75a2592ce",
        "tipe": "Banjir",
        "status": "NOT_YET_VERIFIED",
        "id": "7fa15fde-b09d-4149-bfc5-86ed146060c1",
        "updated_at": "2022-07-07T09:43:20.000000Z",
        "created_at": "2022-07-07T09:43:20.000000Z"
    },
    "status_code": 201
  }
```

#### Post pengaduan drainase rusak

```json
  {
    "message": "Added Successfully!",
    "data": {
        "nama_jalan": "Jalan Sudirman",
        "foto": "no-picture.png",
        "deskripsi": "beton sudah pecah",
        "geometry": "{\"type\": \"Point\", \"coordinates\": [101.415468, 0.584255]}",
        "id_masyarakat": "a40dd247-4b65-40fa-9a5a-47b75a2592ce",
        "tipe": "Drainase Rusak",
        "status": "NOT_YET_VERIFIED",
        "id": "3b7c7389-215c-43a2-b5c7-c903d65ccf4f",
        "updated_at": "2022-07-07T09:44:20.000000Z",
        "created_at": "2022-07-07T09:44:20.000000Z"
    },
    "status_code": 201
  }
```

#### Detail pengaduan
Role == masyarakat
```json
  {
    "id": "7fa15fde-b09d-4149-bfc5-86ed146060c1",
    "id_masyarakat": "a40dd247-4b65-40fa-9a5a-47b75a2592ce",
    "nama_pelapor": "Deanira",
    "id_admin": null,
    "nama_admin": null,
    "nama_jalan": "Jalan Sudirman",
    "foto": "no-picture.png",
    "tipe": "BANJIR",
    "deskripsi": "banjir 2 meter",
    "status": "ON_PROGRESS",
    "feedback_masyarakat": null,
    "created_at": "2022-07-07T09:43:20.000000Z",
    "updated_at": "2022-07-07T09:50:29.000000Z",
    "geometry": "{\"type\": \"Point\", \"coordinates\": [101.415468, 0.584255]}",
    "petugas": [
        {
            "id": "f8079487-6224-4ac2-a487-a021df9aa33a",
            "id_petugas": "0f869432-8e61-495b-9a68-1dd4a7137ce8",
            "nama_petugas": "Joko"
        }
    ],
    "upvote": 0,
    "downvote": 0
    "vote": null
  }
```
Role != masyarakat
```json
  {
    "id": "7fa15fde-b09d-4149-bfc5-86ed146060c1",
    "id_masyarakat": "a40dd247-4b65-40fa-9a5a-47b75a2592ce",
    "nama_pelapor": "Deanira",
    "id_admin": null,
    "nama_admin": null,
    "nama_jalan": "Jalan Sudirman",
    "foto": "no-picture.png",
    "tipe": "BANJIR",
    "deskripsi": "banjir 2 meter",
    "status": "ON_PROGRESS",
    "feedback_masyarakat": null,
    "created_at": "2022-07-07T09:43:20.000000Z",
    "updated_at": "2022-07-07T09:50:29.000000Z",
    "geometry": "{\"type\": \"Point\", \"coordinates\": [101.415468, 0.584255]}",
    "petugas": [
        {
            "id": "f8079487-6224-4ac2-a487-a021df9aa33a",
            "id_petugas": "0f869432-8e61-495b-9a68-1dd4a7137ce8",
            "nama_petugas": "Joko"
        }
    ],
    "upvote": 0,
    "downvote": 0
  }
```

#### Assign petugas
```json
  {
    "message": "Added Successfully!",
    "data": {
        "id_pengaduan": "7fa15fde-b09d-4149-bfc5-86ed146060c1",
        "id_petugas": "0f869432-8e61-495b-9a68-1dd4a7137ce8",
        "id_admin": "a7451150-bd84-11ec-b1c9-005056c00001",
        "id": "f8079487-6224-4ac2-a487-a021df9aa33a",
        "updated_at": "2022-07-07T09:50:29.000000Z",
        "created_at": "2022-07-07T09:50:29.000000Z"
    },
    "status_code": 201
  }
```

#### Post Pembaruan pengaduan
##### Success
```json
  {
    "message": "Added Successfully!",
    "data": {
        "judul": "Mengumpulkan petugas kuning",
        "deskripsi": "Laporan ini membutuhkan sekitar 10 petugas kuning",
        "id_petugas": "0f869432-8e61-495b-9a68-1dd4a7137ce8",
        "foto": "tidak ada",
        "id": "3fca6068-854b-46b5-bed0-9b58c409596a",
        "updated_at": "2022-07-07T09:53:04.000000Z",
        "created_at": "2022-07-07T09:53:04.000000Z"
    },
    "status_code": 201
  }
```
##### Forbidden
```json
  {
    "message": "You don't have access",
    "status_code": 403
  }
```

#### Get riwayat petugas
```json
  {
    "data": [
        {
            "status": "ON_PROGRESS",
            "count": 1
        }
    ],
    "status_code": 200
  }
```

#### Get pengaduan by masyarakat

```json
  [ 
    {
        "id": "3b7c7389-215c-43a2-b5c7-c903d65ccf4f",
        "id_masyarakat": "a40dd247-4b65-40fa-9a5a-47b75a2592ce",
        "nama_pelapor": "Deanira",
        "nama_jalan": "Jalan Sudirman",
        "foto": "no-picture.png",
        "tipe": "DRAINASE RUSAK",
        "deskripsi": "beton sudah pecah",
        "status": "NOT_YET_VERIFIED",
        "created_at": "2022-07-07T09:44:20.000000Z",
        "updated_at": "2022-07-07T09:44:20.000000Z",
        "geometry": "{\"type\": \"Point\", \"coordinates\": [101.415468, 0.584255]}",
        "upvote": 0,
        "downvote": 0
    },
    {
        "id": "7fa15fde-b09d-4149-bfc5-86ed146060c1",
        "id_masyarakat": "a40dd247-4b65-40fa-9a5a-47b75a2592ce",
        "nama_pelapor": "Deanira",
        "nama_jalan": "Jalan Sudirman",
        "foto": "no-picture.png",
        "tipe": "BANJIR",
        "deskripsi": "banjir 2 meter",
        "status": "ON_PROGRESS",
        "created_at": "2022-07-07T09:43:20.000000Z",
        "updated_at": "2022-07-07T09:50:29.000000Z",
        "geometry": "{\"type\": \"Point\", \"coordinates\": [101.415468, 0.584255]}",
        "upvote": 0,
        "downvote": 0
    },
    {
        "id": "00bce130-8bdf-4bbc-8afc-5c0b562d6787",
        "id_masyarakat": "a40dd247-4b65-40fa-9a5a-47b75a2592ce",
        "nama_pelapor": "Deanira",
        "nama_jalan": "Jalan Sudirman",
        "foto": "no-picture.png",
        "tipe": "BANJIR",
        "deskripsi": "banjir 2 meter",
        "status": "NOT_YET_VERIFIED",
        "created_at": "2022-07-06T05:48:48.000000Z",
        "updated_at": "2022-07-06T05:48:48.000000Z",
        "geometry": "{\"type\": \"Point\", \"coordinates\": [101.415468, 0.584255]}",
        "upvote": 1,
        "downvote": 0
    }
  ]
```

#### Get pengaduan by petugas

```json
  [
    {
        "id": "7fa15fde-b09d-4149-bfc5-86ed146060c1",
        "id_masyarakat": "a40dd247-4b65-40fa-9a5a-47b75a2592ce",
        "nama_pelapor": "Deanira",
        "nama_jalan": "Jalan Sudirman",
        "foto": "no-picture.png",
        "tipe": "BANJIR",
        "deskripsi": "banjir 2 meter",
        "status": "ON_PROGRESS",
        "feedback_masyarakat": null,
        "created_at": "2022-07-07T09:43:20.000000Z",
        "updated_at": "2022-07-07T09:50:29.000000Z",
        "geometry": "{\"type\": \"Point\", \"coordinates\": [101.415468, 0.584255]}",
        "upvote": 0,
        "downvote": 0
    }
  ]
```

#### Get menangani by petugas

```json
  [
    {
        "id": "f8079487-6224-4ac2-a487-a021df9aa33a",
        "id_pengaduan": "7fa15fde-b09d-4149-bfc5-86ed146060c1",
        "id_petugas": "0f869432-8e61-495b-9a68-1dd4a7137ce8",
        "nama_petugas": "Joko",
        "id_admin": "a7451150-bd84-11ec-b1c9-005056c00001",
        "nama_admin": "admin",
        "created_at": "2022-07-07T09:50:29.000000Z",
        "updated_at": "2022-07-07T09:50:29.000000Z"
    }
  ]
```

#### Get pengaduan
##### sorted up and role == masyarakat
```json
  [
    {
        "id": "00bce130-8bdf-4bbc-8afc-5c0b562d6787",
        "id_masyarakat": "a40dd247-4b65-40fa-9a5a-47b75a2592ce",
        "nama_pelapor": "Deanira",
        "nama_jalan": "Jalan Sudirman",
        "foto": "no-picture.png",
        "tipe": "BANJIR",
        "deskripsi": "banjir 2 meter",
        "status": "NOT_YET_VERIFIED",
        "created_at": "2022-07-06T05:48:48.000000Z",
        "updated_at": "2022-07-06T05:48:48.000000Z",
        "geometry": "{\"type\": \"Point\", \"coordinates\": [101.415468, 0.584255]}",
        "upvote": 1,
        "downvote": 0,
        "vote": "UPVOTE"
    },
    {
        "id": "3b7c7389-215c-43a2-b5c7-c903d65ccf4f",
        "id_masyarakat": "a40dd247-4b65-40fa-9a5a-47b75a2592ce",
        "nama_pelapor": "Deanira",
        "nama_jalan": "Jalan Sudirman",
        "foto": "no-picture.png",
        "tipe": "DRAINASE RUSAK",
        "deskripsi": "beton sudah pecah",
        "status": "NOT_YET_VERIFIED",
        "created_at": "2022-07-07T09:44:20.000000Z",
        "updated_at": "2022-07-07T09:44:20.000000Z",
        "geometry": "{\"type\": \"Point\", \"coordinates\": [101.415468, 0.584255]}",
        "upvote": 0,
        "downvote": 0,
        "vote": null
    },
    {
        "id": "7fa15fde-b09d-4149-bfc5-86ed146060c1",
        "id_masyarakat": "a40dd247-4b65-40fa-9a5a-47b75a2592ce",
        "nama_pelapor": "Deanira",
        "nama_jalan": "Jalan Sudirman",
        "foto": "no-picture.png",
        "tipe": "BANJIR",
        "deskripsi": "banjir 2 meter",
        "status": "ON_PROGRESS",
        "created_at": "2022-07-07T09:43:20.000000Z",
        "updated_at": "2022-07-07T09:50:29.000000Z",
        "geometry": "{\"type\": \"Point\", \"coordinates\": [101.415468, 0.584255]}",
        "upvote": 0,
        "downvote": 0,
        "vote": null
    }
]
```
##### sorted down and role == masyarakat
```json
  [
    {
        "id": "3b7c7389-215c-43a2-b5c7-c903d65ccf4f",
        "id_masyarakat": "a40dd247-4b65-40fa-9a5a-47b75a2592ce",
        "nama_pelapor": "Deanira",
        "nama_jalan": "Jalan Sudirman",
        "foto": "no-picture.png",
        "tipe": "DRAINASE RUSAK",
        "deskripsi": "beton sudah pecah",
        "status": "NOT_YET_VERIFIED",
        "created_at": "2022-07-07T09:44:20.000000Z",
        "updated_at": "2022-07-07T09:44:20.000000Z",
        "geometry": "{\"type\": \"Point\", \"coordinates\": [101.415468, 0.584255]}",
        "upvote": 0,
        "downvote": 0,
        "vote": null
    },
    {
        "id": "7fa15fde-b09d-4149-bfc5-86ed146060c1",
        "id_masyarakat": "a40dd247-4b65-40fa-9a5a-47b75a2592ce",
        "nama_pelapor": "Deanira",
        "nama_jalan": "Jalan Sudirman",
        "foto": "no-picture.png",
        "tipe": "BANJIR",
        "deskripsi": "banjir 2 meter",
        "status": "ON_PROGRESS",
        "created_at": "2022-07-07T09:43:20.000000Z",
        "updated_at": "2022-07-07T09:50:29.000000Z",
        "geometry": "{\"type\": \"Point\", \"coordinates\": [101.415468, 0.584255]}",
        "upvote": 0,
        "downvote": 0,
        "vote": null
    },
    {
        "id": "00bce130-8bdf-4bbc-8afc-5c0b562d6787",
        "id_masyarakat": "a40dd247-4b65-40fa-9a5a-47b75a2592ce",
        "nama_pelapor": "Deanira",
        "nama_jalan": "Jalan Sudirman",
        "foto": "no-picture.png",
        "tipe": "BANJIR",
        "deskripsi": "banjir 2 meter",
        "status": "NOT_YET_VERIFIED",
        "created_at": "2022-07-06T05:48:48.000000Z",
        "updated_at": "2022-07-06T05:48:48.000000Z",
        "geometry": "{\"type\": \"Point\", \"coordinates\": [101.415468, 0.584255]}",
        "upvote": 1,
        "downvote": 0,
        "vote": "UPVOTE"
    }
]
```

#### Get pengaduan by status/by tipe/ by tipe and status
Role masyarakat
```json
{
    "current_page": 1,
    "data": [
        {
            "id": "3b7c7389-215c-43a2-b5c7-c903d65ccf4f",
            "id_masyarakat": "a40dd247-4b65-40fa-9a5a-47b75a2592ce",
            "nama_pelapor": "Deanira",
            "nama_jalan": "Jalan Sudirman",
            "foto": "no-picture.png",
            "tipe": "DRAINASE RUSAK",
            "deskripsi": "beton sudah pecah",
            "status": "NOT_YET_VERIFIED",
            "feedback_masyarakat": null,
            "created_at": "2022-07-07T09:44:20.000000Z",
            "updated_at": "2022-07-07T09:44:20.000000Z",
            "geometry": "{\"type\": \"Point\", \"coordinates\": [101.415468, 0.584255]}",
            "upvote": 0,
            "downvote": 0,
            "vote": null
        },
        {
            "id": "00bce130-8bdf-4bbc-8afc-5c0b562d6787",
            "id_masyarakat": "a40dd247-4b65-40fa-9a5a-47b75a2592ce",
            "nama_pelapor": "Deanira",
            "nama_jalan": "Jalan Sudirman",
            "foto": "no-picture.png",
            "tipe": "BANJIR",
            "deskripsi": "banjir 2 meter",
            "status": "NOT_YET_VERIFIED",
            "feedback_masyarakat": null,
            "created_at": "2022-07-06T05:48:48.000000Z",
            "updated_at": "2022-07-06T05:48:48.000000Z",
            "geometry": "{\"type\": \"Point\", \"coordinates\": [101.415468, 0.584255]}",
            "upvote": 1,
            "downvote": 0,
            "vote": "UPVOTE"
        }
    ],
    "first_page_url": "http://localhost:8000/api/pengaduan_by_status/NOT_YET_VERIFIED?page=1",
    "from": 1,
    "last_page": 1,
    "last_page_url": "http://localhost:8000/api/pengaduan_by_status/NOT_YET_VERIFIED?page=1",
    "links": [
        {
            "url": null,
            "label": "&laquo; Previous",
            "active": false
        },
        {
            "url": "http://localhost:8000/api/pengaduan_by_status/NOT_YET_VERIFIED?page=1",
            "label": "1",
            "active": true
        },
        {
            "url": null,
            "label": "Next &raquo;",
            "active": false
        }
    ],
    "next_page_url": null,
    "path": "http://localhost:8000/api/pengaduan_by_status/NOT_YET_VERIFIED",
    "per_page": 10,
    "prev_page_url": null,
    "to": 2,
    "total": 2
}
```

#### Update status pengaduan done by petugas
success
```json
{
    "message": "Congratulations, the report has been done!",
    "status_code": 200
}
```
forbidden
```json
{
    "message": "You don't have access",
    "status_code": 403
}
```

#### Get drainase
```json
{
    "message": "Congratulations, the report has been done!",
    "status_code": 200
}
```

#### Get titik banjir
```json
{
    "message": "Congratulations, the report has been done!",
    "status_code": 200
}
```

#### Get titik drainase rusak
```json
{
    "message": "Congratulations, the report has been done!",
    "status_code": 200
}
```
