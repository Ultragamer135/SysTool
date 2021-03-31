dist_bin_SCRIPTS = src/systool
dist_man1_MANS = man/systool.man
dist_info_TEXINFOS = man/systool.texi
all: verify-checksum clean
clean-local:
	@rm -r autom4te.cache/
	@rm aclocal.m4
clean-build: clean
	@rm Makefile Makefile.in
	@rm config.status configure config.log
	@rm install-sh missing
clean-extra: clean
	@rm man/systool.man man/systool.texi
	@rm checksum.md5.txt checksum2.md5.txt
portable:
	@echo "Making portable install..."
	@mv ./src/* .
	@mv ./man/systool.* .
	@make clean
	@echo -n "Portable install complete. Path to current folder is: "
	@pwd
verify-checksum:
	@echo "Verifying Checksums..."
	@md5sum -c checksum.md5.txt
	@md5sum -c checksum2.md5.txt
	@echo "Done! Return status was: $?"
make-man:
	@echo "Creating texinfo documents and man pages from ./man/systool.md ..."
	@pandoc -st texinfo man/systool.md -o man/systool.texi
	@pandoc -st man man/systool.md -o man/systool.man
	@echo "Done!"
make-checksum:
	@echo "Generating checksums using md5..."
	@md5sum src/* ChangeLog AUTHORS COPYING INSTALL LICENCE NEWS README > checksum.md5.txt
	@md5sum checksum.md5.txt > checksum2.md5.txt
	@echo "Done!"