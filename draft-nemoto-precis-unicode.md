---

title: "PRECIS Framework and Unicode 15.0.0"
abbrev: "PRECIS Unicode Update"
date: 2022-02-15
cat: info
stream: IETF

docname: draft-nemoto-precis-unicode-latest
submissiontype: IETF  # also: "independent", "editorial", "IAB", or "IRTF"
area: "Applications and Real-Time"
keyword:
 - PRECIS
 - Unicode
 - Internationalization
venue:
  group: "Preparation and Comparison of Internationalized Strings"
  type: "Working Group"
  mail: "precis@ietf.org"
  arch: "https://mailarchive.ietf.org/arch/browse/precis/"
  github: "stpeter/draft-nemoto-precis-unicode"
  latest: "https://stpeter.github.io/draft-nemoto-precis-unicode/draft-nemoto-precis-unicode.html"

pi:
  compact: 'yes'
  toc: 'yes'
  symrefs: 'yes'
  sortrefs: 'yes'
  comments: 'yes'
  inline: 'yes'

author:
- name: Takahiro Nemoto
  org: Tokyo University of Agriculture and Technology
  street: 2-24-16 Naka-cho
  city: Koganei-shi
  region: Tokyo
  code: 184-8588
  country: Japan
  phone: "+81 42 388 7196"
  email: nemo@go.tuat.ac.jp
- ins: P. Saint-Andre
  fullname: Peter Saint-Andre
  organization: Independent
  country: USA
  phone: "+1 720 256 6756"
  email: stpeter@stpeter.im

informative:
  RFC5890:
  RFC5891:
  RFC5892:
  RFC5893:
  RFC5894:
  RFC5895:
  RFC8264:
  RFC8753:
  I-D.faltstrom-unicode12:
  IAB:
    title: IAB Statement on Identifiers and Unicode 7.0.0
    author:
    - org: Internet Architecture Board
    date: 2015-01
    target:   https://www.iab.org/documents/correspondence-reports-documents/2015-2/iab-statement-on-identifiers-and-unicode-7-0-0/
  IANA-PRECIS:
    title: IDNA Rules and Derived Property Values
    author:
    - org: IANA
    date: 2017-10
    target: https://www.iana.org/assignments/idna-tables-6.0.0/idna-tables-6.0.0.xhtml
  Unicode-6.3.0:
    title: The Unicode Standard, Version 6.3.0
    author:
    - org: The Unicode Consortium
    date: 2013-09
    seriesinfo:
      The Unicode Standard, Version 6.3.0: ISBN 978-1-936213-08-5
  Unicode-7.0.0:
    title: The Unicode Standard, Version 7.0.0
    author:
    - org: The Unicode Consortium
    date: 2014-06
    seriesinfo:
      The Unicode Standard, Version 7.0.0: ISBN 978-1-936213-09-2
  Unicode-8.0.0:
    title: The Unicode Standard, Version 8.0.0
    author:
    - org: The Unicode Consortium
    date: 2015-06
    seriesinfo:
      The Unicode Standard, Version 8.0.0: ISBN 978-1-936213-10-8
  Unicode-9.0.0:
    title: The Unicode Standard, Version 9.0.0
    author:
    - org: The Unicode Consortium
    date: 2016-06
    seriesinfo:
      The Unicode Standard, Version 9.0.0: ISBN 978-1-936213-13-9
  Unicode-10.0.0:
    title: The Unicode Standard, Version 10.0.0
    author:
    - org: The Unicode Consortium
    date: 2017-06
    seriesinfo:
      The Unicode Standard, Version 10.0.0: ISBN 978-1-936213-16-0
  Unicode-11.0.0:
    title: The Unicode Standard, Version 11.0.0
    author:
    - org: The Unicode Consortium
    date: 2018-06
    seriesinfo:
      The Unicode Standard, Version 11.0.0: ISBN 978-1-936213-19-1
  Unicode-12.0.0:
    title: The Unicode Standard, Version 12.0.0
    author:
    - org: The Unicode Consortium
    date: 2019-03
    seriesinfo:
      The Unicode Standard, Version 12.0.0: ISBN 978-1-936213-22-1
  Unicode-13.0.0:
    title: The Unicode Standard, Version 13.0.0
    author:
    - org: The Unicode Consortium
    date: 2020-03
    seriesinfo:
      The Unicode Standard, Version 13.0.0: ISBN 978-1-936213-26-9
  Unicode-14.0.0:
    title: The Unicode Standard, Version 14.0.0
    author:
    - org: The Unicode Consortium
    date: 2021-09
    seriesinfo:
      The Unicode Standard, Version 14.0.0: ISBN 978-1-936213-29-0
  createtables:
    title: IDNA
    author:
    - name: Patrik Faltstrom
    date: 2021
    target: http://stupid.domain.name/idna

--- abstract


This document describes the changes between Unicode 6.3.0 and Unicode 14.0.0
in the context of PRECIS in the same way as draft-faltstrom-unicode12-07.
Note that this document is an updated version of draft-nemoto-precis-unicode13-00.
This document provides the information necessary to consider whether the
PRECIS Framework can follow the Unicode standard's updates since Unicode
6.3.0. This document also describes the differences between the Derived Property
Values of IDNA2008 and PRECIS for each version of Unicode.

--- middle

# Introduction {#intro}

Preparation and Comparison of Internationalized Strings (PRECIS) framework {{RFC8264}}
defines two classes of strings for use in application protocols. One is IdentifierClass,
which classifies characters suitable for a character strings group such as
user IDs, and the other is FreeformClass, which classifies characters suitable
for a character strings group such as passwords. The classification of character
code points for each class is defined by Derived Property Values calculated
based on properties defined in the Unicode standard. These values are registered
in the IANA registry as PRECIS Derived Property Value {{IANA-PRECIS}}.
However, as explained in Section 11.1 of RFC 8264 {{RFC8264}}, this registry
not be updated to Unicode 7.0.0 {{Unicode-7.0.0}} until the issues described
in IAB-Statement {{IAB}} and Section 13.5 of RFC 8264 {{RFC8264}} is resolved.
On the other hand, Internationalized Domain Names for Applications
(IDNA2008) {{RFC5890}} {{RFC5891}} {{RFC5892}} {{RFC5893}} {{RFC5894}} {{RFC5895}}
which had similar problems, was considered by experts, and the IDNA
Parameters registry of Derived Property Values was updated.
PRECIS Framework does not yet have a review model for new versions of Unicode,
such as Section 3 of {{RFC8753}}, so changes or additional
specifications to PRECIS Framework may be needed
in the future. However, since the PRECIS framework is similar to IDNA2008,
updating it in the same way as the RFC8753 {{RFC8753}} review model may
be a practical solution for the PRECIS framework.
Therefore, this document provides the information needed to consider whether
the PRECIS framework can follow the Unicode standard's updates since Unicode
6.3.0 {{Unicode-6.3.0}} by reference to draft-faltstrom-unicode12-07
{{I-D.faltstrom-unicode12}} as a result of {{RFC8753}}.
This document also describes the differences between the IDNA2008 Derived
Property Values and the PRECIS Derived Property Values for each Unicode version.


# Overview of Changes Between Unicode 6.3.0 and 14.0.0 {#ocb}

This section describes the differences in the Derived Property Values for
each Unicode Major Version to consider whether the PRECIS framework can follow
the Unicode standard's updates since Unicode 6.3.0.
This section is also aligned in notation to make it easier to compare with
the changes described in draft-faltstrom-unicode12-07 {{I-D.faltstrom-unicode12}}.

## Changes between Unicode 6.3.0 and 7.0.0 {#ou67}

Change in number of characters in each category:

> PVALID changed from 98,999 to 100,969 (+1,970)

> UNASSIGNED changed from 864,343 to 861,509 (-2,834)

> CONTEXTJ did not change, at 2

> CONTEXTO did not change, at 25

> DISALLOWED changed from 140,423 to 140,428 (+5)

> ID_DIS or FREE_PVAL changed from 10,320 to 11,179 (+859)

> TOTAL did not change, at 1,114,112

Code points that changed derived property value from other than UNASSIGNED:
0

There are no changes made to Unicode between version 6.3.0 {{Unicode-6.3.0}} and 7.0.0 {{Unicode-7.0.0}} that impact PRECIS calculation of the derived property values.

Note: PRECIS Derived Property Value of the character ARABIC LETTER BEH WITH
HAMZA ABOVE (U+08A1) added in Unicode 7.0.0, explained in Section 3.1 of
draft-faltstrom-unicode12-07 {{I-D.faltstrom-unicode12}}, is PVALID in this review.
On the other hand, there is the same normalization problem that this code
point is not defined to be equivalent to code point sequence ARABIC LETTER
BEH (U+0628) and ARABIC HAMZA ABOVE (U+0654) with the same form in the same
script.


## Changes between Unicode 7.0.0 and 8.0.0 {#ou78}

Change in number of characters in each category:

> PVALID changed from 100,969 to 107,978 (+7,009)

> UNASSIGNED changed from 861,509 to 853,793 (-7,716)

> CONTEXTJ did not change, at 2

> CONTEXTO did not change, at 25

> DISALLOWED changed from 140,428 to 140,428 (+0)

> ID_DIS or FREE_PVAL changed from 11,179 to 11,886 (+707)

> TOTAL did not change, at 1,114,112

Code points that changed derived property value from other than UNASSIGNED:
0

There are no changes made to Unicode between version 7.0.0 {{Unicode-7.0.0}} and 8.0.0 {{Unicode-8.0.0}} that impact PRECIS calculation of the derived property values.


## Changes between Unicode 8.0.0 and 9.0.0 {#ou89}

Change in number of characters in each category:

> PVALID changed from 107,978 to 115,317 (+7,339)

> UNASSIGNED changed from 853,793 to 846,293 (-7,500)

> CONTEXTJ did not change, at 2

> CONTEXTO did not change, at 25

> DISALLOWED changed from 140,428 to 140,429 (+1)

> ID_DIS or FREE_PVAL changed from 11,886 to 12,046 (+160)

> TOTAL did not change, at 1,114,112

Code points that changed derived property value from other than UNASSIGNED:
0

There are no changes made to Unicode between version 8.0.0 {{Unicode-8.0.0}} and 9.0.0 {{Unicode-9.0.0}} that impact PRECIS calculation of the derived property values.


## Changes between Unicode 9.0.0 and 10.0.0 {#ou910}

Change in number of characters in each category:

> PVALID changed from 115,317 to 123,734 (+8,417)

> UNASSIGNED changed from 846,293 to 837,775 (-8,518)

> CONTEXTJ did not change, at 2

> CONTEXTO did not change, at 25

> DISALLOWED changed from 140,429 to 140,429 (+0)

> ID_DIS or FREE_PVAL changed from 12,046 to 12,147 (+101)

> TOTAL did not change, at 1,114,112

Code points that changed derived property value from other than UNASSIGNED:
0

There are no changes made to Unicode between version 9.0.0 {{Unicode-9.0.0}} and 10.0.0 {{Unicode-10.0.0}} that impact PRECIS calculation of the derived property values.


## Changes between Unicode 10.0.0 and 11.0.0 {#ou1011}

Change in number of characters in each category:

> PVALID changed from 123,734 to 124,136 (+402)

> UNASSIGNED changed from 837,775 to 837,091 (-684)

> CONTEXTJ did not change, at 2

> CONTEXTO did not change, at 25

> DISALLOWED changed from 140,429 to 140,430 (+1)

> ID_DIS or FREE_PVAL changed from 12,147 to 12,428 (+281)

> TOTAL did not change, at 1,114,112

Code points that changed derived property value from other than UNASSIGNED:
1

As explained in Section 4.3 of draft-faltstrom-unicode12-07 {{I-D.faltstrom-unicode12}}, there are some Unicode General Properties changed.
Changes of properties for Georgian letters in the ranges U+10D0..U+10FA and
U+10FD..U+10FF, ZANABAZAR SQUARE VOWEL SIGN AI (U+11A07) and SPHERICAL ANGLE
OPENING UP (U+29A1) do not affect PRECIS calculation of the derived property
values.

Change of SHARADA SANDHI MARK (U+111C9) added in Unicode 8.0.0 {{Unicode-8.0.0}} affects PRECIS calculation of the derived property values in IdentifierClass.
PRECIS Derived Property Value of this between Unicode 8.0.0 {{Unicode-8.0.0}} and Unicode 10.0.0 {{Unicode-10.0.0}} is ID_DIS or FREE_PVAL, however in Unicode 11.0.0 is PVALID.
This means that FreeformClass is not affected by this change. However, in
IdentifierClass, this code point disallowed between Unicode 8.0.0 {{Unicode-8.0.0}} and Unicode 10.0.0 {{Unicode-10.0.0}} is allowed in Unicode 11.0.0 {{Unicode-11.0.0}}.


## Changes between Unicode 11.0.0 and 12.0.0 {#ou1112}

Change in number of characters in each category:


> PVALID changed from 124,136 to 124,415 (+279)

> UNASSIGNED changed from 837,091 to 836,537 (-554)

> CONTEXTJ did not change, at 2

> CONTEXTO did not change, at 25

> DISALLOWED changed from 140,430 to 140,439 (+9)

> ID_DIS or FREE_PVAL changed from 12,428 to 12,694 (+266)

> TOTAL did not change, at 1,114,112


Code points that changed derived property value from other than UNASSIGNED:
0

There are no changes made to Unicode between version 11.0.0 {{Unicode-11.0.0}} and 12.0.0 {{Unicode-12.0.0}} that impact PRECIS calculation of the derived property values.

Note: Unicode General Propertie of CANADIAN SYLLABICS CHI SIGN (U+166D) was
changed from Po to So in Unicode 12.0.0 {{Unicode-12.0.0}}. This change has changed the basis for calculating of the derived property
value from Punctuation (P) in Section 9.16 of RFC 8264 to Symbols (O) in
Section 9.15 of RFC 8264. However, this change does not affect the calculation
result, because both derived property values are ID_DIS or FREE_PVAL.


## Changes between Unicode 12.0.0 and 13.0.0 {#ou1213}

Change in number of characters in each category:

> PVALID changed from 124,415 to 130,049 (+5,634)

> UNASSIGNED changed from 836,537 to 830,606 (-5,931)

> CONTEXTJ did not change, at 2

> CONTEXTO did not change, at 25

> DISALLOWED changed from 140,439 to 140,439 (+0)

> ID_DIS or FREE_PVAL changed from 12,694 to 12,991 (+297)

> TOTAL did not change, at 1,114,112

Code points that changed derived property value from other than UNASSIGNED:
0

There are no changes made to Unicode between version 12.0.0 {{Unicode-12.0.0}} and 13.0.0 {{Unicode-13.0.0}} that impact PRECIS calculation of the derived property values.


## Changes between Unicode 13.0.0 and 14.0.0 {#ou1314}

Change in number of characters in each category:

> PVALID changed from 130,049 to 130,627 (+5,634)

> UNASSIGNED changed from 830,606 to 829,768 (-838)

> CONTEXTJ did not change, at 2

> CONTEXTO did not change, at 25

> DISALLOWED changed from 140,439 to 140,442 (+3)

> ID_DIS or FREE_PVAL changed from 12,991 to 13,248 (+257)

> TOTAL did not change, at 1,114,112

Code points that changed derived property value from other than UNASSIGNED:
0

There are no changes made to Unicode between version 13.0.0 {{Unicode-13.0.0}} and 14.0.0 {{Unicode-14.0.0}} that impact PRECIS calculation of the derived property values.


# Differences between the Derived Property Values of IDNA2008 and PRECIS for each Unicode version {#diff}

There seems to be no case so far to exchange strings between IDNA2008 and
PRECIS Framework, but this section describes the results of comparing the
differences in Derived Property Values between IDNA2008 and PRECIS for each
Unicode version.
In this section, the classes of PRECIS Framework in the case of character
string exchange between IDNA2008 and PRECIS Framework are considered to be
IdentifierClass, so IdentifierClasses' values are used for comparison.
Also, the derived characteristic values of IDNA2008 in this comparison are
based on the createtables.rb {{createtables}}.

As a result of comparing the Derived Property Values of each Unicode version,
the only difference was that some characters that were "DISALLOWED" in IDNA2008
became "PVALID" in PRECIS.
Only the number of characters that resulted in the above differences are
listed in the following list.

> 11,373 characters in Unicode 6.3.0

> 12,281 characters in Unicode 7.0.0

> 13,129 characters in Unicode 8.0.0

> 13,369 characters in Unicode 9.0.0

> 13,470 characters in Unicode 10.0.0

> 13,830 characters in Unicode 11.0.0

> 14,103 characters in Unicode 12.0.0

> 14,403 characters in Unicode 13.0.0

> 14,700 characters in Unicode 14.0.0

Therefore, if a DNS label is used as another protocol element that uses the
PRECIS Framework, it will not be affected. On the other hand, characters
assigned "PVALID" in the PRECIS Framework may be restricted when used as
a DNS label. For example, in a domain name, uppercase characters are assigned
"DISALLOWED" according to Section 2.2 of RFC5892 {{RFC5892}}, but in PRECIS, they are assigned "PVALID".
In this case, such as uppercase and lowercase, this difference can be resolved
by using case mapping, but whether mappings and normalization will work for
all these differences has not been investigated in this document.


# Conclusion {#conclusion}

As described in {{ocb}}, one incompatible change was made between Unicode 6.3.0 and 14.0.0.
U+111C9 has been changed Derived Property Value from ID_DIS or FREE_PVAL
to PVALID.
Other changes of Unicode General Properties have not affected their Derived
Property Values.
As explained in Section 5 of draft-faltstrom-unicode12-07
{{I-D.faltstrom-unicode12}}, considering the impact on existing
implementations, draft-faltstrom-unicode12-07
{{I-D.faltstrom-unicode12}} concludes that U+111C9 is not added to the
exception list defined BackwardCompatible
(G) in Section 2.7 of RFC 5892 {{RFC5892}}.
And also, PRECIS Framework defines to use of the exception list in Section
2.6 of RFC 8264 {{RFC8264}}. Therefore this document suggests that the
Derived Property Values is considered
PVALID according to draft-faltstrom-unicode12-07 {{I-D.faltstrom-unicode12}}.

As described in {{diff}}, comparing Derived Property Values of IDNA2008
and PRECIS Framework for
each Unicode version shows that are assigned "DISALLOWED" in IDNA2008 but
are assigned "PVALID" in PRECIS Framework. This result is due to each calculation
method of Derived Property Values. And unless special Derived Property Values
are assigned for backward compatibility, it is expected to be as shown in
this difference.
Therefore, when DNS label names are used as other protocol elements that
use the PRECIS Framework, it was found that they can be used without requiring
any special mappings and normalization. On the other hand, if characters
that use the PRECIS Framework are used as domain names that use IDNA2008,
care should be taken because there may be restricted characters.


# IANA Considerations {#iana}

TBD. IANA may be requested to update the PRECIS Derived Property Value registry.


# Security Considerations {#sec}

TBD.


# Acknowledgment {#ack}

John Klensin gave important suggestions for this document.

Patrik Faltstrom provided a program to calculate IDNA2008 Derived Property
Values according to {{RFC5892}} and generate tables {{createtables}}.

Carsten Bormann helpfully converted the XML source to kramdown-rfc.


--- back

# Changes from Unicode 6.3.0 to Unicode 7.0.0

Changes from derived property value UNASSIGNED to either PVALID, DISALLOWED
or ID_DIS or FREE_PVAL.
Note: "ID_DIS or FREE_PVAL" is written as "FREE_PVAL" for convenience.


~~~~
037F        ; PVALID      # GREEK CAPITAL LETTER YOT
0528..052F  ; PVALID      # CYRILLIC CAPITAL LETTER EN WITH LEFT HOOK..C
058D..058E  ; FREE_PVAL   # RIGHT-FACING ARMENIAN ETERNITY SIGN..LEFT-FA
0605        ; DISALLOWED  # ARABIC NUMBER MARK ABOVE
08A1        ; PVALID      # ARABIC LETTER BEH WITH HAMZA ABOVE
08AD..08B2  ; PVALID      # ARABIC LETTER LOW ALEF..ARABIC LETTER ZAIN W
08FF        ; PVALID      # ARABIC MARK SIDEWAYS NOON GHUNNA
0978        ; PVALID      # DEVANAGARI LETTER MARWARI DDA
0980        ; PVALID      # BENGALI ANJI
0C00        ; PVALID      # TELUGU SIGN COMBINING CANDRABINDU ABOVE
0C34        ; PVALID      # TELUGU LETTER LLLA
0C81        ; PVALID      # KANNADA SIGN CANDRABINDU
0D01        ; PVALID      # MALAYALAM SIGN CANDRABINDU
0DE6..0DEF  ; PVALID      # SINHALA LITH DIGIT ZERO..SINHALA LITH DIGIT
16F1..16F8  ; PVALID      # RUNIC LETTER K..RUNIC LETTER FRANKS CASKET A
191D..191E  ; PVALID      # LIMBU LETTER GYAN..LIMBU LETTER TRA
1AB0..1ABD  ; PVALID      # COMBINING DOUBLED CIRCUMFLEX ACCENT..COMBINI
1ABE        ; FREE_PVAL   # COMBINING PARENTHESES OVERLAY
1CF8..1CF9  ; PVALID      # VEDIC TONE RING ABOVE..VEDIC TONE DOUBLE RIN
1DE7..1DF5  ; PVALID      # COMBINING LATIN SMALL LETTER ALPHA..COMBININ
20BB..20BD  ; FREE_PVAL   # NORDIC MARK SIGN..RUBLE SIGN
23F4..23FA  ; FREE_PVAL   # BLACK MEDIUM LEFT-POINTING TRIANGLE..BLACK C
2700        ; FREE_PVAL   # BLACK SAFETY SCISSORS
2B4D..2B4F  ; FREE_PVAL   # DOWNWARDS TRIANGLE-HEADED ZIGZAG ARROW..SHOR
2B5A..2B73  ; FREE_PVAL   # SLANTED NORTH ARROW WITH HOOKED HEAD..DOWNWA
2B76..2B95  ; FREE_PVAL   # NORTH WEST TRIANGLE-HEADED ARROW TO BAR..RIG
2B98..2BB9  ; FREE_PVAL   # THREE-D TOP-LIGHTED LEFTWARDS EQUILATERAL AR
2BBD..2BC8  ; FREE_PVAL   # BALLOT BOX WITH LIGHT X..BLACK MEDIUM RIGHT-
2BCA..2BD1  ; FREE_PVAL   # TOP HALF BLACK CIRCLE..UNCERTAINTY SIGN
2E3C..2E42  ; FREE_PVAL   # STENOGRAPHIC FULL STOP..DOUBLE LOW-REVERSED-
A698..A69B  ; PVALID      # CYRILLIC CAPITAL LETTER DOUBLE O..CYRILLIC S
A69C..A69D  ; FREE_PVAL   # MODIFIER LETTER CYRILLIC HARD SIGN..MODIFIER
A794..A79F  ; PVALID      # LATIN SMALL LETTER C WITH PALATAL HOOK..LATI
A7AB..A7AD  ; PVALID      # LATIN CAPITAL LETTER REVERSED OPEN E..LATIN
A7B0..A7B1  ; PVALID      # LATIN CAPITAL LETTER TURNED K..LATIN CAPITAL
A7F7        ; PVALID      # LATIN EPIGRAPHIC LETTER SIDEWAYS I
A9E0..A9FE  ; PVALID      # MYANMAR LETTER SHAN GHA..MYANMAR LETTER TAI
AA7C..AA7F  ; PVALID      # MYANMAR SIGN TAI LAING TONE-2..MYANMAR LETTE
AB30..AB5A  ; PVALID      # LATIN SMALL LETTER BARRED ALPHA..LATIN SMALL
AB5B..AB5F  ; FREE_PVAL   # MODIFIER BREVE WITH INVERTED BREVE..MODIFIER
AB64..AB65  ; PVALID      # LATIN SMALL LETTER INVERTED ALPHA..GREEK LET
FE27..FE2D  ; PVALID      # COMBINING LIGATURE LEFT HALF BELOW..COMBININ
1018B..1018C; FREE_PVAL   # GREEK ONE QUARTER SIGN..GREEK SINUSOID SIGN
101A0       ; FREE_PVAL   # GREEK SYMBOL TAU RHO
102E0       ; PVALID      # COPTIC EPACT THOUSANDS MARK
102E1..102FB; FREE_PVAL   # COPTIC EPACT DIGIT ONE..COPTIC EPACT NUMBER
1031F       ; PVALID      # OLD ITALIC LETTER ESS
10350..1037A; PVALID      # OLD PERMIC LETTER AN..COMBINING OLD PERMIC L
10500..10527; PVALID      # ELBASAN LETTER A..ELBASAN LETTER KHE
10530..10563; PVALID      # CAUCASIAN ALBANIAN LETTER ALT..CAUCASIAN ALB
1056F       ; FREE_PVAL   # CAUCASIAN ALBANIAN CITATION MARK
10600..10736; PVALID      # LINEAR A SIGN AB001..LINEAR A SIGN A664
10740..10755; PVALID      # LINEAR A SIGN A701 A..LINEAR A SIGN A732 JE
10760..10767; PVALID      # LINEAR A SIGN A800..LINEAR A SIGN A807
10860..10876; PVALID      # PALMYRENE LETTER ALEPH..PALMYRENE LETTER TAW
10877..1087F; FREE_PVAL   # PALMYRENE LEFT-POINTING FLEURON..PALMYRENE N
10880..1089E; PVALID      # NABATAEAN LETTER FINAL ALEPH..NABATAEAN LETT
108A7..108AF; FREE_PVAL   # NABATAEAN NUMBER ONE..NABATAEAN NUMBER ONE H
10A80..10A9C; PVALID      # OLD NORTH ARABIAN LETTER HEH..OLD NORTH ARAB
10A9D..10A9F; FREE_PVAL   # OLD NORTH ARABIAN NUMBER ONE..OLD NORTH ARAB
10AC0..10AC7; PVALID      # MANICHAEAN LETTER ALEPH..MANICHAEAN LETTER W
10AC8       ; FREE_PVAL   # MANICHAEAN SIGN UD
10AC9..10AE6; PVALID      # MANICHAEAN LETTER ZAYIN..MANICHAEAN ABBREVIA
10AEB..10AF6; FREE_PVAL   # MANICHAEAN NUMBER ONE..MANICHAEAN PUNCTUATIO
10B80..10B91; PVALID      # PSALTER PAHLAVI LETTER ALEPH..PSALTER PAHLAV
10B99..10B9C; FREE_PVAL   # PSALTER PAHLAVI SECTION MARK..PSALTER PAHLAV
10BA9..10BAF; FREE_PVAL   # PSALTER PAHLAVI NUMBER ONE..PSALTER PAHLAVI
1107F       ; PVALID      # BRAHMI NUMBER JOINER
11150..11173; PVALID      # MAHAJANI LETTER A..MAHAJANI SIGN NUKTA
11174..11175; FREE_PVAL   # MAHAJANI ABBREVIATION SIGN..MAHAJANI SECTION
11176       ; PVALID      # MAHAJANI LIGATURE SHRI
111CD       ; FREE_PVAL   # SHARADA SUTRA MARK
111DA       ; PVALID      # SHARADA EKAM
111E1..111F4; FREE_PVAL   # SINHALA ARCHAIC DIGIT ONE..SINHALA ARCHAIC N
11200..11211; PVALID      # KHOJKI LETTER A..KHOJKI LETTER JJA
11213..11237; PVALID      # KHOJKI LETTER NYA..KHOJKI SIGN SHADDA
11238..1123D; FREE_PVAL   # KHOJKI DANDA..KHOJKI ABBREVIATION SIGN
112B0..112EA; PVALID      # KHUDAWADI LETTER A..KHUDAWADI SIGN VIRAMA
112F0..112F9; PVALID      # KHUDAWADI DIGIT ZERO..KHUDAWADI DIGIT NINE
11301..11303; PVALID      # GRANTHA SIGN CANDRABINDU..GRANTHA SIGN VISAR
11305..1130C; PVALID      # GRANTHA LETTER A..GRANTHA LETTER VOCALIC L
1130F..11310; PVALID      # GRANTHA LETTER EE..GRANTHA LETTER AI
11313..11328; PVALID      # GRANTHA LETTER OO..GRANTHA LETTER NA
1132A..11330; PVALID      # GRANTHA LETTER PA..GRANTHA LETTER RA
11332..11333; PVALID      # GRANTHA LETTER LA..GRANTHA LETTER LLA
11335..11339; PVALID      # GRANTHA LETTER VA..GRANTHA LETTER HA
1133C..11344; PVALID      # GRANTHA SIGN NUKTA..GRANTHA VOWEL SIGN VOCAL
11347..11348; PVALID      # GRANTHA VOWEL SIGN EE..GRANTHA VOWEL SIGN AI
1134B..1134D; PVALID      # GRANTHA VOWEL SIGN OO..GRANTHA SIGN VIRAMA
11357       ; PVALID      # GRANTHA AU LENGTH MARK
1135D..11363; PVALID      # GRANTHA SIGN PLUTA..GRANTHA VOWEL SIGN VOCAL
11366..1136C; PVALID      # COMBINING GRANTHA DIGIT ZERO..COMBINING GRAN
11370..11374; PVALID      # COMBINING GRANTHA LETTER A..COMBINING GRANTH
11480..114C5; PVALID      # TIRHUTA ANJI..TIRHUTA GVANG
114C6       ; FREE_PVAL   # TIRHUTA ABBREVIATION SIGN
114C7       ; PVALID      # TIRHUTA OM
114D0..114D9; PVALID      # TIRHUTA DIGIT ZERO..TIRHUTA DIGIT NINE
11580..115B5; PVALID      # SIDDHAM LETTER A..SIDDHAM VOWEL SIGN VOCALIC
115B8..115C0; PVALID      # SIDDHAM VOWEL SIGN E..SIDDHAM SIGN NUKTA
115C1..115C9; FREE_PVAL   # SIDDHAM SIGN SIDDHAM..SIDDHAM END OF TEXT MA
11600..11640; PVALID      # MODI LETTER A..MODI SIGN ARDHACANDRA
11641..11643; FREE_PVAL   # MODI DANDA..MODI ABBREVIATION SIGN
11644       ; PVALID      # MODI SIGN HUVA
11650..11659; PVALID      # MODI DIGIT ZERO..MODI DIGIT NINE
118A0..118E9; PVALID      # WARANG CITI CAPITAL LETTER NGAA..WARANG CITI
118EA..118F2; FREE_PVAL   # WARANG CITI NUMBER TEN..WARANG CITI NUMBER N
118FF       ; PVALID      # WARANG CITI OM
11AC0..11AF8; PVALID      # PAU CIN HAU LETTER PA..PAU CIN HAU GLOTTAL S
1236F..12398; PVALID      # CUNEIFORM SIGN KAP ELAMITE..CUNEIFORM SIGN U
12463..1246E; FREE_PVAL   # CUNEIFORM NUMERIC SIGN ONE QUARTER GUR..CUNE
12474       ; FREE_PVAL   # CUNEIFORM PUNCTUATION SIGN DIAGONAL QUADCOLO
16A40..16A5E; PVALID      # MRO LETTER TA..MRO LETTER TEK
16A60..16A69; PVALID      # MRO DIGIT ZERO..MRO DIGIT NINE
16A6E..16A6F; FREE_PVAL   # MRO DANDA..MRO DOUBLE DANDA
16AD0..16AED; PVALID      # BASSA VAH LETTER ENNI..BASSA VAH LETTER I
16AF0..16AF4; PVALID      # BASSA VAH COMBINING HIGH TONE..BASSA VAH COM
16AF5       ; FREE_PVAL   # BASSA VAH FULL STOP
16B00..16B36; PVALID      # PAHAWH HMONG VOWEL KEEB..PAHAWH HMONG MARK C
16B37..16B3F; FREE_PVAL   # PAHAWH HMONG SIGN VOS THOM..PAHAWH HMONG SIG
16B40..16B43; PVALID      # PAHAWH HMONG SIGN VOS SEEV..PAHAWH HMONG SIG
16B44..16B45; FREE_PVAL   # PAHAWH HMONG SIGN XAUS..PAHAWH HMONG SIGN CI
16B50..16B59; PVALID      # PAHAWH HMONG DIGIT ZERO..PAHAWH HMONG DIGIT
16B5B..16B61; FREE_PVAL   # PAHAWH HMONG NUMBER TENS..PAHAWH HMONG NUMBE
16B63..16B77; PVALID      # PAHAWH HMONG SIGN VOS LUB..PAHAWH HMONG SIGN
16B7D..16B8F; PVALID      # PAHAWH HMONG CLAN SIGN TSHEEJ..PAHAWH HMONG
1BC00..1BC6A; PVALID      # DUPLOYAN LETTER H..DUPLOYAN LETTER VOCALIC M
1BC70..1BC7C; PVALID      # DUPLOYAN AFFIX LEFT HORIZONTAL SECANT..DUPLO
1BC80..1BC88; PVALID      # DUPLOYAN AFFIX HIGH ACUTE..DUPLOYAN AFFIX HI
1BC90..1BC99; PVALID      # DUPLOYAN AFFIX LOW ACUTE..DUPLOYAN AFFIX LOW
1BC9C       ; FREE_PVAL   # DUPLOYAN SIGN O WITH CROSS
1BC9D..1BC9E; PVALID      # DUPLOYAN THICK LETTER SELECTOR..DUPLOYAN DOU
1BC9F       ; FREE_PVAL   # DUPLOYAN PUNCTUATION CHINOOK FULL STOP
1BCA0..1BCA3; DISALLOWED  # SHORTHAND FORMAT LETTER OVERLAP..SHORTHAND F
1E800..1E8C4; PVALID      # MENDE KIKAKUI SYLLABLE M001 KI..MENDE KIKAKU
1E8C7..1E8CF; FREE_PVAL   # MENDE KIKAKUI DIGIT ONE..MENDE KIKAKUI DIGIT
1E8D0..1E8D6; PVALID      # MENDE KIKAKUI COMBINING NUMBER TEENS..MENDE
1F0BF       ; FREE_PVAL   # PLAYING CARD RED JOKER
1F0E0..1F0F5; FREE_PVAL   # PLAYING CARD FOOL..PLAYING CARD TRUMP-21
1F10B..1F10C; FREE_PVAL   # DINGBAT CIRCLED SANS-SERIF DIGIT ZERO..DINGB
1F321..1F32C; FREE_PVAL   # THERMOMETER..WIND BLOWING FACE
1F336       ; FREE_PVAL   # HOT PEPPER
1F37D       ; FREE_PVAL   # FORK AND KNIFE WITH PLATE
1F394..1F39F; FREE_PVAL   # HEART WITH TIP ON THE LEFT..ADMISSION TICKET
1F3C5       ; FREE_PVAL   # SPORTS MEDAL
1F3CB..1F3CE; FREE_PVAL   # WEIGHT LIFTER..RACING CAR
1F3D4..1F3DF; FREE_PVAL   # SNOW CAPPED MOUNTAIN..STADIUM
1F3F1..1F3F7; FREE_PVAL   # WHITE PENNANT..LABEL
1F43F       ; FREE_PVAL   # CHIPMUNK
1F441       ; FREE_PVAL   # EYE
1F4F8       ; FREE_PVAL   # CAMERA WITH FLASH
1F4FD..1F4FE; FREE_PVAL   # FILM PROJECTOR..PORTABLE STEREO
1F53E..1F53F; FREE_PVAL   # LOWER RIGHT SHADOWED WHITE CIRCLE..UPPER RIG
1F544..1F54A; FREE_PVAL   # NOTCHED RIGHT SEMICIRCLE WITH THREE DOTS..DO
1F568..1F579; FREE_PVAL   # RIGHT SPEAKER..JOYSTICK
1F57B..1F5A3; FREE_PVAL   # LEFT HAND TELEPHONE RECEIVER..BLACK DOWN POI
1F5A5..1F5FA; FREE_PVAL   # DESKTOP COMPUTER..WORLD MAP
1F641..1F642; FREE_PVAL   # SLIGHTLY FROWNING FACE..SLIGHTLY SMILING FAC
1F650..1F67F; FREE_PVAL   # NORTH WEST POINTING LEAF..REVERSE CHECKER BO
1F6C6..1F6CF; FREE_PVAL   # TRIANGLE WITH ROUNDED CORNERS..BED
1F6E0..1F6EC; FREE_PVAL   # HAMMER AND WRENCH..AIRPLANE ARRIVING
1F6F0..1F6F3; FREE_PVAL   # SATELLITE..PASSENGER SHIP
1F780..1F7D4; FREE_PVAL   # BLACK LEFT-POINTING ISOSCELES RIGHT TRIANGLE
1F800..1F80B; FREE_PVAL   # LEFTWARDS ARROW WITH SMALL TRIANGLE ARROWHEA
1F810..1F847; FREE_PVAL   # LEFTWARDS ARROW WITH SMALL EQUILATERAL ARROW
1F850..1F859; FREE_PVAL   # LEFTWARDS SANS-SERIF ARROW..UP DOWN SANS-SER
1F860..1F887; FREE_PVAL   # WIDE-HEADED LEFTWARDS LIGHT BARB ARROW..WIDE
1F890..1F8AD; FREE_PVAL   # LEFTWARDS TRIANGLE ARROWHEAD..WHITE ARROW SH
~~~~


# Changes from Unicode 7.0.0 to Unicode 8.0.0

Changes from derived property value UNASSIGNED to either PVALID or ID_DIS
or FREE_PVAL.
Note: "ID_DIS or FREE_PVAL" is written as "FREE_PVAL" for convenience.


~~~~
08B3..08B4  ; PVALID      # ARABIC LETTER AIN WITH THREE DOTS BELOW..ARA
08E3        ; PVALID      # ARABIC TURNED DAMMA BELOW
0AF9        ; PVALID      # GUJARATI LETTER ZHA
0C5A        ; PVALID      # TELUGU LETTER RRRA
0D5F        ; PVALID      # MALAYALAM LETTER ARCHAIC II
13F5        ; PVALID      # CHEROKEE LETTER MV
13F8..13FD  ; PVALID      # CHEROKEE SMALL LETTER YE..CHEROKEE SMALL LET
20BE        ; FREE_PVAL   # LARI SIGN
218A..218B  ; FREE_PVAL   # TURNED DIGIT TWO..TURNED DIGIT THREE
2BEC..2BEF  ; FREE_PVAL   # LEFTWARDS TWO-HEADED ARROW WITH TRIANGLE ARR
9FCD..9FD5  ; PVALID      # <CJK Ideograph>..<CJK Ideograph>
A69E        ; PVALID      # COMBINING CYRILLIC LETTER EF
A78F        ; PVALID      # LATIN LETTER SINOLOGICAL DOT
A7B2..A7B7  ; PVALID      # LATIN CAPITAL LETTER J WITH CROSSED-TAIL..LA
A8FC        ; FREE_PVAL   # DEVANAGARI SIGN SIDDHAM
A8FD        ; PVALID      # DEVANAGARI JAIN OM
AB60..AB63  ; PVALID      # LATIN SMALL LETTER SAKHA YAT..LATIN SMALL LE
AB70..ABBF  ; PVALID      # CHEROKEE SMALL LETTER A..CHEROKEE SMALL LETT
FE2E..FE2F  ; PVALID      # COMBINING CYRILLIC TITLO LEFT HALF..COMBININ
108E0..108F2; PVALID      # HATRAN LETTER ALEPH..HATRAN LETTER QOPH
108F4..108F5; PVALID      # HATRAN LETTER SHIN..HATRAN LETTER TAW
108FB..108FF; FREE_PVAL   # HATRAN NUMBER ONE..HATRAN NUMBER ONE HUNDRED
109BC..109BD; FREE_PVAL   # MEROITIC CURSIVE FRACTION ELEVEN TWELFTHS..M
109C0..109CF; FREE_PVAL   # MEROITIC CURSIVE NUMBER ONE..MEROITIC CURSIV
109D2..109FF; FREE_PVAL   # MEROITIC CURSIVE NUMBER ONE HUNDRED..MEROITI
10C80..10CB2; PVALID      # OLD HUNGARIAN CAPITAL LETTER A..OLD HUNGARIA
10CC0..10CF2; PVALID      # OLD HUNGARIAN SMALL LETTER A..OLD HUNGARIAN
10CFA..10CFF; FREE_PVAL   # OLD HUNGARIAN NUMBER ONE..OLD HUNGARIAN NUMB
111C9       ; FREE_PVAL   # SHARADA SANDHI MARK
111CA..111CC; PVALID      # SHARADA SIGN NUKTA..SHARADA EXTRA SHORT VOWE
111DB       ; FREE_PVAL   # SHARADA SIGN SIDDHAM
111DC       ; PVALID      # SHARADA HEADSTROKE
111DD..111DF; FREE_PVAL   # SHARADA CONTINUATION SIGN..SHARADA SECTION M
11280..11286; PVALID      # MULTANI LETTER A..MULTANI LETTER GA
11288       ; PVALID      # MULTANI LETTER GHA
1128A..1128D; PVALID      # MULTANI LETTER CA..MULTANI LETTER JJA
1128F..1129D; PVALID      # MULTANI LETTER NYA..MULTANI LETTER BA
1129F..112A8; PVALID      # MULTANI LETTER BHA..MULTANI LETTER RHA
112A9       ; FREE_PVAL   # MULTANI SECTION MARK
11300       ; PVALID      # GRANTHA SIGN COMBINING ANUSVARA ABOVE
11350       ; PVALID      # GRANTHA OM
115CA..115D7; FREE_PVAL   # SIDDHAM SECTION MARK WITH TRIDENT AND U-SHAP
115D8..115DD; PVALID      # SIDDHAM LETTER THREE-CIRCLE ALTERNATE I..SID
11700..11719; PVALID      # AHOM LETTER KA..AHOM LETTER JHA
1171D..1172B; PVALID      # AHOM CONSONANT SIGN MEDIAL LA..AHOM SIGN KIL
11730..11739; PVALID      # AHOM DIGIT ZERO..AHOM DIGIT NINE
1173A..1173F; FREE_PVAL   # AHOM NUMBER TEN..AHOM SYMBOL VI
12399       ; PVALID      # CUNEIFORM SIGN U U
12480..12543; PVALID      # CUNEIFORM SIGN AB TIMES NUN TENU..CUNEIFORM
14400..14646; PVALID      # ANATOLIAN HIEROGLYPH A001..ANATOLIAN HIEROGL
1D1DE..1D1E8; FREE_PVAL   # MUSICAL SYMBOL KIEVAN C CLEF..MUSICAL SYMBOL
1D800..1D9FF; FREE_PVAL   # SIGNWRITING HAND-FIST INDEX..SIGNWRITING HEA
1DA00..1DA36; PVALID      # SIGNWRITING HEAD RIM..SIGNWRITING AIR SUCKIN
1DA37..1DA3A; FREE_PVAL   # SIGNWRITING AIR BLOW SMALL ROTATIONS..SIGNWR
1DA3B..1DA6C; PVALID      # SIGNWRITING MOUTH CLOSED NEUTRAL..SIGNWRITIN
1DA6D..1DA74; FREE_PVAL   # SIGNWRITING SHOULDER HIP SPINE..SIGNWRITING
1DA75       ; PVALID      # SIGNWRITING UPPER BODY TILTING FROM HIP JOIN
1DA76..1DA83; FREE_PVAL   # SIGNWRITING LIMB COMBINATION..SIGNWRITING LO
1DA84       ; PVALID      # SIGNWRITING LOCATION HEAD NECK
1DA85..1DA8B; FREE_PVAL   # SIGNWRITING LOCATION TORSO..SIGNWRITING PARE
1DA9B..1DA9F; PVALID      # SIGNWRITING FILL MODIFIER-2..SIGNWRITING FIL
1DAA1..1DAAF; PVALID      # SIGNWRITING ROTATION MODIFIER-2..SIGNWRITING
1F32D..1F32F; FREE_PVAL   # HOT DOG..BURRITO
1F37E..1F37F; FREE_PVAL   # BOTTLE WITH POPPING CORK..POPCORN
1F3CF..1F3D3; FREE_PVAL   # CRICKET BAT AND BALL..TABLE TENNIS PADDLE AN
1F3F8..1F3FF; FREE_PVAL   # BADMINTON RACQUET AND SHUTTLECOCK..EMOJI MOD
1F4FF       ; FREE_PVAL   # PRAYER BEADS
1F54B..1F54F; FREE_PVAL   # KAABA..BOWL OF HYGIEIA
1F643..1F644; FREE_PVAL   # UPSIDE-DOWN FACE..FACE WITH ROLLING EYES
1F6D0       ; FREE_PVAL   # PLACE OF WORSHIP
1F910..1F918; FREE_PVAL   # ZIPPER-MOUTH FACE..SIGN OF THE HORNS
1F980..1F984; FREE_PVAL   # CRAB..UNICORN FACE
1F9C0       ; FREE_PVAL   # CHEESE WEDGE
2B820..2CEA1; PVALID      # <CJK Ideograph Extension E>..<CJK Ideograph
~~~~


# Changes from Unicode 8.0.0 to Unicode 9.0.0

Changes from derived property value UNASSIGNED to either PVALID, DISALLOWED
or ID_DIS or FREE_PVAL.
Note: "ID_DIS or FREE_PVAL" is written as "FREE_PVAL" for convenience.


~~~~
08B6..08BD  ; PVALID      # ARABIC LETTER BEH WITH SMALL MEEM ABOVE..ARA
08D4..08E1  ; PVALID      # ARABIC SMALL HIGH WORD AR-RUB..ARABIC SMALL
08E2        ; DISALLOWED  # ARABIC DISPUTED END OF AYAH
0C80        ; PVALID      # KANNADA SIGN SPACING CANDRABINDU
0D4F        ; FREE_PVAL   # MALAYALAM SIGN PARA
0D54..0D56  ; PVALID      # MALAYALAM LETTER CHILLU M..MALAYALAM LETTER
0D58..0D5E  ; FREE_PVAL   # MALAYALAM FRACTION ONE ONE-HUNDRED-AND-SIXTI
0D76..0D78  ; FREE_PVAL   # MALAYALAM FRACTION ONE SIXTEENTH..MALAYALAM
1C80..1C88  ; PVALID      # CYRILLIC SMALL LETTER ROUNDED VE..CYRILLIC S
1DFB        ; PVALID      # COMBINING DELETION MARK
23FB..23FE  ; FREE_PVAL   # POWER SYMBOL..POWER SLEEP SYMBOL
2E43..2E44  ; FREE_PVAL   # DASH WITH LEFT UPTURN..DOUBLE SUSPENSION MAR
A7AE        ; PVALID      # LATIN CAPITAL LETTER SMALL CAPITAL I
A8C5        ; PVALID      # SAURASHTRA SIGN CANDRABINDU
1018D..1018E; FREE_PVAL   # GREEK INDICTION SIGN..NOMISMA SIGN
104B0..104D3; PVALID      # OSAGE CAPITAL LETTER A..OSAGE CAPITAL LETTER
104D8..104FB; PVALID      # OSAGE SMALL LETTER A..OSAGE SMALL LETTER ZHA
1123E       ; PVALID      # KHOJKI SIGN SUKUN
11400..1144A; PVALID      # NEWA LETTER A..NEWA SIDDHI
1144B..1144F; FREE_PVAL   # NEWA DANDA..NEWA ABBREVIATION SIGN
11450..11459; PVALID      # NEWA DIGIT ZERO..NEWA DIGIT NINE
1145B       ; FREE_PVAL   # NEWA PLACEHOLDER MARK
1145D       ; FREE_PVAL   # NEWA INSERTION SIGN
11660..1166C; FREE_PVAL   # MONGOLIAN BIRGA WITH ORNAMENT..MONGOLIAN TUR
11C00..11C08; PVALID      # BHAIKSUKI LETTER A..BHAIKSUKI LETTER VOCALIC
11C0A..11C36; PVALID      # BHAIKSUKI LETTER E..BHAIKSUKI VOWEL SIGN VOC
11C38..11C40; PVALID      # BHAIKSUKI VOWEL SIGN E..BHAIKSUKI SIGN AVAGR
11C41..11C45; FREE_PVAL   # BHAIKSUKI DANDA..BHAIKSUKI GAP FILLER-2
11C50..11C59; PVALID      # BHAIKSUKI DIGIT ZERO..BHAIKSUKI DIGIT NINE
11C5A..11C6C; FREE_PVAL   # BHAIKSUKI NUMBER ONE..BHAIKSUKI HUNDREDS UNI
11C70..11C71; FREE_PVAL   # MARCHEN HEAD MARK..MARCHEN MARK SHAD
11C72..11C8F; PVALID      # MARCHEN LETTER KA..MARCHEN LETTER A
11C92..11CA7; PVALID      # MARCHEN SUBJOINED LETTER KA..MARCHEN SUBJOIN
11CA9..11CB6; PVALID      # MARCHEN SUBJOINED LETTER YA..MARCHEN SIGN CA
16FE0       ; PVALID      # TANGUT ITERATION MARK
17000..187EC; PVALID      # <Tangut Ideograph>..<Tangut Ideograph>
18800..18AF2; PVALID      # TANGUT COMPONENT-001..TANGUT COMPONENT-755
1E000..1E006; PVALID      # COMBINING GLAGOLITIC LETTER AZU..COMBINING G
1E008..1E018; PVALID      # COMBINING GLAGOLITIC LETTER ZEMLJA..COMBININ
1E01B..1E021; PVALID      # COMBINING GLAGOLITIC LETTER SHTA..COMBINING
1E023..1E024; PVALID      # COMBINING GLAGOLITIC LETTER YU..COMBINING GL
1E026..1E02A; PVALID      # COMBINING GLAGOLITIC LETTER YO..COMBINING GL
1E900..1E94A; PVALID      # ADLAM CAPITAL LETTER ALIF..ADLAM NUKTA
1E950..1E959; PVALID      # ADLAM DIGIT ZERO..ADLAM DIGIT NINE
1E95E..1E95F; FREE_PVAL   # ADLAM INITIAL EXCLAMATION MARK..ADLAM INITIA
1F19B..1F1AC; FREE_PVAL   # SQUARED THREE D..SQUARED VOD
1F23B       ; FREE_PVAL   # SQUARED CJK UNIFIED IDEOGRAPH-914D
1F57A       ; FREE_PVAL   # MAN DANCING
1F5A4       ; FREE_PVAL   # BLACK HEART
1F6D1..1F6D2; FREE_PVAL   # OCTAGONAL SIGN..SHOPPING TROLLEY
1F6F4..1F6F6; FREE_PVAL   # SCOOTER..CANOE
1F919..1F91E; FREE_PVAL   # CALL ME HAND..HAND WITH INDEX AND MIDDLE FIN
1F920..1F927; FREE_PVAL   # FACE WITH COWBOY HAT..SNEEZING FACE
1F930       ; FREE_PVAL   # PREGNANT WOMAN
1F933..1F93E; FREE_PVAL   # SELFIE..HANDBALL
1F940..1F94B; FREE_PVAL   # WILTED FLOWER..MARTIAL ARTS UNIFORM
1F950..1F95E; FREE_PVAL   # CROISSANT..PANCAKES
1F985..1F991; FREE_PVAL   # EAGLE..SQUID
~~~~


# Changes from Unicode 9.0.0 to Unicode 10.0.0

Changes from derived property value UNASSIGNED to either PVALID or ID_DIS
or FREE_PVAL.
Note: "ID_DIS or FREE_PVAL" is written as "FREE_PVAL" for convenience.


~~~~
0860..086A  ; PVALID      # SYRIAC LETTER MALAYALAM NGA..SYRIAC LETTER M
09FC        ; PVALID      # BENGALI LETTER VEDIC ANUSVARA
09FD        ; FREE_PVAL   # BENGALI ABBREVIATION SIGN
0AFA..0AFF  ; PVALID      # GUJARATI SIGN SUKUN..GUJARATI SIGN TWO-CIRCL
0D00        ; PVALID      # MALAYALAM SIGN COMBINING ANUSVARA ABOVE
0D3B..0D3C  ; PVALID      # MALAYALAM SIGN VERTICAL BAR VIRAMA..MALAYALA
1CF7        ; PVALID      # VEDIC SIGN ATIKRAMA
1DF6..1DF9  ; PVALID      # COMBINING KAVYKA ABOVE RIGHT..COMBINING WIDE
20BF        ; FREE_PVAL   # BITCOIN SIGN
23FF        ; FREE_PVAL   # OBSERVER EYE SYMBOL
2BD2        ; FREE_PVAL   # GROUP MARK
2E45..2E49  ; FREE_PVAL   # INVERTED LOW KAVYKA..DOUBLE STACKED COMMA
312E        ; PVALID      # BOPOMOFO LETTER O WITH DOT ABOVE
9FD6..9FEA  ; PVALID      # <CJK Ideograph>..<CJK Ideograph>
1032D..1032F; PVALID      # OLD ITALIC LETTER YE..OLD ITALIC LETTER SOUT
11A00..11A3E; PVALID      # ZANABAZAR SQUARE LETTER A..ZANABAZAR SQUARE
11A3F..11A46; FREE_PVAL   # ZANABAZAR SQUARE INITIAL HEAD MARK..ZANABAZA
11A47       ; PVALID      # ZANABAZAR SQUARE SUBJOINER
11A50..11A83; PVALID      # SOYOMBO LETTER A..SOYOMBO LETTER KSSA
11A86..11A99; PVALID      # SOYOMBO CLUSTER-INITIAL LETTER RA..SOYOMBO S
11A9A..11A9C; FREE_PVAL   # SOYOMBO MARK TSHEG..SOYOMBO MARK DOUBLE SHAD
11A9E..11AA2; FREE_PVAL   # SOYOMBO HEAD MARK WITH MOON AND SUN AND TRIP
11D00..11D06; PVALID      # MASARAM GONDI LETTER A..MASARAM GONDI LETTER
11D08..11D09; PVALID      # MASARAM GONDI LETTER AI..MASARAM GONDI LETTE
11D0B..11D36; PVALID      # MASARAM GONDI LETTER AU..MASARAM GONDI VOWEL
11D3A       ; PVALID      # MASARAM GONDI VOWEL SIGN E
11D3C..11D3D; PVALID      # MASARAM GONDI VOWEL SIGN AI..MASARAM GONDI V
11D3F..11D47; PVALID      # MASARAM GONDI VOWEL SIGN AU..MASARAM GONDI R
11D50..11D59; PVALID      # MASARAM GONDI DIGIT ZERO..MASARAM GONDI DIGI
16FE1       ; PVALID      # NUSHU ITERATION MARK
1B002..1B11E; PVALID      # HENTAIGANA LETTER A-1..HENTAIGANA LETTER N-M
1B170..1B2FB; PVALID      # NUSHU CHARACTER-1B170..NUSHU CHARACTER-1B2FB
1F260..1F265; FREE_PVAL   # ROUNDED SYMBOL FOR FU..ROUNDED SYMBOL FOR CA
1F6D3..1F6D4; FREE_PVAL   # STUPA..PAGODA
1F6F7..1F6F8; FREE_PVAL   # SLED..FLYING SAUCER
1F900..1F90B; FREE_PVAL   # CIRCLED CROSS FORMEE WITH FOUR DOTS..DOWNWAR
1F91F       ; FREE_PVAL   # I LOVE YOU HAND SIGN
1F928..1F92F; FREE_PVAL   # FACE WITH ONE EYEBROW RAISED..SHOCKED FACE W
1F931..1F932; FREE_PVAL   # BREAST-FEEDING..PALMS UP TOGETHER
1F94C       ; FREE_PVAL   # CURLING STONE
1F95F..1F96B; FREE_PVAL   # DUMPLING..CANNED FOOD
1F992..1F997; FREE_PVAL   # GIRAFFE FACE..CRICKET
1F9D0..1F9E6; FREE_PVAL   # FACE WITH MONOCLE..SOCKS
2CEB0..2EBE0; PVALID      # <CJK Ideograph Extension F>..<CJK Ideograph
~~~~


# Changes from Unicode 10.0.0 to Unicode 11.0.0

Changes from derived property value ID_DIS or FREE_PVAL to PVALID.


~~~~
111C9       ; PVALID      # SHARADA SANDHI MARK
~~~~

Changes from derived property value UNASSIGNED to either PVALID, DISALLOWED
or ID_DIS or FREE_PVAL.
Note: "ID_DIS or FREE_PVAL" is written as "FREE_PVAL" for convenience.


~~~~
0560        ; PVALID      # ARMENIAN SMALL LETTER TURNED AYB
0588        ; PVALID      # ARMENIAN SMALL LETTER YI WITH STROKE
05EF        ; PVALID      # HEBREW YOD TRIANGLE
07FD        ; PVALID      # NKO DANTAYALAN
07FE..07FF  ; FREE_PVAL   # NKO DOROME SIGN..NKO TAMAN SIGN
08D3        ; PVALID      # ARABIC SMALL LOW WAW
09FE        ; PVALID      # BENGALI SANDHI MARK
0A76        ; FREE_PVAL   # GURMUKHI ABBREVIATION SIGN
0C04        ; PVALID      # TELUGU SIGN COMBINING ANUSVARA ABOVE
0C84        ; FREE_PVAL   # KANNADA SIGN SIDDHAM
1878        ; PVALID      # MONGOLIAN LETTER CHA WITH TWO DOTS
1C90..1CBA  ; PVALID      # GEORGIAN MTAVRULI CAPITAL LETTER AN..GEORGIA
1CBD..1CBF  ; PVALID      # GEORGIAN MTAVRULI CAPITAL LETTER AEN..GEORGI
2BBA..2BBC  ; FREE_PVAL   # OVERLAPPING WHITE SQUARES..OVERLAPPING BLACK
2BD3..2BEB  ; FREE_PVAL   # PLUTO FORM TWO..STAR WITH RIGHT HALF BLACK
2BF0..2BFE  ; FREE_PVAL   # ERIS FORM ONE..REVERSED RIGHT ANGLE
2E4A..2E4E  ; FREE_PVAL   # DOTTED SOLIDUS..PUNCTUS ELEVATUS MARK
312F        ; PVALID      # BOPOMOFO LETTER NN
9FEB..9FEF  ; PVALID      # <CJK Ideograph>..<CJK Ideograph>
A7AF        ; PVALID      # LATIN LETTER SMALL CAPITAL Q
A7B8..A7B9  ; PVALID      # LATIN CAPITAL LETTER U WITH STROKE..LATIN SM
A8FE..A8FF  ; PVALID      # DEVANAGARI LETTER AY..DEVANAGARI VOWEL SIGN
10A34..10A35; PVALID      # KHAROSHTHI LETTER TTTA..KHAROSHTHI LETTER VH
10A48       ; FREE_PVAL   # KHAROSHTHI FRACTION ONE HALF
10D00..10D27; PVALID      # HANIFI ROHINGYA LETTER A..HANIFI ROHINGYA SI
10D30..10D39; PVALID      # HANIFI ROHINGYA DIGIT ZERO..HANIFI ROHINGYA
10F00..10F1C; PVALID      # OLD SOGDIAN LETTER ALEPH..OLD SOGDIAN LETTER
10F1D..10F26; FREE_PVAL   # OLD SOGDIAN NUMBER ONE..OLD SOGDIAN FRACTION
10F27       ; PVALID      # OLD SOGDIAN LIGATURE AYIN-DALETH
10F30..10F50; PVALID      # SOGDIAN LETTER ALEPH..SOGDIAN COMBINING STRO
10F51..10F59; FREE_PVAL   # SOGDIAN NUMBER ONE..SOGDIAN PUNCTUATION HALF
110CD       ; DISALLOWED  # KAITHI NUMBER SIGN ABOVE
11144..11146; PVALID      # CHAKMA LETTER LHAA..CHAKMA VOWEL SIGN EI
111C9       ; PVALID      # SHARADA SANDHI MARK
1133B       ; PVALID      # COMBINING BINDU BELOW
1145E       ; PVALID      # NEWA SANDHI MARK
1171A       ; PVALID      # AHOM LETTER ALTERNATE BA
11800..1183A; PVALID      # DOGRA LETTER A..DOGRA SIGN NUKTA
1183B       ; FREE_PVAL   # DOGRA ABBREVIATION SIGN
11A9D       ; PVALID      # SOYOMBO MARK PLUTA
11D60..11D65; PVALID      # GUNJALA GONDI LETTER A..GUNJALA GONDI LETTER
11D67..11D68; PVALID      # GUNJALA GONDI LETTER EE..GUNJALA GONDI LETTE
11D6A..11D8E; PVALID      # GUNJALA GONDI LETTER OO..GUNJALA GONDI VOWEL
11D90..11D91; PVALID      # GUNJALA GONDI VOWEL SIGN EE..GUNJALA GONDI V
11D93..11D98; PVALID      # GUNJALA GONDI VOWEL SIGN OO..GUNJALA GONDI O
11DA0..11DA9; PVALID      # GUNJALA GONDI DIGIT ZERO..GUNJALA GONDI DIGI
11EE0..11EF6; PVALID      # MAKASAR LETTER KA..MAKASAR VOWEL SIGN O
11EF7..11EF8; FREE_PVAL   # MAKASAR PASSIMBANG..MAKASAR END OF SECTION
16E40..16E7F; PVALID      # MEDEFAIDRIN CAPITAL LETTER M..MEDEFAIDRIN SM
16E80..16E9A; FREE_PVAL   # MEDEFAIDRIN DIGIT ZERO..MEDEFAIDRIN EXCLAMAT
187ED..187F1; PVALID      # <Tangut Ideograph>..<Tangut Ideograph>
1D2E0..1D2F3; FREE_PVAL   # MAYAN NUMERAL ZERO..MAYAN NUMERAL NINETEEN
1D372..1D378; FREE_PVAL   # IDEOGRAPHIC TALLY MARK ONE..TALLY MARK FIVE
1EC71..1ECB4; FREE_PVAL   # INDIC SIYAQ NUMBER ONE..INDIC SIYAQ ALTERNAT
1F12F       ; FREE_PVAL   # COPYLEFT SYMBOL
1F6F9       ; FREE_PVAL   # SKATEBOARD
1F7D5..1F7D8; FREE_PVAL   # CIRCLED TRIANGLE..NEGATIVE CIRCLED SQUARE
1F94D..1F94F; FREE_PVAL   # LACROSSE STICK AND BALL..FLYING DISC
1F96C..1F970; FREE_PVAL   # LEAFY GREEN..SMILING FACE WITH SMILING EYES
1F973..1F976; FREE_PVAL   # FACE WITH PARTY HORN AND PARTY HAT..FREEZING
1F97A       ; FREE_PVAL   # FACE WITH PLEADING EYES
1F97C..1F97F; FREE_PVAL   # LAB COAT..FLAT SHOE
1F998..1F9A2; FREE_PVAL   # KANGAROO..SWAN
1F9B0..1F9B9; FREE_PVAL   # EMOJI COMPONENT RED HAIR..SUPERVILLAIN
1F9C1..1F9C2; FREE_PVAL   # CUPCAKE..SALT SHAKER
1F9E7..1F9FF; FREE_PVAL   # RED GIFT ENVELOPE..NAZAR AMULET
1FA60..1FA6D; FREE_PVAL   # XIANGQI RED GENERAL..XIANGQI BLACK SOLDIER
~~~~


# Changes from Unicode 11.0.0 to Unicode 12.0.0

Changes from derived property value UNASSIGNED to either PVALID, DISALLOWED
or ID_DIS or FREE_PVAL.
Note: "ID_DIS or FREE_PVAL" is written as "FREE_PVAL" for convenience.


~~~~
0C77        ; FREE_PVAL   # TELUGU SIGN SIDDHAM
0E86        ; PVALID      # LAO LETTER PALI GHA
0E89        ; PVALID      # LAO LETTER PALI CHA
0E8C        ; PVALID      # LAO LETTER PALI JHA
0E8E..0E93  ; PVALID      # LAO LETTER PALI NYA..LAO LETTER PALI NNA
0E98        ; PVALID      # LAO LETTER PALI DHA
0EA0        ; PVALID      # LAO LETTER PALI BHA
0EA8..0EA9  ; PVALID      # LAO LETTER SANSKRIT SHA..LAO LETTER SANSKRIT
0EAC        ; PVALID      # LAO LETTER PALI LLA
0EBA        ; PVALID      # LAO SIGN PALI VIRAMA
166D        ; FREE_PVAL   # CANADIAN SYLLABICS CHI SIGN
1CFA        ; PVALID      # VEDIC SIGN DOUBLE ANUSVARA ANTARGOMUKHA
2BC9        ; FREE_PVAL   # NEPTUNE FORM TWO
2BFF        ; FREE_PVAL   # HELLSCHREIBER PAUSE SYMBOL
2E4F        ; FREE_PVAL   # CORNISH VERSE DIVIDER
A7BA..A7BF  ; PVALID      # LATIN CAPITAL LETTER GLOTTAL A..LATIN SMALL
A7C2..A7C6  ; PVALID      # LATIN CAPITAL LETTER ANGLICANA W..LATIN CAPI
AB66..AB67  ; PVALID      # LATIN SMALL LETTER DZ DIGRAPH WITH RETROFLEX
10FE0..10FF6; PVALID      # ELYMAIC LETTER ALEPH..ELYMAIC LIGATURE ZAYIN
1145F       ; PVALID      # NEWA LETTER VEDIC ANUSVARA
116B8       ; PVALID      # TAKRI LETTER ARCHAIC KHA
119A0..119A7; PVALID      # NANDINAGARI LETTER A..NANDINAGARI LETTER VOC
119AA..119D7; PVALID      # NANDINAGARI LETTER E..NANDINAGARI VOWEL SIGN
119DA..119E1; PVALID      # NANDINAGARI VOWEL SIGN E..NANDINAGARI SIGN A
119E2       ; FREE_PVAL   # NANDINAGARI SIGN SIDDHAM
119E3..119E4; PVALID      # NANDINAGARI HEADSTROKE..NANDINAGARI VOWEL SI
11A84..11A85; PVALID      # SOYOMBO SIGN JIHVAMULIYA..SOYOMBO SIGN UPADH
11FC0..11FF1; FREE_PVAL   # TAMIL FRACTION ONE THREE-HUNDRED-AND-TWENTIE
11FFF       ; FREE_PVAL   # TAMIL PUNCTUATION END OF TEXT
13430..13438; DISALLOWED  # EGYPTIAN HIEROGLYPH VERTICAL JOINER..EGYPTIA
16F45..16F4A; PVALID      # MIAO LETTER BRI..MIAO LETTER RTE
16F4F       ; PVALID      # MIAO SIGN CONSONANT MODIFIER BAR
16F7F..16F87; PVALID      # MIAO VOWEL SIGN UOG..MIAO VOWEL SIGN UI
16FE2       ; FREE_PVAL   # OLD CHINESE HOOK MARK
16FE3       ; PVALID      # OLD CHINESE ITERATION MARK
187F2..187F7; PVALID      # <Tangut Ideograph>..<Tangut Ideograph>
1B150..1B152; PVALID      # HIRAGANA LETTER SMALL WI..HIRAGANA LETTER SM
1B164..1B167; PVALID      # KATAKANA LETTER SMALL WI..KATAKANA LETTER SM
1E100..1E12C; PVALID      # NYIAKENG PUACHUE HMONG LETTER MA..NYIAKENG P
1E130..1E13D; PVALID      # NYIAKENG PUACHUE HMONG TONE-B..NYIAKENG PUAC
1E140..1E149; PVALID      # NYIAKENG PUACHUE HMONG DIGIT ZERO..NYIAKENG
1E14E       ; PVALID      # NYIAKENG PUACHUE HMONG LOGOGRAM NYAJ
1E14F       ; FREE_PVAL   # NYIAKENG PUACHUE HMONG CIRCLED CA
1E2C0..1E2F9; PVALID      # WANCHO LETTER AA..WANCHO DIGIT NINE
1E2FF       ; FREE_PVAL   # WANCHO NGUN SIGN
1E94B       ; PVALID      # ADLAM NASALIZATION MARK
1ED01..1ED3D; FREE_PVAL   # OTTOMAN SIYAQ NUMBER ONE..OTTOMAN SIYAQ FRAC
1F16C       ; FREE_PVAL   # RAISED MR SIGN
1F6D5       ; FREE_PVAL   # HINDU TEMPLE
1F6FA       ; FREE_PVAL   # AUTO RICKSHAW
1F7E0..1F7EB; FREE_PVAL   # LARGE ORANGE CIRCLE..LARGE BROWN SQUARE
1F90D..1F90F; FREE_PVAL   # WHITE HEART..PINCHING HAND
1F93F       ; FREE_PVAL   # DIVING MASK
1F971       ; FREE_PVAL   # YAWNING FACE
1F97B       ; FREE_PVAL   # SARI
1F9A5..1F9AA; FREE_PVAL   # SLOTH..OYSTER
1F9AE..1F9AF; FREE_PVAL   # GUIDE DOG..PROBING CANE
1F9BA..1F9BF; FREE_PVAL   # SAFETY VEST..MECHANICAL LEG
1F9C3..1F9CA; FREE_PVAL   # BEVERAGE BOX..ICE CUBE
1F9CD..1F9CF; FREE_PVAL   # STANDING PERSON..DEAF PERSON
1FA00..1FA53; FREE_PVAL   # NEUTRAL CHESS KING..BLACK CHESS KNIGHT-BISHO
1FA70..1FA73; FREE_PVAL   # BALLET SHOES..SHORTS
1FA78..1FA7A; FREE_PVAL   # DROP OF BLOOD..STETHOSCOPE
1FA80..1FA82; FREE_PVAL   # YO-YO..PARACHUTE
1FA90..1FA95; FREE_PVAL   # RINGED PLANET..BANJO
~~~~


# Changes from Unicode 12.0.0 to Unicode 13.0.0

Changes from derived property value UNASSIGNED to either PVALID or ID_DIS
or FREE_PVAL.
Note: "ID_DIS or FREE_PVAL" is written as "FREE_PVAL" for convenience.


~~~~
08BE..08C7  ; PVALID      # ARABIC LETTER PEH WITH SMALL V..ARABIC LETTE
0B55        ; PVALID      # ORIYA SIGN OVERLINE
0D04        ; PVALID      # MALAYALAM LETTER VEDIC ANUSVARA
0D81        ; PVALID      # SINHALA SIGN CANDRABINDU
1ABF..1AC0  ; PVALID      # COMBINING LATIN SMALL LETTER W BELOW..COMBIN
2B97        ; FREE_PVAL   # SYMBOL FOR TYPE A ELECTRONICS
2E50..2E52  ; FREE_PVAL   # CROSS PATTY WITH RIGHT CROSSBAR..TIRONIAN SI
31BB..31BF  ; PVALID      # BOPOMOFO FINAL LETTER G..BOPOMOFO LETTER AH
32FF        ; FREE_PVAL   # SQUARE ERA NAME REIWA
4DB6..4DBF  ; PVALID      # <CJK Ideograph Extension A>..<CJK Ideograph
9FF0..9FFC  ; PVALID      # <CJK Ideograph>..<CJK Ideograph>
A7C7..A7CA  ; PVALID      # LATIN CAPITAL LETTER D WITH SHORT STROKE OVE
A7F5..A7F6  ; PVALID      # LATIN CAPITAL LETTER REVERSED HALF H..LATIN
A82C        ; PVALID      # SYLOTI NAGRI SIGN ALTERNATE HASANTA
AB68        ; PVALID      # LATIN SMALL LETTER TURNED R WITH MIDDLE TILD
AB69..AB6B  ; FREE_PVAL   # MODIFIER LETTER SMALL TURNED W..MODIFIER LET
1019C       ; FREE_PVAL   # ASCIA SYMBOL
10E80..10EA9; PVALID      # YEZIDI LETTER ELIF..YEZIDI LETTER ET
10EAB..10EAC; PVALID      # YEZIDI COMBINING HAMZA MARK..YEZIDI COMBININ
10EAD       ; FREE_PVAL   # YEZIDI HYPHENATION MARK
10EB0..10EB1; PVALID      # YEZIDI LETTER LAM WITH DOT ABOVE..YEZIDI LET
10FB0..10FC4; PVALID      # CHORASMIAN LETTER ALEPH..CHORASMIAN LETTER T
10FC5..10FCB; FREE_PVAL   # CHORASMIAN NUMBER ONE..CHORASMIAN NUMBER ONE
11147       ; PVALID      # CHAKMA LETTER VAA
111CE..111CF; PVALID      # SHARADA VOWEL SIGN PRISHTHAMATRA E..SHARADA
1145A       ; FREE_PVAL   # NEWA DOUBLE COMMA
11460..11461; PVALID      # NEWA SIGN JIHVAMULIYA..NEWA SIGN UPADHMANIYA
11900..11906; PVALID      # DIVES AKURU LETTER A..DIVES AKURU LETTER E
11909       ; PVALID      # DIVES AKURU LETTER O
1190C..11913; PVALID      # DIVES AKURU LETTER KA..DIVES AKURU LETTER JA
11915..11916; PVALID      # DIVES AKURU LETTER NYA..DIVES AKURU LETTER T
11918..11935; PVALID      # DIVES AKURU LETTER DDA..DIVES AKURU VOWEL SI
11937..11938; PVALID      # DIVES AKURU VOWEL SIGN AI..DIVES AKURU VOWEL
1193B..11943; PVALID      # DIVES AKURU SIGN ANUSVARA..DIVES AKURU SIGN
11944..11946; FREE_PVAL   # DIVES AKURU DOUBLE DANDA..DIVES AKURU END OF
11950..11959; PVALID      # DIVES AKURU DIGIT ZERO..DIVES AKURU DIGIT NI
11FB0       ; PVALID      # LISU LETTER YHA
16FE4       ; PVALID      # KHITAN SMALL SCRIPT FILLER
16FF0..16FF1; PVALID      # VIETNAMESE ALTERNATE READING MARK CA..VIETNA
18AF3..18CD5; PVALID      # TANGUT COMPONENT-756..KHITAN SMALL SCRIPT CH
18D00..18D08; PVALID      # <Tangut Ideograph Supplement>..<Tangut Ideog
1F10D..1F10F; FREE_PVAL   # CIRCLED ZERO WITH SLASH..CIRCLED DOLLAR SIGN
1F16D..1F16F; FREE_PVAL   # CIRCLED CC..CIRCLED HUMAN FIGURE
1F1AD       ; FREE_PVAL   # MASK WORK SYMBOL
1F6D6..1F6D7; FREE_PVAL   # HUT..ELEVATOR
1F6FB..1F6FC; FREE_PVAL   # PICKUP TRUCK..ROLLER SKATE
1F8B0..1F8B1; FREE_PVAL   # ARROW POINTING UPWARDS THEN NORTH WEST..ARRO
1F90C       ; FREE_PVAL   # PINCHED FINGERS
1F972       ; FREE_PVAL   # SMILING FACE WITH TEAR
1F977..1F978; FREE_PVAL   # NINJA..DISGUISED FACE
1F9A3..1F9A4; FREE_PVAL   # MAMMOTH..DODO
1F9AB..1F9AD; FREE_PVAL   # BEAVER..SEAL
1F9CB       ; FREE_PVAL   # BUBBLE TEA
1FA74       ; FREE_PVAL   # THONG SANDAL
1FA83..1FA86; FREE_PVAL   # BOOMERANG..NESTING DOLLS
1FA96..1FAA8; FREE_PVAL   # MILITARY HELMET..ROCK
1FAB0..1FAB6; FREE_PVAL   # FLY..FEATHER
1FAC0..1FAC2; FREE_PVAL   # ANATOMICAL HEART..PEOPLE HUGGING
1FAD0..1FAD6; FREE_PVAL   # BLUEBERRIES..TEAPOT
1FB00..1FB92; FREE_PVAL   # BLOCK SEXTANT-1..UPPER HALF INVERSE MEDIUM S
1FB94..1FBCA; FREE_PVAL   # LEFT HALF INVERSE MEDIUM SHADE AND RIGHT HAL
1FBF0..1FBF9; FREE_PVAL   # SEGMENTED DIGIT ZERO..SEGMENTED DIGIT NINE
2A6D7..2A6DD; PVALID      # <CJK Ideograph Extension B>..<CJK Ideograph
30000..3134A; PVALID      # <CJK Ideograph Extension G>..<CJK Ideograph
~~~~


# Changes from Unicode 13.0.0 to Unicode 14.0.0

Changes from derived property value UNASSIGNED to either PVALID, DISALLOWED
or ID_DIS or FREE_PVAL.
Note: "ID_DIS or FREE_PVAL" is written as "FREE_PVAL" for convenience.


~~~~
061D        ; FREE_PVAL  # ARABIC END OF TEXT MARK
0870..0887  ; PVALID     # ARABIC LETTER ALEF WITH ATTACHED FATHA..ARAB
0888        ; FREE_PVAL  # ARABIC RAISED ROUND DOT
0889..088E  ; PVALID     # ARABIC LETTER NOON WITH INVERTED SMALL V..AR
0890..0891  ; DISALLOWED # ARABIC POUND MARK ABOVE..ARABIC PIASTRE MARK
0898..089F  ; PVALID     # ARABIC SMALL HIGH WORD AL-JUZ..ARABIC HALF M
08B5        ; PVALID     # ARABIC LETTER QAF WITH DOT BELOW AND NO DOTS
08C8..08D2  ; PVALID     # ARABIC LETTER GRAF..ARABIC LARGE ROUND DOT I
0C3C        ; PVALID     # TELUGU SIGN NUKTA
0C5D        ; PVALID     # TELUGU LETTER NAKAARA POLLU
0CDD        ; PVALID     # KANNADA LETTER NAKAARA POLLU
170D        ; PVALID     # TAGALOG LETTER RA
1715        ; PVALID     # TAGALOG SIGN PAMUDPOD
171F        ; PVALID     # TAGALOG LETTER ARCHAIC RA
180F        ; DISALLOWED # MONGOLIAN FREE VARIATION SELECTOR FOUR
1AC1..1ACE  ; PVALID     # COMBINING LEFT PARENTHESIS ABOVE LEFT..COMBI
1B4C        ; PVALID     # BALINESE LETTER ARCHAIC JNYA
1B7D..1B7E  ; FREE_PVAL  # BALINESE PANTI LANTANG..BALINESE PAMADA LANT
1DFA        ; PVALID     # COMBINING DOT BELOW LEFT
20C0        ; FREE_PVAL  # SOM SIGN
2C2F        ; PVALID     # GLAGOLITIC CAPITAL LETTER CAUDATE CHRIVI
2C5F        ; PVALID     # GLAGOLITIC SMALL LETTER CAUDATE CHRIVI
2E53..2E5D  ; FREE_PVAL  # MEDIEVAL EXCLAMATION MARK..OBLIQUE HYPHEN
9FFD..9FFF  ; PVALID     # <CJK Ideograph>..<CJK Ideograph>
A7C0..A7C1  ; PVALID     # LATIN CAPITAL LETTER OLD POLISH O..LATIN SMA
A7D0..A7D1  ; PVALID     # LATIN CAPITAL LETTER CLOSED INSULAR G..LATIN
A7D3        ; PVALID     # LATIN SMALL LETTER DOUBLE THORN
A7D5..A7D9  ; PVALID     # LATIN SMALL LETTER DOUBLE WYNN..LATIN SMALL
A7F2..A7F4  ; FREE_PVAL  # MODIFIER LETTER CAPITAL C..MODIFIER LETTER C
FBC2        ; FREE_PVAL  # ARABIC SYMBOL WASLA ABOVE
FD40..FD4F  ; FREE_PVAL  # ARABIC LIGATURE RAHIMAHU ALLAAH..ARABIC LIGA
FDCF        ; FREE_PVAL  # ARABIC LIGATURE SALAAMUHU ALAYNAA
FDFE..FDFF  ; FREE_PVAL  # ARABIC LIGATURE SUBHAANAHU WA TAAALAA..ARABI
10570..1057A; PVALID     # VITHKUQI CAPITAL LETTER A..VITHKUQI CAPITAL
1057C..1058A; PVALID     # VITHKUQI CAPITAL LETTER HA..VITHKUQI CAPITAL
1058C..10592; PVALID     # VITHKUQI CAPITAL LETTER SE..VITHKUQI CAPITAL
10594..10595; PVALID     # VITHKUQI CAPITAL LETTER Y..VITHKUQI CAPITAL
10597..105A1; PVALID     # VITHKUQI SMALL LETTER A..VITHKUQI SMALL LETT
105A3..105B1; PVALID     # VITHKUQI SMALL LETTER HA..VITHKUQI SMALL LET
105B3..105B9; PVALID     # VITHKUQI SMALL LETTER SE..VITHKUQI SMALL LET
105BB..105BC; PVALID     # VITHKUQI SMALL LETTER Y..VITHKUQI SMALL LETT
10780       ; PVALID     # MODIFIER LETTER SMALL CAPITAL AA
10781..10785; FREE_PVAL  # MODIFIER LETTER SUPERSCRIPT TRIANGULAR COLON
10787..107B0; FREE_PVAL  # MODIFIER LETTER SMALL DZ DIGRAPH..MODIFIER L
107B2..107BA; FREE_PVAL  # MODIFIER LETTER SMALL CAPITAL Y..MODIFIER LE
10F70..10F85; PVALID     # OLD UYGHUR LETTER ALEPH..OLD UYGHUR COMBININ
10F86..10F89; FREE_PVAL  # OLD UYGHUR PUNCTUATION BAR..OLD UYGHUR PUNCT
11070..11075; PVALID     # BRAHMI SIGN OLD TAMIL VIRAMA..BRAHMI LETTER
110C2       ; PVALID     # KAITHI VOWEL SIGN VOCALIC R
116B9       ; FREE_PVAL  # TAKRI ABBREVIATION SIGN
11740..11746; PVALID     # AHOM LETTER CA..AHOM LETTER LLA
11AB0..11ABF; PVALID     # CANADIAN SYLLABICS NATTILIK HI..CANADIAN SYL
12F90..12FF0; PVALID     # CYPRO-MINOAN SIGN CM001..CYPRO-MINOAN SIGN C
12FF1..12FF2; FREE_PVAL  # CYPRO-MINOAN SIGN CM301..CYPRO-MINOAN SIGN C
16A70..16ABE; PVALID     # TANGSA LETTER OZ..TANGSA LETTER ZA
16AC0..16AC9; PVALID     # TANGSA DIGIT ZERO..TANGSA DIGIT NINE
1AFF0..1AFF3; PVALID     # KATAKANA LETTER MINNAN TONE-2..KATAKANA LETT
1AFF5..1AFFB; PVALID     # KATAKANA LETTER MINNAN TONE-7..KATAKANA LETT
1AFFD..1AFFE; PVALID     # KATAKANA LETTER MINNAN NASALIZED TONE-7..KAT
1B11F..1B122; PVALID     # HIRAGANA LETTER ARCHAIC WU..KATAKANA LETTER
1CF00..1CF2D; PVALID     # ZNAMENNY COMBINING MARK GORAZDO NIZKO S KRYZ
1CF30..1CF46; PVALID     # ZNAMENNY COMBINING TONAL RANGE MARK MRACHNO.
1CF50..1CFC3; FREE_PVAL  # ZNAMENNY NEUME KRYUK..ZNAMENNY NEUME PAUK
1D1E9..1D1EA; FREE_PVAL  # MUSICAL SYMBOL SORI..MUSICAL SYMBOL KORON
1DF00..1DF1E; PVALID     # LATIN SMALL LETTER FENG DIGRAPH WITH TRILL..
1E290..1E2AE; PVALID     # TOTO LETTER PA..TOTO SIGN RISING TONE
1E7E0..1E7E6; PVALID     # ETHIOPIC SYLLABLE HHYA..ETHIOPIC SYLLABLE HH
1E7E8..1E7EB; PVALID     # ETHIOPIC SYLLABLE GURAGE HHWA..ETHIOPIC SYLL
1E7ED..1E7EE; PVALID     # ETHIOPIC SYLLABLE GURAGE MWI..ETHIOPIC SYLLA
1E7F0..1E7FE; PVALID     # ETHIOPIC SYLLABLE GURAGE QWI..ETHIOPIC SYLLA
1F6DD..1F6DF; FREE_PVAL  # PLAYGROUND SLIDE..RING BUOY
1F7F0       ; FREE_PVAL  # HEAVY EQUALS SIGN
1F979       ; FREE_PVAL  # FACE HOLDING BACK TEARS
1F9CC       ; FREE_PVAL  # TROLL
1FA7B..1FA7C; FREE_PVAL  # X-RAY..CRUTCH
1FAA9..1FAAC; FREE_PVAL  # MIRROR BALL..HAMSA
1FAB7..1FABA; FREE_PVAL  # LOTUS..NEST WITH EGGS
1FAC3..1FAC5; FREE_PVAL  # PREGNANT MAN..PERSON WITH CROWN
1FAD7..1FAD9; FREE_PVAL  # POURING LIQUID..JAR
1FAE0..1FAE7; FREE_PVAL  # MELTING FACE..BUBBLES
1FAF0..1FAF6; FREE_PVAL  # HAND WITH INDEX FINGER AND THUMB CROSSED..HE
2A6DE..2A6DF; PVALID     # <CJK Ideograph Extension B>..<CJK Ideograph
2B735..2B738; PVALID     # <CJK Ideograph Extension C>..<CJK Ideograph
~~~~


# Code points in Unicode Character Database (UCD) format for Unicode 14.0.0

Note: "ID_DIS or FREE_PVAL" is written as "FREE_PVAL" for convenience.


~~~~
0000..001F  ; DISALLOWED  # NULL..NULL
0020        ; FREE_PVAL   # SPACE
0021..007E  ; PVALID      # EXCLAMATION MARK..TILDE
007F..009F  ; DISALLOWED  # NULL..NULL
00A0..00AC  ; FREE_PVAL   # NO-BREAK SPACE..NOT SIGN
00AD        ; DISALLOWED  # SOFT HYPHEN
00AE..00B6  ; FREE_PVAL   # REGISTERED SIGN..PILCROW SIGN
00B7        ; CONTEXTO    # MIDDLE DOT
00B8..00BF  ; FREE_PVAL   # CEDILLA..INVERTED QUESTION MARK
00C0..00D6  ; PVALID      # LATIN CAPITAL LETTER A WITH GRAVE..LATIN CAP
00D7        ; FREE_PVAL   # MULTIPLICATION SIGN
00D8..00F6  ; PVALID      # LATIN CAPITAL LETTER O WITH STROKE..LATIN SM
00F7        ; FREE_PVAL   # DIVISION SIGN
00F8..0131  ; PVALID      # LATIN SMALL LETTER O WITH STROKE..LATIN SMAL
0132..0133  ; FREE_PVAL   # LATIN CAPITAL LIGATURE IJ..LATIN SMALL LIGAT
0134..013E  ; PVALID      # LATIN CAPITAL LETTER J WITH CIRCUMFLEX..LATI
013F..0140  ; FREE_PVAL   # LATIN CAPITAL LETTER L WITH MIDDLE DOT..LATI
0141..0148  ; PVALID      # LATIN CAPITAL LETTER L WITH STROKE..LATIN SM
0149        ; FREE_PVAL   # LATIN SMALL LETTER N PRECEDED BY APOSTROPHE
014A..017E  ; PVALID      # LATIN CAPITAL LETTER ENG..LATIN SMALL LETTER
017F        ; FREE_PVAL   # LATIN SMALL LETTER LONG S
0180..01C3  ; PVALID      # LATIN SMALL LETTER B WITH STROKE..LATIN LETT
01C4..01CC  ; FREE_PVAL   # LATIN CAPITAL LETTER DZ WITH CARON..LATIN SM
01CD..01F0  ; PVALID      # LATIN CAPITAL LETTER A WITH CARON..LATIN SMA
01F1..01F3  ; FREE_PVAL   # LATIN CAPITAL LETTER DZ..LATIN SMALL LETTER
01F4..02AF  ; PVALID      # LATIN CAPITAL LETTER G WITH ACUTE..LATIN SMA
02B0..02B8  ; FREE_PVAL   # MODIFIER LETTER SMALL H..MODIFIER LETTER SMA
02B9..02C1  ; PVALID      # MODIFIER LETTER PRIME..MODIFIER LETTER REVER
02C2..02C5  ; FREE_PVAL   # MODIFIER LETTER LEFT ARROWHEAD..MODIFIER LET
02C6..02D1  ; PVALID      # MODIFIER LETTER CIRCUMFLEX ACCENT..MODIFIER
02D2..02EB  ; FREE_PVAL   # MODIFIER LETTER CENTRED RIGHT HALF RING..MOD
02EC        ; PVALID      # MODIFIER LETTER VOICING
02ED        ; FREE_PVAL   # MODIFIER LETTER UNASPIRATED
02EE        ; PVALID      # MODIFIER LETTER DOUBLE APOSTROPHE
02EF..02FF  ; FREE_PVAL   # MODIFIER LETTER LOW DOWN ARROWHEAD..MODIFIER
0300..033F  ; PVALID      # COMBINING GRAVE ACCENT..COMBINING DOUBLE OVE
0340..0341  ; FREE_PVAL   # COMBINING GRAVE TONE MARK..COMBINING ACUTE T
0342        ; PVALID      # COMBINING GREEK PERISPOMENI
0343..0344  ; FREE_PVAL   # COMBINING GREEK KORONIS..COMBINING GREEK DIA
0345..034E  ; PVALID      # COMBINING GREEK YPOGEGRAMMENI..COMBINING UPW
034F        ; DISALLOWED  # COMBINING GRAPHEME JOINER
0350..0373  ; PVALID      # COMBINING RIGHT ARROWHEAD ABOVE..GREEK SMALL
0374        ; FREE_PVAL   # GREEK NUMERAL SIGN
0375        ; CONTEXTO    # GREEK LOWER NUMERAL SIGN
0376..0377  ; PVALID      # GREEK CAPITAL LETTER PAMPHYLIAN DIGAMMA..GRE
0378..0379  ; UNASSIGNED  # <RESERVED>..<RESERVED>
037A        ; FREE_PVAL   # GREEK YPOGEGRAMMENI
037B..037D  ; PVALID      # GREEK SMALL REVERSED LUNATE SIGMA SYMBOL..GR
037E        ; FREE_PVAL   # GREEK QUESTION MARK
037F        ; PVALID      # GREEK CAPITAL LETTER YOT
0380..0383  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0384..0385  ; FREE_PVAL   # GREEK TONOS..GREEK DIALYTIKA TONOS
0386        ; PVALID      # GREEK CAPITAL LETTER ALPHA WITH TONOS
0387        ; FREE_PVAL   # GREEK ANO TELEIA
0388..038A  ; PVALID      # GREEK CAPITAL LETTER EPSILON WITH TONOS..GRE
038B        ; UNASSIGNED  # <RESERVED>
038C        ; PVALID      # GREEK CAPITAL LETTER OMICRON WITH TONOS
038D        ; UNASSIGNED  # <RESERVED>
038E..03A1  ; PVALID      # GREEK CAPITAL LETTER UPSILON WITH TONOS..GRE
03A2        ; UNASSIGNED  # <RESERVED>
03A3..03CF  ; PVALID      # GREEK CAPITAL LETTER SIGMA..GREEK CAPITAL KA
03D0..03D6  ; FREE_PVAL   # GREEK BETA SYMBOL..GREEK PI SYMBOL
03D7..03EF  ; PVALID      # GREEK KAI SYMBOL..COPTIC SMALL LETTER DEI
03F0..03F2  ; FREE_PVAL   # GREEK KAPPA SYMBOL..GREEK LUNATE SIGMA SYMBO
03F3        ; PVALID      # GREEK LETTER YOT
03F4..03F6  ; FREE_PVAL   # GREEK CAPITAL THETA SYMBOL..GREEK REVERSED L
03F7..03F8  ; PVALID      # GREEK CAPITAL LETTER SHO..GREEK SMALL LETTER
03F9        ; FREE_PVAL   # GREEK CAPITAL LUNATE SIGMA SYMBOL
03FA..0481  ; PVALID      # GREEK CAPITAL LETTER SAN..CYRILLIC SMALL LET
0482        ; FREE_PVAL   # CYRILLIC THOUSANDS SIGN
0483..0487  ; PVALID      # COMBINING CYRILLIC TITLO..COMBINING CYRILLIC
0488..0489  ; FREE_PVAL   # COMBINING CYRILLIC HUNDRED THOUSANDS SIGN..C
048A..052F  ; PVALID      # CYRILLIC CAPITAL LETTER SHORT I WITH TAIL..C
0530        ; UNASSIGNED  # <RESERVED>
0531..0556  ; PVALID      # ARMENIAN CAPITAL LETTER AYB..ARMENIAN CAPITA
0557..0558  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0559        ; PVALID      # ARMENIAN MODIFIER LETTER LEFT HALF RING
055A..055F  ; FREE_PVAL   # ARMENIAN APOSTROPHE..ARMENIAN ABBREVIATION M
0560..0586  ; PVALID      # ARMENIAN SMALL LETTER TURNED AYB..ARMENIAN S
0587        ; FREE_PVAL   # ARMENIAN SMALL LIGATURE ECH YIWN
0588        ; PVALID      # ARMENIAN SMALL LETTER YI WITH STROKE
0589..058A  ; FREE_PVAL   # ARMENIAN FULL STOP..ARMENIAN HYPHEN
058B..058C  ; UNASSIGNED  # <RESERVED>..<RESERVED>
058D..058F  ; FREE_PVAL   # RIGHT-FACING ARMENIAN ETERNITY SIGN..ARMENIA
0590        ; UNASSIGNED  # <RESERVED>
0591..05BD  ; PVALID      # HEBREW ACCENT ETNAHTA..HEBREW POINT METEG
05BE        ; FREE_PVAL   # HEBREW PUNCTUATION MAQAF
05BF        ; PVALID      # HEBREW POINT RAFE
05C0        ; FREE_PVAL   # HEBREW PUNCTUATION PASEQ
05C1..05C2  ; PVALID      # HEBREW POINT SHIN DOT..HEBREW POINT SIN DOT
05C3        ; FREE_PVAL   # HEBREW PUNCTUATION SOF PASUQ
05C4..05C5  ; PVALID      # HEBREW MARK UPPER DOT..HEBREW MARK LOWER DOT
05C6        ; FREE_PVAL   # HEBREW PUNCTUATION NUN HAFUKHA
05C7        ; PVALID      # HEBREW POINT QAMATS QATAN
05C8..05CF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
05D0..05EA  ; PVALID      # HEBREW LETTER ALEF..HEBREW LETTER TAV
05EB..05EE  ; UNASSIGNED  # <RESERVED>..<RESERVED>
05EF..05F2  ; PVALID      # HEBREW YOD TRIANGLE..HEBREW LIGATURE YIDDISH
05F3..05F4  ; CONTEXTO    # HEBREW PUNCTUATION GERESH..HEBREW PUNCTUATIO
05F5..05FF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0600..0605  ; DISALLOWED  # ARABIC NUMBER SIGN..ARABIC NUMBER MARK ABOVE
0606..060F  ; FREE_PVAL   # ARABIC-INDIC CUBE ROOT..ARABIC SIGN MISRA
0610..061A  ; PVALID      # ARABIC SIGN SALLALLAHOU ALAYHE WASSALLAM..AR
061B        ; FREE_PVAL   # ARABIC SEMICOLON
061C        ; DISALLOWED  # ARABIC LETTER MARK
061D..061F  ; FREE_PVAL   # ARABIC END OF TEXT MARK..ARABIC QUESTION MAR
0620..063F  ; PVALID      # ARABIC LETTER KASHMIRI YEH..ARABIC LETTER FA
0640        ; DISALLOWED  # ARABIC TATWEEL
0641..065F  ; PVALID      # ARABIC LETTER FEH..ARABIC WAVY HAMZA BELOW
0660..0669  ; CONTEXTO    # ARABIC-INDIC DIGIT ZERO..ARABIC-INDIC DIGIT
066A..066D  ; FREE_PVAL   # ARABIC PERCENT SIGN..ARABIC FIVE POINTED STA
066E..0674  ; PVALID      # ARABIC LETTER DOTLESS BEH..ARABIC LETTER HIG
0675..0678  ; FREE_PVAL   # ARABIC LETTER HIGH HAMZA ALEF..ARABIC LETTER
0679..06D3  ; PVALID      # ARABIC LETTER TTEH..ARABIC LETTER YEH BARREE
06D4        ; FREE_PVAL   # ARABIC FULL STOP
06D5..06DC  ; PVALID      # ARABIC LETTER AE..ARABIC SMALL HIGH SEEN
06DD        ; DISALLOWED  # ARABIC END OF AYAH
06DE        ; FREE_PVAL   # ARABIC START OF RUB EL HIZB
06DF..06E8  ; PVALID      # ARABIC SMALL HIGH ROUNDED ZERO..ARABIC SMALL
06E9        ; FREE_PVAL   # ARABIC PLACE OF SAJDAH
06EA..06EF  ; PVALID      # ARABIC EMPTY CENTRE LOW STOP..ARABIC LETTER
06F0..06F9  ; CONTEXTO    # EXTENDED ARABIC-INDIC DIGIT ZERO..EXTENDED A
06FA..06FF  ; PVALID      # ARABIC LETTER SHEEN WITH DOT BELOW..ARABIC L
0700..070D  ; FREE_PVAL   # SYRIAC END OF PARAGRAPH..SYRIAC HARKLEAN AST
070E        ; UNASSIGNED  # <RESERVED>
070F        ; DISALLOWED  # SYRIAC ABBREVIATION MARK
0710..074A  ; PVALID      # SYRIAC LETTER ALAPH..SYRIAC BARREKH
074B..074C  ; UNASSIGNED  # <RESERVED>..<RESERVED>
074D..07B1  ; PVALID      # SYRIAC LETTER SOGDIAN ZHAIN..THAANA LETTER N
07B2..07BF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
07C0..07F5  ; PVALID      # NKO DIGIT ZERO..NKO LOW TONE APOSTROPHE
07F6..07F9  ; FREE_PVAL   # NKO SYMBOL OO DENNEN..NKO EXCLAMATION MARK
07FA        ; DISALLOWED  # NKO LAJANYALAN
07FB..07FC  ; UNASSIGNED  # <RESERVED>..<RESERVED>
07FD        ; PVALID      # NKO DANTAYALAN
07FE..07FF  ; FREE_PVAL   # NKO DOROME SIGN..NKO TAMAN SIGN
0800..082D  ; PVALID      # SAMARITAN LETTER ALAF..SAMARITAN MARK NEQUDA
082E..082F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0830..083E  ; FREE_PVAL   # SAMARITAN PUNCTUATION NEQUDAA..SAMARITAN PUN
083F        ; UNASSIGNED  # <RESERVED>
0840..085B  ; PVALID      # MANDAIC LETTER HALQA..MANDAIC GEMINATION MAR
085C..085D  ; UNASSIGNED  # <RESERVED>..<RESERVED>
085E        ; FREE_PVAL   # MANDAIC PUNCTUATION
085F        ; UNASSIGNED  # <RESERVED>
0860..086A  ; PVALID      # SYRIAC LETTER MALAYALAM NGA..SYRIAC LETTER M
086B..086F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0870..0887  ; PVALID      # ARABIC LETTER ALEF WITH ATTACHED FATHA..ARAB
0888        ; FREE_PVAL   # ARABIC RAISED ROUND DOT
0889..088E  ; PVALID      # ARABIC LETTER NOON WITH INVERTED SMALL V..AR
088F        ; UNASSIGNED  # <RESERVED>
0890..0891  ; DISALLOWED  # ARABIC POUND MARK ABOVE..ARABIC PIASTRE MARK
0892..0897  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0898..08E1  ; PVALID      # ARABIC SMALL HIGH WORD AL-JUZ..ARABIC SMALL
08E2        ; DISALLOWED  # ARABIC DISPUTED END OF AYAH
08E3..0957  ; PVALID      # ARABIC TURNED DAMMA BELOW..DEVANAGARI VOWEL
0958..095F  ; FREE_PVAL   # DEVANAGARI LETTER QA..DEVANAGARI LETTER YYA
0960..0963  ; PVALID      # DEVANAGARI LETTER VOCALIC RR..DEVANAGARI VOW
0964..0965  ; FREE_PVAL   # DEVANAGARI DANDA..DEVANAGARI DOUBLE DANDA
0966..096F  ; PVALID      # DEVANAGARI DIGIT ZERO..DEVANAGARI DIGIT NINE
0970        ; FREE_PVAL   # DEVANAGARI ABBREVIATION SIGN
0971..0983  ; PVALID      # DEVANAGARI SIGN HIGH SPACING DOT..BENGALI SI
0984        ; UNASSIGNED  # <RESERVED>
0985..098C  ; PVALID      # BENGALI LETTER A..BENGALI LETTER VOCALIC L
098D..098E  ; UNASSIGNED  # <RESERVED>..<RESERVED>
098F..0990  ; PVALID      # BENGALI LETTER E..BENGALI LETTER AI
0991..0992  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0993..09A8  ; PVALID      # BENGALI LETTER O..BENGALI LETTER NA
09A9        ; UNASSIGNED  # <RESERVED>
09AA..09B0  ; PVALID      # BENGALI LETTER PA..BENGALI LETTER RA
09B1        ; UNASSIGNED  # <RESERVED>
09B2        ; PVALID      # BENGALI LETTER LA
09B3..09B5  ; UNASSIGNED  # <RESERVED>..<RESERVED>
09B6..09B9  ; PVALID      # BENGALI LETTER SHA..BENGALI LETTER HA
09BA..09BB  ; UNASSIGNED  # <RESERVED>..<RESERVED>
09BC..09C4  ; PVALID      # BENGALI SIGN NUKTA..BENGALI VOWEL SIGN VOCAL
09C5..09C6  ; UNASSIGNED  # <RESERVED>..<RESERVED>
09C7..09C8  ; PVALID      # BENGALI VOWEL SIGN E..BENGALI VOWEL SIGN AI
09C9..09CA  ; UNASSIGNED  # <RESERVED>..<RESERVED>
09CB..09CE  ; PVALID      # BENGALI VOWEL SIGN O..BENGALI LETTER KHANDA
09CF..09D6  ; UNASSIGNED  # <RESERVED>..<RESERVED>
09D7        ; PVALID      # BENGALI AU LENGTH MARK
09D8..09DB  ; UNASSIGNED  # <RESERVED>..<RESERVED>
09DC..09DD  ; FREE_PVAL   # BENGALI LETTER RRA..BENGALI LETTER RHA
09DE        ; UNASSIGNED  # <RESERVED>
09DF        ; FREE_PVAL   # BENGALI LETTER YYA
09E0..09E3  ; PVALID      # BENGALI LETTER VOCALIC RR..BENGALI VOWEL SIG
09E4..09E5  ; UNASSIGNED  # <RESERVED>..<RESERVED>
09E6..09F1  ; PVALID      # BENGALI DIGIT ZERO..BENGALI LETTER RA WITH L
09F2..09FB  ; FREE_PVAL   # BENGALI RUPEE MARK..BENGALI GANDA MARK
09FC        ; PVALID      # BENGALI LETTER VEDIC ANUSVARA
09FD        ; FREE_PVAL   # BENGALI ABBREVIATION SIGN
09FE        ; PVALID      # BENGALI SANDHI MARK
09FF..0A00  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0A01..0A03  ; PVALID      # GURMUKHI SIGN ADAK BINDI..GURMUKHI SIGN VISA
0A04        ; UNASSIGNED  # <RESERVED>
0A05..0A0A  ; PVALID      # GURMUKHI LETTER A..GURMUKHI LETTER UU
0A0B..0A0E  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0A0F..0A10  ; PVALID      # GURMUKHI LETTER EE..GURMUKHI LETTER AI
0A11..0A12  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0A13..0A28  ; PVALID      # GURMUKHI LETTER OO..GURMUKHI LETTER NA
0A29        ; UNASSIGNED  # <RESERVED>
0A2A..0A30  ; PVALID      # GURMUKHI LETTER PA..GURMUKHI LETTER RA
0A31        ; UNASSIGNED  # <RESERVED>
0A32        ; PVALID      # GURMUKHI LETTER LA
0A33        ; FREE_PVAL   # GURMUKHI LETTER LLA
0A34        ; UNASSIGNED  # <RESERVED>
0A35        ; PVALID      # GURMUKHI LETTER VA
0A36        ; FREE_PVAL   # GURMUKHI LETTER SHA
0A37        ; UNASSIGNED  # <RESERVED>
0A38..0A39  ; PVALID      # GURMUKHI LETTER SA..GURMUKHI LETTER HA
0A3A..0A3B  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0A3C        ; PVALID      # GURMUKHI SIGN NUKTA
0A3D        ; UNASSIGNED  # <RESERVED>
0A3E..0A42  ; PVALID      # GURMUKHI VOWEL SIGN AA..GURMUKHI VOWEL SIGN
0A43..0A46  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0A47..0A48  ; PVALID      # GURMUKHI VOWEL SIGN EE..GURMUKHI VOWEL SIGN
0A49..0A4A  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0A4B..0A4D  ; PVALID      # GURMUKHI VOWEL SIGN OO..GURMUKHI SIGN VIRAMA
0A4E..0A50  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0A51        ; PVALID      # GURMUKHI SIGN UDAAT
0A52..0A58  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0A59..0A5B  ; FREE_PVAL   # GURMUKHI LETTER KHHA..GURMUKHI LETTER ZA
0A5C        ; PVALID      # GURMUKHI LETTER RRA
0A5D        ; UNASSIGNED  # <RESERVED>
0A5E        ; FREE_PVAL   # GURMUKHI LETTER FA
0A5F..0A65  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0A66..0A75  ; PVALID      # GURMUKHI DIGIT ZERO..GURMUKHI SIGN YAKASH
0A76        ; FREE_PVAL   # GURMUKHI ABBREVIATION SIGN
0A77..0A80  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0A81..0A83  ; PVALID      # GUJARATI SIGN CANDRABINDU..GUJARATI SIGN VIS
0A84        ; UNASSIGNED  # <RESERVED>
0A85..0A8D  ; PVALID      # GUJARATI LETTER A..GUJARATI VOWEL CANDRA E
0A8E        ; UNASSIGNED  # <RESERVED>
0A8F..0A91  ; PVALID      # GUJARATI LETTER E..GUJARATI VOWEL CANDRA O
0A92        ; UNASSIGNED  # <RESERVED>
0A93..0AA8  ; PVALID      # GUJARATI LETTER O..GUJARATI LETTER NA
0AA9        ; UNASSIGNED  # <RESERVED>
0AAA..0AB0  ; PVALID      # GUJARATI LETTER PA..GUJARATI LETTER RA
0AB1        ; UNASSIGNED  # <RESERVED>
0AB2..0AB3  ; PVALID      # GUJARATI LETTER LA..GUJARATI LETTER LLA
0AB4        ; UNASSIGNED  # <RESERVED>
0AB5..0AB9  ; PVALID      # GUJARATI LETTER VA..GUJARATI LETTER HA
0ABA..0ABB  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0ABC..0AC5  ; PVALID      # GUJARATI SIGN NUKTA..GUJARATI VOWEL SIGN CAN
0AC6        ; UNASSIGNED  # <RESERVED>
0AC7..0AC9  ; PVALID      # GUJARATI VOWEL SIGN E..GUJARATI VOWEL SIGN C
0ACA        ; UNASSIGNED  # <RESERVED>
0ACB..0ACD  ; PVALID      # GUJARATI VOWEL SIGN O..GUJARATI SIGN VIRAMA
0ACE..0ACF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0AD0        ; PVALID      # GUJARATI OM
0AD1..0ADF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0AE0..0AE3  ; PVALID      # GUJARATI LETTER VOCALIC RR..GUJARATI VOWEL S
0AE4..0AE5  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0AE6..0AEF  ; PVALID      # GUJARATI DIGIT ZERO..GUJARATI DIGIT NINE
0AF0..0AF1  ; FREE_PVAL   # GUJARATI ABBREVIATION SIGN..GUJARATI RUPEE S
0AF2..0AF8  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0AF9..0AFF  ; PVALID      # GUJARATI LETTER ZHA..GUJARATI SIGN TWO-CIRCL
0B00        ; UNASSIGNED  # <RESERVED>
0B01..0B03  ; PVALID      # ORIYA SIGN CANDRABINDU..ORIYA SIGN VISARGA
0B04        ; UNASSIGNED  # <RESERVED>
0B05..0B0C  ; PVALID      # ORIYA LETTER A..ORIYA LETTER VOCALIC L
0B0D..0B0E  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0B0F..0B10  ; PVALID      # ORIYA LETTER E..ORIYA LETTER AI
0B11..0B12  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0B13..0B28  ; PVALID      # ORIYA LETTER O..ORIYA LETTER NA
0B29        ; UNASSIGNED  # <RESERVED>
0B2A..0B30  ; PVALID      # ORIYA LETTER PA..ORIYA LETTER RA
0B31        ; UNASSIGNED  # <RESERVED>
0B32..0B33  ; PVALID      # ORIYA LETTER LA..ORIYA LETTER LLA
0B34        ; UNASSIGNED  # <RESERVED>
0B35..0B39  ; PVALID      # ORIYA LETTER VA..ORIYA LETTER HA
0B3A..0B3B  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0B3C..0B44  ; PVALID      # ORIYA SIGN NUKTA..ORIYA VOWEL SIGN VOCALIC R
0B45..0B46  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0B47..0B48  ; PVALID      # ORIYA VOWEL SIGN E..ORIYA VOWEL SIGN AI
0B49..0B4A  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0B4B..0B4D  ; PVALID      # ORIYA VOWEL SIGN O..ORIYA SIGN VIRAMA
0B4E..0B54  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0B55..0B57  ; PVALID      # ORIYA SIGN OVERLINE..ORIYA AU LENGTH MARK
0B58..0B5B  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0B5C..0B5D  ; FREE_PVAL   # ORIYA LETTER RRA..ORIYA LETTER RHA
0B5E        ; UNASSIGNED  # <RESERVED>
0B5F..0B63  ; PVALID      # ORIYA LETTER YYA..ORIYA VOWEL SIGN VOCALIC L
0B64..0B65  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0B66..0B6F  ; PVALID      # ORIYA DIGIT ZERO..ORIYA DIGIT NINE
0B70        ; FREE_PVAL   # ORIYA ISSHAR
0B71        ; PVALID      # ORIYA LETTER WA
0B72..0B77  ; FREE_PVAL   # ORIYA FRACTION ONE QUARTER..ORIYA FRACTION T
0B78..0B81  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0B82..0B83  ; PVALID      # TAMIL SIGN ANUSVARA..TAMIL SIGN VISARGA
0B84        ; UNASSIGNED  # <RESERVED>
0B85..0B8A  ; PVALID      # TAMIL LETTER A..TAMIL LETTER UU
0B8B..0B8D  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0B8E..0B90  ; PVALID      # TAMIL LETTER E..TAMIL LETTER AI
0B91        ; UNASSIGNED  # <RESERVED>
0B92..0B95  ; PVALID      # TAMIL LETTER O..TAMIL LETTER KA
0B96..0B98  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0B99..0B9A  ; PVALID      # TAMIL LETTER NGA..TAMIL LETTER CA
0B9B        ; UNASSIGNED  # <RESERVED>
0B9C        ; PVALID      # TAMIL LETTER JA
0B9D        ; UNASSIGNED  # <RESERVED>
0B9E..0B9F  ; PVALID      # TAMIL LETTER NYA..TAMIL LETTER TTA
0BA0..0BA2  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0BA3..0BA4  ; PVALID      # TAMIL LETTER NNA..TAMIL LETTER TA
0BA5..0BA7  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0BA8..0BAA  ; PVALID      # TAMIL LETTER NA..TAMIL LETTER PA
0BAB..0BAD  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0BAE..0BB9  ; PVALID      # TAMIL LETTER MA..TAMIL LETTER HA
0BBA..0BBD  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0BBE..0BC2  ; PVALID      # TAMIL VOWEL SIGN AA..TAMIL VOWEL SIGN UU
0BC3..0BC5  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0BC6..0BC8  ; PVALID      # TAMIL VOWEL SIGN E..TAMIL VOWEL SIGN AI
0BC9        ; UNASSIGNED  # <RESERVED>
0BCA..0BCD  ; PVALID      # TAMIL VOWEL SIGN O..TAMIL SIGN VIRAMA
0BCE..0BCF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0BD0        ; PVALID      # TAMIL OM
0BD1..0BD6  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0BD7        ; PVALID      # TAMIL AU LENGTH MARK
0BD8..0BE5  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0BE6..0BEF  ; PVALID      # TAMIL DIGIT ZERO..TAMIL DIGIT NINE
0BF0..0BFA  ; FREE_PVAL   # TAMIL NUMBER TEN..TAMIL NUMBER SIGN
0BFB..0BFF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0C00..0C0C  ; PVALID      # TELUGU SIGN COMBINING CANDRABINDU ABOVE..TEL
0C0D        ; UNASSIGNED  # <RESERVED>
0C0E..0C10  ; PVALID      # TELUGU LETTER E..TELUGU LETTER AI
0C11        ; UNASSIGNED  # <RESERVED>
0C12..0C28  ; PVALID      # TELUGU LETTER O..TELUGU LETTER NA
0C29        ; UNASSIGNED  # <RESERVED>
0C2A..0C39  ; PVALID      # TELUGU LETTER PA..TELUGU LETTER HA
0C3A..0C3B  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0C3C..0C44  ; PVALID      # TELUGU SIGN NUKTA..TELUGU VOWEL SIGN VOCALIC
0C45        ; UNASSIGNED  # <RESERVED>
0C46..0C48  ; PVALID      # TELUGU VOWEL SIGN E..TELUGU VOWEL SIGN AI
0C49        ; UNASSIGNED  # <RESERVED>
0C4A..0C4D  ; PVALID      # TELUGU VOWEL SIGN O..TELUGU SIGN VIRAMA
0C4E..0C54  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0C55..0C56  ; PVALID      # TELUGU LENGTH MARK..TELUGU AI LENGTH MARK
0C57        ; UNASSIGNED  # <RESERVED>
0C58..0C5A  ; PVALID      # TELUGU LETTER TSA..TELUGU LETTER RRRA
0C5B..0C5C  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0C5D        ; PVALID      # TELUGU LETTER NAKAARA POLLU
0C5E..0C5F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0C60..0C63  ; PVALID      # TELUGU LETTER VOCALIC RR..TELUGU VOWEL SIGN
0C64..0C65  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0C66..0C6F  ; PVALID      # TELUGU DIGIT ZERO..TELUGU DIGIT NINE
0C70..0C76  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0C77..0C7F  ; FREE_PVAL   # TELUGU SIGN SIDDHAM..TELUGU SIGN TUUMU
0C80..0C83  ; PVALID      # KANNADA SIGN SPACING CANDRABINDU..KANNADA SI
0C84        ; FREE_PVAL   # KANNADA SIGN SIDDHAM
0C85..0C8C  ; PVALID      # KANNADA LETTER A..KANNADA LETTER VOCALIC L
0C8D        ; UNASSIGNED  # <RESERVED>
0C8E..0C90  ; PVALID      # KANNADA LETTER E..KANNADA LETTER AI
0C91        ; UNASSIGNED  # <RESERVED>
0C92..0CA8  ; PVALID      # KANNADA LETTER O..KANNADA LETTER NA
0CA9        ; UNASSIGNED  # <RESERVED>
0CAA..0CB3  ; PVALID      # KANNADA LETTER PA..KANNADA LETTER LLA
0CB4        ; UNASSIGNED  # <RESERVED>
0CB5..0CB9  ; PVALID      # KANNADA LETTER VA..KANNADA LETTER HA
0CBA..0CBB  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0CBC..0CC4  ; PVALID      # KANNADA SIGN NUKTA..KANNADA VOWEL SIGN VOCAL
0CC5        ; UNASSIGNED  # <RESERVED>
0CC6..0CC8  ; PVALID      # KANNADA VOWEL SIGN E..KANNADA VOWEL SIGN AI
0CC9        ; UNASSIGNED  # <RESERVED>
0CCA..0CCD  ; PVALID      # KANNADA VOWEL SIGN O..KANNADA SIGN VIRAMA
0CCE..0CD4  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0CD5..0CD6  ; PVALID      # KANNADA LENGTH MARK..KANNADA AI LENGTH MARK
0CD7..0CDC  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0CDD..0CDE  ; PVALID      # KANNADA LETTER NAKAARA POLLU..KANNADA LETTER
0CDF        ; UNASSIGNED  # <RESERVED>
0CE0..0CE3  ; PVALID      # KANNADA LETTER VOCALIC RR..KANNADA VOWEL SIG
0CE4..0CE5  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0CE6..0CEF  ; PVALID      # KANNADA DIGIT ZERO..KANNADA DIGIT NINE
0CF0        ; UNASSIGNED  # <RESERVED>
0CF1..0CF2  ; PVALID      # KANNADA SIGN JIHVAMULIYA..KANNADA SIGN UPADH
0CF3..0CFF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0D00..0D0C  ; PVALID      # MALAYALAM SIGN COMBINING ANUSVARA ABOVE..MAL
0D0D        ; UNASSIGNED  # <RESERVED>
0D0E..0D10  ; PVALID      # MALAYALAM LETTER E..MALAYALAM LETTER AI
0D11        ; UNASSIGNED  # <RESERVED>
0D12..0D44  ; PVALID      # MALAYALAM LETTER O..MALAYALAM VOWEL SIGN VOC
0D45        ; UNASSIGNED  # <RESERVED>
0D46..0D48  ; PVALID      # MALAYALAM VOWEL SIGN E..MALAYALAM VOWEL SIGN
0D49        ; UNASSIGNED  # <RESERVED>
0D4A..0D4E  ; PVALID      # MALAYALAM VOWEL SIGN O..MALAYALAM LETTER DOT
0D4F        ; FREE_PVAL   # MALAYALAM SIGN PARA
0D50..0D53  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0D54..0D57  ; PVALID      # MALAYALAM LETTER CHILLU M..MALAYALAM AU LENG
0D58..0D5E  ; FREE_PVAL   # MALAYALAM FRACTION ONE ONE-HUNDRED-AND-SIXTI
0D5F..0D63  ; PVALID      # MALAYALAM LETTER ARCHAIC II..MALAYALAM VOWEL
0D64..0D65  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0D66..0D6F  ; PVALID      # MALAYALAM DIGIT ZERO..MALAYALAM DIGIT NINE
0D70..0D79  ; FREE_PVAL   # MALAYALAM NUMBER TEN..MALAYALAM DATE MARK
0D7A..0D7F  ; PVALID      # MALAYALAM LETTER CHILLU NN..MALAYALAM LETTER
0D80        ; UNASSIGNED  # <RESERVED>
0D81..0D83  ; PVALID      # SINHALA SIGN CANDRABINDU..SINHALA SIGN VISAR
0D84        ; UNASSIGNED  # <RESERVED>
0D85..0D96  ; PVALID      # SINHALA LETTER AYANNA..SINHALA LETTER AUYANN
0D97..0D99  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0D9A..0DB1  ; PVALID      # SINHALA LETTER ALPAPRAANA KAYANNA..SINHALA L
0DB2        ; UNASSIGNED  # <RESERVED>
0DB3..0DBB  ; PVALID      # SINHALA LETTER SANYAKA DAYANNA..SINHALA LETT
0DBC        ; UNASSIGNED  # <RESERVED>
0DBD        ; PVALID      # SINHALA LETTER DANTAJA LAYANNA
0DBE..0DBF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0DC0..0DC6  ; PVALID      # SINHALA LETTER VAYANNA..SINHALA LETTER FAYAN
0DC7..0DC9  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0DCA        ; PVALID      # SINHALA SIGN AL-LAKUNA
0DCB..0DCE  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0DCF..0DD4  ; PVALID      # SINHALA VOWEL SIGN AELA-PILLA..SINHALA VOWEL
0DD5        ; UNASSIGNED  # <RESERVED>
0DD6        ; PVALID      # SINHALA VOWEL SIGN DIGA PAA-PILLA
0DD7        ; UNASSIGNED  # <RESERVED>
0DD8..0DDF  ; PVALID      # SINHALA VOWEL SIGN GAETTA-PILLA..SINHALA VOW
0DE0..0DE5  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0DE6..0DEF  ; PVALID      # SINHALA LITH DIGIT ZERO..SINHALA LITH DIGIT
0DF0..0DF1  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0DF2..0DF3  ; PVALID      # SINHALA VOWEL SIGN DIGA GAETTA-PILLA..SINHAL
0DF4        ; FREE_PVAL   # SINHALA PUNCTUATION KUNDDALIYA
0DF5..0E00  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0E01..0E32  ; PVALID      # THAI CHARACTER KO KAI..THAI CHARACTER SARA A
0E33        ; FREE_PVAL   # THAI CHARACTER SARA AM
0E34..0E3A  ; PVALID      # THAI CHARACTER SARA I..THAI CHARACTER PHINTH
0E3B..0E3E  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0E3F        ; FREE_PVAL   # THAI CURRENCY SYMBOL BAHT
0E40..0E4E  ; PVALID      # THAI CHARACTER SARA E..THAI CHARACTER YAMAKK
0E4F        ; FREE_PVAL   # THAI CHARACTER FONGMAN
0E50..0E59  ; PVALID      # THAI DIGIT ZERO..THAI DIGIT NINE
0E5A..0E5B  ; FREE_PVAL   # THAI CHARACTER ANGKHANKHU..THAI CHARACTER KH
0E5C..0E80  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0E81..0E82  ; PVALID      # LAO LETTER KO..LAO LETTER KHO SUNG
0E83        ; UNASSIGNED  # <RESERVED>
0E84        ; PVALID      # LAO LETTER KHO TAM
0E85        ; UNASSIGNED  # <RESERVED>
0E86..0E8A  ; PVALID      # LAO LETTER PALI GHA..LAO LETTER SO TAM
0E8B        ; UNASSIGNED  # <RESERVED>
0E8C..0EA3  ; PVALID      # LAO LETTER PALI JHA..LAO LETTER LO LING
0EA4        ; UNASSIGNED  # <RESERVED>
0EA5        ; PVALID      # LAO LETTER LO LOOT
0EA6        ; UNASSIGNED  # <RESERVED>
0EA7..0EB2  ; PVALID      # LAO LETTER WO..LAO VOWEL SIGN AA
0EB3        ; FREE_PVAL   # LAO VOWEL SIGN AM
0EB4..0EBD  ; PVALID      # LAO VOWEL SIGN I..LAO SEMIVOWEL SIGN NYO
0EBE..0EBF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0EC0..0EC4  ; PVALID      # LAO VOWEL SIGN E..LAO VOWEL SIGN AI
0EC5        ; UNASSIGNED  # <RESERVED>
0EC6        ; PVALID      # LAO KO LA
0EC7        ; UNASSIGNED  # <RESERVED>
0EC8..0ECD  ; PVALID      # LAO TONE MAI EK..LAO NIGGAHITA
0ECE..0ECF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0ED0..0ED9  ; PVALID      # LAO DIGIT ZERO..LAO DIGIT NINE
0EDA..0EDB  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0EDC..0EDD  ; FREE_PVAL   # LAO HO NO..LAO HO MO
0EDE..0EDF  ; PVALID      # LAO LETTER KHMU GO..LAO LETTER KHMU NYO
0EE0..0EFF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0F00        ; PVALID      # TIBETAN SYLLABLE OM
0F01..0F0A  ; FREE_PVAL   # TIBETAN MARK GTER YIG MGO TRUNCATED A..TIBET
0F0B        ; PVALID      # TIBETAN MARK INTERSYLLABIC TSHEG
0F0C..0F17  ; FREE_PVAL   # TIBETAN MARK DELIMITER TSHEG BSTAR..TIBETAN
0F18..0F19  ; PVALID      # TIBETAN ASTROLOGICAL SIGN -KHYUD PA..TIBETAN
0F1A..0F1F  ; FREE_PVAL   # TIBETAN SIGN RDEL DKAR GCIG..TIBETAN SIGN RD
0F20..0F29  ; PVALID      # TIBETAN DIGIT ZERO..TIBETAN DIGIT NINE
0F2A..0F34  ; FREE_PVAL   # TIBETAN DIGIT HALF ONE..TIBETAN MARK BSDUS R
0F35        ; PVALID      # TIBETAN MARK NGAS BZUNG NYI ZLA
0F36        ; FREE_PVAL   # TIBETAN MARK CARET -DZUD RTAGS BZHI MIG CAN
0F37        ; PVALID      # TIBETAN MARK NGAS BZUNG SGOR RTAGS
0F38        ; FREE_PVAL   # TIBETAN MARK CHE MGO
0F39        ; PVALID      # TIBETAN MARK TSA -PHRU
0F3A..0F3D  ; FREE_PVAL   # TIBETAN MARK GUG RTAGS GYON..TIBETAN MARK AN
0F3E..0F42  ; PVALID      # TIBETAN SIGN YAR TSHES..TIBETAN LETTER GA
0F43        ; FREE_PVAL   # TIBETAN LETTER GHA
0F44..0F47  ; PVALID      # TIBETAN LETTER NGA..TIBETAN LETTER JA
0F48        ; UNASSIGNED  # <RESERVED>
0F49..0F4C  ; PVALID      # TIBETAN LETTER NYA..TIBETAN LETTER DDA
0F4D        ; FREE_PVAL   # TIBETAN LETTER DDHA
0F4E..0F51  ; PVALID      # TIBETAN LETTER NNA..TIBETAN LETTER DA
0F52        ; FREE_PVAL   # TIBETAN LETTER DHA
0F53..0F56  ; PVALID      # TIBETAN LETTER NA..TIBETAN LETTER BA
0F57        ; FREE_PVAL   # TIBETAN LETTER BHA
0F58..0F5B  ; PVALID      # TIBETAN LETTER MA..TIBETAN LETTER DZA
0F5C        ; FREE_PVAL   # TIBETAN LETTER DZHA
0F5D..0F68  ; PVALID      # TIBETAN LETTER WA..TIBETAN LETTER A
0F69        ; FREE_PVAL   # TIBETAN LETTER KSSA
0F6A..0F6C  ; PVALID      # TIBETAN LETTER FIXED-FORM RA..TIBETAN LETTER
0F6D..0F70  ; UNASSIGNED  # <RESERVED>..<RESERVED>
0F71..0F72  ; PVALID      # TIBETAN VOWEL SIGN AA..TIBETAN VOWEL SIGN I
0F73        ; FREE_PVAL   # TIBETAN VOWEL SIGN II
0F74        ; PVALID      # TIBETAN VOWEL SIGN U
0F75..0F79  ; FREE_PVAL   # TIBETAN VOWEL SIGN UU..TIBETAN VOWEL SIGN VO
0F7A..0F80  ; PVALID      # TIBETAN VOWEL SIGN E..TIBETAN VOWEL SIGN REV
0F81        ; FREE_PVAL   # TIBETAN VOWEL SIGN REVERSED II
0F82..0F84  ; PVALID      # TIBETAN SIGN NYI ZLA NAA DA..TIBETAN MARK HA
0F85        ; FREE_PVAL   # TIBETAN MARK PALUTA
0F86..0F92  ; PVALID      # TIBETAN SIGN LCI RTAGS..TIBETAN SUBJOINED LE
0F93        ; FREE_PVAL   # TIBETAN SUBJOINED LETTER GHA
0F94..0F97  ; PVALID      # TIBETAN SUBJOINED LETTER NGA..TIBETAN SUBJOI
0F98        ; UNASSIGNED  # <RESERVED>
0F99..0F9C  ; PVALID      # TIBETAN SUBJOINED LETTER NYA..TIBETAN SUBJOI
0F9D        ; FREE_PVAL   # TIBETAN SUBJOINED LETTER DDHA
0F9E..0FA1  ; PVALID      # TIBETAN SUBJOINED LETTER NNA..TIBETAN SUBJOI
0FA2        ; FREE_PVAL   # TIBETAN SUBJOINED LETTER DHA
0FA3..0FA6  ; PVALID      # TIBETAN SUBJOINED LETTER NA..TIBETAN SUBJOIN
0FA7        ; FREE_PVAL   # TIBETAN SUBJOINED LETTER BHA
0FA8..0FAB  ; PVALID      # TIBETAN SUBJOINED LETTER MA..TIBETAN SUBJOIN
0FAC        ; FREE_PVAL   # TIBETAN SUBJOINED LETTER DZHA
0FAD..0FB8  ; PVALID      # TIBETAN SUBJOINED LETTER WA..TIBETAN SUBJOIN
0FB9        ; FREE_PVAL   # TIBETAN SUBJOINED LETTER KSSA
0FBA..0FBC  ; PVALID      # TIBETAN SUBJOINED LETTER FIXED-FORM WA..TIBE
0FBD        ; UNASSIGNED  # <RESERVED>
0FBE..0FC5  ; FREE_PVAL   # TIBETAN KU RU KHA..TIBETAN SYMBOL RDO RJE
0FC6        ; PVALID      # TIBETAN SYMBOL PADMA GDAN
0FC7..0FCC  ; FREE_PVAL   # TIBETAN SYMBOL RDO RJE RGYA GRAM..TIBETAN SY
0FCD        ; UNASSIGNED  # <RESERVED>
0FCE..0FDA  ; FREE_PVAL   # TIBETAN SIGN RDEL NAG RDEL DKAR..TIBETAN MAR
0FDB..0FFF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1000..1049  ; PVALID      # MYANMAR LETTER KA..MYANMAR DIGIT NINE
104A..104F  ; FREE_PVAL   # MYANMAR SIGN LITTLE SECTION..MYANMAR SYMBOL
1050..109D  ; PVALID      # MYANMAR LETTER SHA..MYANMAR VOWEL SIGN AITON
109E..109F  ; FREE_PVAL   # MYANMAR SYMBOL SHAN ONE..MYANMAR SYMBOL SHAN
10A0..10C5  ; PVALID      # GEORGIAN CAPITAL LETTER AN..GEORGIAN CAPITAL
10C6        ; UNASSIGNED  # <RESERVED>
10C7        ; PVALID      # GEORGIAN CAPITAL LETTER YN
10C8..10CC  ; UNASSIGNED  # <RESERVED>..<RESERVED>
10CD        ; PVALID      # GEORGIAN CAPITAL LETTER AEN
10CE..10CF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
10D0..10FA  ; PVALID      # GEORGIAN LETTER AN..GEORGIAN LETTER AIN
10FB..10FC  ; FREE_PVAL   # GEORGIAN PARAGRAPH SEPARATOR..MODIFIER LETTE
10FD..10FF  ; PVALID      # GEORGIAN LETTER AEN..GEORGIAN LETTER LABIAL
1100..11FF  ; DISALLOWED  # HANGUL CHOSEONG KIYEOK..HANGUL JONGSEONG SSA
1200..1248  ; PVALID      # ETHIOPIC SYLLABLE HA..ETHIOPIC SYLLABLE QWA
1249        ; UNASSIGNED  # <RESERVED>
124A..124D  ; PVALID      # ETHIOPIC SYLLABLE QWI..ETHIOPIC SYLLABLE QWE
124E..124F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1250..1256  ; PVALID      # ETHIOPIC SYLLABLE QHA..ETHIOPIC SYLLABLE QHO
1257        ; UNASSIGNED  # <RESERVED>
1258        ; PVALID      # ETHIOPIC SYLLABLE QHWA
1259        ; UNASSIGNED  # <RESERVED>
125A..125D  ; PVALID      # ETHIOPIC SYLLABLE QHWI..ETHIOPIC SYLLABLE QH
125E..125F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1260..1288  ; PVALID      # ETHIOPIC SYLLABLE BA..ETHIOPIC SYLLABLE XWA
1289        ; UNASSIGNED  # <RESERVED>
128A..128D  ; PVALID      # ETHIOPIC SYLLABLE XWI..ETHIOPIC SYLLABLE XWE
128E..128F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1290..12B0  ; PVALID      # ETHIOPIC SYLLABLE NA..ETHIOPIC SYLLABLE KWA
12B1        ; UNASSIGNED  # <RESERVED>
12B2..12B5  ; PVALID      # ETHIOPIC SYLLABLE KWI..ETHIOPIC SYLLABLE KWE
12B6..12B7  ; UNASSIGNED  # <RESERVED>..<RESERVED>
12B8..12BE  ; PVALID      # ETHIOPIC SYLLABLE KXA..ETHIOPIC SYLLABLE KXO
12BF        ; UNASSIGNED  # <RESERVED>
12C0        ; PVALID      # ETHIOPIC SYLLABLE KXWA
12C1        ; UNASSIGNED  # <RESERVED>
12C2..12C5  ; PVALID      # ETHIOPIC SYLLABLE KXWI..ETHIOPIC SYLLABLE KX
12C6..12C7  ; UNASSIGNED  # <RESERVED>..<RESERVED>
12C8..12D6  ; PVALID      # ETHIOPIC SYLLABLE WA..ETHIOPIC SYLLABLE PHAR
12D7        ; UNASSIGNED  # <RESERVED>
12D8..1310  ; PVALID      # ETHIOPIC SYLLABLE ZA..ETHIOPIC SYLLABLE GWA
1311        ; UNASSIGNED  # <RESERVED>
1312..1315  ; PVALID      # ETHIOPIC SYLLABLE GWI..ETHIOPIC SYLLABLE GWE
1316..1317  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1318..135A  ; PVALID      # ETHIOPIC SYLLABLE GGA..ETHIOPIC SYLLABLE FYA
135B..135C  ; UNASSIGNED  # <RESERVED>..<RESERVED>
135D..135F  ; PVALID      # ETHIOPIC COMBINING GEMINATION AND VOWEL LENG
1360..137C  ; FREE_PVAL   # ETHIOPIC SECTION MARK..ETHIOPIC NUMBER TEN T
137D..137F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1380..138F  ; PVALID      # ETHIOPIC SYLLABLE SEBATBEIT MWA..ETHIOPIC SY
1390..1399  ; FREE_PVAL   # ETHIOPIC TONAL MARK YIZET..ETHIOPIC TONAL MA
139A..139F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
13A0..13F5  ; PVALID      # CHEROKEE LETTER A..CHEROKEE LETTER MV
13F6..13F7  ; UNASSIGNED  # <RESERVED>..<RESERVED>
13F8..13FD  ; PVALID      # CHEROKEE SMALL LETTER YE..CHEROKEE SMALL LET
13FE..13FF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1400        ; FREE_PVAL   # CANADIAN SYLLABICS HYPHEN
1401..166C  ; PVALID      # CANADIAN SYLLABICS E..CANADIAN SYLLABICS CAR
166D..166E  ; FREE_PVAL   # CANADIAN SYLLABICS CHI SIGN..CANADIAN SYLLAB
166F..167F  ; PVALID      # CANADIAN SYLLABICS QAI..CANADIAN SYLLABICS B
1680        ; FREE_PVAL   # OGHAM SPACE MARK
1681..169A  ; PVALID      # OGHAM LETTER BEITH..OGHAM LETTER PEITH
169B..169C  ; FREE_PVAL   # OGHAM FEATHER MARK..OGHAM REVERSED FEATHER M
169D..169F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
16A0..16EA  ; PVALID      # RUNIC LETTER FEHU FEOH FE F..RUNIC LETTER X
16EB..16F0  ; FREE_PVAL   # RUNIC SINGLE PUNCTUATION..RUNIC BELGTHOR SYM
16F1..16F8  ; PVALID      # RUNIC LETTER K..RUNIC LETTER FRANKS CASKET A
16F9..16FF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1700..1715  ; PVALID      # TAGALOG LETTER A..TAGALOG SIGN PAMUDPOD
1716..171E  ; UNASSIGNED  # <RESERVED>..<RESERVED>
171F..1734  ; PVALID      # TAGALOG LETTER ARCHAIC RA..HANUNOO SIGN PAMU
1735..1736  ; FREE_PVAL   # PHILIPPINE SINGLE PUNCTUATION..PHILIPPINE DO
1737..173F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1740..1753  ; PVALID      # BUHID LETTER A..BUHID VOWEL SIGN U
1754..175F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1760..176C  ; PVALID      # TAGBANWA LETTER A..TAGBANWA LETTER YA
176D        ; UNASSIGNED  # <RESERVED>
176E..1770  ; PVALID      # TAGBANWA LETTER LA..TAGBANWA LETTER SA
1771        ; UNASSIGNED  # <RESERVED>
1772..1773  ; PVALID      # TAGBANWA VOWEL SIGN I..TAGBANWA VOWEL SIGN U
1774..177F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1780..17B3  ; PVALID      # KHMER LETTER KA..KHMER INDEPENDENT VOWEL QAU
17B4..17B5  ; DISALLOWED  # KHMER VOWEL INHERENT AQ..KHMER VOWEL INHEREN
17B6..17D3  ; PVALID      # KHMER VOWEL SIGN AA..KHMER SIGN BATHAMASAT
17D4..17D6  ; FREE_PVAL   # KHMER SIGN KHAN..KHMER SIGN CAMNUC PII KUUH
17D7        ; PVALID      # KHMER SIGN LEK TOO
17D8..17DB  ; FREE_PVAL   # KHMER SIGN BEYYAL..KHMER CURRENCY SYMBOL RIE
17DC..17DD  ; PVALID      # KHMER SIGN AVAKRAHASANYA..KHMER SIGN ATTHACA
17DE..17DF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
17E0..17E9  ; PVALID      # KHMER DIGIT ZERO..KHMER DIGIT NINE
17EA..17EF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
17F0..17F9  ; FREE_PVAL   # KHMER SYMBOL LEK ATTAK SON..KHMER SYMBOL LEK
17FA..17FF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1800..180A  ; FREE_PVAL   # MONGOLIAN BIRGA..MONGOLIAN NIRUGU
180B..180F  ; DISALLOWED  # MONGOLIAN FREE VARIATION SELECTOR ONE..MONGO
1810..1819  ; PVALID      # MONGOLIAN DIGIT ZERO..MONGOLIAN DIGIT NINE
181A..181F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1820..1878  ; PVALID      # MONGOLIAN LETTER A..MONGOLIAN LETTER CHA WIT
1879..187F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1880..18AA  ; PVALID      # MONGOLIAN LETTER ALI GALI ANUSVARA ONE..MONG
18AB..18AF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
18B0..18F5  ; PVALID      # CANADIAN SYLLABICS OY..CANADIAN SYLLABICS CA
18F6..18FF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1900..191E  ; PVALID      # LIMBU VOWEL-CARRIER LETTER..LIMBU LETTER TRA
191F        ; UNASSIGNED  # <RESERVED>
1920..192B  ; PVALID      # LIMBU VOWEL SIGN A..LIMBU SUBJOINED LETTER W
192C..192F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1930..193B  ; PVALID      # LIMBU SMALL LETTER KA..LIMBU SIGN SA-I
193C..193F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1940        ; FREE_PVAL   # LIMBU SIGN LOO
1941..1943  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1944..1945  ; FREE_PVAL   # LIMBU EXCLAMATION MARK..LIMBU QUESTION MARK
1946..196D  ; PVALID      # LIMBU DIGIT ZERO..TAI LE LETTER AI
196E..196F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1970..1974  ; PVALID      # TAI LE LETTER TONE-2..TAI LE LETTER TONE-6
1975..197F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1980..19AB  ; PVALID      # NEW TAI LUE LETTER HIGH QA..NEW TAI LUE LETT
19AC..19AF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
19B0..19C9  ; PVALID      # NEW TAI LUE VOWEL SIGN VOWEL SHORTENER..NEW
19CA..19CF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
19D0..19D9  ; PVALID      # NEW TAI LUE DIGIT ZERO..NEW TAI LUE DIGIT NI
19DA        ; FREE_PVAL   # NEW TAI LUE THAM DIGIT ONE
19DB..19DD  ; UNASSIGNED  # <RESERVED>..<RESERVED>
19DE..19FF  ; FREE_PVAL   # NEW TAI LUE SIGN LAE..KHMER SYMBOL DAP-PRAM
1A00..1A1B  ; PVALID      # BUGINESE LETTER KA..BUGINESE VOWEL SIGN AE
1A1C..1A1D  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1A1E..1A1F  ; FREE_PVAL   # BUGINESE PALLAWA..BUGINESE END OF SECTION
1A20..1A5E  ; PVALID      # TAI THAM LETTER HIGH KA..TAI THAM CONSONANT
1A5F        ; UNASSIGNED  # <RESERVED>
1A60..1A7C  ; PVALID      # TAI THAM SIGN SAKOT..TAI THAM SIGN KHUEN-LUE
1A7D..1A7E  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1A7F..1A89  ; PVALID      # TAI THAM COMBINING CRYPTOGRAMMIC DOT..TAI TH
1A8A..1A8F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1A90..1A99  ; PVALID      # TAI THAM THAM DIGIT ZERO..TAI THAM THAM DIGI
1A9A..1A9F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1AA0..1AA6  ; FREE_PVAL   # TAI THAM SIGN WIANG..TAI THAM SIGN REVERSED
1AA7        ; PVALID      # TAI THAM SIGN MAI YAMOK
1AA8..1AAD  ; FREE_PVAL   # TAI THAM SIGN KAAN..TAI THAM SIGN CAANG
1AAE..1AAF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1AB0..1ABD  ; PVALID      # COMBINING DOUBLED CIRCUMFLEX ACCENT..COMBINI
1ABE        ; FREE_PVAL   # COMBINING PARENTHESES OVERLAY
1ABF..1ACE  ; PVALID      # COMBINING LATIN SMALL LETTER W BELOW..COMBIN
1ACF..1AFF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1B00..1B4C  ; PVALID      # BALINESE SIGN ULU RICEM..BALINESE LETTER ARC
1B4D..1B4F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1B50..1B59  ; PVALID      # BALINESE DIGIT ZERO..BALINESE DIGIT NINE
1B5A..1B6A  ; FREE_PVAL   # BALINESE PANTI..BALINESE MUSICAL SYMBOL DANG
1B6B..1B73  ; PVALID      # BALINESE MUSICAL SYMBOL COMBINING TEGEH..BAL
1B74..1B7E  ; FREE_PVAL   # BALINESE MUSICAL SYMBOL RIGHT-HAND OPEN DUG.
1B7F        ; UNASSIGNED  # <RESERVED>
1B80..1BF3  ; PVALID      # SUNDANESE SIGN PANYECEK..BATAK PANONGONAN
1BF4..1BFB  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1BFC..1BFF  ; FREE_PVAL   # BATAK SYMBOL BINDU NA METEK..BATAK SYMBOL BI
1C00..1C37  ; PVALID      # LEPCHA LETTER KA..LEPCHA SIGN NUKTA
1C38..1C3A  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1C3B..1C3F  ; FREE_PVAL   # LEPCHA PUNCTUATION TA-ROL..LEPCHA PUNCTUATIO
1C40..1C49  ; PVALID      # LEPCHA DIGIT ZERO..LEPCHA DIGIT NINE
1C4A..1C4C  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1C4D..1C7D  ; PVALID      # LEPCHA LETTER TTA..OL CHIKI AHAD
1C7E..1C7F  ; FREE_PVAL   # OL CHIKI PUNCTUATION MUCAAD..OL CHIKI PUNCTU
1C80..1C88  ; PVALID      # CYRILLIC SMALL LETTER ROUNDED VE..CYRILLIC S
1C89..1C8F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1C90..1CBA  ; PVALID      # GEORGIAN MTAVRULI CAPITAL LETTER AN..GEORGIA
1CBB..1CBC  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1CBD..1CBF  ; PVALID      # GEORGIAN MTAVRULI CAPITAL LETTER AEN..GEORGI
1CC0..1CC7  ; FREE_PVAL   # SUNDANESE PUNCTUATION BINDU SURYA..SUNDANESE
1CC8..1CCF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1CD0..1CD2  ; PVALID      # VEDIC TONE KARSHANA..VEDIC TONE PRENKHA
1CD3        ; FREE_PVAL   # VEDIC SIGN NIHSHVASA
1CD4..1CFA  ; PVALID      # VEDIC SIGN YAJURVEDIC MIDLINE SVARITA..VEDIC
1CFB..1CFF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1D00..1D2B  ; PVALID      # LATIN LETTER SMALL CAPITAL A..CYRILLIC LETTE
1D2C..1D2E  ; FREE_PVAL   # MODIFIER LETTER CAPITAL A..MODIFIER LETTER C
1D2F        ; PVALID      # MODIFIER LETTER CAPITAL BARRED B
1D30..1D3A  ; FREE_PVAL   # MODIFIER LETTER CAPITAL D..MODIFIER LETTER C
1D3B        ; PVALID      # MODIFIER LETTER CAPITAL REVERSED N
1D3C..1D4D  ; FREE_PVAL   # MODIFIER LETTER CAPITAL O..MODIFIER LETTER S
1D4E        ; PVALID      # MODIFIER LETTER SMALL TURNED I
1D4F..1D6A  ; FREE_PVAL   # MODIFIER LETTER SMALL K..GREEK SUBSCRIPT SMA
1D6B..1D77  ; PVALID      # LATIN SMALL LETTER UE..LATIN SMALL LETTER TU
1D78        ; FREE_PVAL   # MODIFIER LETTER CYRILLIC EN
1D79..1D9A  ; PVALID      # LATIN SMALL LETTER INSULAR G..LATIN SMALL LE
1D9B..1DBF  ; FREE_PVAL   # MODIFIER LETTER SMALL TURNED ALPHA..MODIFIER
1DC0..1E99  ; PVALID      # COMBINING DOTTED GRAVE ACCENT..LATIN SMALL L
1E9A..1E9B  ; FREE_PVAL   # LATIN SMALL LETTER A WITH RIGHT HALF RING..L
1E9C..1F15  ; PVALID      # LATIN SMALL LETTER LONG S WITH DIAGONAL STRO
1F16..1F17  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1F18..1F1D  ; PVALID      # GREEK CAPITAL LETTER EPSILON WITH PSILI..GRE
1F1E..1F1F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1F20..1F45  ; PVALID      # GREEK SMALL LETTER ETA WITH PSILI..GREEK SMA
1F46..1F47  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1F48..1F4D  ; PVALID      # GREEK CAPITAL LETTER OMICRON WITH PSILI..GRE
1F4E..1F4F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1F50..1F57  ; PVALID      # GREEK SMALL LETTER UPSILON WITH PSILI..GREEK
1F58        ; UNASSIGNED  # <RESERVED>
1F59        ; PVALID      # GREEK CAPITAL LETTER UPSILON WITH DASIA
1F5A        ; UNASSIGNED  # <RESERVED>
1F5B        ; PVALID      # GREEK CAPITAL LETTER UPSILON WITH DASIA AND
1F5C        ; UNASSIGNED  # <RESERVED>
1F5D        ; PVALID      # GREEK CAPITAL LETTER UPSILON WITH DASIA AND
1F5E        ; UNASSIGNED  # <RESERVED>
1F5F..1F70  ; PVALID      # GREEK CAPITAL LETTER UPSILON WITH DASIA AND
1F71        ; FREE_PVAL   # GREEK SMALL LETTER ALPHA WITH OXIA
1F72        ; PVALID      # GREEK SMALL LETTER EPSILON WITH VARIA
1F73        ; FREE_PVAL   # GREEK SMALL LETTER EPSILON WITH OXIA
1F74        ; PVALID      # GREEK SMALL LETTER ETA WITH VARIA
1F75        ; FREE_PVAL   # GREEK SMALL LETTER ETA WITH OXIA
1F76        ; PVALID      # GREEK SMALL LETTER IOTA WITH VARIA
1F77        ; FREE_PVAL   # GREEK SMALL LETTER IOTA WITH OXIA
1F78        ; PVALID      # GREEK SMALL LETTER OMICRON WITH VARIA
1F79        ; FREE_PVAL   # GREEK SMALL LETTER OMICRON WITH OXIA
1F7A        ; PVALID      # GREEK SMALL LETTER UPSILON WITH VARIA
1F7B        ; FREE_PVAL   # GREEK SMALL LETTER UPSILON WITH OXIA
1F7C        ; PVALID      # GREEK SMALL LETTER OMEGA WITH VARIA
1F7D        ; FREE_PVAL   # GREEK SMALL LETTER OMEGA WITH OXIA
1F7E..1F7F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1F80..1F87  ; PVALID      # GREEK SMALL LETTER ALPHA WITH PSILI AND YPOG
1F88..1F8F  ; FREE_PVAL   # GREEK CAPITAL LETTER ALPHA WITH PSILI AND PR
1F90..1F97  ; PVALID      # GREEK SMALL LETTER ETA WITH PSILI AND YPOGEG
1F98..1F9F  ; FREE_PVAL   # GREEK CAPITAL LETTER ETA WITH PSILI AND PROS
1FA0..1FA7  ; PVALID      # GREEK SMALL LETTER OMEGA WITH PSILI AND YPOG
1FA8..1FAF  ; FREE_PVAL   # GREEK CAPITAL LETTER OMEGA WITH PSILI AND PR
1FB0..1FB4  ; PVALID      # GREEK SMALL LETTER ALPHA WITH VRACHY..GREEK
1FB5        ; UNASSIGNED  # <RESERVED>
1FB6..1FBA  ; PVALID      # GREEK SMALL LETTER ALPHA WITH PERISPOMENI..G
1FBB..1FC1  ; FREE_PVAL   # GREEK CAPITAL LETTER ALPHA WITH OXIA..GREEK
1FC2..1FC4  ; PVALID      # GREEK SMALL LETTER ETA WITH VARIA AND YPOGEG
1FC5        ; UNASSIGNED  # <RESERVED>
1FC6..1FC8  ; PVALID      # GREEK SMALL LETTER ETA WITH PERISPOMENI..GRE
1FC9        ; FREE_PVAL   # GREEK CAPITAL LETTER EPSILON WITH OXIA
1FCA        ; PVALID      # GREEK CAPITAL LETTER ETA WITH VARIA
1FCB..1FCF  ; FREE_PVAL   # GREEK CAPITAL LETTER ETA WITH OXIA..GREEK PS
1FD0..1FD2  ; PVALID      # GREEK SMALL LETTER IOTA WITH VRACHY..GREEK S
1FD3        ; FREE_PVAL   # GREEK SMALL LETTER IOTA WITH DIALYTIKA AND O
1FD4..1FD5  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1FD6..1FDA  ; PVALID      # GREEK SMALL LETTER IOTA WITH PERISPOMENI..GR
1FDB        ; FREE_PVAL   # GREEK CAPITAL LETTER IOTA WITH OXIA
1FDC        ; UNASSIGNED  # <RESERVED>
1FDD..1FDF  ; FREE_PVAL   # GREEK DASIA AND VARIA..GREEK DASIA AND PERIS
1FE0..1FE2  ; PVALID      # GREEK SMALL LETTER UPSILON WITH VRACHY..GREE
1FE3        ; FREE_PVAL   # GREEK SMALL LETTER UPSILON WITH DIALYTIKA AN
1FE4..1FEA  ; PVALID      # GREEK SMALL LETTER RHO WITH PSILI..GREEK CAP
1FEB        ; FREE_PVAL   # GREEK CAPITAL LETTER UPSILON WITH OXIA
1FEC        ; PVALID      # GREEK CAPITAL LETTER RHO WITH DASIA
1FED..1FEF  ; FREE_PVAL   # GREEK DIALYTIKA AND VARIA..GREEK VARIA
1FF0..1FF1  ; UNASSIGNED  # <RESERVED>..<RESERVED>
1FF2..1FF4  ; PVALID      # GREEK SMALL LETTER OMEGA WITH VARIA AND YPOG
1FF5        ; UNASSIGNED  # <RESERVED>
1FF6..1FF8  ; PVALID      # GREEK SMALL LETTER OMEGA WITH PERISPOMENI..G
1FF9        ; FREE_PVAL   # GREEK CAPITAL LETTER OMICRON WITH OXIA
1FFA        ; PVALID      # GREEK CAPITAL LETTER OMEGA WITH VARIA
1FFB..1FFE  ; FREE_PVAL   # GREEK CAPITAL LETTER OMEGA WITH OXIA..GREEK
1FFF        ; UNASSIGNED  # <RESERVED>
2000..200A  ; FREE_PVAL   # EN QUAD..HAIR SPACE
200B        ; DISALLOWED  # ZERO WIDTH SPACE
200C..200D  ; CONTEXTJ    # ZERO WIDTH NON-JOINER..ZERO WIDTH JOINER
200E..200F  ; DISALLOWED  # LEFT-TO-RIGHT MARK..RIGHT-TO-LEFT MARK
2010..2027  ; FREE_PVAL   # HYPHEN..HYPHENATION POINT
2028..202E  ; DISALLOWED  # LINE SEPARATOR..RIGHT-TO-LEFT OVERRIDE
202F..205F  ; FREE_PVAL   # NARROW NO-BREAK SPACE..MEDIUM MATHEMATICAL S
2060..2064  ; DISALLOWED  # WORD JOINER..INVISIBLE PLUS
2065        ; UNASSIGNED  # <RESERVED>
2066..206F  ; DISALLOWED  # LEFT-TO-RIGHT ISOLATE..NOMINAL DIGIT SHAPES
2070..2071  ; FREE_PVAL   # SUPERSCRIPT ZERO..SUPERSCRIPT LATIN SMALL LE
2072..2073  ; UNASSIGNED  # <RESERVED>..<RESERVED>
2074..208E  ; FREE_PVAL   # SUPERSCRIPT FOUR..SUBSCRIPT RIGHT PARENTHESI
208F        ; UNASSIGNED  # <RESERVED>
2090..209C  ; FREE_PVAL   # LATIN SUBSCRIPT SMALL LETTER A..LATIN SUBSCR
209D..209F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
20A0..20C0  ; FREE_PVAL   # EURO-CURRENCY SIGN..SOM SIGN
20C1..20CF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
20D0..20DC  ; PVALID      # COMBINING LEFT HARPOON ABOVE..COMBINING FOUR
20DD..20E0  ; FREE_PVAL   # COMBINING ENCLOSING CIRCLE..COMBINING ENCLOS
20E1        ; PVALID      # COMBINING LEFT RIGHT ARROW ABOVE
20E2..20E4  ; FREE_PVAL   # COMBINING ENCLOSING SCREEN..COMBINING ENCLOS
20E5..20F0  ; PVALID      # COMBINING REVERSE SOLIDUS OVERLAY..COMBINING
20F1..20FF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
2100..2131  ; FREE_PVAL   # ACCOUNT OF..SCRIPT CAPITAL F
2132        ; PVALID      # TURNED CAPITAL F
2133..214D  ; FREE_PVAL   # SCRIPT CAPITAL M..AKTIESELSKAB
214E        ; PVALID      # TURNED SMALL F
214F..2182  ; FREE_PVAL   # SYMBOL FOR SAMARITAN SOURCE..ROMAN NUMERAL T
2183..2184  ; PVALID      # ROMAN NUMERAL REVERSED ONE HUNDRED..LATIN SM
2185..218B  ; FREE_PVAL   # ROMAN NUMERAL SIX LATE FORM..TURNED DIGIT TH
218C..218F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
2190..2426  ; FREE_PVAL   # LEFTWARDS ARROW..SYMBOL FOR SUBSTITUTE FORM
2427..243F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
2440..244A  ; FREE_PVAL   # OCR HOOK..OCR DOUBLE BACKSLASH
244B..245F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
2460..2B73  ; FREE_PVAL   # CIRCLED DIGIT ONE..DOWNWARDS TRIANGLE-HEADED
2B74..2B75  ; UNASSIGNED  # <RESERVED>..<RESERVED>
2B76..2B95  ; FREE_PVAL   # NORTH WEST TRIANGLE-HEADED ARROW TO BAR..RIG
2B96        ; UNASSIGNED  # <RESERVED>
2B97..2BFF  ; FREE_PVAL   # SYMBOL FOR TYPE A ELECTRONICS..HELLSCHREIBER
2C00..2C7B  ; PVALID      # GLAGOLITIC CAPITAL LETTER AZU..LATIN LETTER
2C7C..2C7D  ; FREE_PVAL   # LATIN SUBSCRIPT SMALL LETTER J..MODIFIER LET
2C7E..2CE4  ; PVALID      # LATIN CAPITAL LETTER S WITH SWASH TAIL..COPT
2CE5..2CEA  ; FREE_PVAL   # COPTIC SYMBOL MI RO..COPTIC SYMBOL SHIMA SIM
2CEB..2CF3  ; PVALID      # COPTIC CAPITAL LETTER CRYPTOGRAMMIC SHEI..CO
2CF4..2CF8  ; UNASSIGNED  # <RESERVED>..<RESERVED>
2CF9..2CFF  ; FREE_PVAL   # COPTIC OLD NUBIAN FULL STOP..COPTIC MORPHOLO
2D00..2D25  ; PVALID      # GEORGIAN SMALL LETTER AN..GEORGIAN SMALL LET
2D26        ; UNASSIGNED  # <RESERVED>
2D27        ; PVALID      # GEORGIAN SMALL LETTER YN
2D28..2D2C  ; UNASSIGNED  # <RESERVED>..<RESERVED>
2D2D        ; PVALID      # GEORGIAN SMALL LETTER AEN
2D2E..2D2F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
2D30..2D67  ; PVALID      # TIFINAGH LETTER YA..TIFINAGH LETTER YO
2D68..2D6E  ; UNASSIGNED  # <RESERVED>..<RESERVED>
2D6F..2D70  ; FREE_PVAL   # TIFINAGH MODIFIER LETTER LABIALIZATION MARK.
2D71..2D7E  ; UNASSIGNED  # <RESERVED>..<RESERVED>
2D7F..2D96  ; PVALID      # TIFINAGH CONSONANT JOINER..ETHIOPIC SYLLABLE
2D97..2D9F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
2DA0..2DA6  ; PVALID      # ETHIOPIC SYLLABLE SSA..ETHIOPIC SYLLABLE SSO
2DA7        ; UNASSIGNED  # <RESERVED>
2DA8..2DAE  ; PVALID      # ETHIOPIC SYLLABLE CCA..ETHIOPIC SYLLABLE CCO
2DAF        ; UNASSIGNED  # <RESERVED>
2DB0..2DB6  ; PVALID      # ETHIOPIC SYLLABLE ZZA..ETHIOPIC SYLLABLE ZZO
2DB7        ; UNASSIGNED  # <RESERVED>
2DB8..2DBE  ; PVALID      # ETHIOPIC SYLLABLE CCHA..ETHIOPIC SYLLABLE CC
2DBF        ; UNASSIGNED  # <RESERVED>
2DC0..2DC6  ; PVALID      # ETHIOPIC SYLLABLE QYA..ETHIOPIC SYLLABLE QYO
2DC7        ; UNASSIGNED  # <RESERVED>
2DC8..2DCE  ; PVALID      # ETHIOPIC SYLLABLE KYA..ETHIOPIC SYLLABLE KYO
2DCF        ; UNASSIGNED  # <RESERVED>
2DD0..2DD6  ; PVALID      # ETHIOPIC SYLLABLE XYA..ETHIOPIC SYLLABLE XYO
2DD7        ; UNASSIGNED  # <RESERVED>
2DD8..2DDE  ; PVALID      # ETHIOPIC SYLLABLE GYA..ETHIOPIC SYLLABLE GYO
2DDF        ; UNASSIGNED  # <RESERVED>
2DE0..2DFF  ; PVALID      # COMBINING CYRILLIC LETTER BE..COMBINING CYRI
2E00..2E2E  ; FREE_PVAL   # RIGHT ANGLE SUBSTITUTION MARKER..REVERSED QU
2E2F        ; PVALID      # VERTICAL TILDE
2E30..2E5D  ; FREE_PVAL   # RING POINT..OBLIQUE HYPHEN
2E5E..2E7F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
2E80..2E99  ; FREE_PVAL   # CJK RADICAL REPEAT..CJK RADICAL RAP
2E9A        ; UNASSIGNED  # <RESERVED>
2E9B..2EF3  ; FREE_PVAL   # CJK RADICAL CHOKE..CJK RADICAL C-SIMPLIFIED
2EF4..2EFF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
2F00..2FD5  ; FREE_PVAL   # KANGXI RADICAL ONE..KANGXI RADICAL FLUTE
2FD6..2FEF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
2FF0..2FFB  ; FREE_PVAL   # IDEOGRAPHIC DESCRIPTION CHARACTER LEFT TO RI
2FFC..2FFF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
3000..3004  ; FREE_PVAL   # IDEOGRAPHIC SPACE..JAPANESE INDUSTRIAL STAND
3005..3007  ; PVALID      # IDEOGRAPHIC ITERATION MARK..IDEOGRAPHIC NUMB
3008..3029  ; FREE_PVAL   # LEFT ANGLE BRACKET..HANGZHOU NUMERAL NINE
302A..302D  ; PVALID      # IDEOGRAPHIC LEVEL TONE MARK..IDEOGRAPHIC ENT
302E..302F  ; DISALLOWED  # HANGUL SINGLE DOT TONE MARK..HANGUL DOUBLE D
3030        ; FREE_PVAL   # WAVY DASH
3031..3035  ; DISALLOWED  # VERTICAL KANA REPEAT MARK..VERTICAL KANA REP
3036..303A  ; FREE_PVAL   # CIRCLED POSTAL MARK..HANGZHOU NUMERAL THIRTY
303B        ; DISALLOWED  # VERTICAL IDEOGRAPHIC ITERATION MARK
303C        ; PVALID      # MASU MARK
303D..303F  ; FREE_PVAL   # PART ALTERNATION MARK..IDEOGRAPHIC HALF FILL
3040        ; UNASSIGNED  # <RESERVED>
3041..3096  ; PVALID      # HIRAGANA LETTER SMALL A..HIRAGANA LETTER SMA
3097..3098  ; UNASSIGNED  # <RESERVED>..<RESERVED>
3099..309A  ; PVALID      # COMBINING KATAKANA-HIRAGANA VOICED SOUND MAR
309B..309C  ; FREE_PVAL   # KATAKANA-HIRAGANA VOICED SOUND MARK..KATAKAN
309D..309E  ; PVALID      # HIRAGANA ITERATION MARK..HIRAGANA VOICED ITE
309F..30A0  ; FREE_PVAL   # HIRAGANA DIGRAPH YORI..KATAKANA-HIRAGANA DOU
30A1..30FA  ; PVALID      # KATAKANA LETTER SMALL A..KATAKANA LETTER VO
30FB        ; CONTEXTO    # KATAKANA MIDDLE DOT
30FC..30FE  ; PVALID      # KATAKANA-HIRAGANA PROLONGED SOUND MARK..KATA
30FF        ; FREE_PVAL   # KATAKANA DIGRAPH KOTO
3100..3104  ; UNASSIGNED  # <RESERVED>..<RESERVED>
3105..312F  ; PVALID      # BOPOMOFO LETTER B..BOPOMOFO LETTER NN
3130        ; UNASSIGNED  # <RESERVED>
3131..3163  ; FREE_PVAL   # HANGUL LETTER KIYEOK..HANGUL LETTER I
3164        ; DISALLOWED  # HANGUL FILLER
3165..318E  ; FREE_PVAL   # HANGUL LETTER SSANGNIEUN..HANGUL LETTER ARAE
318F        ; UNASSIGNED  # <RESERVED>
3190..319F  ; FREE_PVAL   # IDEOGRAPHIC ANNOTATION LINKING MARK..IDEOGRA
31A0..31BF  ; PVALID      # BOPOMOFO LETTER BU..BOPOMOFO LETTER AH
31C0..31E3  ; FREE_PVAL   # CJK STROKE T..CJK STROKE Q
31E4..31EF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
31F0..31FF  ; PVALID      # KATAKANA LETTER SMALL KU..KATAKANA LETTER SM
3200..321E  ; FREE_PVAL   # PARENTHESIZED HANGUL KIYEOK..PARENTHESIZED K
321F        ; UNASSIGNED  # <RESERVED>
3220..33FF  ; FREE_PVAL   # PARENTHESIZED IDEOGRAPH ONE..SQUARE GAL
3400..4DBF  ; PVALID      # <CJK Ideograph Extension A>..<CJK Ideograph
4DC0..4DFF  ; FREE_PVAL   # HEXAGRAM FOR THE CREATIVE HEAVEN..HEXAGRAM F
4E00..A48C  ; PVALID      # <CJK Ideograph>..YI SYLLABLE YYR
A48D..A48F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
A490..A4C6  ; FREE_PVAL   # YI RADICAL QOT..YI RADICAL KE
A4C7..A4CF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
A4D0..A4FD  ; PVALID      # LISU LETTER BA..LISU LETTER TONE MYA JEU
A4FE..A4FF  ; FREE_PVAL   # LISU PUNCTUATION COMMA..LISU PUNCTUATION FUL
A500..A60C  ; PVALID      # VAI SYLLABLE EE..VAI SYLLABLE LENGTHENER
A60D..A60F  ; FREE_PVAL   # VAI COMMA..VAI QUESTION MARK
A610..A62B  ; PVALID      # VAI SYLLABLE NDOLE FA..VAI SYLLABLE NDOLE DO
A62C..A63F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
A640..A66F  ; PVALID      # CYRILLIC CAPITAL LETTER ZEMLYA..COMBINING CY
A670..A673  ; FREE_PVAL   # COMBINING CYRILLIC TEN MILLIONS SIGN..SLAVON
A674..A67D  ; PVALID      # COMBINING CYRILLIC LETTER UKRAINIAN IE..COMB
A67E        ; FREE_PVAL   # CYRILLIC KAVYKA
A67F..A69B  ; PVALID      # CYRILLIC PAYEROK..CYRILLIC SMALL LETTER CROS
A69C..A69D  ; FREE_PVAL   # MODIFIER LETTER CYRILLIC HARD SIGN..MODIFIER
A69E..A6E5  ; PVALID      # COMBINING CYRILLIC LETTER EF..BAMUM LETTER K
A6E6..A6EF  ; FREE_PVAL   # BAMUM LETTER MO..BAMUM LETTER KOGHOM
A6F0..A6F1  ; PVALID      # BAMUM COMBINING MARK KOQNDON..BAMUM COMBININ
A6F2..A6F7  ; FREE_PVAL   # BAMUM NJAEMLI..BAMUM QUESTION MARK
A6F8..A6FF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
A700..A716  ; FREE_PVAL   # MODIFIER LETTER CHINESE TONE YIN PING..MODIF
A717..A71F  ; PVALID      # MODIFIER LETTER DOT VERTICAL BAR..MODIFIER L
A720..A721  ; FREE_PVAL   # MODIFIER LETTER STRESS AND HIGH TONE..MODIFI
A722..A76F  ; PVALID      # LATIN CAPITAL LETTER EGYPTOLOGICAL ALEF..LAT
A770        ; FREE_PVAL   # MODIFIER LETTER US
A771..A788  ; PVALID      # LATIN SMALL LETTER DUM..MODIFIER LETTER LOW
A789..A78A  ; FREE_PVAL   # MODIFIER LETTER COLON..MODIFIER LETTER SHORT
A78B..A7CA  ; PVALID      # LATIN CAPITAL LETTER SALTILLO..LATIN SMALL L
A7CB..A7CF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
A7D0..A7D1  ; PVALID      # LATIN CAPITAL LETTER CLOSED INSULAR G..LATIN
A7D2        ; UNASSIGNED  # <RESERVED>
A7D3        ; PVALID      # LATIN SMALL LETTER DOUBLE THORN
A7D4        ; UNASSIGNED  # <RESERVED>
A7D5..A7D9  ; PVALID      # LATIN SMALL LETTER DOUBLE WYNN..LATIN SMALL
A7DA..A7F1  ; UNASSIGNED  # <RESERVED>..<RESERVED>
A7F2..A7F4  ; FREE_PVAL   # MODIFIER LETTER CAPITAL C..MODIFIER LETTER C
A7F5..A7F7  ; PVALID      # LATIN CAPITAL LETTER REVERSED HALF H..LATIN
A7F8..A7F9  ; FREE_PVAL   # MODIFIER LETTER CAPITAL H WITH STROKE..MODIF
A7FA..A827  ; PVALID      # LATIN LETTER SMALL CAPITAL TURNED M..SYLOTI
A828..A82B  ; FREE_PVAL   # SYLOTI NAGRI POETRY MARK-1..SYLOTI NAGRI POE
A82C        ; PVALID      # SYLOTI NAGRI SIGN ALTERNATE HASANTA
A82D..A82F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
A830..A839  ; FREE_PVAL   # NORTH INDIC FRACTION ONE QUARTER..NORTH INDI
A83A..A83F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
A840..A873  ; PVALID      # PHAGS-PA LETTER KA..PHAGS-PA LETTER CANDRABI
A874..A877  ; FREE_PVAL   # PHAGS-PA SINGLE HEAD MARK..PHAGS-PA MARK DOU
A878..A87F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
A880..A8C5  ; PVALID      # SAURASHTRA SIGN ANUSVARA..SAURASHTRA SIGN CA
A8C6..A8CD  ; UNASSIGNED  # <RESERVED>..<RESERVED>
A8CE..A8CF  ; FREE_PVAL   # SAURASHTRA DANDA..SAURASHTRA DOUBLE DANDA
A8D0..A8D9  ; PVALID      # SAURASHTRA DIGIT ZERO..SAURASHTRA DIGIT NINE
A8DA..A8DF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
A8E0..A8F7  ; PVALID      # COMBINING DEVANAGARI DIGIT ZERO..DEVANAGARI
A8F8..A8FA  ; FREE_PVAL   # DEVANAGARI SIGN PUSHPIKA..DEVANAGARI CARET
A8FB        ; PVALID      # DEVANAGARI HEADSTROKE
A8FC        ; FREE_PVAL   # DEVANAGARI SIGN SIDDHAM
A8FD..A92D  ; PVALID      # DEVANAGARI JAIN OM..KAYAH LI TONE CALYA PLOP
A92E..A92F  ; FREE_PVAL   # KAYAH LI SIGN CWI..KAYAH LI SIGN SHYA
A930..A953  ; PVALID      # REJANG LETTER KA..REJANG VIRAMA
A954..A95E  ; UNASSIGNED  # <RESERVED>..<RESERVED>
A95F        ; FREE_PVAL   # REJANG SECTION MARK
A960..A97C  ; DISALLOWED  # HANGUL CHOSEONG TIKEUT-MIEUM..HANGUL CHOSEON
A97D..A97F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
A980..A9C0  ; PVALID      # JAVANESE SIGN PANYANGGA..JAVANESE PANGKON
A9C1..A9CD  ; FREE_PVAL   # JAVANESE LEFT RERENGGAN..JAVANESE TURNED PAD
A9CE        ; UNASSIGNED  # <RESERVED>
A9CF..A9D9  ; PVALID      # JAVANESE PANGRANGKEP..JAVANESE DIGIT NINE
A9DA..A9DD  ; UNASSIGNED  # <RESERVED>..<RESERVED>
A9DE..A9DF  ; FREE_PVAL   # JAVANESE PADA TIRTA TUMETES..JAVANESE PADA I
A9E0..A9FE  ; PVALID      # MYANMAR LETTER SHAN GHA..MYANMAR LETTER TAI
A9FF        ; UNASSIGNED  # <RESERVED>
AA00..AA36  ; PVALID      # CHAM LETTER A..CHAM CONSONANT SIGN WA
AA37..AA3F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
AA40..AA4D  ; PVALID      # CHAM LETTER FINAL K..CHAM CONSONANT SIGN FIN
AA4E..AA4F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
AA50..AA59  ; PVALID      # CHAM DIGIT ZERO..CHAM DIGIT NINE
AA5A..AA5B  ; UNASSIGNED  # <RESERVED>..<RESERVED>
AA5C..AA5F  ; FREE_PVAL   # CHAM PUNCTUATION SPIRAL..CHAM PUNCTUATION TR
AA60..AA76  ; PVALID      # MYANMAR LETTER KHAMTI GA..MYANMAR LOGOGRAM K
AA77..AA79  ; FREE_PVAL   # MYANMAR SYMBOL AITON EXCLAMATION..MYANMAR SY
AA7A..AAC2  ; PVALID      # MYANMAR LETTER AITON RA..TAI VIET TONE MAI S
AAC3..AADA  ; UNASSIGNED  # <RESERVED>..<RESERVED>
AADB..AADD  ; PVALID      # TAI VIET SYMBOL KON..TAI VIET SYMBOL SAM
AADE..AADF  ; FREE_PVAL   # TAI VIET SYMBOL HO HOI..TAI VIET SYMBOL KOI
AAE0..AAEF  ; PVALID      # MEETEI MAYEK LETTER E..MEETEI MAYEK VOWEL SI
AAF0..AAF1  ; FREE_PVAL   # MEETEI MAYEK CHEIKHAN..MEETEI MAYEK AHANG KH
AAF2..AAF6  ; PVALID      # MEETEI MAYEK ANJI..MEETEI MAYEK VIRAMA
AAF7..AB00  ; UNASSIGNED  # <RESERVED>..<RESERVED>
AB01..AB06  ; PVALID      # ETHIOPIC SYLLABLE TTHU..ETHIOPIC SYLLABLE TT
AB07..AB08  ; UNASSIGNED  # <RESERVED>..<RESERVED>
AB09..AB0E  ; PVALID      # ETHIOPIC SYLLABLE DDHU..ETHIOPIC SYLLABLE DD
AB0F..AB10  ; UNASSIGNED  # <RESERVED>..<RESERVED>
AB11..AB16  ; PVALID      # ETHIOPIC SYLLABLE DZU..ETHIOPIC SYLLABLE DZO
AB17..AB1F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
AB20..AB26  ; PVALID      # ETHIOPIC SYLLABLE CCHHA..ETHIOPIC SYLLABLE C
AB27        ; UNASSIGNED  # <RESERVED>
AB28..AB2E  ; PVALID      # ETHIOPIC SYLLABLE BBA..ETHIOPIC SYLLABLE BBO
AB2F        ; UNASSIGNED  # <RESERVED>
AB30..AB5A  ; PVALID      # LATIN SMALL LETTER BARRED ALPHA..LATIN SMALL
AB5B..AB5F  ; FREE_PVAL   # MODIFIER BREVE WITH INVERTED BREVE..MODIFIER
AB60..AB68  ; PVALID      # LATIN SMALL LETTER SAKHA YAT..LATIN SMALL LE
AB69..AB6B  ; FREE_PVAL   # MODIFIER LETTER SMALL TURNED W..MODIFIER LET
AB6C..AB6F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
AB70..ABEA  ; PVALID      # CHEROKEE SMALL LETTER A..MEETEI MAYEK VOWEL
ABEB        ; FREE_PVAL   # MEETEI MAYEK CHEIKHEI
ABEC..ABED  ; PVALID      # MEETEI MAYEK LUM IYEK..MEETEI MAYEK APUN IYE
ABEE..ABEF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
ABF0..ABF9  ; PVALID      # MEETEI MAYEK DIGIT ZERO..MEETEI MAYEK DIGIT
ABFA..ABFF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
AC00..D7A3  ; PVALID      # <Hangul Syllable>..<Hangul Syllable>
D7A4..D7AF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
D7B0..D7C6  ; DISALLOWED  # HANGUL JUNGSEONG O-YEO..HANGUL JUNGSEONG ARA
D7C7..D7CA  ; UNASSIGNED  # <RESERVED>..<RESERVED>
D7CB..D7FB  ; DISALLOWED  # HANGUL JONGSEONG NIEUN-RIEUL..HANGUL JONGSEO
D7FC..D7FF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
D800..F8FF  ; DISALLOWED  # <Non Private Use High Surrogate>..<Private U
F900..FA0D  ; FREE_PVAL   # CJK COMPATIBILITY IDEOGRAPH-F900..CJK COMPAT
FA0E..FA0F  ; PVALID      # CJK COMPATIBILITY IDEOGRAPH-FA0E..CJK COMPAT
FA10        ; FREE_PVAL   # CJK COMPATIBILITY IDEOGRAPH-FA10
FA11        ; PVALID      # CJK COMPATIBILITY IDEOGRAPH-FA11
FA12        ; FREE_PVAL   # CJK COMPATIBILITY IDEOGRAPH-FA12
FA13..FA14  ; PVALID      # CJK COMPATIBILITY IDEOGRAPH-FA13..CJK COMPAT
FA15..FA1E  ; FREE_PVAL   # CJK COMPATIBILITY IDEOGRAPH-FA15..CJK COMPAT
FA1F        ; PVALID      # CJK COMPATIBILITY IDEOGRAPH-FA1F
FA20        ; FREE_PVAL   # CJK COMPATIBILITY IDEOGRAPH-FA20
FA21        ; PVALID      # CJK COMPATIBILITY IDEOGRAPH-FA21
FA22        ; FREE_PVAL   # CJK COMPATIBILITY IDEOGRAPH-FA22
FA23..FA24  ; PVALID      # CJK COMPATIBILITY IDEOGRAPH-FA23..CJK COMPAT
FA25..FA26  ; FREE_PVAL   # CJK COMPATIBILITY IDEOGRAPH-FA25..CJK COMPAT
FA27..FA29  ; PVALID      # CJK COMPATIBILITY IDEOGRAPH-FA27..CJK COMPAT
FA2A..FA6D  ; FREE_PVAL   # CJK COMPATIBILITY IDEOGRAPH-FA2A..CJK COMPAT
FA6E..FA6F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
FA70..FAD9  ; FREE_PVAL   # CJK COMPATIBILITY IDEOGRAPH-FA70..CJK COMPAT
FADA..FAFF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
FB00..FB06  ; FREE_PVAL   # LATIN SMALL LIGATURE FF..LATIN SMALL LIGATUR
FB07..FB12  ; UNASSIGNED  # <RESERVED>..<RESERVED>
FB13..FB17  ; FREE_PVAL   # ARMENIAN SMALL LIGATURE MEN NOW..ARMENIAN SM
FB18..FB1C  ; UNASSIGNED  # <RESERVED>..<RESERVED>
FB1D        ; FREE_PVAL   # HEBREW LETTER YOD WITH HIRIQ
FB1E        ; PVALID      # HEBREW POINT JUDEO-SPANISH VARIKA
FB1F..FB36  ; FREE_PVAL   # HEBREW LIGATURE YIDDISH YOD YOD PATAH..HEBRE
FB37        ; UNASSIGNED  # <RESERVED>
FB38..FB3C  ; FREE_PVAL   # HEBREW LETTER TET WITH DAGESH..HEBREW LETTER
FB3D        ; UNASSIGNED  # <RESERVED>
FB3E        ; FREE_PVAL   # HEBREW LETTER MEM WITH DAGESH
FB3F        ; UNASSIGNED  # <RESERVED>
FB40..FB41  ; FREE_PVAL   # HEBREW LETTER NUN WITH DAGESH..HEBREW LETTER
FB42        ; UNASSIGNED  # <RESERVED>
FB43..FB44  ; FREE_PVAL   # HEBREW LETTER FINAL PE WITH DAGESH..HEBREW L
FB45        ; UNASSIGNED  # <RESERVED>
FB46..FBC2  ; FREE_PVAL   # HEBREW LETTER TSADI WITH DAGESH..ARABIC SYMB
FBC3..FBD2  ; UNASSIGNED  # <RESERVED>..<RESERVED>
FBD3..FD8F  ; FREE_PVAL   # ARABIC LETTER NG ISOLATED FORM..ARABIC LIGAT
FD90..FD91  ; UNASSIGNED  # <RESERVED>..<RESERVED>
FD92..FDC7  ; FREE_PVAL   # ARABIC LIGATURE MEEM WITH JEEM WITH KHAH INI
FDC8..FDCE  ; UNASSIGNED  # <RESERVED>..<RESERVED>
FDCF        ; FREE_PVAL   # ARABIC LIGATURE SALAAMUHU ALAYNAA
FDD0..FDEF  ; DISALLOWED  # <NOT A CHARACTER>..<NOT A CHARACTER>
FDF0..FDFF  ; FREE_PVAL   # ARABIC LIGATURE SALLA USED AS KORANIC STOP S
FE00..FE0F  ; DISALLOWED  # VARIATION SELECTOR-1..VARIATION SELECTOR-16
FE10..FE19  ; FREE_PVAL   # PRESENTATION FORM FOR VERTICAL COMMA..PRESEN
FE1A..FE1F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
FE20..FE2F  ; PVALID      # COMBINING LIGATURE LEFT HALF..COMBINING CYRI
FE30..FE52  ; FREE_PVAL   # PRESENTATION FORM FOR VERTICAL TWO DOT LEADE
FE53        ; UNASSIGNED  # <RESERVED>
FE54..FE66  ; FREE_PVAL   # SMALL SEMICOLON..SMALL EQUALS SIGN
FE67        ; UNASSIGNED  # <RESERVED>
FE68..FE6B  ; FREE_PVAL   # SMALL REVERSE SOLIDUS..SMALL COMMERCIAL AT
FE6C..FE6F  ; UNASSIGNED  # <RESERVED>..<RESERVED>
FE70..FE72  ; FREE_PVAL   # ARABIC FATHATAN ISOLATED FORM..ARABIC DAMMAT
FE73        ; PVALID      # ARABIC TAIL FRAGMENT
FE74        ; FREE_PVAL   # ARABIC KASRATAN ISOLATED FORM
FE75        ; UNASSIGNED  # <RESERVED>
FE76..FEFC  ; FREE_PVAL   # ARABIC FATHA ISOLATED FORM..ARABIC LIGATURE
FEFD..FEFE  ; UNASSIGNED  # <RESERVED>..<RESERVED>
FEFF        ; DISALLOWED  # ZERO WIDTH NO-BREAK SPACE
FF00        ; UNASSIGNED  # <RESERVED>
FF01..FF9F  ; FREE_PVAL   # FULLWIDTH EXCLAMATION MARK..HALFWIDTH KATAKA
FFA0        ; DISALLOWED  # HALFWIDTH HANGUL FILLER
FFA1..FFBE  ; FREE_PVAL   # HALFWIDTH HANGUL LETTER KIYEOK..HALFWIDTH HA
FFBF..FFC1  ; UNASSIGNED  # <RESERVED>..<RESERVED>
FFC2..FFC7  ; FREE_PVAL   # HALFWIDTH HANGUL LETTER A..HALFWIDTH HANGUL
FFC8..FFC9  ; UNASSIGNED  # <RESERVED>..<RESERVED>
FFCA..FFCF  ; FREE_PVAL   # HALFWIDTH HANGUL LETTER YEO..HALFWIDTH HANGU
FFD0..FFD1  ; UNASSIGNED  # <RESERVED>..<RESERVED>
FFD2..FFD7  ; FREE_PVAL   # HALFWIDTH HANGUL LETTER YO..HALFWIDTH HANGUL
FFD8..FFD9  ; UNASSIGNED  # <RESERVED>..<RESERVED>
FFDA..FFDC  ; FREE_PVAL   # HALFWIDTH HANGUL LETTER EU..HALFWIDTH HANGUL
FFDD..FFDF  ; UNASSIGNED  # <RESERVED>..<RESERVED>
FFE0..FFE6  ; FREE_PVAL   # FULLWIDTH CENT SIGN..FULLWIDTH WON SIGN
FFE7        ; UNASSIGNED  # <RESERVED>
FFE8..FFEE  ; FREE_PVAL   # HALFWIDTH FORMS LIGHT VERTICAL..HALFWIDTH WH
FFEF..FFF8  ; UNASSIGNED  # <RESERVED>..<RESERVED>
FFF9..FFFB  ; DISALLOWED  # INTERLINEAR ANNOTATION ANCHOR..INTERLINEAR A
FFFC..FFFD  ; FREE_PVAL   # OBJECT REPLACEMENT CHARACTER..REPLACEMENT CH
FFFE..FFFF  ; DISALLOWED  # <NOT A CHARACTER>..<NOT A CHARACTER>
10000..1000B; PVALID      # LINEAR B SYLLABLE B008 A..LINEAR B SYLLABLE
1000C       ; UNASSIGNED  # <RESERVED>
1000D..10026; PVALID      # LINEAR B SYLLABLE B036 JO..LINEAR B SYLLABLE
10027       ; UNASSIGNED  # <RESERVED>
10028..1003A; PVALID      # LINEAR B SYLLABLE B060 RA..LINEAR B SYLLABLE
1003B       ; UNASSIGNED  # <RESERVED>
1003C..1003D; PVALID      # LINEAR B SYLLABLE B017 ZA..LINEAR B SYLLABLE
1003E       ; UNASSIGNED  # <RESERVED>
1003F..1004D; PVALID      # LINEAR B SYLLABLE B020 ZO..LINEAR B SYLLABLE
1004E..1004F; UNASSIGNED  # <RESERVED>..<RESERVED>
10050..1005D; PVALID      # LINEAR B SYMBOL B018..LINEAR B SYMBOL B089
1005E..1007F; UNASSIGNED  # <RESERVED>..<RESERVED>
10080..100FA; PVALID      # LINEAR B IDEOGRAM B100 MAN..LINEAR B IDEOGRA
100FB..100FF; UNASSIGNED  # <RESERVED>..<RESERVED>
10100..10102; FREE_PVAL   # AEGEAN WORD SEPARATOR LINE..AEGEAN CHECK MAR
10103..10106; UNASSIGNED  # <RESERVED>..<RESERVED>
10107..10133; FREE_PVAL   # AEGEAN NUMBER ONE..AEGEAN NUMBER NINETY THOU
10134..10136; UNASSIGNED  # <RESERVED>..<RESERVED>
10137..1018E; FREE_PVAL   # AEGEAN WEIGHT BASE UNIT..NOMISMA SIGN
1018F       ; UNASSIGNED  # <RESERVED>
10190..1019C; FREE_PVAL   # ROMAN SEXTANS SIGN..ASCIA SYMBOL
1019D..1019F; UNASSIGNED  # <RESERVED>..<RESERVED>
101A0       ; FREE_PVAL   # GREEK SYMBOL TAU RHO
101A1..101CF; UNASSIGNED  # <RESERVED>..<RESERVED>
101D0..101FC; FREE_PVAL   # PHAISTOS DISC SIGN PEDESTRIAN..PHAISTOS DISC
101FD       ; PVALID      # PHAISTOS DISC SIGN COMBINING OBLIQUE STROKE
101FE..1027F; UNASSIGNED  # <RESERVED>..<RESERVED>
10280..1029C; PVALID      # LYCIAN LETTER A..LYCIAN LETTER X
1029D..1029F; UNASSIGNED  # <RESERVED>..<RESERVED>
102A0..102D0; PVALID      # CARIAN LETTER A..CARIAN LETTER UUU3
102D1..102DF; UNASSIGNED  # <RESERVED>..<RESERVED>
102E0       ; PVALID      # COPTIC EPACT THOUSANDS MARK
102E1..102FB; FREE_PVAL   # COPTIC EPACT DIGIT ONE..COPTIC EPACT NUMBER
102FC..102FF; UNASSIGNED  # <RESERVED>..<RESERVED>
10300..1031F; PVALID      # OLD ITALIC LETTER A..OLD ITALIC LETTER ESS
10320..10323; FREE_PVAL   # OLD ITALIC NUMERAL ONE..OLD ITALIC NUMERAL F
10324..1032C; UNASSIGNED  # <RESERVED>..<RESERVED>
1032D..10340; PVALID      # OLD ITALIC LETTER YE..GOTHIC LETTER PAIRTHRA
10341       ; FREE_PVAL   # GOTHIC LETTER NINETY
10342..10349; PVALID      # GOTHIC LETTER RAIDA..GOTHIC LETTER OTHAL
1034A       ; FREE_PVAL   # GOTHIC LETTER NINE HUNDRED
1034B..1034F; UNASSIGNED  # <RESERVED>..<RESERVED>
10350..1037A; PVALID      # OLD PERMIC LETTER AN..COMBINING OLD PERMIC L
1037B..1037F; UNASSIGNED  # <RESERVED>..<RESERVED>
10380..1039D; PVALID      # UGARITIC LETTER ALPA..UGARITIC LETTER SSU
1039E       ; UNASSIGNED  # <RESERVED>
1039F       ; FREE_PVAL   # UGARITIC WORD DIVIDER
103A0..103C3; PVALID      # OLD PERSIAN SIGN A..OLD PERSIAN SIGN HA
103C4..103C7; UNASSIGNED  # <RESERVED>..<RESERVED>
103C8..103CF; PVALID      # OLD PERSIAN SIGN AURAMAZDAA..OLD PERSIAN SIG
103D0..103D5; FREE_PVAL   # OLD PERSIAN WORD DIVIDER..OLD PERSIAN NUMBER
103D6..103FF; UNASSIGNED  # <RESERVED>..<RESERVED>
10400..1049D; PVALID      # DESERET CAPITAL LETTER LONG I..OSMANYA LETTE
1049E..1049F; UNASSIGNED  # <RESERVED>..<RESERVED>
104A0..104A9; PVALID      # OSMANYA DIGIT ZERO..OSMANYA DIGIT NINE
104AA..104AF; UNASSIGNED  # <RESERVED>..<RESERVED>
104B0..104D3; PVALID      # OSAGE CAPITAL LETTER A..OSAGE CAPITAL LETTER
104D4..104D7; UNASSIGNED  # <RESERVED>..<RESERVED>
104D8..104FB; PVALID      # OSAGE SMALL LETTER A..OSAGE SMALL LETTER ZHA
104FC..104FF; UNASSIGNED  # <RESERVED>..<RESERVED>
10500..10527; PVALID      # ELBASAN LETTER A..ELBASAN LETTER KHE
10528..1052F; UNASSIGNED  # <RESERVED>..<RESERVED>
10530..10563; PVALID      # CAUCASIAN ALBANIAN LETTER ALT..CAUCASIAN ALB
10564..1056E; UNASSIGNED  # <RESERVED>..<RESERVED>
1056F       ; FREE_PVAL   # CAUCASIAN ALBANIAN CITATION MARK
10570..1057A; PVALID      # VITHKUQI CAPITAL LETTER A..VITHKUQI CAPITAL
1057B       ; UNASSIGNED  # <RESERVED>
1057C..1058A; PVALID      # VITHKUQI CAPITAL LETTER HA..VITHKUQI CAPITAL
1058B       ; UNASSIGNED  # <RESERVED>
1058C..10592; PVALID      # VITHKUQI CAPITAL LETTER SE..VITHKUQI CAPITAL
10593       ; UNASSIGNED  # <RESERVED>
10594..10595; PVALID      # VITHKUQI CAPITAL LETTER Y..VITHKUQI CAPITAL
10596       ; UNASSIGNED  # <RESERVED>
10597..105A1; PVALID      # VITHKUQI SMALL LETTER A..VITHKUQI SMALL LETT
105A2       ; UNASSIGNED  # <RESERVED>
105A3..105B1; PVALID      # VITHKUQI SMALL LETTER HA..VITHKUQI SMALL LET
105B2       ; UNASSIGNED  # <RESERVED>
105B3..105B9; PVALID      # VITHKUQI SMALL LETTER SE..VITHKUQI SMALL LET
105BA       ; UNASSIGNED  # <RESERVED>
105BB..105BC; PVALID      # VITHKUQI SMALL LETTER Y..VITHKUQI SMALL LETT
105BD..105FF; UNASSIGNED  # <RESERVED>..<RESERVED>
10600..10736; PVALID      # LINEAR A SIGN AB001..LINEAR A SIGN A664
10737..1073F; UNASSIGNED  # <RESERVED>..<RESERVED>
10740..10755; PVALID      # LINEAR A SIGN A701 A..LINEAR A SIGN A732 JE
10756..1075F; UNASSIGNED  # <RESERVED>..<RESERVED>
10760..10767; PVALID      # LINEAR A SIGN A800..LINEAR A SIGN A807
10768..1077F; UNASSIGNED  # <RESERVED>..<RESERVED>
10780       ; PVALID      # MODIFIER LETTER SMALL CAPITAL AA
10781..10785; FREE_PVAL   # MODIFIER LETTER SUPERSCRIPT TRIANGULAR COLON
10786       ; UNASSIGNED  # <RESERVED>
10787..107B0; FREE_PVAL   # MODIFIER LETTER SMALL DZ DIGRAPH..MODIFIER L
107B1       ; UNASSIGNED  # <RESERVED>
107B2..107BA; FREE_PVAL   # MODIFIER LETTER SMALL CAPITAL Y..MODIFIER LE
107BB..107FF; UNASSIGNED  # <RESERVED>..<RESERVED>
10800..10805; PVALID      # CYPRIOT SYLLABLE A..CYPRIOT SYLLABLE JA
10806..10807; UNASSIGNED  # <RESERVED>..<RESERVED>
10808       ; PVALID      # CYPRIOT SYLLABLE JO
10809       ; UNASSIGNED  # <RESERVED>
1080A..10835; PVALID      # CYPRIOT SYLLABLE KA..CYPRIOT SYLLABLE WO
10836       ; UNASSIGNED  # <RESERVED>
10837..10838; PVALID      # CYPRIOT SYLLABLE XA..CYPRIOT SYLLABLE XE
10839..1083B; UNASSIGNED  # <RESERVED>..<RESERVED>
1083C       ; PVALID      # CYPRIOT SYLLABLE ZA
1083D..1083E; UNASSIGNED  # <RESERVED>..<RESERVED>
1083F..10855; PVALID      # CYPRIOT SYLLABLE ZO..IMPERIAL ARAMAIC LETTER
10856       ; UNASSIGNED  # <RESERVED>
10857..1085F; FREE_PVAL   # IMPERIAL ARAMAIC SECTION SIGN..IMPERIAL ARAM
10860..10876; PVALID      # PALMYRENE LETTER ALEPH..PALMYRENE LETTER TAW
10877..1087F; FREE_PVAL   # PALMYRENE LEFT-POINTING FLEURON..PALMYRENE N
10880..1089E; PVALID      # NABATAEAN LETTER FINAL ALEPH..NABATAEAN LETT
1089F..108A6; UNASSIGNED  # <RESERVED>..<RESERVED>
108A7..108AF; FREE_PVAL   # NABATAEAN NUMBER ONE..NABATAEAN NUMBER ONE H
108B0..108DF; UNASSIGNED  # <RESERVED>..<RESERVED>
108E0..108F2; PVALID      # HATRAN LETTER ALEPH..HATRAN LETTER QOPH
108F3       ; UNASSIGNED  # <RESERVED>
108F4..108F5; PVALID      # HATRAN LETTER SHIN..HATRAN LETTER TAW
108F6..108FA; UNASSIGNED  # <RESERVED>..<RESERVED>
108FB..108FF; FREE_PVAL   # HATRAN NUMBER ONE..HATRAN NUMBER ONE HUNDRED
10900..10915; PVALID      # PHOENICIAN LETTER ALF..PHOENICIAN LETTER TAU
10916..1091B; FREE_PVAL   # PHOENICIAN NUMBER ONE..PHOENICIAN NUMBER THR
1091C..1091E; UNASSIGNED  # <RESERVED>..<RESERVED>
1091F       ; FREE_PVAL   # PHOENICIAN WORD SEPARATOR
10920..10939; PVALID      # LYDIAN LETTER A..LYDIAN LETTER C
1093A..1093E; UNASSIGNED  # <RESERVED>..<RESERVED>
1093F       ; FREE_PVAL   # LYDIAN TRIANGULAR MARK
10940..1097F; UNASSIGNED  # <RESERVED>..<RESERVED>
10980..109B7; PVALID      # MEROITIC HIEROGLYPHIC LETTER A..MEROITIC CUR
109B8..109BB; UNASSIGNED  # <RESERVED>..<RESERVED>
109BC..109BD; FREE_PVAL   # MEROITIC CURSIVE FRACTION ELEVEN TWELFTHS..M
109BE..109BF; PVALID      # MEROITIC CURSIVE LOGOGRAM RMT..MEROITIC CURS
109C0..109CF; FREE_PVAL   # MEROITIC CURSIVE NUMBER ONE..MEROITIC CURSIV
109D0..109D1; UNASSIGNED  # <RESERVED>..<RESERVED>
109D2..109FF; FREE_PVAL   # MEROITIC CURSIVE NUMBER ONE HUNDRED..MEROITI
10A00..10A03; PVALID      # KHAROSHTHI LETTER A..KHAROSHTHI VOWEL SIGN V
10A04       ; UNASSIGNED  # <RESERVED>
10A05..10A06; PVALID      # KHAROSHTHI VOWEL SIGN E..KHAROSHTHI VOWEL SI
10A07..10A0B; UNASSIGNED  # <RESERVED>..<RESERVED>
10A0C..10A13; PVALID      # KHAROSHTHI VOWEL LENGTH MARK..KHAROSHTHI LET
10A14       ; UNASSIGNED  # <RESERVED>
10A15..10A17; PVALID      # KHAROSHTHI LETTER CA..KHAROSHTHI LETTER JA
10A18       ; UNASSIGNED  # <RESERVED>
10A19..10A35; PVALID      # KHAROSHTHI LETTER NYA..KHAROSHTHI LETTER VHA
10A36..10A37; UNASSIGNED  # <RESERVED>..<RESERVED>
10A38..10A3A; PVALID      # KHAROSHTHI SIGN BAR ABOVE..KHAROSHTHI SIGN D
10A3B..10A3E; UNASSIGNED  # <RESERVED>..<RESERVED>
10A3F       ; PVALID      # KHAROSHTHI VIRAMA
10A40..10A48; FREE_PVAL   # KHAROSHTHI DIGIT ONE..KHAROSHTHI FRACTION ON
10A49..10A4F; UNASSIGNED  # <RESERVED>..<RESERVED>
10A50..10A58; FREE_PVAL   # KHAROSHTHI PUNCTUATION DOT..KHAROSHTHI PUNCT
10A59..10A5F; UNASSIGNED  # <RESERVED>..<RESERVED>
10A60..10A7C; PVALID      # OLD SOUTH ARABIAN LETTER HE..OLD SOUTH ARABI
10A7D..10A7F; FREE_PVAL   # OLD SOUTH ARABIAN NUMBER ONE..OLD SOUTH ARAB
10A80..10A9C; PVALID      # OLD NORTH ARABIAN LETTER HEH..OLD NORTH ARAB
10A9D..10A9F; FREE_PVAL   # OLD NORTH ARABIAN NUMBER ONE..OLD NORTH ARAB
10AA0..10ABF; UNASSIGNED  # <RESERVED>..<RESERVED>
10AC0..10AC7; PVALID      # MANICHAEAN LETTER ALEPH..MANICHAEAN LETTER W
10AC8       ; FREE_PVAL   # MANICHAEAN SIGN UD
10AC9..10AE6; PVALID      # MANICHAEAN LETTER ZAYIN..MANICHAEAN ABBREVIA
10AE7..10AEA; UNASSIGNED  # <RESERVED>..<RESERVED>
10AEB..10AF6; FREE_PVAL   # MANICHAEAN NUMBER ONE..MANICHAEAN PUNCTUATIO
10AF7..10AFF; UNASSIGNED  # <RESERVED>..<RESERVED>
10B00..10B35; PVALID      # AVESTAN LETTER A..AVESTAN LETTER HE
10B36..10B38; UNASSIGNED  # <RESERVED>..<RESERVED>
10B39..10B3F; FREE_PVAL   # AVESTAN ABBREVIATION MARK..LARGE ONE RING OV
10B40..10B55; PVALID      # INSCRIPTIONAL PARTHIAN LETTER ALEPH..INSCRIP
10B56..10B57; UNASSIGNED  # <RESERVED>..<RESERVED>
10B58..10B5F; FREE_PVAL   # INSCRIPTIONAL PARTHIAN NUMBER ONE..INSCRIPTI
10B60..10B72; PVALID      # INSCRIPTIONAL PAHLAVI LETTER ALEPH..INSCRIPT
10B73..10B77; UNASSIGNED  # <RESERVED>..<RESERVED>
10B78..10B7F; FREE_PVAL   # INSCRIPTIONAL PAHLAVI NUMBER ONE..INSCRIPTIO
10B80..10B91; PVALID      # PSALTER PAHLAVI LETTER ALEPH..PSALTER PAHLAV
10B92..10B98; UNASSIGNED  # <RESERVED>..<RESERVED>
10B99..10B9C; FREE_PVAL   # PSALTER PAHLAVI SECTION MARK..PSALTER PAHLAV
10B9D..10BA8; UNASSIGNED  # <RESERVED>..<RESERVED>
10BA9..10BAF; FREE_PVAL   # PSALTER PAHLAVI NUMBER ONE..PSALTER PAHLAVI
10BB0..10BFF; UNASSIGNED  # <RESERVED>..<RESERVED>
10C00..10C48; PVALID      # OLD TURKIC LETTER ORKHON A..OLD TURKIC LETTE
10C49..10C7F; UNASSIGNED  # <RESERVED>..<RESERVED>
10C80..10CB2; PVALID      # OLD HUNGARIAN CAPITAL LETTER A..OLD HUNGARIA
10CB3..10CBF; UNASSIGNED  # <RESERVED>..<RESERVED>
10CC0..10CF2; PVALID      # OLD HUNGARIAN SMALL LETTER A..OLD HUNGARIAN
10CF3..10CF9; UNASSIGNED  # <RESERVED>..<RESERVED>
10CFA..10CFF; FREE_PVAL   # OLD HUNGARIAN NUMBER ONE..OLD HUNGARIAN NUMB
10D00..10D27; PVALID      # HANIFI ROHINGYA LETTER A..HANIFI ROHINGYA SI
10D28..10D2F; UNASSIGNED  # <RESERVED>..<RESERVED>
10D30..10D39; PVALID      # HANIFI ROHINGYA DIGIT ZERO..HANIFI ROHINGYA
10D3A..10E5F; UNASSIGNED  # <RESERVED>..<RESERVED>
10E60..10E7E; FREE_PVAL   # RUMI DIGIT ONE..RUMI FRACTION TWO THIRDS
10E7F       ; UNASSIGNED  # <RESERVED>
10E80..10EA9; PVALID      # YEZIDI LETTER ELIF..YEZIDI LETTER ET
10EAA       ; UNASSIGNED  # <RESERVED>
10EAB..10EAC; PVALID      # YEZIDI COMBINING HAMZA MARK..YEZIDI COMBININ
10EAD       ; FREE_PVAL   # YEZIDI HYPHENATION MARK
10EAE..10EAF; UNASSIGNED  # <RESERVED>..<RESERVED>
10EB0..10EB1; PVALID      # YEZIDI LETTER LAM WITH DOT ABOVE..YEZIDI LET
10EB2..10EFF; UNASSIGNED  # <RESERVED>..<RESERVED>
10F00..10F1C; PVALID      # OLD SOGDIAN LETTER ALEPH..OLD SOGDIAN LETTER
10F1D..10F26; FREE_PVAL   # OLD SOGDIAN NUMBER ONE..OLD SOGDIAN FRACTION
10F27       ; PVALID      # OLD SOGDIAN LIGATURE AYIN-DALETH
10F28..10F2F; UNASSIGNED  # <RESERVED>..<RESERVED>
10F30..10F50; PVALID      # SOGDIAN LETTER ALEPH..SOGDIAN COMBINING STRO
10F51..10F59; FREE_PVAL   # SOGDIAN NUMBER ONE..SOGDIAN PUNCTUATION HALF
10F5A..10F6F; UNASSIGNED  # <RESERVED>..<RESERVED>
10F70..10F85; PVALID      # OLD UYGHUR LETTER ALEPH..OLD UYGHUR COMBININ
10F86..10F89; FREE_PVAL   # OLD UYGHUR PUNCTUATION BAR..OLD UYGHUR PUNCT
10F8A..10FAF; UNASSIGNED  # <RESERVED>..<RESERVED>
10FB0..10FC4; PVALID      # CHORASMIAN LETTER ALEPH..CHORASMIAN LETTER T
10FC5..10FCB; FREE_PVAL   # CHORASMIAN NUMBER ONE..CHORASMIAN NUMBER ONE
10FCC..10FDF; UNASSIGNED  # <RESERVED>..<RESERVED>
10FE0..10FF6; PVALID      # ELYMAIC LETTER ALEPH..ELYMAIC LIGATURE ZAYIN
10FF7..10FFF; UNASSIGNED  # <RESERVED>..<RESERVED>
11000..11046; PVALID      # BRAHMI SIGN CANDRABINDU..BRAHMI VIRAMA
11047..1104D; FREE_PVAL   # BRAHMI DANDA..BRAHMI PUNCTUATION LOTUS
1104E..11051; UNASSIGNED  # <RESERVED>..<RESERVED>
11052..11065; FREE_PVAL   # BRAHMI NUMBER ONE..BRAHMI NUMBER ONE THOUSAN
11066..11075; PVALID      # BRAHMI DIGIT ZERO..BRAHMI LETTER OLD TAMIL L
11076..1107E; UNASSIGNED  # <RESERVED>..<RESERVED>
1107F..110BA; PVALID      # BRAHMI NUMBER JOINER..KAITHI SIGN NUKTA
110BB..110BC; FREE_PVAL   # KAITHI ABBREVIATION SIGN..KAITHI ENUMERATION
110BD       ; DISALLOWED  # KAITHI NUMBER SIGN
110BE..110C1; FREE_PVAL   # KAITHI SECTION MARK..KAITHI DOUBLE DANDA
110C2       ; PVALID      # KAITHI VOWEL SIGN VOCALIC R
110C3..110CC; UNASSIGNED  # <RESERVED>..<RESERVED>
110CD       ; DISALLOWED  # KAITHI NUMBER SIGN ABOVE
110CE..110CF; UNASSIGNED  # <RESERVED>..<RESERVED>
110D0..110E8; PVALID      # SORA SOMPENG LETTER SAH..SORA SOMPENG LETTER
110E9..110EF; UNASSIGNED  # <RESERVED>..<RESERVED>
110F0..110F9; PVALID      # SORA SOMPENG DIGIT ZERO..SORA SOMPENG DIGIT
110FA..110FF; UNASSIGNED  # <RESERVED>..<RESERVED>
11100..11134; PVALID      # CHAKMA SIGN CANDRABINDU..CHAKMA MAAYYAA
11135       ; UNASSIGNED  # <RESERVED>
11136..1113F; PVALID      # CHAKMA DIGIT ZERO..CHAKMA DIGIT NINE
11140..11143; FREE_PVAL   # CHAKMA SECTION MARK..CHAKMA QUESTION MARK
11144..11147; PVALID      # CHAKMA LETTER LHAA..CHAKMA LETTER VAA
11148..1114F; UNASSIGNED  # <RESERVED>..<RESERVED>
11150..11173; PVALID      # MAHAJANI LETTER A..MAHAJANI SIGN NUKTA
11174..11175; FREE_PVAL   # MAHAJANI ABBREVIATION SIGN..MAHAJANI SECTION
11176       ; PVALID      # MAHAJANI LIGATURE SHRI
11177..1117F; UNASSIGNED  # <RESERVED>..<RESERVED>
11180..111C4; PVALID      # SHARADA SIGN CANDRABINDU..SHARADA OM
111C5..111C8; FREE_PVAL   # SHARADA DANDA..SHARADA SEPARATOR
111C9..111CC; PVALID      # SHARADA SANDHI MARK..SHARADA EXTRA SHORT VOW
111CD       ; FREE_PVAL   # SHARADA SUTRA MARK
111CE..111DA; PVALID      # SHARADA VOWEL SIGN PRISHTHAMATRA E..SHARADA
111DB       ; FREE_PVAL   # SHARADA SIGN SIDDHAM
111DC       ; PVALID      # SHARADA HEADSTROKE
111DD..111DF; FREE_PVAL   # SHARADA CONTINUATION SIGN..SHARADA SECTION M
111E0       ; UNASSIGNED  # <RESERVED>
111E1..111F4; FREE_PVAL   # SINHALA ARCHAIC DIGIT ONE..SINHALA ARCHAIC N
111F5..111FF; UNASSIGNED  # <RESERVED>..<RESERVED>
11200..11211; PVALID      # KHOJKI LETTER A..KHOJKI LETTER JJA
11212       ; UNASSIGNED  # <RESERVED>
11213..11237; PVALID      # KHOJKI LETTER NYA..KHOJKI SIGN SHADDA
11238..1123D; FREE_PVAL   # KHOJKI DANDA..KHOJKI ABBREVIATION SIGN
1123E       ; PVALID      # KHOJKI SIGN SUKUN
1123F..1127F; UNASSIGNED  # <RESERVED>..<RESERVED>
11280..11286; PVALID      # MULTANI LETTER A..MULTANI LETTER GA
11287       ; UNASSIGNED  # <RESERVED>
11288       ; PVALID      # MULTANI LETTER GHA
11289       ; UNASSIGNED  # <RESERVED>
1128A..1128D; PVALID      # MULTANI LETTER CA..MULTANI LETTER JJA
1128E       ; UNASSIGNED  # <RESERVED>
1128F..1129D; PVALID      # MULTANI LETTER NYA..MULTANI LETTER BA
1129E       ; UNASSIGNED  # <RESERVED>
1129F..112A8; PVALID      # MULTANI LETTER BHA..MULTANI LETTER RHA
112A9       ; FREE_PVAL   # MULTANI SECTION MARK
112AA..112AF; UNASSIGNED  # <RESERVED>..<RESERVED>
112B0..112EA; PVALID      # KHUDAWADI LETTER A..KHUDAWADI SIGN VIRAMA
112EB..112EF; UNASSIGNED  # <RESERVED>..<RESERVED>
112F0..112F9; PVALID      # KHUDAWADI DIGIT ZERO..KHUDAWADI DIGIT NINE
112FA..112FF; UNASSIGNED  # <RESERVED>..<RESERVED>
11300..11303; PVALID      # GRANTHA SIGN COMBINING ANUSVARA ABOVE..GRANT
11304       ; UNASSIGNED  # <RESERVED>
11305..1130C; PVALID      # GRANTHA LETTER A..GRANTHA LETTER VOCALIC L
1130D..1130E; UNASSIGNED  # <RESERVED>..<RESERVED>
1130F..11310; PVALID      # GRANTHA LETTER EE..GRANTHA LETTER AI
11311..11312; UNASSIGNED  # <RESERVED>..<RESERVED>
11313..11328; PVALID      # GRANTHA LETTER OO..GRANTHA LETTER NA
11329       ; UNASSIGNED  # <RESERVED>
1132A..11330; PVALID      # GRANTHA LETTER PA..GRANTHA LETTER RA
11331       ; UNASSIGNED  # <RESERVED>
11332..11333; PVALID      # GRANTHA LETTER LA..GRANTHA LETTER LLA
11334       ; UNASSIGNED  # <RESERVED>
11335..11339; PVALID      # GRANTHA LETTER VA..GRANTHA LETTER HA
1133A       ; UNASSIGNED  # <RESERVED>
1133B..11344; PVALID      # COMBINING BINDU BELOW..GRANTHA VOWEL SIGN VO
11345..11346; UNASSIGNED  # <RESERVED>..<RESERVED>
11347..11348; PVALID      # GRANTHA VOWEL SIGN EE..GRANTHA VOWEL SIGN AI
11349..1134A; UNASSIGNED  # <RESERVED>..<RESERVED>
1134B..1134D; PVALID      # GRANTHA VOWEL SIGN OO..GRANTHA SIGN VIRAMA
1134E..1134F; UNASSIGNED  # <RESERVED>..<RESERVED>
11350       ; PVALID      # GRANTHA OM
11351..11356; UNASSIGNED  # <RESERVED>..<RESERVED>
11357       ; PVALID      # GRANTHA AU LENGTH MARK
11358..1135C; UNASSIGNED  # <RESERVED>..<RESERVED>
1135D..11363; PVALID      # GRANTHA SIGN PLUTA..GRANTHA VOWEL SIGN VOCAL
11364..11365; UNASSIGNED  # <RESERVED>..<RESERVED>
11366..1136C; PVALID      # COMBINING GRANTHA DIGIT ZERO..COMBINING GRAN
1136D..1136F; UNASSIGNED  # <RESERVED>..<RESERVED>
11370..11374; PVALID      # COMBINING GRANTHA LETTER A..COMBINING GRANTH
11375..113FF; UNASSIGNED  # <RESERVED>..<RESERVED>
11400..1144A; PVALID      # NEWA LETTER A..NEWA SIDDHI
1144B..1144F; FREE_PVAL   # NEWA DANDA..NEWA ABBREVIATION SIGN
11450..11459; PVALID      # NEWA DIGIT ZERO..NEWA DIGIT NINE
1145A..1145B; FREE_PVAL   # NEWA DOUBLE COMMA..NEWA PLACEHOLDER MARK
1145C       ; UNASSIGNED  # <RESERVED>
1145D       ; FREE_PVAL   # NEWA INSERTION SIGN
1145E..11461; PVALID      # NEWA SANDHI MARK..NEWA SIGN UPADHMANIYA
11462..1147F; UNASSIGNED  # <RESERVED>..<RESERVED>
11480..114C5; PVALID      # TIRHUTA ANJI..TIRHUTA GVANG
114C6       ; FREE_PVAL   # TIRHUTA ABBREVIATION SIGN
114C7       ; PVALID      # TIRHUTA OM
114C8..114CF; UNASSIGNED  # <RESERVED>..<RESERVED>
114D0..114D9; PVALID      # TIRHUTA DIGIT ZERO..TIRHUTA DIGIT NINE
114DA..1157F; UNASSIGNED  # <RESERVED>..<RESERVED>
11580..115B5; PVALID      # SIDDHAM LETTER A..SIDDHAM VOWEL SIGN VOCALIC
115B6..115B7; UNASSIGNED  # <RESERVED>..<RESERVED>
115B8..115C0; PVALID      # SIDDHAM VOWEL SIGN E..SIDDHAM SIGN NUKTA
115C1..115D7; FREE_PVAL   # SIDDHAM SIGN SIDDHAM..SIDDHAM SECTION MARK W
115D8..115DD; PVALID      # SIDDHAM LETTER THREE-CIRCLE ALTERNATE I..SID
115DE..115FF; UNASSIGNED  # <RESERVED>..<RESERVED>
11600..11640; PVALID      # MODI LETTER A..MODI SIGN ARDHACANDRA
11641..11643; FREE_PVAL   # MODI DANDA..MODI ABBREVIATION SIGN
11644       ; PVALID      # MODI SIGN HUVA
11645..1164F; UNASSIGNED  # <RESERVED>..<RESERVED>
11650..11659; PVALID      # MODI DIGIT ZERO..MODI DIGIT NINE
1165A..1165F; UNASSIGNED  # <RESERVED>..<RESERVED>
11660..1166C; FREE_PVAL   # MONGOLIAN BIRGA WITH ORNAMENT..MONGOLIAN TUR
1166D..1167F; UNASSIGNED  # <RESERVED>..<RESERVED>
11680..116B8; PVALID      # TAKRI LETTER A..TAKRI LETTER ARCHAIC KHA
116B9       ; FREE_PVAL   # TAKRI ABBREVIATION SIGN
116BA..116BF; UNASSIGNED  # <RESERVED>..<RESERVED>
116C0..116C9; PVALID      # TAKRI DIGIT ZERO..TAKRI DIGIT NINE
116CA..116FF; UNASSIGNED  # <RESERVED>..<RESERVED>
11700..1171A; PVALID      # AHOM LETTER KA..AHOM LETTER ALTERNATE BA
1171B..1171C; UNASSIGNED  # <RESERVED>..<RESERVED>
1171D..1172B; PVALID      # AHOM CONSONANT SIGN MEDIAL LA..AHOM SIGN KIL
1172C..1172F; UNASSIGNED  # <RESERVED>..<RESERVED>
11730..11739; PVALID      # AHOM DIGIT ZERO..AHOM DIGIT NINE
1173A..1173F; FREE_PVAL   # AHOM NUMBER TEN..AHOM SYMBOL VI
11740..11746; PVALID      # AHOM LETTER CA..AHOM LETTER LLA
11747..117FF; UNASSIGNED  # <RESERVED>..<RESERVED>
11800..1183A; PVALID      # DOGRA LETTER A..DOGRA SIGN NUKTA
1183B       ; FREE_PVAL   # DOGRA ABBREVIATION SIGN
1183C..1189F; UNASSIGNED  # <RESERVED>..<RESERVED>
118A0..118E9; PVALID      # WARANG CITI CAPITAL LETTER NGAA..WARANG CITI
118EA..118F2; FREE_PVAL   # WARANG CITI NUMBER TEN..WARANG CITI NUMBER N
118F3..118FE; UNASSIGNED  # <RESERVED>..<RESERVED>
118FF..11906; PVALID      # WARANG CITI OM..DIVES AKURU LETTER E
11907..11908; UNASSIGNED  # <RESERVED>..<RESERVED>
11909       ; PVALID      # DIVES AKURU LETTER O
1190A..1190B; UNASSIGNED  # <RESERVED>..<RESERVED>
1190C..11913; PVALID      # DIVES AKURU LETTER KA..DIVES AKURU LETTER JA
11914       ; UNASSIGNED  # <RESERVED>
11915..11916; PVALID      # DIVES AKURU LETTER NYA..DIVES AKURU LETTER T
11917       ; UNASSIGNED  # <RESERVED>
11918..11935; PVALID      # DIVES AKURU LETTER DDA..DIVES AKURU VOWEL SI
11936       ; UNASSIGNED  # <RESERVED>
11937..11938; PVALID      # DIVES AKURU VOWEL SIGN AI..DIVES AKURU VOWEL
11939..1193A; UNASSIGNED  # <RESERVED>..<RESERVED>
1193B..11943; PVALID      # DIVES AKURU SIGN ANUSVARA..DIVES AKURU SIGN
11944..11946; FREE_PVAL   # DIVES AKURU DOUBLE DANDA..DIVES AKURU END OF
11947..1194F; UNASSIGNED  # <RESERVED>..<RESERVED>
11950..11959; PVALID      # DIVES AKURU DIGIT ZERO..DIVES AKURU DIGIT NI
1195A..1199F; UNASSIGNED  # <RESERVED>..<RESERVED>
119A0..119A7; PVALID      # NANDINAGARI LETTER A..NANDINAGARI LETTER VOC
119A8..119A9; UNASSIGNED  # <RESERVED>..<RESERVED>
119AA..119D7; PVALID      # NANDINAGARI LETTER E..NANDINAGARI VOWEL SIGN
119D8..119D9; UNASSIGNED  # <RESERVED>..<RESERVED>
119DA..119E1; PVALID      # NANDINAGARI VOWEL SIGN E..NANDINAGARI SIGN A
119E2       ; FREE_PVAL   # NANDINAGARI SIGN SIDDHAM
119E3..119E4; PVALID      # NANDINAGARI HEADSTROKE..NANDINAGARI VOWEL SI
119E5..119FF; UNASSIGNED  # <RESERVED>..<RESERVED>
11A00..11A3E; PVALID      # ZANABAZAR SQUARE LETTER A..ZANABAZAR SQUARE
11A3F..11A46; FREE_PVAL   # ZANABAZAR SQUARE INITIAL HEAD MARK..ZANABAZA
11A47       ; PVALID      # ZANABAZAR SQUARE SUBJOINER
11A48..11A4F; UNASSIGNED  # <RESERVED>..<RESERVED>
11A50..11A99; PVALID      # SOYOMBO LETTER A..SOYOMBO SUBJOINER
11A9A..11A9C; FREE_PVAL   # SOYOMBO MARK TSHEG..SOYOMBO MARK DOUBLE SHAD
11A9D       ; PVALID      # SOYOMBO MARK PLUTA
11A9E..11AA2; FREE_PVAL   # SOYOMBO HEAD MARK WITH MOON AND SUN AND TRIP
11AA3..11AAF; UNASSIGNED  # <RESERVED>..<RESERVED>
11AB0..11AF8; PVALID      # CANADIAN SYLLABICS NATTILIK HI..PAU CIN HAU
11AF9..11BFF; UNASSIGNED  # <RESERVED>..<RESERVED>
11C00..11C08; PVALID      # BHAIKSUKI LETTER A..BHAIKSUKI LETTER VOCALIC
11C09       ; UNASSIGNED  # <RESERVED>
11C0A..11C36; PVALID      # BHAIKSUKI LETTER E..BHAIKSUKI VOWEL SIGN VOC
11C37       ; UNASSIGNED  # <RESERVED>
11C38..11C40; PVALID      # BHAIKSUKI VOWEL SIGN E..BHAIKSUKI SIGN AVAGR
11C41..11C45; FREE_PVAL   # BHAIKSUKI DANDA..BHAIKSUKI GAP FILLER-2
11C46..11C4F; UNASSIGNED  # <RESERVED>..<RESERVED>
11C50..11C59; PVALID      # BHAIKSUKI DIGIT ZERO..BHAIKSUKI DIGIT NINE
11C5A..11C6C; FREE_PVAL   # BHAIKSUKI NUMBER ONE..BHAIKSUKI HUNDREDS UNI
11C6D..11C6F; UNASSIGNED  # <RESERVED>..<RESERVED>
11C70..11C71; FREE_PVAL   # MARCHEN HEAD MARK..MARCHEN MARK SHAD
11C72..11C8F; PVALID      # MARCHEN LETTER KA..MARCHEN LETTER A
11C90..11C91; UNASSIGNED  # <RESERVED>..<RESERVED>
11C92..11CA7; PVALID      # MARCHEN SUBJOINED LETTER KA..MARCHEN SUBJOIN
11CA8       ; UNASSIGNED  # <RESERVED>
11CA9..11CB6; PVALID      # MARCHEN SUBJOINED LETTER YA..MARCHEN SIGN CA
11CB7..11CFF; UNASSIGNED  # <RESERVED>..<RESERVED>
11D00..11D06; PVALID      # MASARAM GONDI LETTER A..MASARAM GONDI LETTER
11D07       ; UNASSIGNED  # <RESERVED>
11D08..11D09; PVALID      # MASARAM GONDI LETTER AI..MASARAM GONDI LETTE
11D0A       ; UNASSIGNED  # <RESERVED>
11D0B..11D36; PVALID      # MASARAM GONDI LETTER AU..MASARAM GONDI VOWEL
11D37..11D39; UNASSIGNED  # <RESERVED>..<RESERVED>
11D3A       ; PVALID      # MASARAM GONDI VOWEL SIGN E
11D3B       ; UNASSIGNED  # <RESERVED>
11D3C..11D3D; PVALID      # MASARAM GONDI VOWEL SIGN AI..MASARAM GONDI V
11D3E       ; UNASSIGNED  # <RESERVED>
11D3F..11D47; PVALID      # MASARAM GONDI VOWEL SIGN AU..MASARAM GONDI R
11D48..11D4F; UNASSIGNED  # <RESERVED>..<RESERVED>
11D50..11D59; PVALID      # MASARAM GONDI DIGIT ZERO..MASARAM GONDI DIGI
11D5A..11D5F; UNASSIGNED  # <RESERVED>..<RESERVED>
11D60..11D65; PVALID      # GUNJALA GONDI LETTER A..GUNJALA GONDI LETTER
11D66       ; UNASSIGNED  # <RESERVED>
11D67..11D68; PVALID      # GUNJALA GONDI LETTER EE..GUNJALA GONDI LETTE
11D69       ; UNASSIGNED  # <RESERVED>
11D6A..11D8E; PVALID      # GUNJALA GONDI LETTER OO..GUNJALA GONDI VOWEL
11D8F       ; UNASSIGNED  # <RESERVED>
11D90..11D91; PVALID      # GUNJALA GONDI VOWEL SIGN EE..GUNJALA GONDI V
11D92       ; UNASSIGNED  # <RESERVED>
11D93..11D98; PVALID      # GUNJALA GONDI VOWEL SIGN OO..GUNJALA GONDI O
11D99..11D9F; UNASSIGNED  # <RESERVED>..<RESERVED>
11DA0..11DA9; PVALID      # GUNJALA GONDI DIGIT ZERO..GUNJALA GONDI DIGI
11DAA..11EDF; UNASSIGNED  # <RESERVED>..<RESERVED>
11EE0..11EF6; PVALID      # MAKASAR LETTER KA..MAKASAR VOWEL SIGN O
11EF7..11EF8; FREE_PVAL   # MAKASAR PASSIMBANG..MAKASAR END OF SECTION
11EF9..11FAF; UNASSIGNED  # <RESERVED>..<RESERVED>
11FB0       ; PVALID      # LISU LETTER YHA
11FB1..11FBF; UNASSIGNED  # <RESERVED>..<RESERVED>
11FC0..11FF1; FREE_PVAL   # TAMIL FRACTION ONE THREE-HUNDRED-AND-TWENTIE
11FF2..11FFE; UNASSIGNED  # <RESERVED>..<RESERVED>
11FFF       ; FREE_PVAL   # TAMIL PUNCTUATION END OF TEXT
12000..12399; PVALID      # CUNEIFORM SIGN A..CUNEIFORM SIGN U U
1239A..123FF; UNASSIGNED  # <RESERVED>..<RESERVED>
12400..1246E; FREE_PVAL   # CUNEIFORM NUMERIC SIGN TWO ASH..CUNEIFORM NU
1246F       ; UNASSIGNED  # <RESERVED>
12470..12474; FREE_PVAL   # CUNEIFORM PUNCTUATION SIGN OLD ASSYRIAN WORD
12475..1247F; UNASSIGNED  # <RESERVED>..<RESERVED>
12480..12543; PVALID      # CUNEIFORM SIGN AB TIMES NUN TENU..CUNEIFORM
12544..12F8F; UNASSIGNED  # <RESERVED>..<RESERVED>
12F90..12FF0; PVALID      # CYPRO-MINOAN SIGN CM001..CYPRO-MINOAN SIGN C
12FF1..12FF2; FREE_PVAL   # CYPRO-MINOAN SIGN CM301..CYPRO-MINOAN SIGN C
12FF3..12FFF; UNASSIGNED  # <RESERVED>..<RESERVED>
13000..1342E; PVALID      # EGYPTIAN HIEROGLYPH A001..EGYPTIAN HIEROGLYP
1342F       ; UNASSIGNED  # <RESERVED>
13430..13438; DISALLOWED  # EGYPTIAN HIEROGLYPH VERTICAL JOINER..EGYPTIA
13439..143FF; UNASSIGNED  # <RESERVED>..<RESERVED>
14400..14646; PVALID      # ANATOLIAN HIEROGLYPH A001..ANATOLIAN HIEROGL
14647..167FF; UNASSIGNED  # <RESERVED>..<RESERVED>
16800..16A38; PVALID      # BAMUM LETTER PHASE-A NGKUE MFON..BAMUM LETTE
16A39..16A3F; UNASSIGNED  # <RESERVED>..<RESERVED>
16A40..16A5E; PVALID      # MRO LETTER TA..MRO LETTER TEK
16A5F       ; UNASSIGNED  # <RESERVED>
16A60..16A69; PVALID      # MRO DIGIT ZERO..MRO DIGIT NINE
16A6A..16A6D; UNASSIGNED  # <RESERVED>..<RESERVED>
16A6E..16A6F; FREE_PVAL   # MRO DANDA..MRO DOUBLE DANDA
16A70..16ABE; PVALID      # TANGSA LETTER OZ..TANGSA LETTER ZA
16ABF       ; UNASSIGNED  # <RESERVED>
16AC0..16AC9; PVALID      # TANGSA DIGIT ZERO..TANGSA DIGIT NINE
16ACA..16ACF; UNASSIGNED  # <RESERVED>..<RESERVED>
16AD0..16AED; PVALID      # BASSA VAH LETTER ENNI..BASSA VAH LETTER I
16AEE..16AEF; UNASSIGNED  # <RESERVED>..<RESERVED>
16AF0..16AF4; PVALID      # BASSA VAH COMBINING HIGH TONE..BASSA VAH COM
16AF5       ; FREE_PVAL   # BASSA VAH FULL STOP
16AF6..16AFF; UNASSIGNED  # <RESERVED>..<RESERVED>
16B00..16B36; PVALID      # PAHAWH HMONG VOWEL KEEB..PAHAWH HMONG MARK C
16B37..16B3F; FREE_PVAL   # PAHAWH HMONG SIGN VOS THOM..PAHAWH HMONG SIG
16B40..16B43; PVALID      # PAHAWH HMONG SIGN VOS SEEV..PAHAWH HMONG SIG
16B44..16B45; FREE_PVAL   # PAHAWH HMONG SIGN XAUS..PAHAWH HMONG SIGN CI
16B46..16B4F; UNASSIGNED  # <RESERVED>..<RESERVED>
16B50..16B59; PVALID      # PAHAWH HMONG DIGIT ZERO..PAHAWH HMONG DIGIT
16B5A       ; UNASSIGNED  # <RESERVED>
16B5B..16B61; FREE_PVAL   # PAHAWH HMONG NUMBER TENS..PAHAWH HMONG NUMBE
16B62       ; UNASSIGNED  # <RESERVED>
16B63..16B77; PVALID      # PAHAWH HMONG SIGN VOS LUB..PAHAWH HMONG SIGN
16B78..16B7C; UNASSIGNED  # <RESERVED>..<RESERVED>
16B7D..16B8F; PVALID      # PAHAWH HMONG CLAN SIGN TSHEEJ..PAHAWH HMONG
16B90..16E3F; UNASSIGNED  # <RESERVED>..<RESERVED>
16E40..16E7F; PVALID      # MEDEFAIDRIN CAPITAL LETTER M..MEDEFAIDRIN SM
16E80..16E9A; FREE_PVAL   # MEDEFAIDRIN DIGIT ZERO..MEDEFAIDRIN EXCLAMAT
16E9B..16EFF; UNASSIGNED  # <RESERVED>..<RESERVED>
16F00..16F4A; PVALID      # MIAO LETTER PA..MIAO LETTER RTE
16F4B..16F4E; UNASSIGNED  # <RESERVED>..<RESERVED>
16F4F..16F87; PVALID      # MIAO SIGN CONSONANT MODIFIER BAR..MIAO VOWEL
16F88..16F8E; UNASSIGNED  # <RESERVED>..<RESERVED>
16F8F..16F9F; PVALID      # MIAO TONE RIGHT..MIAO LETTER REFORMED TONE-8
16FA0..16FDF; UNASSIGNED  # <RESERVED>..<RESERVED>
16FE0..16FE1; PVALID      # TANGUT ITERATION MARK..NUSHU ITERATION MARK
16FE2       ; FREE_PVAL   # OLD CHINESE HOOK MARK
16FE3..16FE4; PVALID      # OLD CHINESE ITERATION MARK..KHITAN SMALL SCR
16FE5..16FEF; UNASSIGNED  # <RESERVED>..<RESERVED>
16FF0..16FF1; PVALID      # VIETNAMESE ALTERNATE READING MARK CA..VIETNA
16FF2..16FFF; UNASSIGNED  # <RESERVED>..<RESERVED>
17000..187F7; PVALID      # <Tangut Ideograph>..<Tangut Ideograph>
187F8..187FF; UNASSIGNED  # <RESERVED>..<RESERVED>
18800..18CD5; PVALID      # TANGUT COMPONENT-001..KHITAN SMALL SCRIPT CH
18CD6..18CFF; UNASSIGNED  # <RESERVED>..<RESERVED>
18D00..18D08; PVALID      # <Tangut Ideograph Supplement>..<Tangut Ideog
18D09..1AFEF; UNASSIGNED  # <RESERVED>..<RESERVED>
1AFF0..1AFF3; PVALID      # KATAKANA LETTER MINNAN TONE-2..KATAKANA LETT
1AFF4       ; UNASSIGNED  # <RESERVED>
1AFF5..1AFFB; PVALID      # KATAKANA LETTER MINNAN TONE-7..KATAKANA LETT
1AFFC       ; UNASSIGNED  # <RESERVED>
1AFFD..1AFFE; PVALID      # KATAKANA LETTER MINNAN NASALIZED TONE-7..KAT
1AFFF       ; UNASSIGNED  # <RESERVED>
1B000..1B122; PVALID      # KATAKANA LETTER ARCHAIC E..KATAKANA LETTER A
1B123..1B14F; UNASSIGNED  # <RESERVED>..<RESERVED>
1B150..1B152; PVALID      # HIRAGANA LETTER SMALL WI..HIRAGANA LETTER SM
1B153..1B163; UNASSIGNED  # <RESERVED>..<RESERVED>
1B164..1B167; PVALID      # KATAKANA LETTER SMALL WI..KATAKANA LETTER SM
1B168..1B16F; UNASSIGNED  # <RESERVED>..<RESERVED>
1B170..1B2FB; PVALID      # NUSHU CHARACTER-1B170..NUSHU CHARACTER-1B2FB
1B2FC..1BBFF; UNASSIGNED  # <RESERVED>..<RESERVED>
1BC00..1BC6A; PVALID      # DUPLOYAN LETTER H..DUPLOYAN LETTER VOCALIC M
1BC6B..1BC6F; UNASSIGNED  # <RESERVED>..<RESERVED>
1BC70..1BC7C; PVALID      # DUPLOYAN AFFIX LEFT HORIZONTAL SECANT..DUPLO
1BC7D..1BC7F; UNASSIGNED  # <RESERVED>..<RESERVED>
1BC80..1BC88; PVALID      # DUPLOYAN AFFIX HIGH ACUTE..DUPLOYAN AFFIX HI
1BC89..1BC8F; UNASSIGNED  # <RESERVED>..<RESERVED>
1BC90..1BC99; PVALID      # DUPLOYAN AFFIX LOW ACUTE..DUPLOYAN AFFIX LOW
1BC9A..1BC9B; UNASSIGNED  # <RESERVED>..<RESERVED>
1BC9C       ; FREE_PVAL   # DUPLOYAN SIGN O WITH CROSS
1BC9D..1BC9E; PVALID      # DUPLOYAN THICK LETTER SELECTOR..DUPLOYAN DOU
1BC9F       ; FREE_PVAL   # DUPLOYAN PUNCTUATION CHINOOK FULL STOP
1BCA0..1BCA3; DISALLOWED  # SHORTHAND FORMAT LETTER OVERLAP..SHORTHAND F
1BCA4..1CEFF; UNASSIGNED  # <RESERVED>..<RESERVED>
1CF00..1CF2D; PVALID      # ZNAMENNY COMBINING MARK GORAZDO NIZKO S KRYZ
1CF2E..1CF2F; UNASSIGNED  # <RESERVED>..<RESERVED>
1CF30..1CF46; PVALID      # ZNAMENNY COMBINING TONAL RANGE MARK MRACHNO.
1CF47..1CF4F; UNASSIGNED  # <RESERVED>..<RESERVED>
1CF50..1CFC3; FREE_PVAL   # ZNAMENNY NEUME KRYUK..ZNAMENNY NEUME PAUK
1CFC4..1CFFF; UNASSIGNED  # <RESERVED>..<RESERVED>
1D000..1D0F5; FREE_PVAL   # BYZANTINE MUSICAL SYMBOL PSILI..BYZANTINE MU
1D0F6..1D0FF; UNASSIGNED  # <RESERVED>..<RESERVED>
1D100..1D126; FREE_PVAL   # MUSICAL SYMBOL SINGLE BARLINE..MUSICAL SYMBO
1D127..1D128; UNASSIGNED  # <RESERVED>..<RESERVED>
1D129..1D164; FREE_PVAL   # MUSICAL SYMBOL MULTIPLE MEASURE REST..MUSICA
1D165..1D169; PVALID      # MUSICAL SYMBOL COMBINING STEM..MUSICAL SYMBO
1D16A..1D16C; FREE_PVAL   # MUSICAL SYMBOL FINGERED TREMOLO-1..MUSICAL S
1D16D..1D172; PVALID      # MUSICAL SYMBOL COMBINING AUGMENTATION DOT..M
1D173..1D17A; DISALLOWED  # MUSICAL SYMBOL BEGIN BEAM..MUSICAL SYMBOL EN
1D17B..1D182; PVALID      # MUSICAL SYMBOL COMBINING ACCENT..MUSICAL SYM
1D183..1D184; FREE_PVAL   # MUSICAL SYMBOL ARPEGGIATO UP..MUSICAL SYMBOL
1D185..1D18B; PVALID      # MUSICAL SYMBOL COMBINING DOIT..MUSICAL SYMBO
1D18C..1D1A9; FREE_PVAL   # MUSICAL SYMBOL RINFORZANDO..MUSICAL SYMBOL D
1D1AA..1D1AD; PVALID      # MUSICAL SYMBOL COMBINING DOWN BOW..MUSICAL S
1D1AE..1D1EA; FREE_PVAL   # MUSICAL SYMBOL PEDAL MARK..MUSICAL SYMBOL KO
1D1EB..1D1FF; UNASSIGNED  # <RESERVED>..<RESERVED>
1D200..1D241; FREE_PVAL   # GREEK VOCAL NOTATION SYMBOL-1..GREEK INSTRUM
1D242..1D244; PVALID      # COMBINING GREEK MUSICAL TRISEME..COMBINING G
1D245       ; FREE_PVAL   # GREEK MUSICAL LEIMMA
1D246..1D2DF; UNASSIGNED  # <RESERVED>..<RESERVED>
1D2E0..1D2F3; FREE_PVAL   # MAYAN NUMERAL ZERO..MAYAN NUMERAL NINETEEN
1D2F4..1D2FF; UNASSIGNED  # <RESERVED>..<RESERVED>
1D300..1D356; FREE_PVAL   # MONOGRAM FOR EARTH..TETRAGRAM FOR FOSTERING
1D357..1D35F; UNASSIGNED  # <RESERVED>..<RESERVED>
1D360..1D378; FREE_PVAL   # COUNTING ROD UNIT DIGIT ONE..TALLY MARK FIVE
1D379..1D3FF; UNASSIGNED  # <RESERVED>..<RESERVED>
1D400..1D454; FREE_PVAL   # MATHEMATICAL BOLD CAPITAL A..MATHEMATICAL IT
1D455       ; UNASSIGNED  # <RESERVED>
1D456..1D49C; FREE_PVAL   # MATHEMATICAL ITALIC SMALL I..MATHEMATICAL SC
1D49D       ; UNASSIGNED  # <RESERVED>
1D49E..1D49F; FREE_PVAL   # MATHEMATICAL SCRIPT CAPITAL C..MATHEMATICAL
1D4A0..1D4A1; UNASSIGNED  # <RESERVED>..<RESERVED>
1D4A2       ; FREE_PVAL   # MATHEMATICAL SCRIPT CAPITAL G
1D4A3..1D4A4; UNASSIGNED  # <RESERVED>..<RESERVED>
1D4A5..1D4A6; FREE_PVAL   # MATHEMATICAL SCRIPT CAPITAL J..MATHEMATICAL
1D4A7..1D4A8; UNASSIGNED  # <RESERVED>..<RESERVED>
1D4A9..1D4AC; FREE_PVAL   # MATHEMATICAL SCRIPT CAPITAL N..MATHEMATICAL
1D4AD       ; UNASSIGNED  # <RESERVED>
1D4AE..1D4B9; FREE_PVAL   # MATHEMATICAL SCRIPT CAPITAL S..MATHEMATICAL
1D4BA       ; UNASSIGNED  # <RESERVED>
1D4BB       ; FREE_PVAL   # MATHEMATICAL SCRIPT SMALL F
1D4BC       ; UNASSIGNED  # <RESERVED>
1D4BD..1D4C3; FREE_PVAL   # MATHEMATICAL SCRIPT SMALL H..MATHEMATICAL SC
1D4C4       ; UNASSIGNED  # <RESERVED>
1D4C5..1D505; FREE_PVAL   # MATHEMATICAL SCRIPT SMALL P..MATHEMATICAL FR
1D506       ; UNASSIGNED  # <RESERVED>
1D507..1D50A; FREE_PVAL   # MATHEMATICAL FRAKTUR CAPITAL D..MATHEMATICAL
1D50B..1D50C; UNASSIGNED  # <RESERVED>..<RESERVED>
1D50D..1D514; FREE_PVAL   # MATHEMATICAL FRAKTUR CAPITAL J..MATHEMATICAL
1D515       ; UNASSIGNED  # <RESERVED>
1D516..1D51C; FREE_PVAL   # MATHEMATICAL FRAKTUR CAPITAL S..MATHEMATICAL
1D51D       ; UNASSIGNED  # <RESERVED>
1D51E..1D539; FREE_PVAL   # MATHEMATICAL FRAKTUR SMALL A..MATHEMATICAL D
1D53A       ; UNASSIGNED  # <RESERVED>
1D53B..1D53E; FREE_PVAL   # MATHEMATICAL DOUBLE-STRUCK CAPITAL D..MATHEM
1D53F       ; UNASSIGNED  # <RESERVED>
1D540..1D544; FREE_PVAL   # MATHEMATICAL DOUBLE-STRUCK CAPITAL I..MATHEM
1D545       ; UNASSIGNED  # <RESERVED>
1D546       ; FREE_PVAL   # MATHEMATICAL DOUBLE-STRUCK CAPITAL O
1D547..1D549; UNASSIGNED  # <RESERVED>..<RESERVED>
1D54A..1D550; FREE_PVAL   # MATHEMATICAL DOUBLE-STRUCK CAPITAL S..MATHEM
1D551       ; UNASSIGNED  # <RESERVED>
1D552..1D6A5; FREE_PVAL   # MATHEMATICAL DOUBLE-STRUCK SMALL A..MATHEMAT
1D6A6..1D6A7; UNASSIGNED  # <RESERVED>..<RESERVED>
1D6A8..1D7CB; FREE_PVAL   # MATHEMATICAL BOLD CAPITAL ALPHA..MATHEMATICA
1D7CC..1D7CD; UNASSIGNED  # <RESERVED>..<RESERVED>
1D7CE..1D9FF; FREE_PVAL   # MATHEMATICAL BOLD DIGIT ZERO..SIGNWRITING HE
1DA00..1DA36; PVALID      # SIGNWRITING HEAD RIM..SIGNWRITING AIR SUCKIN
1DA37..1DA3A; FREE_PVAL   # SIGNWRITING AIR BLOW SMALL ROTATIONS..SIGNWR
1DA3B..1DA6C; PVALID      # SIGNWRITING MOUTH CLOSED NEUTRAL..SIGNWRITIN
1DA6D..1DA74; FREE_PVAL   # SIGNWRITING SHOULDER HIP SPINE..SIGNWRITING
1DA75       ; PVALID      # SIGNWRITING UPPER BODY TILTING FROM HIP JOIN
1DA76..1DA83; FREE_PVAL   # SIGNWRITING LIMB COMBINATION..SIGNWRITING LO
1DA84       ; PVALID      # SIGNWRITING LOCATION HEAD NECK
1DA85..1DA8B; FREE_PVAL   # SIGNWRITING LOCATION TORSO..SIGNWRITING PARE
1DA8C..1DA9A; UNASSIGNED  # <RESERVED>..<RESERVED>
1DA9B..1DA9F; PVALID      # SIGNWRITING FILL MODIFIER-2..SIGNWRITING FIL
1DAA0       ; UNASSIGNED  # <RESERVED>
1DAA1..1DAAF; PVALID      # SIGNWRITING ROTATION MODIFIER-2..SIGNWRITING
1DAB0..1DEFF; UNASSIGNED  # <RESERVED>..<RESERVED>
1DF00..1DF1E; PVALID      # LATIN SMALL LETTER FENG DIGRAPH WITH TRILL..
1DF1F..1DFFF; UNASSIGNED  # <RESERVED>..<RESERVED>
1E000..1E006; PVALID      # COMBINING GLAGOLITIC LETTER AZU..COMBINING G
1E007       ; UNASSIGNED  # <RESERVED>
1E008..1E018; PVALID      # COMBINING GLAGOLITIC LETTER ZEMLJA..COMBININ
1E019..1E01A; UNASSIGNED  # <RESERVED>..<RESERVED>
1E01B..1E021; PVALID      # COMBINING GLAGOLITIC LETTER SHTA..COMBINING
1E022       ; UNASSIGNED  # <RESERVED>
1E023..1E024; PVALID      # COMBINING GLAGOLITIC LETTER YU..COMBINING GL
1E025       ; UNASSIGNED  # <RESERVED>
1E026..1E02A; PVALID      # COMBINING GLAGOLITIC LETTER YO..COMBINING GL
1E02B..1E0FF; UNASSIGNED  # <RESERVED>..<RESERVED>
1E100..1E12C; PVALID      # NYIAKENG PUACHUE HMONG LETTER MA..NYIAKENG P
1E12D..1E12F; UNASSIGNED  # <RESERVED>..<RESERVED>
1E130..1E13D; PVALID      # NYIAKENG PUACHUE HMONG TONE-B..NYIAKENG PUAC
1E13E..1E13F; UNASSIGNED  # <RESERVED>..<RESERVED>
1E140..1E149; PVALID      # NYIAKENG PUACHUE HMONG DIGIT ZERO..NYIAKENG
1E14A..1E14D; UNASSIGNED  # <RESERVED>..<RESERVED>
1E14E       ; PVALID      # NYIAKENG PUACHUE HMONG LOGOGRAM NYAJ
1E14F       ; FREE_PVAL   # NYIAKENG PUACHUE HMONG CIRCLED CA
1E150..1E28F; UNASSIGNED  # <RESERVED>..<RESERVED>
1E290..1E2AE; PVALID      # TOTO LETTER PA..TOTO SIGN RISING TONE
1E2AF..1E2BF; UNASSIGNED  # <RESERVED>..<RESERVED>
1E2C0..1E2F9; PVALID      # WANCHO LETTER AA..WANCHO DIGIT NINE
1E2FA..1E2FE; UNASSIGNED  # <RESERVED>..<RESERVED>
1E2FF       ; FREE_PVAL   # WANCHO NGUN SIGN
1E300..1E7DF; UNASSIGNED  # <RESERVED>..<RESERVED>
1E7E0..1E7E6; PVALID      # ETHIOPIC SYLLABLE HHYA..ETHIOPIC SYLLABLE HH
1E7E7       ; UNASSIGNED  # <RESERVED>
1E7E8..1E7EB; PVALID      # ETHIOPIC SYLLABLE GURAGE HHWA..ETHIOPIC SYLL
1E7EC       ; UNASSIGNED  # <RESERVED>
1E7ED..1E7EE; PVALID      # ETHIOPIC SYLLABLE GURAGE MWI..ETHIOPIC SYLLA
1E7EF       ; UNASSIGNED  # <RESERVED>
1E7F0..1E7FE; PVALID      # ETHIOPIC SYLLABLE GURAGE QWI..ETHIOPIC SYLLA
1E7FF       ; UNASSIGNED  # <RESERVED>
1E800..1E8C4; PVALID      # MENDE KIKAKUI SYLLABLE M001 KI..MENDE KIKAKU
1E8C5..1E8C6; UNASSIGNED  # <RESERVED>..<RESERVED>
1E8C7..1E8CF; FREE_PVAL   # MENDE KIKAKUI DIGIT ONE..MENDE KIKAKUI DIGIT
1E8D0..1E8D6; PVALID      # MENDE KIKAKUI COMBINING NUMBER TEENS..MENDE
1E8D7..1E8FF; UNASSIGNED  # <RESERVED>..<RESERVED>
1E900..1E94B; PVALID      # ADLAM CAPITAL LETTER ALIF..ADLAM NASALIZATIO
1E94C..1E94F; UNASSIGNED  # <RESERVED>..<RESERVED>
1E950..1E959; PVALID      # ADLAM DIGIT ZERO..ADLAM DIGIT NINE
1E95A..1E95D; UNASSIGNED  # <RESERVED>..<RESERVED>
1E95E..1E95F; FREE_PVAL   # ADLAM INITIAL EXCLAMATION MARK..ADLAM INITIA
1E960..1EC70; UNASSIGNED  # <RESERVED>..<RESERVED>
1EC71..1ECB4; FREE_PVAL   # INDIC SIYAQ NUMBER ONE..INDIC SIYAQ ALTERNAT
1ECB5..1ED00; UNASSIGNED  # <RESERVED>..<RESERVED>
1ED01..1ED3D; FREE_PVAL   # OTTOMAN SIYAQ NUMBER ONE..OTTOMAN SIYAQ FRAC
1ED3E..1EDFF; UNASSIGNED  # <RESERVED>..<RESERVED>
1EE00..1EE03; FREE_PVAL   # ARABIC MATHEMATICAL ALEF..ARABIC MATHEMATICA
1EE04       ; UNASSIGNED  # <RESERVED>
1EE05..1EE1F; FREE_PVAL   # ARABIC MATHEMATICAL WAW..ARABIC MATHEMATICAL
1EE20       ; UNASSIGNED  # <RESERVED>
1EE21..1EE22; FREE_PVAL   # ARABIC MATHEMATICAL INITIAL BEH..ARABIC MATH
1EE23       ; UNASSIGNED  # <RESERVED>
1EE24       ; FREE_PVAL   # ARABIC MATHEMATICAL INITIAL HEH
1EE25..1EE26; UNASSIGNED  # <RESERVED>..<RESERVED>
1EE27       ; FREE_PVAL   # ARABIC MATHEMATICAL INITIAL HAH
1EE28       ; UNASSIGNED  # <RESERVED>
1EE29..1EE32; FREE_PVAL   # ARABIC MATHEMATICAL INITIAL YEH..ARABIC MATH
1EE33       ; UNASSIGNED  # <RESERVED>
1EE34..1EE37; FREE_PVAL   # ARABIC MATHEMATICAL INITIAL SHEEN..ARABIC MA
1EE38       ; UNASSIGNED  # <RESERVED>
1EE39       ; FREE_PVAL   # ARABIC MATHEMATICAL INITIAL DAD
1EE3A       ; UNASSIGNED  # <RESERVED>
1EE3B       ; FREE_PVAL   # ARABIC MATHEMATICAL INITIAL GHAIN
1EE3C..1EE41; UNASSIGNED  # <RESERVED>..<RESERVED>
1EE42       ; FREE_PVAL   # ARABIC MATHEMATICAL TAILED JEEM
1EE43..1EE46; UNASSIGNED  # <RESERVED>..<RESERVED>
1EE47       ; FREE_PVAL   # ARABIC MATHEMATICAL TAILED HAH
1EE48       ; UNASSIGNED  # <RESERVED>
1EE49       ; FREE_PVAL   # ARABIC MATHEMATICAL TAILED YEH
1EE4A       ; UNASSIGNED  # <RESERVED>
1EE4B       ; FREE_PVAL   # ARABIC MATHEMATICAL TAILED LAM
1EE4C       ; UNASSIGNED  # <RESERVED>
1EE4D..1EE4F; FREE_PVAL   # ARABIC MATHEMATICAL TAILED NOON..ARABIC MATH
1EE50       ; UNASSIGNED  # <RESERVED>
1EE51..1EE52; FREE_PVAL   # ARABIC MATHEMATICAL TAILED SAD..ARABIC MATHE
1EE53       ; UNASSIGNED  # <RESERVED>
1EE54       ; FREE_PVAL   # ARABIC MATHEMATICAL TAILED SHEEN
1EE55..1EE56; UNASSIGNED  # <RESERVED>..<RESERVED>
1EE57       ; FREE_PVAL   # ARABIC MATHEMATICAL TAILED KHAH
1EE58       ; UNASSIGNED  # <RESERVED>
1EE59       ; FREE_PVAL   # ARABIC MATHEMATICAL TAILED DAD
1EE5A       ; UNASSIGNED  # <RESERVED>
1EE5B       ; FREE_PVAL   # ARABIC MATHEMATICAL TAILED GHAIN
1EE5C       ; UNASSIGNED  # <RESERVED>
1EE5D       ; FREE_PVAL   # ARABIC MATHEMATICAL TAILED DOTLESS NOON
1EE5E       ; UNASSIGNED  # <RESERVED>
1EE5F       ; FREE_PVAL   # ARABIC MATHEMATICAL TAILED DOTLESS QAF
1EE60       ; UNASSIGNED  # <RESERVED>
1EE61..1EE62; FREE_PVAL   # ARABIC MATHEMATICAL STRETCHED BEH..ARABIC MA
1EE63       ; UNASSIGNED  # <RESERVED>
1EE64       ; FREE_PVAL   # ARABIC MATHEMATICAL STRETCHED HEH
1EE65..1EE66; UNASSIGNED  # <RESERVED>..<RESERVED>
1EE67..1EE6A; FREE_PVAL   # ARABIC MATHEMATICAL STRETCHED HAH..ARABIC MA
1EE6B       ; UNASSIGNED  # <RESERVED>
1EE6C..1EE72; FREE_PVAL   # ARABIC MATHEMATICAL STRETCHED MEEM..ARABIC M
1EE73       ; UNASSIGNED  # <RESERVED>
1EE74..1EE77; FREE_PVAL   # ARABIC MATHEMATICAL STRETCHED SHEEN..ARABIC
1EE78       ; UNASSIGNED  # <RESERVED>
1EE79..1EE7C; FREE_PVAL   # ARABIC MATHEMATICAL STRETCHED DAD..ARABIC MA
1EE7D       ; UNASSIGNED  # <RESERVED>
1EE7E       ; FREE_PVAL   # ARABIC MATHEMATICAL STRETCHED DOTLESS FEH
1EE7F       ; UNASSIGNED  # <RESERVED>
1EE80..1EE89; FREE_PVAL   # ARABIC MATHEMATICAL LOOPED ALEF..ARABIC MATH
1EE8A       ; UNASSIGNED  # <RESERVED>
1EE8B..1EE9B; FREE_PVAL   # ARABIC MATHEMATICAL LOOPED LAM..ARABIC MATHE
1EE9C..1EEA0; UNASSIGNED  # <RESERVED>..<RESERVED>
1EEA1..1EEA3; FREE_PVAL   # ARABIC MATHEMATICAL DOUBLE-STRUCK BEH..ARABI
1EEA4       ; UNASSIGNED  # <RESERVED>
1EEA5..1EEA9; FREE_PVAL   # ARABIC MATHEMATICAL DOUBLE-STRUCK WAW..ARABI
1EEAA       ; UNASSIGNED  # <RESERVED>
1EEAB..1EEBB; FREE_PVAL   # ARABIC MATHEMATICAL DOUBLE-STRUCK LAM..ARABI
1EEBC..1EEEF; UNASSIGNED  # <RESERVED>..<RESERVED>
1EEF0..1EEF1; FREE_PVAL   # ARABIC MATHEMATICAL OPERATOR MEEM WITH HAH W
1EEF2..1EFFF; UNASSIGNED  # <RESERVED>..<RESERVED>
1F000..1F02B; FREE_PVAL   # MAHJONG TILE EAST WIND..MAHJONG TILE BACK
1F02C..1F02F; UNASSIGNED  # <RESERVED>..<RESERVED>
1F030..1F093; FREE_PVAL   # DOMINO TILE HORIZONTAL BACK..DOMINO TILE VER
1F094..1F09F; UNASSIGNED  # <RESERVED>..<RESERVED>
1F0A0..1F0AE; FREE_PVAL   # PLAYING CARD BACK..PLAYING CARD KING OF SPAD
1F0AF..1F0B0; UNASSIGNED  # <RESERVED>..<RESERVED>
1F0B1..1F0BF; FREE_PVAL   # PLAYING CARD ACE OF HEARTS..PLAYING CARD RED
1F0C0       ; UNASSIGNED  # <RESERVED>
1F0C1..1F0CF; FREE_PVAL   # PLAYING CARD ACE OF DIAMONDS..PLAYING CARD B
1F0D0       ; UNASSIGNED  # <RESERVED>
1F0D1..1F0F5; FREE_PVAL   # PLAYING CARD ACE OF CLUBS..PLAYING CARD TRUM
1F0F6..1F0FF; UNASSIGNED  # <RESERVED>..<RESERVED>
1F100..1F1AD; FREE_PVAL   # DIGIT ZERO FULL STOP..MASK WORK SYMBOL
1F1AE..1F1E5; UNASSIGNED  # <RESERVED>..<RESERVED>
1F1E6..1F202; FREE_PVAL   # REGIONAL INDICATOR SYMBOL LETTER A..SQUARED
1F203..1F20F; UNASSIGNED  # <RESERVED>..<RESERVED>
1F210..1F23B; FREE_PVAL   # SQUARED CJK UNIFIED IDEOGRAPH-624B..SQUARED
1F23C..1F23F; UNASSIGNED  # <RESERVED>..<RESERVED>
1F240..1F248; FREE_PVAL   # TORTOISE SHELL BRACKETED CJK UNIFIED IDEOGRA
1F249..1F24F; UNASSIGNED  # <RESERVED>..<RESERVED>
1F250..1F251; FREE_PVAL   # CIRCLED IDEOGRAPH ADVANTAGE..CIRCLED IDEOGRA
1F252..1F25F; UNASSIGNED  # <RESERVED>..<RESERVED>
1F260..1F265; FREE_PVAL   # ROUNDED SYMBOL FOR FU..ROUNDED SYMBOL FOR CA
1F266..1F2FF; UNASSIGNED  # <RESERVED>..<RESERVED>
1F300..1F6D7; FREE_PVAL   # CYCLONE..ELEVATOR
1F6D8..1F6DC; UNASSIGNED  # <RESERVED>..<RESERVED>
1F6DD..1F6EC; FREE_PVAL   # PLAYGROUND SLIDE..AIRPLANE ARRIVING
1F6ED..1F6EF; UNASSIGNED  # <RESERVED>..<RESERVED>
1F6F0..1F6FC; FREE_PVAL   # SATELLITE..ROLLER SKATE
1F6FD..1F6FF; UNASSIGNED  # <RESERVED>..<RESERVED>
1F700..1F773; FREE_PVAL   # ALCHEMICAL SYMBOL FOR QUINTESSENCE..ALCHEMIC
1F774..1F77F; UNASSIGNED  # <RESERVED>..<RESERVED>
1F780..1F7D8; FREE_PVAL   # BLACK LEFT-POINTING ISOSCELES RIGHT TRIANGLE
1F7D9..1F7DF; UNASSIGNED  # <RESERVED>..<RESERVED>
1F7E0..1F7EB; FREE_PVAL   # LARGE ORANGE CIRCLE..LARGE BROWN SQUARE
1F7EC..1F7EF; UNASSIGNED  # <RESERVED>..<RESERVED>
1F7F0       ; FREE_PVAL   # HEAVY EQUALS SIGN
1F7F1..1F7FF; UNASSIGNED  # <RESERVED>..<RESERVED>
1F800..1F80B; FREE_PVAL   # LEFTWARDS ARROW WITH SMALL TRIANGLE ARROWHEA
1F80C..1F80F; UNASSIGNED  # <RESERVED>..<RESERVED>
1F810..1F847; FREE_PVAL   # LEFTWARDS ARROW WITH SMALL EQUILATERAL ARROW
1F848..1F84F; UNASSIGNED  # <RESERVED>..<RESERVED>
1F850..1F859; FREE_PVAL   # LEFTWARDS SANS-SERIF ARROW..UP DOWN SANS-SER
1F85A..1F85F; UNASSIGNED  # <RESERVED>..<RESERVED>
1F860..1F887; FREE_PVAL   # WIDE-HEADED LEFTWARDS LIGHT BARB ARROW..WIDE
1F888..1F88F; UNASSIGNED  # <RESERVED>..<RESERVED>
1F890..1F8AD; FREE_PVAL   # LEFTWARDS TRIANGLE ARROWHEAD..WHITE ARROW SH
1F8AE..1F8AF; UNASSIGNED  # <RESERVED>..<RESERVED>
1F8B0..1F8B1; FREE_PVAL   # ARROW POINTING UPWARDS THEN NORTH WEST..ARRO
1F8B2..1F8FF; UNASSIGNED  # <RESERVED>..<RESERVED>
1F900..1FA53; FREE_PVAL   # CIRCLED CROSS FORMEE WITH FOUR DOTS..BLACK C
1FA54..1FA5F; UNASSIGNED  # <RESERVED>..<RESERVED>
1FA60..1FA6D; FREE_PVAL   # XIANGQI RED GENERAL..XIANGQI BLACK SOLDIER
1FA6E..1FA6F; UNASSIGNED  # <RESERVED>..<RESERVED>
1FA70..1FA74; FREE_PVAL   # BALLET SHOES..THONG SANDAL
1FA75..1FA77; UNASSIGNED  # <RESERVED>..<RESERVED>
1FA78..1FA7C; FREE_PVAL   # DROP OF BLOOD..CRUTCH
1FA7D..1FA7F; UNASSIGNED  # <RESERVED>..<RESERVED>
1FA80..1FA86; FREE_PVAL   # YO-YO..NESTING DOLLS
1FA87..1FA8F; UNASSIGNED  # <RESERVED>..<RESERVED>
1FA90..1FAAC; FREE_PVAL   # RINGED PLANET..HAMSA
1FAAD..1FAAF; UNASSIGNED  # <RESERVED>..<RESERVED>
1FAB0..1FABA; FREE_PVAL   # FLY..NEST WITH EGGS
1FABB..1FABF; UNASSIGNED  # <RESERVED>..<RESERVED>
1FAC0..1FAC5; FREE_PVAL   # ANATOMICAL HEART..PERSON WITH CROWN
1FAC6..1FACF; UNASSIGNED  # <RESERVED>..<RESERVED>
1FAD0..1FAD9; FREE_PVAL   # BLUEBERRIES..JAR
1FADA..1FADF; UNASSIGNED  # <RESERVED>..<RESERVED>
1FAE0..1FAE7; FREE_PVAL   # MELTING FACE..BUBBLES
1FAE8..1FAEF; UNASSIGNED  # <RESERVED>..<RESERVED>
1FAF0..1FAF6; FREE_PVAL   # HAND WITH INDEX FINGER AND THUMB CROSSED..HE
1FAF7..1FAFF; UNASSIGNED  # <RESERVED>..<RESERVED>
1FB00..1FB92; FREE_PVAL   # BLOCK SEXTANT-1..UPPER HALF INVERSE MEDIUM S
1FB93       ; UNASSIGNED  # <RESERVED>
1FB94..1FBCA; FREE_PVAL   # LEFT HALF INVERSE MEDIUM SHADE AND RIGHT HAL
1FBCB..1FBEF; UNASSIGNED  # <RESERVED>..<RESERVED>
1FBF0..1FBF9; FREE_PVAL   # SEGMENTED DIGIT ZERO..SEGMENTED DIGIT NINE
1FBFA..1FFFD; UNASSIGNED  # <RESERVED>..<RESERVED>
1FFFE..1FFFF; DISALLOWED  # <NOT A CHARACTER>..<NOT A CHARACTER>
20000..2A6DF; PVALID      # <CJK Ideograph Extension B>..<CJK Ideograph
2A6E0..2A6FF; UNASSIGNED  # <RESERVED>..<RESERVED>
2A700..2B738; PVALID      # <CJK Ideograph Extension C>..<CJK Ideograph
2B739..2B73F; UNASSIGNED  # <RESERVED>..<RESERVED>
2B740..2B81D; PVALID      # <CJK Ideograph Extension D>..<CJK Ideograph
2B81E..2B81F; UNASSIGNED  # <RESERVED>..<RESERVED>
2B820..2CEA1; PVALID      # <CJK Ideograph Extension E>..<CJK Ideograph
2CEA2..2CEAF; UNASSIGNED  # <RESERVED>..<RESERVED>
2CEB0..2EBE0; PVALID      # <CJK Ideograph Extension F>..<CJK Ideograph
2EBE1..2F7FF; UNASSIGNED  # <RESERVED>..<RESERVED>
2F800..2FA1D; FREE_PVAL   # CJK COMPATIBILITY IDEOGRAPH-2F800..CJK COMPA
2FA1E..2FFFD; UNASSIGNED  # <RESERVED>..<RESERVED>
2FFFE..2FFFF; DISALLOWED  # <NOT A CHARACTER>..<NOT A CHARACTER>
30000..3134A; PVALID      # <CJK Ideograph Extension G>..<CJK Ideograph
3134B..3FFFD; UNASSIGNED  # <RESERVED>..<RESERVED>
3FFFE..3FFFF; DISALLOWED  # <NOT A CHARACTER>..<NOT A CHARACTER>
40000..4FFFD; UNASSIGNED  # <RESERVED>..<RESERVED>
4FFFE..4FFFF; DISALLOWED  # <NOT A CHARACTER>..<NOT A CHARACTER>
50000..5FFFD; UNASSIGNED  # <RESERVED>..<RESERVED>
5FFFE..5FFFF; DISALLOWED  # <NOT A CHARACTER>..<NOT A CHARACTER>
60000..6FFFD; UNASSIGNED  # <RESERVED>..<RESERVED>
6FFFE..6FFFF; DISALLOWED  # <NOT A CHARACTER>..<NOT A CHARACTER>
70000..7FFFD; UNASSIGNED  # <RESERVED>..<RESERVED>
7FFFE..7FFFF; DISALLOWED  # <NOT A CHARACTER>..<NOT A CHARACTER>
80000..8FFFD; UNASSIGNED  # <RESERVED>..<RESERVED>
8FFFE..8FFFF; DISALLOWED  # <NOT A CHARACTER>..<NOT A CHARACTER>
90000..9FFFD; UNASSIGNED  # <RESERVED>..<RESERVED>
9FFFE..9FFFF; DISALLOWED  # <NOT A CHARACTER>..<NOT A CHARACTER>
A0000..AFFFD; UNASSIGNED  # <RESERVED>..<RESERVED>
AFFFE..AFFFF; DISALLOWED  # <NOT A CHARACTER>..<NOT A CHARACTER>
B0000..BFFFD; UNASSIGNED  # <RESERVED>..<RESERVED>
BFFFE..BFFFF; DISALLOWED  # <NOT A CHARACTER>..<NOT A CHARACTER>
C0000..CFFFD; UNASSIGNED  # <RESERVED>..<RESERVED>
CFFFE..CFFFF; DISALLOWED  # <NOT A CHARACTER>..<NOT A CHARACTER>
D0000..DFFFD; UNASSIGNED  # <RESERVED>..<RESERVED>
DFFFE..DFFFF; DISALLOWED  # <NOT A CHARACTER>..<NOT A CHARACTER>
E0000       ; UNASSIGNED  # <RESERVED>
E0001       ; DISALLOWED  # LANGUAGE TAG
E0002..E001F; UNASSIGNED  # <RESERVED>..<RESERVED>
E0020..E007F; DISALLOWED  # TAG SPACE..CANCEL TAG
E0080..E00FF; UNASSIGNED  # <RESERVED>..<RESERVED>
E0100..E01EF; DISALLOWED  # VARIATION SELECTOR-17..VARIATION SELECTOR-25
E01F0..EFFFD; UNASSIGNED  # <RESERVED>..<RESERVED>
EFFFE..10FFFE; DISALLOWED  # <NOT A CHARACTER>..<NOT A CHARACTER>
~~~~

