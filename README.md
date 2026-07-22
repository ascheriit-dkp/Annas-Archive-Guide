# Anna's Archive Guide

Welcome to the Anna's Archive Guide! This repository provides a step-by-step guide for newcomers on how to use Anna's Archive efficiently and with some additional privacy and safety precautions.

## Table of Contents

1. [Setup (First-Time Users)](#setup-first-time-users)
2. [Accessing Anna's Archive (Registered Users)](#accessing-annas-archive-registered-users)
3. [Searching and Downloading](#searching-and-downloading)
4. [Using Calibre with Your E-Reader](#using-calibre-with-your-e-reader)
5. [Tips and Tricks](#tips-and-tricks)
6. [Troubleshooting and FAQs](#troubleshooting-and-faqs)
7. [License](#license)

## Setup (First-Time Users)

Follow these steps to set up your browser and account:

1. **Download LibreWolf (Optional)**:
   - You can use Anna's Archive with your usual browser. Installing LibreWolf is not mandatory.
   - LibreWolf provides stronger default protection against some trackers, cookies, and browser fingerprinting than browsers such as Chrome or Edge.
   - It does not hide your public IP address and does not make you anonymous.
   - Visit [LibreWolf's official installation page](https://librewolf.net/installation/).
   - Select the appropriate operating system and follow the installation instructions.
   ![LibreWolf Installation](images/librewolf-installation.png)

2. **Visit Anna's Archive**:
   - Go to one of the current Anna's Archive mirrors:
     - [annas-archive.pk](https://annas-archive.pk/)
     - [annas-archive.gd](https://annas-archive.gd/)
     - [annas-archive.gl](https://annas-archive.gl/)
   - Anna's Archive uses mirrors so that the service can remain available when one domain is blocked, suspended, or taken down.
   - If the links above no longer work, a common practice is to check the domains listed on the [Anna's Archive Wikipedia page](https://en.wikipedia.org/wiki/Anna%27s_Archive), which is often updated when the official mirrors change.
   - Be careful: fake mirrors and impersonation websites exist. Check the exact spelling of the domain and avoid random or sponsored search results before entering a secret key or downloading anything.

<details>
<summary><strong>Optional: Verify an Anna's Archive announcement with its signing key</strong></summary>

Anna's Archive has published a public signing key that can be used to verify signed announcements, including announcements about new domains.

This is optional and intended for users who want a stronger way to check authenticity.

### Expected Fingerprint

```text
0D71 8B0A 3412 9CE1 AB50 42DF DB31 2C32 7E58 6040
```

### Public Key

Save the following content in a file named `annas-archive-public-key.asc`:

```text
-----BEGIN PGP PUBLIC KEY BLOCK-----

xjMEAAAAABYJKwYBBAHaRw8BAQdALQ/QcjyTg8kjI3qpoudsCX+jwh5tl2ExBBm0
LgE9hHnNDkFubmEgQXJjaGl2aXN0wmEEExYIABMFAgAAAAAJENsxLDJ+WGBAAhsD
AABppwEArVPP1JLxdnnahvHiiG6CpqnGdylqBDJ4YGwYcwP7Qk4BAIVFVYmd0aQg
Yf6q+OhORfJN9w+ytvUQ/q3p2fSFweEL
=keqc
-----END PGP PUBLIC KEY BLOCK-----
```

### Install GnuPG

- **Windows**: Install [Gpg4win](https://www.gpg4win.org/).
- **macOS with Homebrew**:

```bash
brew install gnupg
```

- **Debian or Ubuntu**:

```bash
sudo apt install gnupg
```

### Import the Key

Open a terminal in the folder containing the key and run:

```bash
gpg --import annas-archive-public-key.asc
```

### Check the Fingerprint

Run:

```bash
gpg --fingerprint "Anna Archivist"
```

Make sure the displayed fingerprint is exactly:

```text
0D71 8B0A 3412 9CE1 AB50 42DF DB31 2C32 7E58 6040
```

Stop if the fingerprint is different.

### Verify a Signed Announcement

For an announcement and a separate signature file:

```bash
gpg --verify announcement.txt.asc announcement.txt
```

For a clear-signed announcement contained in one file:

```bash
gpg --verify announcement.asc
```

A valid result should include a message similar to:

```text
Good signature from "Anna Archivist"
```

Also verify that:

- The fingerprint matches the expected fingerprint above.
- The signed message clearly names the announced domain.
- The announcement is recent.
- The message has not been revoked or replaced.

A valid signature proves that the message was signed by the matching private key. It does not make every website using the Anna's Archive name trustworthy.

</details>

3. **Register an Account (Optional)**:
   - Registration is not required for basic searching and slow downloads.
   - To register, click on "Log in / Register" on the homepage.
   - Select "Register new account."
   - Store the secret key in a password manager or an encrypted offline note.
   - Treat the secret key like a password. Do not save it in a synchronized bookmark, screenshot, email, or public message.
   ![Anna's Archive Registration](images/annas-archive-registration.png)

4. **Download Calibre**:
   - Visit [Calibre's website](https://calibre-ebook.com/).
   - Click on "Download calibre" and select the appropriate operating system.
   - For Windows users, click on "Download calibre 64bit." Select the equivalent option for other operating systems.
   ![Calibre Download](images/calibre-download.png)

## Accessing Anna's Archive (Registered Users)

Registration is optional. Skip this section if you are using Anna's Archive without an account.

1. **Log In**:
   - Open one of the verified Anna's Archive mirrors.
   - Click on "Log in / Register."
   - Copy the secret key from your password manager or encrypted backup and paste it into the "Secret key" field to log in.
   ![Anna's Archive Login](images/annas-archive-login.png)

## Searching and Downloading

1. **Search for Resources**:
   - Use the search bar to enter the Title, Author, DOI, ISBN, ASIN, MD5, etc.
   ![Search Resources](images/search-resources.png)

2. **Refine Search Results**:
   - Use the sidebar filters to refine your search:
     - **Filetype**: Choose `epub` when available. EPUB is usually the best format for ordinary books on an e-reader because the text adapts to the screen. Avoid PDF when a good EPUB version is available.
     - **Source**: You can disable sources you do not trust. For example, it is possible to disable books coming from the Russian Libgen source `Libgen.rs`. 
     - **Language**: Select the desired language.
   ![Refine Search](images/refine-search.png)

3. **Open Multiple Options**:
   - Open at least the first three options for the book in new tabs.

4. **Evaluate Download Options**:
   - Check the "Report file issue" number:
     - Avoid downloading files with reports related to malware, corruption, or the wrong book.
     - If the reported issue is only download difficulty, the file may still be usable.
     - No report doesn't mean the file is fully safe, only use it as an indicator. 
   - Check the "Stats" number:
     - Prefer options with higher statistics for better reliability.
     - A more popular file has usually been used by more people, but popularity is still only an indicator and not proof that the file is safe.
   - Confirm the title, author, language, edition, file type, and approximate file size.
   ![Download Options](images/download-options.png)

<details>
<summary><strong>Optional: Perform a stronger file-safety check</strong></summary>

The checks above are useful indicators, but they are not foolproof. Users who want a stronger check can follow these additional steps.

### 1. Check the Real Filename

Make sure the filename ends with the expected extension:

```text
book-name.epub
```

Avoid unexpected or double extensions such as:

```text
book-name.epub.exe
book-name.pdf.scr
book-name.zip.bat
```

On Windows, enable **View > Show > File name extensions** in File Explorer so that the complete filename is visible.

### 2. Avoid Unexpected File Types

For normal book reading, avoid files ending in:

```text
.exe
.msi
.bat
.cmd
.scr
.com
.js
.jar
.apk
.dmg
.iso
```

Also be cautious with password-protected archives or unexpected `.zip`, `.rar`, and `.7z` files.

An EPUB should normally be an `.epub` file, not an installer or executable.

### 3. Scan the File Locally

On Windows:

1. Right-click the downloaded file.
2. Select "Scan with Microsoft Defender" or the equivalent option from your antivirus.
3. Do not open the file if a detection is reported.

On Linux with ClamAV installed:

```bash
clamscan --infected book-name.epub
```

A clean scan is useful, but it does not guarantee that the file is harmless.

### 4. Inspect an EPUB

An EPUB is normally a ZIP-based container. You can inspect it with an archive viewer such as 7-Zip without opening the book in a reader.

A normal EPUB commonly contains files and folders such as:

```text
META-INF/
OEBPS/
mimetype
content.opf
.xhtml
.css
.jpg
.png
```

Be cautious if it contains unexpected executables, installers, shortcuts, or deeply nested archives.

### 5. Create a SHA-256 Hash

A hash provides a stable identifier for the exact file. It can be useful when comparing copies or reporting a suspicious file.

On Windows PowerShell:

```powershell
Get-FileHash ".\book-name.epub" -Algorithm SHA256
```

On macOS or Linux:

```bash
shasum -a 256 book-name.epub
```

A hash identifies the file but does not prove that it is safe.

If you use an online reputation service, search for the hash first instead of immediately uploading the complete file. Do not upload private or sensitive documents to a public scanning service.

### 6. Use Updated Reading Software

Open the file using an updated version of Calibre, your e-reader software, or another trusted EPUB reader.

</details>

5. **Download the Book**:
   - Go to the downloads tab and select the option labeled "(no waitlist, but can be very slow)" when it is available. This is usually the simplest free option, although the download may take time.
   ![Download Book](images/download-book-1.png)
   - Click "Download now" in a new tab.
   - Choose the download location and keep the book name intact.
   - Organize your downloads by creating a folder for each day's downloads.
   - Avoid starting several downloads simultaneously. Multiple downloads may fail, stop partway through, or make each other slower. For better reliability, let one book finish before starting the next one.
   ![Download Book](images/download-book-2.png)

## Using Calibre with Your E-Reader

1. **Open Calibre**:
   - Launch the Calibre application on your computer.

2. **Add Books to Calibre**:
   - Drag and drop the books you downloaded into the Calibre app.

3. **Connect Your E-Reader**:
   - Connect your e-reader to your computer.
   - Wait for Calibre to recognize the e-reader.

4. **Send Books to Your E-Reader**:
   - Select the books in Calibre.
   - Click on "Send to device" to transfer the books to your e-reader.
   - Monitor the jobs in the bottom-right corner to ensure the transfer is complete.

5. **Disconnect Your E-Reader**:
   - Safely eject your e-reader like a USB drive to avoid data corruption.
   - Enjoy reading your new books!

## Tips and Tricks

- **Amazon as a Resource**:
  - Look up the book or series on Amazon for easy identification.
  - Click on the series name to view all book titles and covers.
  - Find the ASIN of the book on Amazon to use it in your search.

- **Managing Series and Metadata in Calibre**:
  - To ensure your books are recognized as part of a series with the correct author, edit metadata in Calibre before transferring to your e-reader.
  - Right-click the book and select "Edit metadata" > "Edit metadata individually."
  - In the series field, enter the series name (ensure consistency with casing and spelling).
  - Enter the book's number in the series.
  - Correct any typos in the author name and author sort fields.
  - For multiple books, select them all and use "Edit metadata" > "Edit metadata in bulk."

## Troubleshooting and FAQs

- **Common Issues**:
  - **Download Failures**: Ensure your internet connection is stable. Retry if needed. If the problem continues, try another result or another verified Anna's Archive mirror.
  - **Logging In**: Make sure you are using the correct secret key and a verified Anna's Archive mirror.

- **FAQs**:
  - **Do I need to register an account?**
    - No. Registration is optional for basic searching and slow downloads.
  - **Can I download multiple books at once?**
    - It may be possible, but simultaneous downloads can fail or interrupt one another. For better reliability, download one book at a time.
  - **Does LibreWolf make me anonymous?**
    - No. LibreWolf can reduce some browser tracking, but it does not hide your public IP address.
  - **Is EPUB completely safe?**
    - No file format is completely safe. EPUB is generally convenient for books and e-readers, but files should still be opened with updated software.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
