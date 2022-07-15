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
[
    {
        "id": "05cc2f5a-b0d0-11ec-8bf9-005056c00001",
        "nama_jalan": "Jalan Pramuka",
        "lebar": 0.3,
        "panjang": 1216,
        "kedalaman": 0.4,
        "bahan": "Beton",
        "kondisi": "BAGUS",
        "akhir_pembuangan": "Parit Besar",
        "arah_alir": "kanan ke kiri",
        "foto": "-",
        "tipe_drainase": "Buatan",
        "geometry": "{\"type\": \"LineString\", \"coordinates\": [[101.447969, 0.570624], [101.450033, 0.571408], [101.451251, 0.571523], [101.453153, 0.570869], [101.955003, 0.570639], [101.455417, 0.570935], [101.4556079, 0.571172], [101.457315, 0.573201]]}"
    },
    {
        "id": "05cd4834-b0d0-11ec-8bf9-005056c00001",
        "nama_jalan": "Jalan Haji m.nur",
        "lebar": 0.8,
        "panjang": 1010,
        "kedalaman": 0.6,
        "bahan": "Beton",
        "kondisi": "BAGUS",
        "akhir_pembuangan": "-",
        "arah_alir": "Tidak Mengalir",
        "foto": "-",
        "tipe_drainase": "Buatan",
        "geometry": "{\"type\": \"LineString\", \"coordinates\": [[101.540011, 0.563056], [101.453309, 0.563403], [101.454922, 0.563549], [101.455416, 0.563557], [101.455718, 0.564211]]}"
    },
    {
        "id": "0bde578b-b0d3-11ec-8bf9-005056c00001",
        "nama_jalan": "Jalan Semarang",
        "lebar": 1,
        "panjang": 1260,
        "kedalaman": 0.64,
        "bahan": " Batu",
        "kondisi": "BAGUS",
        "akhir_pembuangan": "-",
        "arah_alir": "tenang",
        "foto": "-",
        "tipe_drainase": "Buatan",
        "geometry": "{\"type\": \"LineString\", \"coordinates\": [[101.433249, 0.564161], [101.434594, 0.564143], [101.433657, 0.564086], [101.43459, 0.564164]]}"
    },
    {
        "id": "14705a58-b0d2-11ec-8bf9-005056c00001",
        "nama_jalan": "Jalan Limbungan / Hidayah 1 (kiri)",
        "lebar": 0.45,
        "panjang": 640,
        "kedalaman": 0.3,
        "bahan": "batu",
        "kondisi": "BAGUS",
        "akhir_pembuangan": "titik kumpul air",
        "arah_alir": "kering",
        "foto": "-",
        "tipe_drainase": "Buatan",
        "geometry": "{\"type\": \"LineString\", \"coordinates\": [[101.451476, 0.565622], [101.452575, 0.567404], [101.448548, 0.561943], [101.4526554, 0.565519]]}"
    },
    {
        "id": "14719386-b0d2-11ec-8bf9-005056c00001",
        "nama_jalan": "Jalan Limbungan / Hidayah 2 (kanan)",
        "lebar": 0.37,
        "panjang": 510,
        "kedalaman": 0.3,
        "bahan": "batu",
        "kondisi": "BAGUS",
        "akhir_pembuangan": "titik kumpul air ",
        "arah_alir": "kering ",
        "foto": "-",
        "tipe_drainase": "Buatan",
        "geometry": "{\"type\": \"LineString\", \"coordinates\": [[101.451901, 0.565848], [101.452131, 0.565593], [101.452531, 0.565593]]}"
    },
]
```

#### Get titik banjir
```json
[
    {
        "id": "a59b604d-b0d4-11ec-8bf9-005056c00001",
        "nama_jalan": "Jalan Kemping",
        "foto": "-",
        "keterangan": null,
        "status": "INACTIVE",
        "geometry": "{\"type\": \"Point\", \"coordinates\": [101.4732942, 0.5785191]}"
    },
    {
        "id": "e8b642a9-b0d2-11ec-8bf9-005056c00001",
        "nama_jalan": "Jalan Harapan",
        "foto": "-",
        "keterangan": null,
        "status": "INACTIVE",
        "geometry": "{\"type\": \"Point\", \"coordinates\": [101.4313344, 0.565203]}"
    },
    {
        "id": "e8b925e9-b0d2-11ec-8bf9-005056c00001",
        "nama_jalan": "Jalan Harmonis",
        "foto": "-",
        "keterangan": null,
        "status": "INACTIVE",
        "geometry": "{\"type\": \"Point\", \"coordinates\": [101.433535, 0.561156]}"
    }
]
```

#### Get titik drainase rusak
```json
[
    {
        "id": "a59b604d-b0d4-11ec-8bf9-005056c00001",
        "nama_jalan": "Jalan Kemping",
        "foto": "-",
        "keterangan": null,
        "status": "INACTIVE",
        "geometry": "{\"type\": \"Point\", \"coordinates\": [101.4732942, 0.5785191]}"
    },
    {
        "id": "e8b642a9-b0d2-11ec-8bf9-005056c00001",
        "nama_jalan": "Jalan Harapan",
        "foto": "-",
        "keterangan": null,
        "status": "INACTIVE",
        "geometry": "{\"type\": \"Point\", \"coordinates\": [101.4313344, 0.565203]}"
    },
    {
        "id": "e8b925e9-b0d2-11ec-8bf9-005056c00001",
        "nama_jalan": "Jalan Harmonis",
        "foto": "-",
        "keterangan": null,
        "status": "INACTIVE",
        "geometry": "{\"type\": \"Point\", \"coordinates\": [101.433535, 0.561156]}"
    }
]
```
