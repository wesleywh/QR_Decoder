# What Is This?
This is a copy of a series of githubs and blog posts combined into a single convienant package for getting
your qr code values from your authenticator app. I made this so I could easily transfer already made time
base codes from one authenticator app into any other without having to turn off 2fa and turn it back on
for the purpose of just having it in more than one place.

# Installation Steps
1. brew install zbar
    - if M1 mac:
        a. mkdir ~/lib
        b. ln -s $(brew --prefix zbar)/lib/libzbar.dylib ~/lib/libzbar.dylib
    - if windows, this comes pre-installed can skip
    - if linux apt-get install zbar
2. pip install -r requirements.txt -t "full/path/to/this/dir"

# How To Run
```
python decode_qr.py
```
Then open google authenticator (or some other TOTP app) and generate the QR code (normally via export menu).
Show the QR code to your camera and it will spit out all the content you need from the QR code to your console.
It will also save the content to a barcodes.csv file for you.

## Generate QR Code Images
If you want to generate the QR code image to scan into another app on your phone (without another phone) then
run the following command:
```
python decode_qr.py --generate qr_code
```
This will do all the same things as above but will also generate a `qr_code.png` file that is the url content
of the qr code.

## Change Saved FileName
```
python decode_qr.py --output my-new-file.csv
```
This will change the qr code content getting saved from `barcodes.csv` to `my-new-file.csv`.

## Additional Notes
The `start_webcam.py` file, like the name suggests, will only start your webcam. Does nothing by
itself. I only kept this for learning how to do this yourself.