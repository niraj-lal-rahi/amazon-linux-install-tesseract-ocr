# amazon-linux-install-tesseract-ocr
This is steps to install tesseract on aws server amazon-linux

sudo yum install gcc-c++

sudo yum install autoconf aclocal automake

sudo yum install libtool

sudo yum install libjpeg-devel libpng-devel libtiff-devel zlib-devel

cd ~/downloads

wget http://www.leptonica.com/source/leptonica-1.72.tar.gz

tar -zxvf leptonica-1.72.tar.gz

cd leptonica-1.72

./configure

make

sudo make install

cd ..
wget https://github.com/tesseract-ocr/tesseract/archive/3.04.00.tar.gz

tar -zxvf 3.04.00.tar.gz

cd tesseract-3.04.00/

./autogen.sh

./configure

make

sudo make install

sudo ldconfig

cd /usr/local/share/tessdata

sudo wget https://mirrors.xtom.com/osdn//sfnet/t/te/tesseract-ocr-alt/tesseract-ocr-3.02.eng.tar.gz

sudo tar xvf tesseract-ocr-3.02.eng.tar.gz

sudo wget https://mirrors.bfsu.edu.cn/osdn//sfnet/t/te/tesseract-ocr-alt/tesseract-ocr-3.01.osd.tar.gz

sudo tar xvf tesseract-ocr-3.01.osd.tar.gz

export TESSDATA_PREFIX=/usr/local/share/

sudo mv tesseract-ocr/tessdata/* .

sudo rm tesseract-ocr-3.02.eng.tar.gz

# we need osd for autorotate

sudo rm tesseract-ocr-3.01.osd.tar.gz

nano ~/.bash_profile

# Copy this line to the end: export TESSDATA_PREFIX=/usr/local/share/
# Verify:

tesseract --list-langs
