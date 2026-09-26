# Padavan Custom Config Builder - TL-MR3020 V3

Workflow tambahan untuk fork `TW641/padavan-builder-workflow`.

Tujuan: cukup simpan/ubah `build.config` di root repository, lalu jalankan:

`Actions -> Build firmware - Custom build.config -> Run workflow`

## Prinsip

- Source Padavan: `TWShiyuLiou1997/padavan-ng`, branch `master`.
- Toolchain: paket toolchain yang dipakai workflow TW641.
- `build.config` milik repository menjadi konfigurasi firmware utama.
- Workflow ini tidak menjalankan Nano Optimization dari workflow TW641.
- Workflow ini tidak mengubah opsi fitur firmware berdasarkan `target_select`, `language_select`, atau JSON customization.
- CAKE/kernel patch tambahan dari workflow TW641 tidak dipaksa oleh workflow ini; konfigurasi Anda tetap menjadi sumber kebenaran untuk fitur firmware.

## Cara menggunakan

1. Upload atau ganti `build.config` di root repository.
2. Buka tab `Actions`.
3. Pilih `Build firmware - Custom build.config`.
4. Klik `Run workflow`.
5. Firmware tersedia di `Artifacts` jika build berhasil.

## Format build.config

Gunakan file konfigurasi Padavan yang valid. Untuk MR3020 V3 minimal harus ada:

```text
CONFIG_VENDOR=TPLINK
CONFIG_PRODUCT=MT7628
CONFIG_FIRMWARE_PRODUCT_ID="TL_MR3020-V3"
```

Konfigurasi dapat berisi opsi `CONFIG_FIRMWARE_ENABLE_*`, `CONFIG_FIRMWARE_INCLUDE_*`, dan opsi build lain yang didukung source Padavan.
