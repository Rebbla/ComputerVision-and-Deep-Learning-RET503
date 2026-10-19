# PJ1 — Object Detection dengan YOLO

**Nama:** Filza Khairi Rahmansyah  
**NIM:** 4222401062

Proyek ini menyiapkan anotasi bounding box, membagi data, lalu membandingkan tiga eksperimen YOLO pada kelas `red_earth_block`, `blue_earth_block`, dan `sky_block`.

## Eksperimen

- **E1 — pretrained:** baseline dengan bobot pretrained COCO.
- **E2 — scratch:** arsitektur yang sama dilatih dari bobot acak.
- **E3 — tuning:** baseline pretrained dengan satu perubahan: E3 mengubah weight decay menjadi 0.001.

E1 dan E2 memakai 30 epoch, ukuran gambar 416, dan batch 8. Semua eksperimen menggunakan split dataset yang sama. Hasil aktual tersimpan di laporan CSV/TXT serta grafik pada `hasil_praktik/` setelah training.

## Menjalankan training

Dari folder proyek ini, siapkan dependensi (`pip install ultralytics`) lalu jalankan:

```bash
python 06_latih_bandingkan.py --nim 4222401062 --nama "Filza Khairi Rahmansyah" --data ../dataset_bbox_split/data.yaml --model yolo26n --epochs 30 --imgsz 416 --batch 8 --device 0 --ubah weight_decay=0.001
```

Laporan, grafik, dan checkpoint tersimpan di `hasil_praktik/`. Skrip `00`–`05` menjelaskan tahap pemeriksaan serta pemrosesan anotasi; presentasi tugas ada di `RET503_Data dan YOLO.pptx`.
