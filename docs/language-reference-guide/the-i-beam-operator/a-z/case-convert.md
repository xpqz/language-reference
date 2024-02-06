<div class="heading">
  <div class="name">Case Convert</div>
  <div class="command">R←{X}(819⌶)Y</div>
</div>
# Note:

This i-beam function has been replaced by a system function and is deprecated. See [Case Convert on page 1](/system-functions/c.md#Case_Convert).

Converts character data in `Y` to upper or lower-case. This function is considerably faster than any comparable function coded in APL, especially on nested arrays.

`Y` may be any array of arbitrary depth so long as all the elements are characters.

The optional left-argument `X` is 0 (convert to lower-case) or 1 (convert to upper-case). If omitted, the default is 0.

The result `R` has the same structure as  `Y` but each character element is case folded to upper or lower case.

Characters are converted per the default case mappings specified by The Unicode Consortium, described at:
 ftp://ftp.unicode.org/Public/3.0-Update/UnicodeData-3.0.0.html

and using the table at:
 http://unicode.org/Public/UNIDATA/UnicodeData.txt

If conversion is being used to do case-insensitive character comparisons then converting everything to lower case is generally preferable to converting everything to upper. This is because converting to lower case can be faster.

This I-beam is supported in Classic Edition  using the same code as the Unicode Edition. This means that any case-folding defined in the input translate tables is ignored, and that `TRANSLATION ERROR`s will be generated if the folded characters do not appear in `⎕AV`.

# Examples
```apl

      (819⌶) 'How many Roads must a man walk down'
how many roads must a man walk down
      1 (819⌶) 'How many Roads must a man walk down'
HOW MANY ROADS MUST A MAN WALK DOWN

      data←1000⍴⊂'Hello there.'
      lc_data←819⌶ data
      4↑lc_data
 hello there.  hello there.  hello there.  hello there.

```
