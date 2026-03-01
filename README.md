# GACS — Install For STB


## Instalasi
```bash
# 1) Update dan Upgrade Repo
apt update && apt upgrade -y
```
```bash
# 2) Download Script GACS
git clone https://github.com/achmad-pr/GenieACS-STB
```
```bash
# 3) Masuk ke folder GACS
cd GenieACS-STB
```
```bash
# 4) Install dos2unix
apt-get update -y && apt-get install -y dos2unix
```
```bash
# 5) Convert format script GACS
dos2unix GACS-Jammy.sh
```
```bash
# 6) Beri izin script GACS
chmod +x GACS-Jammy.sh
```
```bash
# 7) Instal GACS
./GACS-Jammy.sh
```

---

## Install Parameter
```bash
# 1) Masuk ke folder parameter di repo
cd parameter
```
```
# 2) Install parameter
mongorestore --db genieacs --drop .
```
```
# 3) Restart service GenieACS
systemctl restart genieacs-{cwmp,ui,nbi}
```
> Jika dump Anda berada di lokasi lain, sesuaikan path pada langkah nomor (2).

---

## Penting (Provisions → Inform)
Setelah **menambahkan parameter login**, buka **GenieACS UI → Provisions → Show (Inform)** dan perbarui:
- `const url`
- `const AcsUser`
- `const AcsPass`
- `let ConnReqUser`
- `const ConnReqPass`

Simpan perubahan agar **Inform/Connection Request** sesuai dengan kredensial dan alamat ACS Anda.

---
