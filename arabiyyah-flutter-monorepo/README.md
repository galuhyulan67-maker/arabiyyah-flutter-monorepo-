# Arabiyyah Flutter Monorepo

Monorepo pembelajaran bahasa Arab berbasis **Flutter (Dart)** dan **Firebase** (Cloud Firestore koleksi `lessons` & Cloud Storage folder `lesson_images` / `lesson_audio`) dengan dua aplikasi Android:

- **Arabiyyah Host** (`com.arabiyyah.host`) — Untuk guru/pengajar: mengelola materi standar & percakapan A/B (bubble chat), teks Arab berharakat, transliterasi, gambar, audio TTS `ar-SA` atau upload file audio, serta publish/unpublish/hapus.
- **Arabiyyah Siswa** (`com.arabiyyah.siswa`) — Untuk siswa: masuk dengan email, daftar materi dengan cache offline, indikator progres centang item, pemutar audio per item & Putar Semua, serta mode pelan (`0.7x`).

## Struktur Folder

```text
arabiyyah-flutter-monorepo/
├── packages/shared/          # Model data, tema Material 3 hijau zamrud, font Amiri & Poppins, service Firebase/TTS
├── apps/host/                # Aplikasi Arabiyyah Host (com.arabiyyah.host)
│   └── android/app/          # Tempatkan google-services.json Host di sini
├── apps/client/              # Aplikasi Arabiyyah Siswa (com.arabiyyah.siswa)
│   └── android/app/          # Tempatkan google-services.json Siswa di sini
└── .github/workflows/        # CI/CD otomatis build APK release untuk Host & Siswa
```

## Langkah Penggunaan

1. Pasang `google-services.json` masing-masing aplikasi ke:
   - `apps/host/android/app/google-services.json`
   - `apps/client/android/app/google-services.json`
2. Push repository ini ke **GitHub**.
3. Workflow **GitHub Actions** (`.github/workflows/build-apks.yml`) akan otomatis membangun APK release untuk `host` dan `client` serta mengunggahnya sebagai artifact.
