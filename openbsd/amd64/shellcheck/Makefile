## nota bene: TMPDIR must be on a partition with mount options 'exec' and 'wxallowed'
##            .. for example:
# if [[ -x "$(/usr/bin/which cabal 2>/dev/null)" ]] && [[ -d /usr/local/cabal/build ]] && [[ -w /usr/local/cabal/build ]]; then
#         alias cabal='env TMPDIR=/usr/local/cabal/build/ cabal'
# fi
#
## nota bene 2: `cabal new-build` relies on `pandoc` for documentation - please build
#             .. that first or the build will throw an error

all:
	git clone https://github.com/koalaman/shellcheck.git shellcheck-src && \
	cd shellcheck-src && \
	git checkout v0.7.0 && \
	cabal new-update && \
	cabal new-clean && \
	export TMPDIR=/usr/local/cabal/build && \
	patch ShellCheck.cabal ../static.patch && \
	cp ../cabal.project.local . && \
	cabal new-build && \
	find dist-newstyle -type f -name shellcheck -exec cp -p {} ../ \; && \
	strip -s ./shellcheck

clean:
	rm -rf shellcheck shellcheck-src/
