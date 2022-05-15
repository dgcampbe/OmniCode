The OmniCode Specification:
===========================

Description for the New Net
---------------------------

Version 0.1.8
-------------

The OmniCode is a fun little way to present personal information and the spiritual successor to [GeekCode](http://geekcode.com), now a respectable, largely forgotten part of Internet history. It is designed to be both human- and machine-readable, condensed, yet descriptive; it can be put in your forum and email signatures, in your profile blurb, on your homepage and pretty much everywhere else you might desire.

Several tools exist to both create and decode OmniCode, the most notable of which is [IByte's OmniCode Decoder](http://uftoolbox.info/omnidecoder/omnidecode.html). In general, the creation of OmniCode-processing tools is free for all, provided that your implementation doesn't break the specification in some horrible way. Making additions to the OmniCode on your own is also strongly discouraged to avoid breaking other people's implementations.

### General Rules

The basic rules for assembling one's OmniCode are as follows:

* The codes can be in any order;
* All codes are optional. You do not need to disclose anything you do not want to;
* The codes and their attributes are case-sensitive;
* Different codes are separated by a space or a newline;
* If you want to split a particularly long code into two lines, then the next line must begin with a caret sign ('^');
* Multiple codes for a person are joined together with an ampersand ('&'). The code itself is not repeated;
* Modifiers get more and more specific as they are added to the end of a code. Modifiers are separated by a period ('.');
* Several modifiers applying to the same attribute are joined with a semicolon (';');
* Any spaces present in modifiers are replaced with an underscore ('_');

Some attributes are akin to keywords and can be applied to any code. Those are:

|     |     |
| --- | --- |
| !   | Negation (this code does not apply to me) |
| +   | This code applies to me better than normal |
| -   | This code applies to me worse than normal |
| =   | The average value applies |
| *   | All possible values apply |
| ?   | Unknown or unsure |
| (n) | Level of accomplishment (0-9) |
| ^(n) | Aspiration to level of accomplishment (0-9) |

Code Listing
------------

### sx — Gender

Your gender. Not to confuse with [sexual preference](#sp), below. Possible values:

|     |     |
| --- | --- |
| sxy | Male |
| sxx | Female |
| sx* | Hermaphrodite |
| sx! | Genderless |
| sx~ | Transgender |

### cm — Height

Your height in centimeters. One inch is approximately 2.54cm. Fairly straightforward. Automated tools may also calculate and display the feet-inch equivalent. Examples:

|     |     |
| --- | --- |
| cm170 | 170 centimeters (or about 5'7") |
| cm150.With_hat | 150 centimeters tall, but with the hat |

### kg — Weight

Your weight in kilograms. One pound is approximately 0.45kg. Also fairly straightforward. Automated tools may also calculate and display the equivalent in pounds. Example:

|     |     |
| --- | --- |
| kg70 | 70 kilograms (or about 31.5lbs.) |

### sk — Skin Color

The color of your skin in hexadecimal notation. A [color picker tool](http://colorpicker.com) can be used to find a suitable approximation. Automated tools may render a sample of the color in a box for immediate reference. Attribute joining can be used to represent more complex cases (such as some parts of the body having a different color from the rest of the body). Examples:

|     |     |
| --- | --- |
| skffffff | Pure white |
| sk000000 | Pure black |
| skead5c9 | A lighter skin tone |
| sk9e684f | A darker skin tone |
| ske7dbbf&efc7a7.arms;face | a T-shirt tan |

### ha — Hair Color

The color of your hair in hexadecimal notation. See ["skin color"](#sk) above for reference.

### ey — Eye Color

The color of your eyes in hexadecimal notation. See ["skin color"](#sk) above for reference. This is not for [eyesight](#es) — see below. The _{L}_ and _{R}_ attributes can be used to represent more complex cases (such as eyes having different colors). Examples:

|     |     |
| --- | --- |
| ey84a4f0 | Blue eyes |
| ey543408 | Brown eyes |
| ey{R}ey543408&{L}ey3a6e2d | One brown and one green eye |

### es — Eyesight

The _{L}_ and _{R}_ attributes can be used to represent more complex cases (such as different eyesight for different eyes). Possible values:

|     |     |
| --- | --- |
| es= | 20/20 vision |
| es+ | Better than 20/20 vision |
| esO | Nearsighted |
| eso | Farsighted |
| es# | Astigmatic |
| es~ | Colorblind |
| es! | Blind |

### sp — Sexual Preference

Your sexual preference. You may elaborate on this using the period notation. Examples:

|     |     |
| --- | --- |
| sp= | Heterosexual |
| sp< | Homosexual |
| sp* | Bisexual |
| sp! | Asexual |
| sp!.Human | Non-humans |
| spO | Other, please specify with a period (i.e. spO.cars) |

### Ag — Age

Your birth date. You may make it as accurate as you wish, in the order of year, month, day, hour, minute, using the period notation. The minimum is to specify the year. Automated tools may also calculate and display the current age of the code bearer. Examples:

|     |     |
| --- | --- |
| Ag1992 | I was born in 1992 |
| Ag1970.Jan.1.00.00 | I was born at the start of the UNIX Epoch |

### an — Ancestry

Indicates your ancestry, or, simply put, who your parents (and their parents) were. Several may apply. Examples:

|     |     |
| --- | --- |
| anA | African |
| anC | Celt |
| anE | European |
| anO | Asian |
| anP | Polynesian and other Islander |
| anI | Native (North and South) American |
| anU | other aboriginal |
| anE&O.China | part European, part Chinese |
| an? | Unsure |
| an! | Nonhuman |

### hd — Handedness

Indicates your handedness. Possible values:

|     |     |
| --- | --- |
| hdd | Right-handed |
| hds | Left-handed |
| hda | Ambidextrous (both are equal in use) |
| hdn | Ambi-sinistral (neither is any good) |
| hd! | No hands |

### Lo — Longitude and Latitude

Your current, primary or usual location. You can be as accurate or general as you feel comfortable with. The format is the [Google Maps](http://maps.google.com) format and can be easily obtained from it (just search for your address, right-click on the location, select _"What's here?"_ from the drop-down menu and copy the coordinates from the search bar). Automated tools may also look up the location and present it on a map. Example:

|     |     |
| --- | --- |
| Lo49.257498,-123.181458 | Vancouver, BC, Canada |

### GM — Time Zone

The time zone and daylight saving settings in your region. This code consists of five parts:

* The code symbol, _GM_;
* A plus ('+') or minus ('-') sign, or nothing if you are in the UTC;
* The difference from UTC in hours;
* A _'D'_ if daylight saving is practiced in your region, nothing if not;
* A hemisphere symbol (_'S'_ for southern, _'N'_ for northern).

Examples:

|     |     |
| --- | --- |
| GM+2DN | UTC+2 hours, DST in a Northern hemisphere summer |
| GM-10DS | UTC-10 hours, DST in a Southern hemisphere summer |
| GM0N | UTC, no DST in a Northern hemisphere summer |

### Zo — Astrological Sign

Your astrological (zodiac) sign(s). Western astrological signs:

|     |     |
| --- | --- |
| ZoQ | Aquarius |
| ZoP | Pisces |
| ZoA | Aries |
| ZoT | Taurus |
| ZoG | Gemini |
| ZoC | Cancer |
| ZoL | Leo |
| ZoV | Virgo |
| ZoB | Libra |
| ZoS | Scorpio |
| Zos | Sagittarius |
| Zoc | Capricorn |

Chinese astrological signs:

|     |     |
| --- | --- |
| ZoR | Rat |
| ZoO | Ox  |
| Zot | Tiger |
| Zor | Rabbit |
| ZoD | Dragon |
| ZoK | Snake |
| ZoH | Horse |
| Zob | Sheep/Goat |
| ZoM | Monkey |
| Zoo | Rooster |
| Zod | Dog |
| Zop | Pig |

### rl — Religion

Your religious affiliation. You can have more than one, following the ampersand notation. Submit additions to this section (with proof of existence and notability) to the maintainer. Current list:

|     |     |
| --- | --- |
| rlC | Christian |
| rlI | Muslim |
| rlH | Hindu |
| rlB | Buddhist |
| rlS | Sikh |
| rlY | Yoruba |
| rlJ | Jewish |
| rlj | Jainist |
| rls | Shintoist |
| rlN | Neo-pagan |
| rlL | Scientologist |
| rlR | Rastafarian |
| rlZ | Zoroastrian |
| rlD | Discordian |
| rlG | Gravitist |
| rlF | Jedi |
| rlM | Flying Spaghetti Monster |
| rlh | Humanist |
| rlb | Church of the SubGenius |
| rl? | Agnostic |
| rl! | Atheist |
| rl< | Self |
| rlO | Other, please specify with a period |

### LA — Language

Languages you speak. This part of the specification is loosely based on the [ISO-639-2 standard](http://www.loc.gov/standards/iso639-2/php/English_list.php). Fluency is specified using the bracket notation on an [IELTS numeric scale](http://www.ielts.org/format.htm#results), where _(1)_ would mean knowing a few menu items, swear words and likely being able to find a restaurant and the bathroom and _(9)_ would imply perfect fluency. Use the latter with care, as even native speakers might not qualify for "perfect" fluency under certain circumstances. The specific dialect spoken may be specified with the period notation. Current list:

|     |     |
| --- | --- |
| LAAA | Afar |
| LAAB | Abkhazian |
| LAAF | Afrikaans |
| LAAM | Amharic |
| LAAR | Arabic |
| LAAS | Assamese |
| LAAY | Aymara |
| LAAZ | Azerbaijani |
| LABA | Bashkir |
| LABE | Byelorussian |
| LABG | Bulgarian |
| LABH | Bihari |
| LABI | Bislama |
| LABN | Bengali |
| LABO | Tibetan |
| LABR | Breton |
| LACA | Catalan |
| LACO | Corsican |
| LACS | Czech |
| LACY | Welsh |
| LADA | Danish |
| LADE | German |
| LADZ | Bhutani |
| LAEL | Greek |
| LAEN | English |
| LAEO | Esperanto |
| LAES | Spanish |
| LAET | Estonian |
| LAEU | Basque |
| LAFA | Persian |
| LAFI | Finnish |
| LAFJ | Fiji |
| LAFO | Faeroese |
| LAFR | French |
| LAFY | Frisian |
| LAGA | Irish |
| LAGD | Gaelic |
| LAGL | Galician |
| LAGN | Guarani |
| LAGU | Gujarati |
| LAHA | Hausa |
| LAHI | Hindi |
| LAHR | Croatian |
| LAHU | Hungarian |
| LAHY | Armenian |
| LAIA | Interlingua |
| LAIE | Interlingue |
| LAIK | Inupiak |
| LAIN | Indonesian |
| LAIS | Icelandic |
| LAIT | Italian |
| LAIW | Hebrew |
| LAJA | Japanese |
| LAJI | Yiddish |
| LAJW | Javanese |
| LAKA | Georgian |
| LAKI | Klingon |
| LAKK | Kazakh |
| LAKL | Greenlandic |
| LAKM | Cambodian |
| LAKN | Kannada |
| LAKO | Korean |
| LAKS | Kashmiri |
| LAKU | Kurdish |
| LAKY | Kirghiz |
| LALA | Latin |
| LALN | Lingala |
| LALO | Laothian |
| LALT | Lithuanian |
| LALV | Latvian |
| LAMG | Malagasy |
| LAMI | Maori |
| LAMK | Macedonian |
| LAML | Malayalam |
| LAMN | Mongolian |
| LAMO | Moldavian |
| LAMR | Marathi |
| LAMS | Malay |
| LAMT | Maltese |
| LAMY | Burmese |
| LANA | Nauru |
| LANE | Nepali |
| LANL | Dutch |
| LANO | Norwegian |
| LAOC | Occitan |
| LAOM | Oromo |
| LAOR | Oriya |
| LAPA | Punjabi |
| LAPL | Polish |
| LAPS | Pashto |
| LAPT | Portuguese |
| LAQU | Quechua |
| LARM | Rhaeto-Romance |
| LARN | Kirundi |
| LARO | Romanian |
| LARU | Russian |
| LARW | Kinyarwanda |
| LASA | Sanskrit |
| LASD | Sindhi |
| LASG | Sangro |
| LASH | Serbo-Croatian |
| LASI | Singhalese |
| LASK | Slovak |
| LASL | Slovenian |
| LASM | Samoan |
| LASN | Shona |
| LASO | Somali |
| LASQ | Albanian |
| LASR | Serbian |
| LASS | Siswati |
| LAST | Sesotho |
| LASU | Sudanese |
| LASV | Swedish |
| LASW | Swahili |
| LATA | Tamil |
| LATE | Tegulu |
| LATG | Tajik |
| LATH | Thai |
| LATI | Tigrinya |
| LATK | Turkmen |
| LATL | Tagalog |
| LATN | Setswana |
| LATO | Tonga |
| LATR | Turkish |
| LATS | Tsonga |
| LATT | Tatar |
| LATW | Twi |
| LAUK | Ukrainian |
| LAUR | Urdu |
| LAUZ | Uzbek |
| LAVI | Vietnamese |
| LAVO | Volapuk |
| LAWO | Wolof |
| LAXH | Xhosa |
| LAYO | Yoruba |
| LAZH | Chinese |
| LAZU | Zulu |
| LAAL | Artifical language not listed (specify which with a period) |

### Ed — Education

Describes your formal (or informal, if that's your shtick) education. Specify the level of accomplishment with the bracket notation and the specific area of expertise with the period notation. Possible values:

|     |     |
| --- | --- |
| Eda | Arts |
| Edb | Finance and banking |
| Edm | Construction and manufacturing |
| Ede | Education |
| EdE | Engineering |
| Eds | Science |
| Edc | Computing |
| Edh | Health |
| Edp | Philosophy |
| EdM | Military |
| Edl | Law |
| Edg | Government |
| Edd | Media |
| Edn | Nature |
| Edr | Recreation and leisure |
| EdS | Sales |
| Edt | Transportation |
| Ed! | None |
| EdO | Other |
| Ed? | I think I know something but I'm not sure what |

### Cr — Career

Describes your profession or primary source(s) of income. Specify the level of accomplishment with the bracket notation and the specific area of expertise with the period notation. Possible values:

|     |     |
| --- | --- |
| Cra | Arts |
| Crb | Finance and banking |
| Crm | Construction and manufacturing |
| Cre | Education |
| CrE | Engineering |
| Crs | Science |
| Crc | Computing |
| Crh | Health |
| Crp | Philosophy |
| CrM | Military |
| Crl | Law |
| Crg | Government |
| Crd | Media |
| Crn | Nature |
| Crr | Recreation and leisure |
| CrS | Sales |
| Crt | Transportation |
| CrH | Home-worker |
| CrL | Student |
| Cr! | Unemployed |
| CrR | Retired |
| Cr$ | Independently wealthy |
| CrP | Part-time or temporary "odd jobs" |
| CrO | Other |
| Cr? | Money arrives from somewhere |

### Hb — Hobbies

A free-form description of what you like to do in your free time. There are no special rules here, apart from the usual notation guidelines. Examples:

|     |     |
| --- | --- |
| HbMotorbikes | Motorbikes |
| HbGaming.PC.FPS | Gaming in a very specific way (first person shooters on the PC) |
| HbDancing&TV.CSI;House_MD | Dancing and watching specific TV series |

### Pl — Political Leanings

Describes your political leanings. Current possible values:

|     |     |
| --- | --- |
| PlC | Communist |
| Plm | Marxist |
| Pln | Leninist |
| PlD | Democrat |
| PlR | Republican |
| PlL | Labor |
| PlT | Tory |
| PlG | Green |
| Pll | Libertarian |
| Pl{L} | Left/Liberal |
| Pl{R} | Right/Conservative |
| Pl{L}.Far | Far left |
| PlM | Moderate or Centrist |
| Pl! | Anarchist |
| PlO | Other (please specify with a period, i.e., _PlO.Theocrat_) |

### Mv — Transportation Method

Describes your usual method of transportation. Possible values:

|     |     |
| --- | --- |
| MvD | Driving |
| MvW | Walking |
| MvS | Scooter |
| Mvs | 'Segway' |
| MvM | Motorbike |
| MvB | Public transit |
| MvH | Hired transport (i.e., taxi, limo) |
| MvL | School bus |
| MvA | Vehicle capable of air travel |
| MvQ | Vehicle capable of water travel |
| Mv- | Wheelchair |
| MvO | Other (specify with period, i.e., _MvD.Car.Ford_Aspire_) |

### Rl — Relationship Status

Describes your relationship (marital) status. Possible values:

|     |     |
| --- | --- |
| RlM | Married |
| RlC | Living together or common law |
| RlE | Engaged |
| RlD | Dating |
| RlW | Widow(er) |
| RlP | Polygamous |
| Rlx | Divorced |
| Rl! | Single |
| Rl+ | Seeking |
| Rl- | Not seeking |
| RlD&+ | Divorced and seeking |

### Kd — Children

Describes children you consider "yours". The general format is _Kd\[n\]\[g\]..._, where _'n'_ is the number and _'g'_ is the gender. Further specification is possible using the period notation. An example would be _Kd2x1y.brats_ (someone with two girls and a boy who are prone to misbehave). Additional parameters:

|     |     |
| --- | --- |
| Kd! | No kids |
| Kd? | Possible kids somewhere |
| Kd> | Expecting kids |
| Kd* | Too many kids |
| Kd+ | Someone else's kids (stepchildren) |
| Kd!.Never | Resolved to not have any kids |

### Pe — Pets

Describes any pets you might have. The general groups (as well as some specifics, for simplicity's sake) are:

|     |     |
| --- | --- |
| PeA | Amphibian (frog, salamander etc.) |
| PeB | Avian (a bird) |
| PeN | Arachnoid |
| PeI | Insect |
| PeR | Reptile |
| Per | Rodent |
| PeF | Fish |
| PeM | Mollusk (clam, snail, scallop, squid etc.) |
| PeP | Plant |
| PeO | Other, please specify with a period |
| PeC | Cat |
| PeD | Dog |
| PeS | Snake |
| PeH | Hare or rabbit |
| PeT | Rat |

### MB — Myers-Briggs Personality Type

Indicates your [Myers-Briggs personality type](http://en.wikipedia.org/wiki/Myers-Briggs_Type_Indicator). Your personality type can be determined using one (or more) of the many online personality tests available: [\[1\]](http://humanmetrics.com/cgi-win/jtypes2.asp), [\[2\]](http://similarminds.com/embj.html), [\[3\]](http://personality-testing.info/tests/JUNG.php). Additional modifiers can be added using the period notation (i.e., _MBINTP.Extreme_introvert_). Possible values:

|     |     |     |     |
| --- | --- | --- | --- |
| MBENFP | MBINFP | MBENFJ | MBINFJ |
| MBENTP | MBINTP | MBENTJ | MBINTJ |
| MBESTJ | MBISTJ | MBESFJ | MBISFJ |
| MBESTP | MBISTP | MBESFP | MBISFP |

### FH — Facial Hair

Describes your facial hair. You may omit this code if having facial hair would be very strange for you indeed. Specify further using the period notation. Possible values:

|     |     |
| --- | --- |
| FHb | Full beard |
| FHg | Goatee |
| FHp | Soul patch |
| FHm | Mustache |
| FHs | Sideburns |
| FHS | Stubble |
| FH! | No facial hair |
| FHO | Other, please elaborate |
| FHm.Handlebar | Handlebar mustache |

### BA — Body Adornments

Describes any permanent or semi-permanent body adornments you might have. You may chain as many of those as you wish and be as elaborate as you like using the ampersand, semicolon and period joining. A fairly elaborate example would be _BAT.Shoulder.Bird&T.Ankle.Chain&P.Ears;Belly&I_. Possible values:

|     |     |
| --- | --- |
| BAT | Tatoo |
| BAP | Piercing |
| BAB | Branding |
| BAS | Scarring |
| BAI | Implants |
| BAl | Stretching |
| BAO | Other, please elaborate |

### IN — Internet Use

Indicates time spent on the Internet each day in hours. Type or speed of connection can be added with a trailing period modifier. The usual modifiers apply as well.

|     |     |
| --- | --- |
| IN16.Cable | I use cable |
| IN! | I don't use the Internet |
| IN? | Internet? What's that? |
| IN2.Workdays&16.Weekends | 2 hours on workdays and 16 on weekends |

### Ad — Addictions

The addictions you are willing to admit having. Further specification can be indicated using the period notation (i.e. _AdC.Tea.Earl_Grey.Hot_).

The list doesn't include things admitting which can get you in trouble with the law.

|     |     |
| --- | --- |
| AdC | Caffeine |
| AdN | Nicotine |
| AdM | Marijuana |
| AdA | Alcohol |
| AdI | Internet |
| AdG | Gambling |
| AdS | Sex |
| Ad+ | More than I can fit here |
| Ad* | Everything |
| Ad! | No addictions |
| Ad? | Addicted? Me? |
| AdO | Other (i.e. _AdO.Chocolate_) |

### Pr — Programming Languages

Describes languages you program in. This is a simplified notation; just write the code followed by whatever programming language you use. Add modifiers as necessary. Examples:

|     |     |
| --- | --- |
| Pr? | Programming? What's that? |
| Pr! | I don't do programming. |
| Pr* | I program in all languages |
| PrPascal | Pascal |
| PrPascal.Turbo | Turbo Pascal |
| PrPascal.Delphi | Delphi (Object Pascal) |
| PrPHP | PHP |
| PrPerl | Perl |
| PrPython | Python |
| PrBASIC | BASIC |
| PrBASIC.Visual | Visual Basic |
| PrC | C   |
| PrC++ | C++ |
| PrC# | C Sharp |
| PrHTML | HTML |
| PrXML | XML |
| PrCOBOL | COBOL |
| PrJava | Java |
| PrJavaScript | JavaScript |
| PrLisp | Lisp |
| PrSGML | SGML |
| PrRuby | Ruby |
| PrRuby.on_Rails | Ruby on Rails |

### UF — UserFriendly Connection

This code is depreciated and its use is discouraged. The reason is: UserFriendly is (was?) a local phenomenon. OmniCode strives for Internet-wide recognition.

OmniCode processing tool authors may display a depreciation notice with the decoding or ignore this code altogether.

Change Log
----------

* **Version 1.8**
    * Maintainer change. Special thanks to the previous maintainer, [Greg W. Webster](http://gadgeteer.net), for keeping it in such good condition.
    * General rewrite for increased clarity and readability.
    * An obvious error in the [_Mv — Transportation Method_](#mv) section was fixed ("Mv-" and "MvO" had their definitions swapped).
    * An inconsistency in the [_FH — Facial Hair_](#fh) section was corrected. "FHo" ("other") is now "FHO", in line with the rest of the specification.
    * The [_UF — UserFriendly Connection_](#uf) section has been depreciated.
