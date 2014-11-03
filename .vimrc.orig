"	%001 till %007:	http://stackoverflow.com/questions/1878974/redefine-tab-as-4-spaces
" here are some tricks for vim
" 	http://forum.ubuntu-fr.org/viewtopic.php?id=132970
" the line where the #cursor is will be #underlined					%001
" there is a #line_number in the left								%002
" to turn on #color of syntax	#color_syntax						%003
" to set the size(nbr of space) of #hard #tab_stop					%004
" to set the size(nbr of space) of #indent							%005
" make 'tab' insert indents instead of tabs at the beginning of a line	%006
" always uses spaces instead of tab characters						%007
" set a #smart_indent                                      			%008
" set #background to black											%009
" then vim understand the #click of #mounse							%010
" if caracter in one line bo beyound #80_caracter, it will be		%011 
"	colored as #red 				
" the #multi_line_comment #comment like in java with multiline		%012
"	will be set auto
"		#mapping in vim:		http://vim.wikia.com/wiki/Mapping_keys_in_Vim_-_Tutorial_%28Part_1%29
" Ctrl-w+z	will save the file as #root		#nmap					%013
" Ctrl-w+t will give the time				#nmap					%014
" to make remembering the #last_position of a file					%015
" to #ignore_case when I do some research in vim					%016
" to select #columns												%017
" to #highlight ur search											%018
" #start by #editing 												%019
" to make vim in #insert mode #only									%020
" 	to insert a command in, type:	ctrl+0
" to convert the doc opened in vim to #html #tohtml					%021
" to install #bundle 												%022
" to activate&deactivate #nerdtree									%023
" adding another source of vimrc									%024
" opening #gundo													%025
" #remember #lastposition of cursor when u #reopen a file			%026
" research and will colorize it instantly #easymotion				%027
" to add some #templates #automatically when u #create a #shFile	%028
" to add some code automatically for #forr							%029
" there is a file which contains a name and #mail,					%030
" 	when I type a name, I would get the mail
" when I save #view and #session, I would like to save 				%031	
" 	all views in a folder	
" to #load a #session saved in $viewdir_v 							%032
" to open the #lastSession #session of vim #automatically			%033
" to enable #fold													%034

 

inoremap <C-A>o <
inoremap <C-A>c >


"	%034
set foldenable

"	%033
autocmd VimEnter * call LoadSession()
autocmd VimLeave * call SaveSession()
function! SaveSession()
execute 'mksession! $HOME/.vim/nonicken/views/session.vim'
endfunction
function! LoadSession()
if argc() == 0
execute 'source $HOME/.vim/nonicken/views/session.vim'
endif
endfunction


" 	%032
"	in bashrc: search for alias vims

"	%031
set viewdir=$HOME/.vim/nonicken/views

"	%030
set omnifunc=CompleteEmails
function! CompleteEmails(findstart, base)
	if a:findstart
		" locate the start of the word
		let line = getline('.')
		let start = col('.') - 1
		while start > 0 && line[start - 1] =~ '\a'
		let start -= 1
		endwhile
		return start
		else
		" find contact names matching with "a:base"
		let res = []
		" " we read contactlist file and sort the result
		for m in sort(readfile('/root/.vim/nonicken/contactsNnkn'))
		if m =~ '^' . a:base

		let contactinfo = split(m, '|')
		 " show names in list, but insert email address
		 call add(res, {'word': contactinfo[1],
					 \ 'abbr': contactinfo[0].' <'.contactinfo[1].'>',	
					 \ 'icase': 1} )
	 endif
 endfor
 return res
 endif
 endfunction


"	%029
iabbrev <buffer> forr for (x=0;x<var;x++){<cr>!cursor<cr>}

"	%028
autocmd BufNewFile *.sh 0r /root/.vim/nonicken/templates/sh.tpl

"	%027
"http://www.vim.org/scripts/script.php?script_id=3526
" :h easymotion
" map  / <Plug>(easymotion-sn)
" omap / <Plug>(easymotion-tn)

"	%026
if has("autocmd")
	  au BufReadPost * if line("'\"") > 1 && line("'\"") <= line("$") | exe "normal! g'\"" | endif
endif


"	%025
" http://www.vim.org/scripts/script.php?script_id=3304
" :h gundo
nmap <C-P>g	:GundoToggle<CR>

"	%024
source $HOME/ms_conf/viming

"	%023
nmap <C-P>n	:NERDTreeToggle<CR>

" 	%022
call pathogen#infect()
call pathogen#helptags()
syntax on
filetype plugin indent on

"	this is a test of gundo
"	this is another test of gundo

"	%021
"	:TOhtml
noremap toh :TOhtml<CR>


"	%020
" set im

"	%019
" start

"	%018
set hlsearch

"	%017
"	ctrl+v

"	%016
set ignorecase

"	%015
set viminfo='10,\"100,:20,%,n~/.viminfo

"if has("autocmd")
"    autocmd BufReadPost *
"    \ if line("\'") > 0 && line("\'") <= line("$") |
"        \ exe "normal g`" |
"    \ endif
"endif


"	%014
nmap <C-W>t	:echo 'Current time is ' . strftime('%c')<CR>

"	%012
set formatoptions+=r

"	%013
nmap <C-W>z	:w !sudo tee % <CR>

"	%011
highlight OverLength ctermbg=red ctermfg=white guibg=#592929
match OverLength /\%81v.\+/

"	%010
set mouse=a
"	to deactivate it
" set mouse=c

"	%009
hi Normal ctermbg=black
     	
"	%007
" set expandtab   

"	%006
set smarttab

"	%005
set shiftwidth=4

"azer here it is, haezarere ys
"	%004
set tabstop=4

"	%003
syntax on

" 	%001
set cul

"	%002
set nu    

"	%008
set smartindent


