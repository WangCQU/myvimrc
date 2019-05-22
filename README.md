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
 ```vim
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

