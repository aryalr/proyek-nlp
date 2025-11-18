# Python Virtual Environment Setup for NLP in WSL

> Select your language: [English Guide](#english-guide) | [Panduan Bahasa Indonesia](#panduan-bahasa-indonesia)

---

## English Guide

This tutorial explains how to set up a Python virtual environment for NLP practice inside Windows Subsystem for Linux (WSL).

### Step 1: Install Python and pip

Run:

```bash
sudo apt update
sudo apt install python3 python3-pip python3-venv -y
```

Verify that Python and pip are installed:

```bash
python3 --version
pip3 --version
```

Expected output example:

```shell
> Python 3.12.3 #or a similar version
> pip 24.0 from /path/to/file #or a similar version
```

### Step 2: Create the project folder and virtual environment

Run:

```bash
mkdir -p /path/to/project-name
cd /path/to/project-name
python3 -m venv env # <-- replace env with any name you prefer
source ./env/bin/activate
```

Python will create a virtual environment inside your project folder.

If it succeeds, your shell prompt should indicate that you are inside the virtual environment. Example (using zsh + Powerlevel10k, look may vary):

![terminal image](assets/20251117_201337_image.png)

or

```shell
(env) username@DESKTOP:~/path/to/project$
```

### Step 3: Install `requirements.txt` and register the environment in Jupyter

Install the required libraries:

```bash
pip install -r requirements.txt
```

Then register the environment with Jupyter:

```bash
python -m ipykernel install --user --name=env --display-name "project-name"
```

Notes:

| Argument        | Function                                                                 |
| --------------- | ------------------------------------------------------------------------ |
| --user          | Register the kernel only for the current user                             |
| --name=env      | Kernel root name; change it to match your venv name                       |
| --display-name  | Friendly name shown inside Jupyter; change it to whatever you prefer      |

### Step 4: Configure VS Code

Open VS Code inside the WSL remote environment and install the extensions:

* ✔️ Python (Microsoft)
* ✔️ Jupyter (Microsoft)

Press `ctrl+shift+p` → type `Python: Select Interpreter` → choose `Python 3.12.3 (env)` (or your venv name), then reload the window via `ctrl+shift+p` → `Developer: Reload Window`.

### Done

You can now run `.ipynb` notebooks directly in VS Code using an isolated environment backed by the registered Jupyter kernel.

![awesome gif](assets/Tech_Coding_GIF_by_Persona.gif)

---

## Panduan Bahasa Indonesia

Tutorial ini menjelaskan cara setup virtual environment Python untuk kebutuhan praktik NLP di Windows Subsystem for Linux (WSL).

### Langkah 1: Install Python dan pip

Jalankan:

```bash
sudo apt update 
sudo apt install python3 python3-pip python3-venv -y
```

Pastikan Python dan pip terpasang:

```bash
python3 --version
pip3 --version
```

Jika berhasil, kurang lebih akan muncul:

```shell
> Python 3.12.3 #atau versi yang serupa
> pip 24.0 from /path/to/file #atau versi yang serupa
```

### Langkah 2: Buat folder proyek dan virtual environment

Jalankan:

```bash
mkdir -p /path/to/nama-proyek
cd /path/to/nama-proyek
python3 -m venv env # <-- ganti env dengan nama yang Anda mau
source ./env/bin/activate
```

Python akan membuat virtual environment di folder proyek.

Jika berhasil, prompt shell akan menandakan bahwa Anda sudah berada di dalam virtual environment. Contoh (menggunakan zsh + Powerlevel10k, tampilan dapat berbeda):

![terminal image](assets/20251117_201337_image.png)

atau

```shell
(env) username@DESKTOP:~/path/to/project$
```

### Langkah 3: Install `requirements.txt` dan daftarkan environment ke Jupyter

Install library yang dibutuhkan:

```bash
pip install -r requirements.txt
```

Kemudian daftarkan environment ke Jupyter:

```bash
python -m ipykernel install --user --name=env --display-name "nama-proyek"
```

Catatan:

| Argumen        | Fungsi                                                                     |
| -------------- | -------------------------------------------------------------------------- |
| --user         | Mendaftarkan kernel hanya untuk user saat ini                              |
| --name=env     | Nama root kernel, bisa disesuaikan dengan nama venv masing-masing          |
| --display-name | Nama proyek yang muncul di Jupyter, ganti sesuai kebutuhan                 |

### Langkah 4: Setup VS Code

Buka VS Code di dalam remote WSL lalu install ekstensi:

* ✔️ Python (Microsoft)
* ✔️ Jupyter (Microsoft)

Tekan `ctrl+shift+p` → ketik `Python: Select Interpreter` → pilih `Python 3.12.3 (env)` (atau nama venv Anda), lalu reload window dengan `ctrl+shift+p` → `Developer: Reload Window`.

### Selesai

Sekarang Anda bisa menjalankan `.ipynb` langsung di VS Code dengan environment terisolasi dan kernel Jupyter yang sesuai.

![gif keren sekali](assets/Tech_Coding_GIF_by_Persona.gif)