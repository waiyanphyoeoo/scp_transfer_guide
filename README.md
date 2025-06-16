🔄 SCP File Transfer Guide

---

# 🔄 **SCP File Transfer Guide**

### 🔐 Secure Copy (SCP) – Fast, Secure, and Simple File Transfers

---

## 📝 **Overview**

SCP (Secure Copy Protocol) is a secure way to transfer **files** and **directories** between your **local machine** and a **remote server** using **SSH encryption**.

This guide includes:

* 📤 Transfer **from Local to Server**
* 📥 Transfer **from Server to Local**
* 🗂️ **Copy Files & Directories**
* 🧠 Flag reference for quick usage

---

## 🌐 **Local → Server Transfers**

### 🖼️ Copy a File to Remote Server

```bash
scp -i "/path/to/key.pem" /path/to/local-file.ext user@remote-server:/path/to/remote-directory/
```

✅ **Example:**

```bash
scp -i "~/.ssh/server-key.pem" ~/Downloads/logo.png ubuntu@123.45.67.89:/var/www/html/
```

---

### 📁 Copy a Directory to Remote Server

```bash
scp -r -i "/path/to/key.pem" /path/to/local-directory/ user@remote-server:/path/to/remote-directory/
```

✅ **Example:**

```bash
scp -r -i "~/.ssh/server-key.pem" ~/Projects/MyApp ubuntu@123.45.67.89:/var/www/
```

---

## 🌍 **Server → Local Transfers**

### 🖼️ Copy a File from Remote Server

```bash
scp -i "/path/to/key.pem" user@remote-server:/path/to/remote-file.ext /path/to/local-directory/
```

✅ **Example:**

```bash
scp -i "~/.ssh/server-key.pem" ubuntu@123.45.67.89:/var/log/syslog ~/Desktop/
```

---

### 📁 Copy a Directory from Remote Server

```bash
scp -r -i "/path/to/key.pem" user@remote-server:/path/to/remote-directory/ /path/to/local-directory/
```

✅ **Example:**

```bash
scp -r -i "~/.ssh/server-key.pem" ubuntu@123.45.67.89:/etc/nginx/ ~/Backups/nginx-config/
```

---

## 🧠 **Flag Cheat Sheet**

| Flag        | Emoji | Purpose                                      |
| ----------- | ----- | -------------------------------------------- |
| `-r`        | 🌀    | Copy directories recursively                 |
| `-i`        | 🔐    | Path to the SSH private key                  |
| `user@host` | 🌐    | Remote SSH user and server IP or hostname    |
| `:/path`    | 📂    | Absolute or relative file/folder destination |

---

## ✅ **Pro Tips**

* Always check if your file path exists and you have read/write access.
* SCP uses **port 22** by default. To use a custom port, add `-P <port>`:

  ```bash
  scp -P 2222 -i "~/.ssh/key.pem" file user@host:/path/
  ```
* Enclose paths with spaces in quotes (`" "`).


