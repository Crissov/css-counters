Classic European Counter Style Templates
========================================

- **uses**: https://drafts.csswg.org/css-counter-styles/
- **extends**: https://github.com/w3c/predefined-counter-styles
- **author**: Christoph Päper bugzilla@crissov.de

    

Alphabetic
----------

    

`lower-alpha-ancient` without letters *j, v, w* is intended for old-style blackletter and uncial typefaces,
but not limited to them.

    @counter-style lower-alpha-ancient {
      system: alphabetic;
      symbols: 'a' 'b' 'c' 'd' 'e' 'f' 'g' 'h' 'i'
               'k' 'l' 'm' 'n' 'o' 'p' 'q' 'r' 's' 't' 'u'
               'x' 'y' 'z';
    }
    

Numeric
-------

    

`lower-roman-j` is based upon `lower-roman` obviously, but could not use `extends` syntax. 
This variant substitutes a *j* for the final of multiple *i*.
>   i,   ij,   iij,   iv, v,   vi,     vij,     viij,   ix, x – final of multiple i → j

- **issue**: Possible variants:
>   i,   ij,   iij,   iv, v, **vj**,   vij,     viij,   ix, x – final i → j
> **j**, ij,   iij,   iv, v, **vj**,   vij,     viij,   ix, x – solitary and final i → j
>   i,   ij, **ijj**, iv, v,   vi,     vij,   **vijj**, ix, x – non-initial of multiple i → j
>   i,   ij, **ijj**, iv, v, **vj**,   vij,   **vijj**, ix, x – final i or non-initial of multiple i → j
>   i,   ij, **ijj**, iv, v, **vj**, **vjj**, **vjjj**, ix, x – non-initial i → j
> **j**, ij, **ijj**, iv, v, **vj**, **vjj**, **vjjj**, ix, x – solitary and non-initial i → j

- **issue**: possible ligation variants
> i, ĳ,  iĳ,  iv, v, vj, vĳ,  viĳ,  ix, x – final i → j with ligation
> i, ij, üj,  iv, v, vj, vij, vüj,  ix, x – final i → j with u ligation
> i, ÿ,  iÿ,  iv, v, vj, vÿ,  viÿ,  ix, x – final i → j with y ligation
> i, ÿ,  üj,  iv, v, vj, vÿ,  vüj,  ix, x – final i → j with u and y ligation
> i, ŋ̈,  ⃛ɱ,  iv, v, vj, vŋ̈,  v  ⃛,  ix, x – final i → j with alternate full ligation

- **issue**: other final or alternate forms are also possible, but hardly attested
> mm → mɱ
> cc → cɔ / ∝ / oc
> v → u
> xx → ∝

    @counter-style lower-roman-j {
      system: additive;
      range: 1 3999;
      additive-symbols: 1000 'm', 900 'cm', 500 'd', 400 'cd', 
                        100  'c', 90  'xc', 50  'l', 40  'xl',
                        10   'x', 9   'ix', 5   'v', 4   'iv', 3 'iij', 2 'ij', 1 'i';
    }
