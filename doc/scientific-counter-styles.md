Scientific Counter Style Templates
==================================

- **uses**: https://drafts.csswg.org/css-counter-styles/
- **extends**: https://github.com/w3c/predefined-counter-styles
- **author**: Christoph Päper bugzilla@crissov.de

    
Physics and Chemistry
---------------------

    

### To do
- `si-prefixes`: k, M, G, T, E … standalone with or without ^- prefixes; 
use `system: extends si-prefixes;` for your favorite unit, e.g. `suffix: 'g'` for gram.

    

`element-symbols`
Who wouldn’t want to use these for pagination of their physics or chemistry thesis? 

    @counter-style element-symbols {
      system: fixed;
      range: 1 118;
      symbols: 'H',                                                                                                  'He',
               'Li', 'Be',                                                             'B',  'C',  'N',  'O',  'F',  'Ne', 
               'Na', 'Mg',                                                             'Al', 'Si', 'P',  'S',  'Cl', 'Ar',
               'K',  'Ca', 'Sc', 'Ti', 'V',  'Cr', 'Mn', 'Fe', 'Co', 'Ni', 'Cu', 'Zn', 'Ga', 'Ge', 'As', 'Se', 'Br', 'Kr', 
               'Rb', 'Sr', 'Y',  'Zr', 'Nb', 'Mo', 'Tc', 'Ru', 'Rh', 'Pd', 'Ag', 'Cd', 'In', 'Sn', 'Sb', 'Te', 'I',  'Xe',
               'Cs', 'Ba',      /*
                        */ 'La', 'Ce', 'Pr', 'Nd', 'Pm', 'Sm', 'Eu', 'Gd', 'Tb', 'Dy', 'Ho', 'Er', 'Tm', 'Yb', 'Lu', /*
                              */ 'Hf', 'Ta', 'W',  'Re', 'Se', 'Ir', 'Pt', 'Au', 'Hg', 'Tl', 'Pb', 'Bi', 'Po', 'At', 'Rn', 
               'Fr', 'Ra',      /*
                        */ 'Ac', 'Th', 'Pa', 'U',  'Np', 'Pu', 'Am', 'Cm', 'Bk', 'Cf', 'Es', 'Fm', 'Md', 'No', 'Lr', /*
                              */ 'Rf', 'Db', 'Sg', 'Bh', 'Hs', 'Mt', 'Ds', 'Rg', 'Cn', 'uut','Fl', 'uup','Lv', 'uus','uuo';
    }

`element-symbols-boxed`

- **issue**: Would be cooler with enclosing square U+20DE, circle U+20DD, diamond U+20DF, triangle U+20E4 or keycap U+20E3,
but not sure how to do for 2 (or even 3) characters. 
Circle could be faked with parentheses affixes plus U+0361 and U+035C perhaps, and square with brackets and U+035E + U+35F.

    @counter-style element-symbols-boxed {
      system: extends element-symbols;
      prefix: '[';
      suffix: ']'; /* \20DE */
    */
    

Astronomy and Astrology
-----------------------

The latter is of course not a science, but uses the symbols even more.
Both are the base for calendars.

    

`planets` without dwarf planets

Mercury ☿, Venus ♀, Earth ♁, Mars ♂, Jupiter ♃, Saturn ♄, Uranus ♅, Neptune ♆ 

    @counter-style planets {
      system: fixed;
      range: 1 8;
      symbols: '\263F', '\2640', '\2641', '\2642', '\2643', '\2644', '\2645', '\2646';
    }

`solar-system` unlike `planets` includes Sun ☼ and Pluto ♇

    @counter-style solar-system {
      system: fixed;
      range: 0 9;
      symbols: '\263C', '\263F', '\2640', '\2641', '\2642', '\2643', '\2644', '\2645', '\2646', '\2647';
    }
    

`week-days`
- **link**: https://en.wikipedia.org/wiki/Names_of_the_days_of_the_week

1. Monday    ☽ U+263D Moon, variant: ☾ U+263E
2. Tuesday   ♂ U+2642 Mars
3. Wednesday ☿ U+263F Mercury
4. Thursday  ♃ U+2643 Jupiter
5. Friday    ♀ U+2640 Venus
6. Saturday  ♄ U+2644 Saturn 
7. Sunday    ☉ U+2609 Sun, variant: ☼ U+263C

- **issue**: Since the Sun symbol is defined for 0, it should also appear for 7, but not tested yet!

    @counter-style week-days {
      system: cyclic;
      range: 0 6;
      symbols: '\2609', '\263D', '\2642', '\263F', '\2643', '\2640', '\2644';
    }
    

`astronomic-months` and `months` are the same except for the suffix 
which should make the former plain text and the latter emoji-style

The count begins with Northward solstice, hence Julian/Georgian months.

1. January   ♑ U+2651 Capricorn
2. February  ♒ U+2652 Aquarius
3. March     ♓ U+2653 Pisces
4. April     ♈ U+2648 Aries
5. May       ♉ U+2649 Taurus
6. June      ♊ U+264A Gemini
7. July      ♋ U+264B Cancer
8. August    ♌ U+264C Leo
9. September ♍ U+264D Virgo
10. October   ♎ U+264E Libra
11. November  ♏ U+264F Scorpius
12. December  ♐ U+2650 Sagittarius

    @counter-style astronomic-months {
      system: cyclic;
      range: 1 12;
      symbols: '\2651', '\2652', '\2653', '\2648', '\2649', '\264A', '\264B', '\264C', '\264D', '\264E', '\264F', '\2650';
      suffix: '\FE0E'; /* variation selector VS-15 to ensure monochrome text symbols, not colorful emojis */
    }
    @counter-style months {
      system: extends astronomic-months;
      suffix: '\FE0F'; /* variation selector VS-16 to ensure colorful emoji symbols, not monochrome text */
    }
    

`astrologic-months` and `zodiac` are the same except for the suffix 
which should make the former plain text and the latter emoji-style

begins with Northward equinox, i.e. in classical European order of the signs of the Zodiac

1. April     ♈ U+2648 Aries
2. May       ♉ U+2649 Taurus
3. June      ♊ U+264A Gemini
4. July      ♋ U+264B Cancer
5. August    ♌ U+264C Leo
6. September ♍ U+264D Virgo
7. October   ♎ U+264E Libra
8. November  ♏ U+264F Scorpius
9. December  ♐ U+2650 Sagittarius
10. January   ♑ U+2651 Capricorn
11. February  ♒ U+2652 Aquarius
12. March     ♓ U+2653 Pisces

- **issue**: There should probably be a variant with ophicus ⛎ U+26CE

    @counter-style astrologic-months {
      system: cyclic;
      range: 1 12;
      symbols: '\2648', '\2649', '\264A', '\264B', '\264C', '\264D', '\264E', '\264F', '\2650',  '\2651', '\2652', '\2653';
      suffix: '\FE0E'; /* variation selector VS-15 to ensure monochrome text symbols, not colorful emojis */
    }
    @counter-style zodiac {
      system: extends astrologic-months;
      suffix: '\FE0F'; /* variation selector VS-16 to ensure colorful emoji symbols, not monochrome text */
    }
