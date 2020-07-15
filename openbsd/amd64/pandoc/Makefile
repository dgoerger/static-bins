## nota bene: TMPDIR must be on a partition with mount options 'exec' and 'wxallowed'
##            .. for example:
# if [[ -x "$(/usr/bin/which cabal 2>/dev/null)" ]] && [[ -d /usr/local/cabal/build ]] && [[ -w /usr/local/cabal/build ]]; then
#         alias cabal='env TMPDIR=/usr/local/cabal/build/ cabal'
# fi
#
# If you run out of memory while compiling, remember to up the
# 'datasize-cur' value for your build user in /etc/login.conf,
# then log out and back in. The default value for pbuild is
# sufficient.

all:
	git clone https://github.com/jgm/pandoc.git pandoc-src && \
	cd pandoc-src && \
	git checkout 2.10 && \
	patch pandoc.cabal ../disable_ghc_option_threaded.patch && \
	export TMPDIR=/usr/local/cabal/build && \
	cabal new-update && \
	cabal new-clean && \
	cp ../cabal.project.local . && \
	cabal new-build && \
	find dist-newstyle -type f -name pandoc -exec cp -p {} ../ \; && \
	strip -s ../pandoc

clean:
	rm -rf pandoc pandoc-src/
