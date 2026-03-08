
## 1. Compression in Linux

**Compression** means **reducing the size of files** using special algorithms.

### Purpose

- Save **disk space**
    
- Faster **file transfer**
    
- Efficient **data storage**
    
- Easier **backup management**
    

Linux supports many compression tools like:

- `gzip`
    
- `bzip2`
    
- `xz`
    
- `compress`
    

---

# Types of Compression

## 1. Lossless Compression

No data is lost during compression.

Used for:

- Text files
    
- Programs
    
- System files
    

Examples:

- `gzip`
    
- `bzip2`
    
- `xz`
    

---

## 2. Lossy Compression

Some data is removed to reduce file size.

Used for:

- Images
    
- Audio
    
- Video
    

Example formats:

- JPG
    
- MP3
    
- MP4
    

---

# Archiving in Linux

**Archiving** means **combining multiple files and folders into one file**.

The most common archiving tool in Linux is:

```
tar
```

Archive file example:

```
myarchive.tar
```

Important:

```
tar only combines files
It does NOT compress them
```

Compression can be added later.

---

# Why Archiving Is Used

### 1. File Organization

Combine many files into **one file**.

### 2. Backup and Restore

Easier to **backup entire directories**.

### 3. Data Transfer

Transfer **one archive instead of many files**.

### 4. Preserve File Attributes

Tar preserves:

- permissions
    
- ownership
    
- timestamps
    
- directory structure
    

### 5. Software Distribution

Many Linux programs are distributed as:

```
.tar.gz
.tar.xz
.tar.bz2
```

### 6. Long-Term Storage

Useful for storing old or rarely used data.

---

# Tarring Files (Creating Archive)

Example setup:

```bash
mkdir folder1 folder2
touch file1.txt file2.txt
```

Create archive:

```bash
tar -cvf myarchive.tar folder1 folder2 file1.txt file2.txt
```

Result:

```
myarchive.tar
```

---

# Tar Command Flags

|Flag|Meaning|
|---|---|
|c|create archive|
|v|verbose (show files)|
|f|file name|

Example:

```
tar -cvf archive.tar files
```

---

# Important Note

A `.tar` file may be **larger** than original files because:

```
tar does NOT compress
it only bundles files
```

To reduce size → use compression tools.

---

# Compressing Files

## Using gzip

Extension:

```
.gz
```

### Compress files

```bash
gzip file1.txt file2.txt
```

Output:

```
file1.txt.gz
file2.txt.gz
```

---

### Compress tar archive

```bash
gzip myarchive.tar
```

Result:

```
myarchive.tar.gz
```

Also called:

```
tarball
```

---

# Compressing with bzip2

Extension:

```
.bz2
```

Example:

```bash
bzip2 file1.txt
```

Output:

```
file1.txt.bz2
```

---

# gzip vs bzip2

|Feature|gzip|bzip2|
|---|---|---|
|Speed|Faster|Slower|
|Compression|Lower|Higher|
|Best For|Small files|Large files|

---

# Untarring (Extract Archive)

Untarring means **extracting files from a tar archive**.

Example:

```bash
tar -xvf myarchive.tar
```

Files extracted:

```
file1.txt
file2.txt
folder1
folder2
```

---

# Tar Extract Flags

|Flag|Meaning|
|---|---|
|x|extract files|
|v|verbose|
|f|archive file|

Example:

```
tar -xvf archive.tar
```

---

# Decompression

Decompression means **restoring compressed files to original form**.

---

# Decompress gzip

```bash
gunzip file1.txt.gz
```

Output:

```
file1.txt
```

---

# Decompress bzip2

```bash
bunzip2 file1.txt.bz2
```

Output:

```
file1.txt
```

---

# Most Common Linux Archive Formats

|Format|Meaning|
|---|---|
|.tar|archive only|
|.tar.gz|tar + gzip|
|.tar.bz2|tar + bzip2|
|.tar.xz|tar + xz|

---

# Most Important Commands (Quick Revision)

Create archive:

```
tar -cvf archive.tar files
```

Extract archive:

```
tar -xvf archive.tar
```

Compress with gzip:

```
gzip file
```

Compress with bzip2:

```
bzip2 file
```

Decompress gzip:

```
gunzip file.gz
```

Decompress bzip2:

```
bunzip2 file.bz2
```

---

✅ **One simple memory trick**

```
tar → bundle files
gzip → compress fast
bzip2 → compress smaller
gunzip/bunzip2 → decompress
```

