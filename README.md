# What is this
This project is not a single project. Instead, download only the documentation generators you need.

### Adventages of this approach

* Easier to maintain: [KISS](https://en.wikipedia.org/wiki/KISS_principle).
* Easier to hack: Having each plugin self-contained, makes it easier to fork and modify.
* Common codebase: All plugins share the same architecture, and most options.
* Together but not mixed: There is an adventage in keeping the same options for different documentation generators separated. This allows heavy customization.

### Disadventages of this approach

* Oh no, I have to install 3 plugins instead of one.

## Stable projects

* [vim-doxygen](https://github.com/Zeioth/vim-doxygen)
* [vim-typedoc](https://github.com/Zeioth/vim-typedoc)

## Highly experimental

* [vim-rustdoc](https://github.com/Zeioth/vim-rustdoc)
* [vim-godoc](https://github.com/Zeioth/vim-godoc)
* [vim-jsdoc](https://github.com/Zeioth/vim-jsdoc)

If you are not in need of heavy customization, please check [vim-doge](https://github.com/kkoomen/vim-doge).

### How to use

Install the plugins you need. Copy this on your vimconfig, and delete what you don't need:

```
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" => vim doxygen
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

" Enable it for the next languages
let g:doxygen_include_filetypes = ['c', 'cpp', 'cs', 'python', 'd', 'fortran', 'java', 'perl', 'vhdl', 'objc', 'php']

" Enable the keybindings, for the included_filetypes
augroup doxygen_mappings
  for ft in g:doxygen_include_filetypes
    execute 'autocmd FileType ' . ft . ' nnoremap <buffer> <C-h> :<C-u>DoxygenOpen<CR>'
    "execute 'autocmd FileType ' . ft . ' nnoremap <buffer> <C-k> :<C-u>DoxygenRegen<CR>'
  endfor
augroup END


"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" => vim typedoc
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

" Enable it for the next languages
let g:typedoc_include_filetypes = ['typescript']

" Enable the keybindings for the languages in g:typedoc_include_filetypes
augroup typedoc_mappings
  for ft in g:typedoc_include_filetypes
    execute 'autocmd FileType ' . ft . ' nnoremap <buffer> <C-h> :<C-u>TypedocOpen<CR>'
    "execute 'autocmd FileType ' . ft . ' nnoremap <buffer> <C-k> :<C-u>TypedocRegen<CR>'
  endfor
augroup END


"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" => vim rustdoc
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

" Enable it for the next languages
let g:rustdoc_include_filetypes = ['rust']

" Enable the keybindings for the languages in g:rustdoc_include_filetypes
augroup rustdoc_mappings
  for ft in g:rustdoc_include_filetypes
    execute 'autocmd FileType ' . ft . ' nnoremap <buffer> <C-h> :<C-u>RustdocOpen<CR>'
    "execute 'autocmd FileType ' . ft . ' nnoremap <buffer> <C-k> :<C-u>RustdocRegen<CR>'
  endfor
augroup END


"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" => vim jsdoc
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

" Enable it for the next languages
let g:jsdoc_include_filetypes = ['javascript']

" Enable the keybindings for the languages in g:jsdoc_include_filetypes
augroup jsdoc_mappings
  for ft in g:jsdoc_include_filetypes
    execute 'autocmd FileType ' . ft . ' nnoremap <buffer> <C-h> :<C-u>JsdocOpen<CR>'
    "execute 'autocmd FileType ' . ft . ' nnoremap <buffer> <C-k> :<C-u>JsdocRegen<CR>'
  endfor
augroup END


"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" => vim godoc
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

" Enable it for the next languages
let g:godoc_include_filetypes = ['go']

" Enable the keybindings for the languages in g:godoc_include_filetypes
augroup godoc_mappings
  for ft in g:godoc_include_filetypes
    execute 'autocmd FileType ' . ft . ' nnoremap <buffer> <C-h> :<C-u>GodocOpen<CR>'
    "execute 'autocmd FileType ' . ft . ' nnoremap <buffer> <C-k> :<C-u>GodocRegen<CR>'
  endfor
augroup END
```
## Will you unify all this projects in the future into a single plugin? 
Right now I don't see any big adventage in doing so.

## Where do that cheesy name come from?
From [Star Wars](https://starwars.fandom.com/wiki/Dooku).
