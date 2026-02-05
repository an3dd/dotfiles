" "Carica la configurazione di Hyde (attualmente commentato)
" "let s:VIM_DIR = fnamemodify($MYVIMRC, ':h')
" "execute 'source ' . s:VIM_DIR . '/hyde.vim'
" "

" --- IMPOSTAZIONI DI BASE ---
set nocompatible              " Disabilita la compatibilità con il 'vi' originale per usare le funzionalità moderne di Vim.
filetype plugin indent on     " Abilita il rilevamento del tipo di file, i plugin e l'indentazione specifica per file.
syntax on                     " Abilita l'evidenziazione della sintassi.

" --- INTERFACCIA UTENTE E ESPERIENZA D'USO ---
set number                    " Mostra i numeri di riga.
set norelativenumber          " Usa numeri di riga assoluti.
set hidden                    " Permette di nascondere un buffer invece di chiuderlo, preservando le modifiche non salvate.
set mouse=a                   " Abilita l'uso del mouse in tutte le modalità.
set clipboard=unnamedplus     " Usa la clipboard di sistema per le operazioni di copia/incolla.
set signcolumn=yes            " Mostra sempre la colonna dei segni (per linting, git, etc.).
set updatetime=300            " Imposta il tempo di attesa in millisecondi prima di scrivere il file di swap. Utile per plugin come CoC.

" --- IMPOSTAZIONI DI INDENTAZIONE ---
set tabstop=2                 " Imposta la larghezza di un carattere di tabulazione a 2 spazi.
set shiftwidth=2              " Imposta la larghezza per l'indentazione automatica a 2 spazi.
set softtabstop=2             " Consente di cancellare 2 spazi alla volta con il backspace.
set expandtab                 " Converte i caratteri di tabulazione in spazi.
set autoindent                " Mantiene l'indentazione della riga precedente quando si va a capo.
set smartindent               " Abilita un'indentazione più intelligente, consapevole della sintassi.


" --- IMPOSTAZIONI SPECIFICHE PER TIPO DI FILE ---
" C / C++
autocmd FileType c,cpp setlocal cindent " Abilita l'indentazione specifica per C/C++.

" Java
autocmd FileType java setlocal cindent " Abilita l'indentazione specifica per Java.

" JavaScript
autocmd FileType javascript setlocal shiftwidth=2 tabstop=2 softtabstop=2

" Python
autocmd FileType python setlocal
      \ expandtab
      \ shiftwidth=2
      \ tabstop=2
      \ softtabstop=2


" --- MAPPATURE DEI TASTI (SHORTCUTS) ---
" Inserisce automaticamente le parentesi di apertura e gestisce quelle di chiusura.

" Coppie di parentesi (), [], {}
inoremap <silent> ( ()<Left>
inoremap <silent> [ []<Left>
""inoremap <silent> { {}<Left>  
""inoremap <silent> { {<CR>}<C-o>O  // chiude la graffa sotto quella aperta 
inoremap <silent> { {<CR>}<Esc>kA 
inoremap <silent><expr> ) getline('.')[col('.')-1] == ')' ? "\<Right>" : ')'
inoremap <silent><expr> ] getline('.')[col('.')-1] == ']' ? "\<Right>" : ']'
inoremap <silent><expr> } getline('.')[col('.')-1] == '}' ? "\<Right>" : '}'

" Gestione intelligente di apici e virgolette
inoremap <silent><expr> ' getline('.')[col('.')-1] == "'" ? "\<Right>" : "''\<Left>"
inoremap <silent><expr> " getline('.')[col('.')-1] == '"' ? "\<Right>" : "\"\"\<Left>"

" Salva il file con <leader>w (di solito \w).
nnoremap <silent> <leader>w :w<CR>
" Chiude il file con <leader>q (di solito \q).
nnoremap <silent> <leader>q :q<CR>
" Salva e chiude il file con <leader>x (di solito \x).
nnoremap <silent> <leader>x :wq<CR>


" --- GESTORE DI PLUGIN (VIM-PLUG) ---
call plug#begin('~/.vim/plugged')

Plug 'neoclide/coc.nvim', {'branch': 'release'} " Plugin per l'autocompletamento e il Language Server Protocol (LSP).

call plug#end()


" --- CONFIGURAZIONE DI COC (CONQUER OF COMPLETION) ---

" Mappa il tasto Tab per l'autocompletamento e gli snippets.
inoremap <silent><expr> <Tab>
      \ coc#expandableOrJumpable() ? "\<C-r>=coc#rpc#request('doKeymap', ['snippets-expand-jump',''])\<CR>" :
      \ "\<Tab>"

inoremap <silent><expr> <CR>
      \ pumvisible() ? "\<C-y>" :
      \ "\<CR>"

" Mappa Shift-Tab per navigare indietro nel menu di autocompletamento.
inoremap <silent><expr> <S-Tab>
      \ pumvisible() ? "\<C-p>" : "\<C-h>"


" Vai alla definizione di una funzione o variabile.
nnoremap <silent> gd <Plug>(coc-definition)

" Mostra le informazioni (documentazione) del simbolo sotto il cursore.
nnoremap <silent> K :call CocActionAsync('doHover')<CR>

" Rinomina un simbolo (variabile, funzione, etc.) in tutto il progetto.
nnoremap <leader>rn <Plug>(coc-rename)




" --- TEMA COLORI ---
" Di seguito alcuni temi colore, solo 'unokai' è attivo.
"colorscheme zaibatsu "the only nice built-in colorscheme 
"colorscheme dracula
""colorscheme habamax 
"colorscheme koehler
""colorscheme retrobox
"colorscheme sorbet
""colorscheme torte
colorscheme unokai
"colorscheme wildcharm



" --- SFONDO TRASPARENTE ---
" Rende lo sfondo trasparente. Deve essere posizionato DOPO il comando 'colorscheme'.
highlight Normal guibg=NONE ctermbg=NONE
highlight NonText guibg=NONE ctermbg=NONE
highlight LineNr guibg=NONE ctermbg=NONE
highlight SignColumn guibg=NONE ctermbg=NONE
highlight EndOfBuffer guibg=NONE ctermbg=NONE


" --- BARRA INFORMATIVA ---
" Mostra la barra sotto con il nome dle file aperto al momento 
set laststatus=2


" --- MOSTRA IL COMANDO IN PROUZIONE ---
set showcmd
