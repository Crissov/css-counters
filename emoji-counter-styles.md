Emoji Counter Style Templates
=============================

- **uses**: https://drafts.csswg.org/css-counter-styles/
- **extends**: https://github.com/w3c/predefined-counter-styles
- **author**: Christoph Päper bugzilla@crissov.de

    
Ideas
    - `pointed-stars`: 4✦✧ 5★✩✪✫✬✭✮✯ 6✶✡ 8✴︎✴✴️✷✵✸ 12✹
    - `pointed-asterisks`:  4✢✣✤✥ 5*⁎∗⊛ ⁑ ⁂ 6✱✲✻✼✽❃❉ 8✳❊❋ 16✺
    - `hand`: –1…+5: –1👎 0✊/👊/👌 1👍 2✌️/👆 3🖖/👉 4🤘/🖕 5🖐/✋/👊
    - `smiley`: –2…+2 –2☹️😟😠😡 –1😕🙁 0😐😑 +1 😀🙂+2😃😍
    */
    
Decimal
-------

- `fingers`: 0…10: 0✊/👊/👌 1☝️(👆/🖕/👇/👈/👉) 2✌️ 3…/🖖 4…/🤘/✋ 5🖐/✋ 6=5+1 … 10👐
- `decimal-symbols` various variants, e.g. cards
1. 🂡🂱🃁🃑
2. 🂢🂲🃂🃒
3. 🂣🂳🃃🃓
4. 🂤🂴🃄🃔
5. 🂥🂵🃅🃕
6. 🂦🂶🃆🃖
7. 🂧🂷🃇🃗
8. 🂨🂸🃈🃘
9. 🂩🂹🃉🃙
0. 🂪🂺🃊🃚

    

Both emoji styles use standard emoji-style keycap digits with U+FE0F ‘Variation Selector-16’ and U+20E3 ‘Combining Enclosing Keycap’. 
- **issue**: The suffix variant `keycap-decimal` probably only works properly for single-digit numbers.

`emoji-numbers` only supports ten items
> 1️⃣2️⃣3️⃣4️⃣5️⃣6️⃣7️⃣8️⃣9️⃣🔟

`emoji-decimal`, `keycap-decimal` are truly numeric styles
> 0️⃣1️⃣2️⃣3️⃣4️⃣5️⃣6️⃣7️⃣8️⃣9️⃣

    @counter-style emoji-numbers {
      system: fixed;
      range: 1 10;
      symbols: '\31\FE0F\20E3' '\32\FE0F\20E3' '\33\FE0F\20E3' '\34\FE0F\20E3' '\35\FE0F\20E3' '\36\FE0F\20E3' '\37\FE0F\20E3' '\38\FE0F\20E3' '\39\FE0F\20E3' '\1F51F';
    }
    @counter-style emoji-decimal {
      system: numeric;
      symbols: '\30\FE0F\20E3' '\31\FE0F\20E3' '\32\FE0F\20E3' '\33\FE0F\20E3' '\34\FE0F\20E3' '\35\FE0F\20E3' '\36\FE0F\20E3' '\37\FE0F\20E3' '\38\FE0F\20E3' '\39\FE0F\20E3';
    }
    @counter-style keycap-decimal {
      system: extends decimal;
      suffix: "\FE0F\20E3";
    }
    

Dozenal / Dodecimal
-------------------


    

`clock-face` shows full hours on an analog clock face
>  🕐🕑🕒🕓🕔🕕🕖🕗🕘🕙🕚🕛

- **issue**: start with 0=12 or 1?

    @counter-style clock-face {
      system: cyclic;
      symbols: '\1F550', '\1F551', '\1F552', '\1F553', '\1F554', '\1F555', '\1F556', '\1F557', '\1F558', '\1F559', '\1F55A', '\1F55B';
    }
    

Hexadecimal
-----------

- `hexdecimal-notes` ? 16 ♩ 8 ♪ 4 ♫ 2 ♬ 1 \2269…C

    

Octal
----

- `recycling` fixed 1…7: ♳♴♵♶♷♸♹ 
- `octal-recycling` numeric \♳♴♵♶♷♸♹ 2673…9 (♺)
- `lunar-phase`: \1F311 🌑 \1F312 🌒  \1F313 🌓 \1F314🌔 \1F315 🌕 \1F316 🌖 \1F317 🌗  \1F318 🌘
- `cloudy`: \2600 ☀️ \1F324 🌤 \26C5 ⛅️ \1F325 🌥  \2601 ☁️

    

Quadrenary / Quadruply?
----------------------

- `notes` ? ♩♪♫♬ \2269…C
- `lunar-face`: \1F31A 🌚 \1F31B 🌛 \1F31D 🌝 \1F31C 🌜

    

Ternary
-------

- `medal`: gold-silver-bronze, Unicode 9:2016 \1F3C5 🏅
- `globe`: \1F30E 🌎 \1F30D 🌍 \1F30F 🌏

    

Binary
------

- `binary-power`: \2B58 Heavy Circle (= Power Off = 0)  \23FD Power On (= 1)
- `braille`, `binary-braille`/`byte`
- `beer`: \1F37A 🍺 \1F37B 🍻
- `day-night`: \1F31E 🌞 \1F31D 🌝

    

Fixed
-----

- `colored-hearts`/`hearts`: ❤️💛💚💙💜💝/💖/💘
- `books`: \1F4D3 📓 \1F4D5 📕  \1F4D7 📗 \1F4D8 📘 \1F4D9 📙 \1F4D4 📔 \1F4D2 📒 \1F4DA 📚 \1F4D6
- `mailbox`: \1F4EA…D: 📪 📫 📬 📭
- `balls`: \26BD ⚽️ \1F3C0 🏀 \26BE ⚾️ \1F3BE 🎾 \1F3D0 🏐 \1F3B1🎱 \1F3C8 🏈 \1F3C9 🏉
- `daily-routine`


`blood-type` without Rhesus factor
>  🅾️🅰️🅱️🆎

    @counter-style blood-type {
      system: fixed;
      symbols: '\1F17E', '\1F170', '\1F171', '\1F172';
    }
    

Games
-----

- `playing-cards`
- `poker-suits` clubs < diamonds < hearts < spades ♣♢♡♠ \2663…0
- `skat-suits` diamonds < hearts < spades < clubs ♢♡♠♣
- `poker-cards` by *kicker* value 2 < 3 < 4 < 5 < 6 < 7 < 8 < 9 < 10 < J < Q < K < A
- `poker-hands` 5-digits, single-deck
- `skat-cards` 7…10 JQKA
- `chess-white` fixed ♙♘♗♖♕♔
- `chess-black` fixed ♟♞♝♜♛♚
- `go`

     

Alphabetic
---------

- `english-phonics`: 🐒 🐝 🐛 …
- `alphabetic-symbols` various variants
a) 🅰️🗼🖇🔼🔺🔒🎪👖🌲💩🈴
b) 🅱️💪👍
c) ©️☪🗜🌜🌘◀️📞
d) 🌓🌛☝🌮▶️🆔🍺👂👌🐌
e) 📧🍥💶
f) 🎏🎋🗜☦🈂⏬
g) ⛽️↪🌀
h) ♓🏨🏩
i) 🚹ℹ🕧🍾🕯📍🍿
j) 🕗🗾⤴️🎷🎐🏒🏑⏰
k) 🎋🏗
l) 🕒📐💷🏫
m) Ⓜ️〽️♏️♍️♒️⚖🎮
n) 🈂️⁉️🎵🚧🍴
o) 🅾️⭕️🍩🔘⏺💍📯💿📀⚙⚽️🏀⚾️🎾🏐🎱🍪☀️🌕🌝🕳
p) 🅿️🚩
q) 🎯🚫♎️🍭🔍👁‍🗨
r) ®️🎋♌️💃👠
s) 💲💰💵⚡️♋️
) ✝️🌴☂️➕⛏🗡👕
u) ⛎🤘🌙🍉🗑
v) 🖖✌️♈️✅🔽✔️☑️🔻🍕
w) 👐〰️⚓️🔱
x) ❎❌✖️🔀⚔🛠⚒✂️🎀
y) 🏅🍸☢️❣️🔧💴💹🔌🈂️
z) 💤

