# mokuro

Read Japanese manga with selectable text inside a browser.

**See demo: https://kha-white.github.io/manga-demo**

mokuro is aimed towards Japanese learners, who want to read manga in Japanese with a pop-up dictionary like [Yomichan](https://github.com/FooSoft/yomichan).
It works like this:
1. Perform text detection and OCR for each page.
3. After processing a whole volume, generate a HTML file, which you can open in a browser.
4. All processing is done offline (before reading). You can transfer the resulting HTML file together with manga images to
another device (e.g. your mobile phone) and read there.

mokuro uses [comic-text-detector](https://github.com/dmMaze/comic-text-detector) for text detection
and [manga-ocr](https://github.com/kha-white/manga-ocr) for OCR.


# Installation

You need Python 3.6, 3.7, 3.8 or 3.9. Unfortunately, PyTorch does not support Python 3.10 yet.

Some users have reported problems with Python installed from Microsoft Store. If you see an error:
`ImportError: DLL load failed while importing fugashi: The specified module could not be found.`,
try installing Python from the [official site](https://www.python.org/downloads).

If you want to run with GPU, install PyTorch as described [here](https://pytorch.org/get-started/locally/#start-locally),
otherwise this step can be skipped.

Run in command line:

```commandline
pip3 install mokuro
```

# Usage

## Run on one volume

```bash
mokuro /path/to/manga/vol1
```

This will generate `/path/to/manga/vol1.html` file, which you can open in a browser.

## Run on multiple volumes

```bash
mokuro /path/to/manga/vol1 /path/to/manga/vol2 /path/to/manga/vol3
```

For each volume, a separate HTML file will be generated.

## Run on a directory containing multiple volumes

If your directory structure looks somewhat like this:
```
manga_title/
├─vol1/
├─vol2/
├─vol3/
└─vol4/
```

You can process all volumes by running:

```bash
mokuro --parent_dir manga_title/
```

## Other options

```
--force_cpu - disable GPU
--as_one_file - generate separate css and js files instead of embedding everything in html
--disable_confirmation - run without asking for confirmation
```

# Contact
For any inquiries, please feel free to contact me at kha-white@mail.com

# Acknowledgments

- https://github.com/dmMaze/comic-text-detector
- https://github.com/juvian/Manga-Text-Segmentation
