all: libfreenect

TARBALL = build/OpenKinect-libfreenect-master-d1d19df895.tar.gz
TARBALL_URL = http://cs.utexas.edu/~piyushk/bwi_share/OpenKinect-libfreenect-master-d1d19df895.tar.gz
SOURCE_DIR = build/OpenKinect-libfreenect-master-d1d19df895
MD5SUM_FILE = OpenKinect-libfreenect-master-d1d19df895.tar.gz.md5sum
UNPACK_CMD = tar xzf
include $(shell rospack find mk)/download_unpack_build.mk

libfreenect: $(SOURCE_DIR)/unpacked
	mkdir -p $(SOURCE_DIR)/build
	cd $(SOURCE_DIR)/build && cmake ../ 
	cd $(SOURCE_DIR)/build && make
	cp -rf $(SOURCE_DIR)/include include
	cp -rf $(SOURCE_DIR)/build/bin bin
	cp -rf $(SOURCE_DIR)/build/lib lib
	touch libfreenect

clean:
	-rm -rf src $(SOURCE_DIR) libfreenect include bin lib

wipe: clean
	-rm -rf build
