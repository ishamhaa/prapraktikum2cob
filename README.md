| Name                 | NRP         | Kelas     |
| ---                  | ---         | ----------|
| Ahmad Rafli Syarif A | 5025251111  | Jarkom C  |

> [!IMPORTANT]
> Remember to use the IP prefix allocation provided earlier for this pre-lab assignment (pra-praktikan) and for future ones.
> Access it on [Linktree](https://linktr.ee/jarkom)

> [!TIP]
> **Due Date : 15th October 2026, 23.00 WIB**

## Put your GNS3 Project files here!

`https://drive.google.com/drive/folders/1tdtG8xdNOlEfYX3mMDBAMcLgdyR0VQ8o?usp=drive_link`

# Tugas Mandiri (Bagian A, B dan C)

> [!IMPORTANT]
> Tugas mandiri ini adalah kelanjutan dari konfigurasi yang telah dikerjakan pada Bagian A hingga C. Pastikan konfigurasi sebelumnya tetap berjalan sebelum mengerjakan tugas mandiri.
>
> *This independent task is a continuation of the configurations performed in Parts A through C. Ensure that the previous configurations remain running before proceeding with the independent task.*

#### Soal 1

> Buatlah konfigurasi network seperti yang ada pada soal dengan penambahan node Web3 yang akan digunakan sebagai backend HTTP server baru. Gunakan IP address statis pada subnet yang sama dengan node Web1 dan Web2. Tentukan IP address, subnet mask, dan gateway yang digunakan oleh Web3.
>
> Configure the network for the Web3 node, which will be used as a new HTTP backend server. Use a static IP address within the same subnet as Web1 and Web2. Specify the IP address, subnet mask, and gateway used by Web3.

> [!IMPORTANT]
> Pastikan untuk menunjukkan konfigurasi tiap node, termasuk router, netics-pc-X, web1, web2 dan web3. Ikuti semua langkah yang diberikan pada dokumen soal.
>
> Yang ditunjukkan adalah network configuration, dan service configuration yand ada dalam node tersebut, misal Chernobog adalah DNS server, tunjukkan konfigurasi DNS nya, dan seterusnya.
>
> *Ensure you show the configuration for each node, including the router, netics-pc-X, web1, web2, and web3. Follow all the steps provided in the problem document.*
>
> *What is shown is the network configuration and service configuration present on that node, for example, if `Chernobog` is a DNS server, show its DNS configuration, and so on.*

**Answer:**

**KONFIGURASI JARINGAN**
<img width="719" height="565" alt="image" src="https://github.com/user-attachments/assets/00b4bb7a-ecda-4ed1-af01-5d7f1c79947d" />

- Router
<img width="1143" height="606" alt="Screenshot 2026-10-14 200400" src="https://github.com/user-attachments/assets/f9a9d799-7b92-406d-86b9-f1ac9137d6a5" />

- Aegir(server DHCP)
<img width="782" height="500" alt="Screenshot 2026-10-14 200607" src="https://github.com/user-attachments/assets/6ec43964-84e9-4d90-ae48-7de80a5719b2" />

--dhcp service configuration
<img width="979" height="427" alt="image" src="https://github.com/user-attachments/assets/90f82d9b-0e49-4223-804e-a93f1e4c50e8" />


- Kazdel(Web Server & Reverse proxy)
<img width="406" height="249" alt="image" src="https://github.com/user-attachments/assets/377b7da0-45d9-4ce1-b9eb-bc5c855d53ae" />

--Nginx Service Configuration
<img width="673" height="749" alt="image" src="https://github.com/user-attachments/assets/575621be-ae21-4e8b-9795-a0880bfc7f8e" />


- Chernobog(DNS Server)
<img width="804" height="420" alt="image" src="https://github.com/user-attachments/assets/548492bb-d939-4c1b-9bee-eb6f6c22fcb1" />

--DNS configuration

<img width="683" height="752" alt="image" src="https://github.com/user-attachments/assets/f9fba9eb-bbb1-438d-802b-d27fb6554175" />


- Sargon, Iberia, Higashi(client uji)
<img width="629" height="133" alt="image" src="https://github.com/user-attachments/assets/8a48037b-460b-4909-aa78-8ac96b476173" />

- Ognisko(client uji browser)
<img width="688" height="216" alt="image" src="https://github.com/user-attachments/assets/181beba2-7f5c-4c68-b8d6-9895d86ccee3" />

- Web1 (Backend HTTP server)
<img width="573" height="285" alt="image" src="https://github.com/user-attachments/assets/73b9485b-3218-445f-9d9a-6bbb7a595bf2" />


- Web2 (Backend HTTP Server, aplikasi python)
<img width="592" height="261" alt="image" src="https://github.com/user-attachments/assets/d4b195c5-7154-4adf-a15e-6a174816c741" />


- Web3 (Backend HTTP server)
<img width="595" height="288" alt="image" src="https://github.com/user-attachments/assets/b27aca1a-b0bd-4d3e-b5d4-6662a5a7f5e3" />


#### Soal 2

> Install dan konfigurasi nginx pada Web3 sebagai HTTP server backend, mengikuti langkah yang sama seperti pada Web1 (netics-pc-8) dan Web2 (netics-pc-9) di Bagian C: install nginx, lalu buat struktur direktori konfigurasi (`/root/myconfig`), web (`/root/myweb`), dan log (`/root/mylogs`) seperti yang digunakan pada Bagian A. Tunjukkan juga ulang konfigurasi nginx serta struktur direktori yang sudah ada pada Web1 dan Web2 sebagai pembanding/verifikasi bahwa keduanya tetap konsisten dengan Web3.
>
> *Install and configure nginx on Web3 as an HTTP backend server, following the same steps used for Web1 (netics-pc-8) and Web2 (netics-pc-9) in Part C: install nginx, then create the configuration (`/root/myconfig`), web (`/root/myweb`), and log (`/root/mylogs`) directory structure used in Part A. Also show the existing nginx configuration and directory structure on Web1 and Web2 as a comparison/verification that they remain consistent with Web3.*


**Answer:**
Pada soal ini kita perlu menginstall nginx terlebih dahulu sebagai web server dengan memasukkan kode berikut
```
apk update
apk add nginx
```
<img width="960" height="499" alt="image" src="https://github.com/user-attachments/assets/b427a5cb-e92d-4801-8e87-004c08d7b81a" />
Setelah itu kita membuat direktori myconfig, mylogs, dan myweb

```
mkdir -p /root/myconfig
mkdir -p /root/mylogs
mkdir -p /root/myweb
```

-
<img width="375" height="117" alt="Screenshot 2026-10-14 212906" src="https://github.com/user-attachments/assets/164fb963-86ac-4c31-aa86-b977f5e1852f" />

Selanjutnya kita perlu mengatur konfigurasi untuk Nginx nya

```
user root;
worker_processes auto;
worker_cpu_affinity auto;
pid /tmp/nginx.pid;
error_log /root/mylogs/error.log;

events { worker_connections 768; }

http {
    server {
        listen 8080;
        server_name _;

        root /root/myweb;
        index index.html;

        location / {
            try_files $uri $uri/ =404;
        }
    }
}

```


- Web3
<img width="490" height="531" alt="image" src="https://github.com/user-attachments/assets/b700a5a2-3339-4a57-a997-7863efc825fc" />

- web2

<img width="510" height="479" alt="image" src="https://github.com/user-attachments/assets/9b805cae-a803-4a2a-a7ea-169f2b9e92a4" />

- web1
<img width="499" height="483" alt="image" src="https://github.com/user-attachments/assets/cff279cf-f476-46e3-ab29-14ee91202c28" />



#### Soal 3

> Buatlah halaman `index.html` pada Web3 yang memiliki isi berbeda dari Web1 (berisi "Ini WEB-1") dan Web2 (berisi "Ini WEB-2") sehingga dapat digunakan untuk membuktikan bahwa request berhasil diteruskan ke Web3.
>
> *Create an `index.html` page on Web3 with content different from Web1 (which contains "Ini WEB-1") and Web2 (which contains "Ini WEB-2") so that it can be used to prove that requests are successfully forwarded to Web3.*
 
**Answer:**

selanjutnya kita membuat file index.html pada direktori myweb.

```
<html>
<head>
<title>This is My Web</title>
</head>
<body>
<h1>TUGAS MANDIRI JARKOM</h1>
<p>
Ini WEB-3
</p>
</body>
</html>

```

#### Soal 4

> Konfigurasikan nginx pada Web3 agar HTTP server berjalan pada port `8080` (sama seperti Web1 dan Web2). Jelaskan konfigurasi `listen`, `server_name`, `root`, `index`, dan `location` yang digunakan.
> Kemudian buktikan bahwa HTTP server pada Web3 dapat diakses secara langsung dari client menggunakan alamat IP dan port `8080`. Gunakan `curl` untuk melakukan pengujian.
>
> *Configure nginx on Web3 so that the HTTP server runs on port `8080` (the same as Web1 and Web2). Explain the purpose of the `listen`, `server_name`, `root`, `index`, and `location` directives used in the configuration.*
> *Then, prove that the HTTP server on Web3 can be accessed directly from a client using its IP address and port `8080`. Use `curl` to perform the test.*
 
**Answer:**

- listen: Menentukan port HTTP server
- server_name: mendefinisikan nama domain atau ip server
- root: direktori utama file web
- index: nama file html
- location: Blok untuk mengatur routing spesifik. location / mengatur root path, dan try_files akan mencari file sesuai URI, jika tidak ada mengembalikan error 404.

selanjutnya kita akan menjalankan kode berikut untuk mengecek apakah website benar-benar berjalan

```
curl -vL http://10.203.200.22:8080
```

<img width="964" height="731" alt="image" src="https://github.com/user-attachments/assets/a743312c-5a1f-489d-88ff-c4742c74a76f" />

-


#### Soal 5

> Konfigurasikan reverse proxy pada `Kazdel` (yang sudah memiliki blok `location` untuk `/web1` menuju Web1 dan `/web2` menuju Web2) agar request ke `http://www.netics.my.id/web3` diteruskan ke Web3 melalui port `8080`, dengan menambahkan blok `location` baru pada `nginx.conf` tanpa mengganggu konfigurasi `/web1`, `/web2`, dan `/app` yang sudah ada.
>
> *Configure the reverse proxy on `Kazdel` (which already has `location` blocks for `/web1` pointing to Web1 and `/web2` pointing to Web2) so that requests to `http://www.netics.my.id/web3` are forwarded to Web3 through port `8080`, by adding a new `location` block in `nginx.conf` without disrupting the existing `/web1`, `/web2`, and `/app` configuration.*
 
**Answer:**
 
<img width="779" height="906" alt="image" src="https://github.com/user-attachments/assets/dd605869-6a91-42f6-8968-573c63272c06" />


#### Soal 6

> Buktikan bahwa Web3 dapat diakses melalui reverse proxy menggunakan:
>
> `curl http://www.netics.my.id/web3`
>
> Pastikan response yang diterima menunjukkan isi halaman dari Web3, dan tunjukkan juga bahwa endpoint `/web1` dan `/web2` yang sudah ada sebelumnya tetap berfungsi normal setelah penambahan `/web3`.
>
> *Prove that Web3 can be accessed through the reverse proxy using:*
>
> `curl http://www.netics.my.id/web3`
>
> *Make sure that the received response contains the page content served by Web3, and also show that the pre-existing `/web1` and `/web2` endpoints still work normally after adding `/web3`.*
 
**Answer:**

<img width="1266" height="783" alt="image" src="https://github.com/user-attachments/assets/08bcdff8-1378-4580-a1a7-3563d7853424" />

-
<img width="1228" height="619" alt="image" src="https://github.com/user-attachments/assets/9cbca50e-778a-4a29-a947-46b62806c4d5" />

dari gambar diatas dapat diperhatikan bahwa webnya berjalan dan tidak mengganggu aktivitas web lain


#### Soal 7

> Tambahkan record DNS baru untuk domain `app.netics.my.id` pada DNS server (Chernobog, zona `netics.my.id`). Domain tersebut harus mengarah ke IP address reverse proxy `Kazdel` ([IP Prefix].200.11), bukan langsung ke Web3.
> Buktikan bahwa `app.netics.my.id` berhasil di-resolve oleh client menggunakan DNS server internal. Gunakan `ping` atau command DNS yang tersedia untuk menunjukkan hasil resolusi.
>
> *Add a new DNS record for `app.netics.my.id` on the DNS server (Chernobog, zone `netics.my.id`). The domain must point to the IP address of the reverse proxy `Kazdel` ([IP Prefix].200.11), not directly to Web3.*
> *Prove that `app.netics.my.id` can be successfully resolved by the client using the internal DNS server. Use `ping` or an available DNS command to show the resolution result.*
 
**Answer:**

kita perlu menambahkan kode berikut pada file db.netics.my.id pada direktori dns di chernobog
```
app IN A 10.203.200.11
```
untuk mengecek apakah domain bisa digunakan kita bisa melakukan ping pada sargon dan diperoleh hasil berikut
<img width="829" height="195" alt="image" src="https://github.com/user-attachments/assets/4f562b04-72a2-44c4-896c-27ed3b97ceb1" />
dari gambar diatas dapat diketahui bahwa domain bisa berjalan

#### Soal 8

> Konfigurasikan nginx pada `Kazdel` agar `app.netics.my.id` dapat digunakan sebagai name-based virtual host. Request ke domain tersebut harus diteruskan ke Web3.
> Buktikan bahwa `app.netics.my.id` dapat digunakan untuk mengakses Web3 melalui reverse proxy menggunakan `curl`.
>
> *Configure nginx on `Kazdel` so that `app.netics.my.id` can be used as a name-based virtual host. Requests to this domain must be forwarded to Web3.*
> *Prove that `app.netics.my.id` can be used to access Web3 through the reverse proxy using `curl`.*

**Answer:**

```
server {
    listen 80;
    server_name app.netics.my.id;

    location / {
        proxy_pass http://10.203.200.22:8080;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }
}

```
secara keseluruhan bisa dilihat seperti ini
<img width="799" height="928" alt="image" src="https://github.com/user-attachments/assets/9ae4fbcf-f54e-4d77-a28d-0eddb112b586" />

Untuk mengujinya apakah benar benar bekerja kita bisa menggunakan ping
<img width="836" height="219" alt="image" src="https://github.com/user-attachments/assets/6c8fd817-5b54-4cc0-946d-512a293b22a0" />

#### Soal 9

> Buktikan bahwa endpoint berikut menghasilkan backend yang sesuai:
>
> - `http://www.netics.my.id/web1` -> Web1
> - `http://www.netics.my.id/web2` -> Web2
> - `http://www.netics.my.id/app` -> Flask pada Web2
> - `http://www.netics.my.id/web3` -> Web3
> - `http://app.netics.my.id/` -> Web3
>
> *Prove that each of the following endpoints reaches the correct backend:*
>
> - `http://www.netics.my.id/web1` -> Web1
> - `http://www.netics.my.id/web2` -> Web2
> - `http://www.netics.my.id/app` -> Flask on Web2
> - `http://www.netics.my.id/web3` -> Web3
> - `http://app.netics.my.id/` -> Web3

**Answer:**
- `http://www.netics.my.id/web1` -> Web1
<img width="1896" height="1079" alt="image" src="https://github.com/user-attachments/assets/7718cd8c-2eb1-468d-ae8a-793baecd0451" />
tampilan web1

- `http://www.netics.my.id/web2` -> Web2
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/d8d47b0c-cddf-4eb9-855d-8c19f323b880" />
tampilan web2

- `http://www.netics.my.id/app` -> Flask pada Web2
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/e2a74a59-88da-4792-b9fa-f8b6ef8755a8" />
tampilan flask app

- `http://www.netics.my.id/web3` -> Web3
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/78eefa74-2b70-4b4a-9be2-b338ba7d6959" />
tampilan web3

- `http://app.netics.my.id/` -> Web3
<img width="1918" height="1079" alt="image" src="https://github.com/user-attachments/assets/66e1222d-14f1-43b4-912e-1ac29d4bc14d" />
tampilan web3
  
```
put your answer here (and screenshot)
```

#### Soal 10

> Konfigurasikan dan jalankan `termshark` dan nginx reverse-proxy secara bersamaan menggunakan `tmux` untuk menangkap traffic HTTP ketika client mengakses Web3 melalui reverse proxy (Kazdel).
> Gunakan `termshark` untuk mengamati request HTTP yang diterima oleh Web3. Identifikasi source IP, destination IP, source port, destination port, dan informasi HTTP yang terdapat pada packet.
>
> *Configure and run `termshark` and the nginx reverse proxy simultaneously using `tmux` to capture HTTP traffic when a client accesses Web3 via the reverse proxy (Kazdel).*
> *Use `termshark` to observe the HTTP request received by Web3. Identify the source IP, destination IP, source port, destination port, and HTTP information contained in the packet.*

**Answer:**
Sebelum melanjutkan ke soal ini kita perlu menginstall termshark pada node kazdel

```
apk update
apk add termshark tshark
```
selanjutnya kita akan menjalankan nginx dan termshark di node kazdel, dan mencoba melakukan curl di node sargon untuk menjalankan traffic

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/a687817d-5b66-46bd-8618-9a25c722703d" />

Dari gambar diatas dapat diamati ketika Sargon meminta halaman Web3, request tersebut tidak langsung menuju Web3, melainkan ditahan oleh Kazdel. Kazdel kemudian membuat koneksi TCP baru untuk meneruskan request tersebut ke Web3.


#### Soal 11

> Lakukan pengujian akses Web3 melalui reverse proxy dari minimal dua client yang berbeda, misalnya `Sargon` dan `Iberia`. Amati nilai `X-Real-IP` pada masing-masing request menggunakan `termshark`.
>
> Buktikan bahwa header `X-Real-IP` diteruskan oleh reverse proxy kepada Web3. Tunjukkan nilai `X-Real-IP` yang diterima oleh Web3.
> Bandingkan source IP pada packet yang diterima Web3 dengan nilai `X-Real-IP`. Apakah keduanya sama? Jelaskan mengapa nilai tersebut dapat berbeda.
>
> *Test access to Web3 through the reverse proxy from at least two different clients, such as `Sargon` and `Iberia`. Observe the `X-Real-IP` value for each request using `termshark`.*
>
> *Prove that the `X-Real-IP` header is forwarded by the reverse proxy to Web3. Show the value of `X-Real-IP` received by Web3.*
> *Compare the source IP address of the packet received by Web3 with the value of `X-Real-IP`. Are they the same? Explain why the two values may be different.*

**Answer:**

<img width="1917" height="1079" alt="image" src="https://github.com/user-attachments/assets/2ba560a8-bbda-4845-ac73-ed371a995b52" />

-
<img width="1917" height="1076" alt="image" src="https://github.com/user-attachments/assets/33790664-74ae-4cec-9782-246b090be3f4" />
Berdasarkan inspeksi paket menggunakan Termshark, Reverse Proxy Kazdel terbukti berhasil menyisipkan dan meneruskan header X-Real-IP ke Web3. Saat diakses dari Sargon, nilai X-Real-IP yang diterima Web3 adalah 10.203.200.144. Sedangkan saat diakses dari Iberia, nilai X-Real-IP yang diterima Web3 adalah 10.203.200.109

#### Soal 12

> Buatlah kesimpulan mengenai arsitektur yang telah dibuat. Jelaskan hubungan antara DNS server, reverse proxy, Web1, Web2, aplikasi Flask, dan Web3. Jelaskan juga bagaimana request dari client dapat mencapai backend yang berbeda menggunakan satu reverse proxy.
>
> *Write a conclusion about the architecture you have implemented. Explain the relationship between the DNS server, reverse proxy, Web1, Web2, the Flask application, and Web3. Also explain how client requests can reach different backends through a single reverse proxy.*

**Answer:**

1. Hubungan Antar Komponen:
   - DNS Server (Chernobog): Bertindak sebagai sistem penamaan yang menerjemahkan nama domain (www.netics.my.id dan app.netics.my.id) menjadi satu alamat IP publik, yaitu IP milik Reverse Proxy (Kazdel). 
   - Reverse Proxy (Kazdel): Bertindak sebagai pintu masuk yang menerima seluruh request HTTP dari client, lalu meneruskannya ke server backend yang tepat.
   - Web1, Web2, dan Web3: Berperan sebagai backend HTTP server terisolasi yang melayani konten statis.
   - Aplikasi Flask (di Web2): Berperan sebagai backend application server yang melayani layanan dinamis.

2. Mekanisme Reverse Proxy:
   Meskipun menggunakan satu gerbang masuk (Kazdel) pada port yang sama (port 80), request dari client dapat mencapai backend yang berbeda-beda karena Nginx di Kazdel dikonfigurasi menggunakan dua metode routing:

   a. Path-based Routing (Berbasis Direktori/URI): 
      Reverse proxy membaca path URL yang diminta oleh client. 
      - Request ke "/web1" diteruskan ke IP Web1 (port 8080).
      - Request ke "/web2" diteruskan ke IP Web2 (port 8080).
      - Request ke "/app" diteruskan ke IP Web2 (port 5000 / Flask).
      
   b. Name-based Virtual Hosting (Berbasis Nama Domain): 
      Reverse proxy membaca HTTP Header "Host" dari request client. 
      - Jika request datang dengan domain "app.netics.my.id", Kazdel menggunakan blok konfigurasi server_name yang berbeda untuk mengarahkan trafik tersebut secara spesifik ke Web3 (port 8080).

AJK
