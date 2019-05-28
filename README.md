# myvimrc
## Requirements
1. Python 3.7
 - pip install unidecode (for Ultisnips)
2. Nodejs (for coc.nvim)
 - nmp -g install yarn
3. coc.nvim (for completion)
 - CosInstall coc-vimtex
 - CosInstall coc-ultisnips
4. ctags: Ctrl-] jump to the label
 - brew install ctags
 - add '~/.ctags.d/default.ctags': 
 ```bash
 	--langdef=tex2
	--langmap=tex2:.tex
	--regex-tex2=/\\label[ \t]*\*?\{[ \t]*([^}]*)\}/\1/l,label/
	--langdef=bib
	--langmap=bib:.bib
	--regex-bib=/^@[A-Za-z]+\{([^,]+),/\1/e,BibTeX-Entries/i
	--regex-bib=/^@string\{([^ "#%')(,=}{]+)/\1/s,BibTeX-Strings/i
	--regex-bib=/author[[:space:]]*=[[:space:]]*("([^"]+)"|\{([^\}]+)\})[[:space:]]*,?[[:space:]]*$/\2\3/a,BibTeX-Authors/i
```
 - ":! git init" needed in every source folders 
5. latexindent
 - Install perl libraries without root privilege, and intall them in user home!
 ```bash
 	PERL_MM_OPT="INSTALL_BASE=$HOME/.perl5" cpan local::lib
 ```
 - if output with "ExTERN.h" missing error, try
 ```bash
 sudo installer -pkg /Library/Developer/CommandLineTools/Packages/macOS_SDK_headers_for_macOS_10.14.pkg
 ```
 or try
 ```bash
 sudo installer -pkg /Library/Developer/CommandLineTools/Packages/macOS_SDK_headers_for_macOS_10.14.pkg -target /
 ```
 -  In file .bash_profile, add a line
 ```bash
 eval "$(perl -I$HOME/.perl5/lib/perl5 -Mlocal::lib=$HOME/.perl5)"
 ```
 then 
 ```bash
 source ~/.bash_profile
 ```
 - install the nessary library for perl
 ```bash
brew install cpanm
cpanm --local-lib=~/.perl5 local::lib && eval $(perl -I ~/.perl5/lib/perl5/ -Mlocal::lib=$HOME/.perl5)
cpanm Log::Log4perl Log::Dispatch::File YAML::Tiny File::HomeDir Unicode::GCString
```
