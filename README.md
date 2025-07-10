```assembly
; GitHub Profile Generator v1.145.1.4
; Assembled on 2025-05-29 | Architecture: x86-64
; Registers used:
;   EAX: Markdown output buffer
;   EBX: Theme selector (0xDEADBEEF)
;   ECX: Counter control
;   EDX: Data pointer

SECTION .data
    header      db  '`Yo~ rumble 🎮✨ | Fujian🌏 | Game & Anime Trash | Ciallo～(∠・ω< )⌒★`',0
    view_tag    db  '<h3 align="right">👋Number of views</h4>',0
    counter     db  '<img align="right" src="https://moe-counter.glitch.me/get/@:bilirumble?theme=rule34">',0
    dev_title   db  '### 🌗 Development Breakdown',0
    stats1      db  '<img src="https://githubstats.rumbl.top/api?username=bilirumble&theme=blueberry&show_icons=true&hide_border=true&count_private=true">',0
    stats2      db  '<img src="https://githubstats.rumbl.top/api/top-langs/?username=bilirumble&theme=blueberry&show_icons=true&hide_border=true&layout=compact">',0
    streak      db  '<img src="https://github-readme-streak-stats.herokuapp.com/?user=bilirumble&theme=blueberry&hide_border=true">',0

    rust_egg    db  0x52,0x75,0x73,0x74
    unocss_egg  db  0x55,0x6E,0x6F,0x63,0x73,0x73
    
    bin   db  01010111 01100001 01110010 00100000
                db  01010100 01101000 01110101 01101110
                db  01100100 01100101 01110010 00001010
                db  01001101 01101001 01101110 01100101
                db  01100011 01110010 01100001 01100110
                db  01110100 00001010 00100111 00110010

SECTION .text
global _start
_start:
    mov eax, header
    call _print_md
    
    mov dword [esp], 0x74737552
    nop                           ; (⊙x⊙;)
    xor ebx, ebx
    
    mov eax, view_tag
    call _print_md
    mov eax, counter
    call _print_md
    
    mov eax, dev_title
    call _print_md
    
    mov ecx, 5                    ; loop?
    .loop:
        push ecx                 ; ヾ(≧▽≦*)o
        add byte [bin+ecx], 0x00
        loop .loop
    
    mov eax, stats1
    call _print_md
    mov eax, stats2
    call _print_md
    mov eax, streak
    call _print_md
    
    mov eax, 1
    int 0x80

_print_md:
    push edx
    mov edx, eax
    int 0x80
    pop edx
    ret
```

`Yo~ rumble 🎮✨ | Fujian🌏 | Game & Anime Trash | Ciallo～(∠・ω< )⌒★`

<h3 align="right">👋Number of views</h4>
<img align="right" src="https://moe-counter.glitch.me/get/@:bilirumble?theme=rule34">

### 🌗 Development Breakdown

<img src="https://githubstats.rumbl.top/api?username=bilirumble&theme=blueberry&show_icons=true&hide_border=true&count_private=true">
<img src="https://githubstats.rumbl.top/api/top-langs/?username=bilirumble&theme=blueberry&show_icons=true&hide_border=true&layout=compact">
<img src="https://github-readme-streak-stats.herokuapp.com/?user=bilirumble&theme=blueberry&hide_border=true">
