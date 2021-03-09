dist_bin_SCRIPTS = src/systool
dist_man1_MANS = man/systool.man
dist_info_TEXINFOS = man/systool.texi
clean-local:
	@rm config.status configure config.log
	@rm Makefile
	@rm aclocal.m4
	@rm -r autom4te.cache/
	@rm install-sh missing Makefile.in
clean-extra:
	@rm COPYING INSTALL
	@make clean
portable:
	@echo "Making portable install..."
	@mv ./src/* .
	@mv ./man/systool.* .
	@make clean
	@echo -n "Portable install complete. Path to current folder is: "
	@pwd
generate-manpages:
	@echo "Creating texinfo documents and man pages from ./man/systool.md ..."
	@pandoc -st texinfo man/systool.md -o man/systool.texi
	@pandoc -st man man/systool.md -o man/systool.man
	@echo "Done!"