# Iosevka ![Version](https://img.shields.io/github/release/be5invis/Iosevka.svg)
Coders’ typeface, built from code.

![](https://raw.githubusercontent.com/be5invis/Iosevka/master/images/preview-all.png)

## Installation

Quit your editor/program. Unzip and open the folder.

* **Instructions for Windows**: Download the fonts from the [Releases](https://github.com/be5invis/Iosevka/releases), select the font files and right click, then hit "Install".
  * On Windows 10 1809 or newer the default font installation is per-user, and it may cause compatibility issues for some applications, mostly written in Java. To cope with this, right click and select "Install for all users" instead. [Ref.](https://youtrack.jetbrains.com/issue/JRE-1166?p=IDEA-200145)
* **[Instructions for macOS](http://support.apple.com/kb/HT2509)**
  * Standard distribution in Homebrew: `brew tap homebrew/cask-fonts && brew cask install font-iosevka && brew cask install font-iosevka-slab`. Search for other variants using `brew search font-iosevka` and install what you want.
  * Customizable install using Homebrew: see [robertgzr/homebrew-tap](https://github.com/robertgzr/homebrew-tap).
* **Linux** : Copy the TTF files to your fonts directory → Run `sudo fc-cache`. 
  - Arch Linux users can install the font from the AUR [here](https://aur.archlinux.org/packages/ttf-iosevka) using an AUR wrapper or by doing it manually. [All variants](https://aur.archlinux.org/packages/?O=0&SeB=nd&K=ttf-iosevka&SB=n&SO=a&PP=50&do_Search=Go).
  - Void Linux users can install the font with `xbps-install font-iosevka`.
* **FreeBSD**: The font can be installed with `pkg install iosevka`.
* **OpenBSD**: Run `pkg_info -Q iosevka` to see which Iosevka packages are available. Use `pkg_add` to install the chosen package(s).

## Weights, Variants and OpenType features

The typeface contains 9 weights (Thin to Heavy) alongside with both italic and oblique versions, with the same metrics as the regular one. 

![Weights sample](https://raw.githubusercontent.com/be5invis/Iosevka/master/images/weights.png)

All versions include the same ranges of characters: Latin letters, Greek letters (including Polytonic), some Cyrillic letters, IPA symbols and common punctuations and some symbols. You can check out the full list [here](http://be5invis.github.io/Iosevka/specimen).

![Languages Sample](https://raw.githubusercontent.com/be5invis/Iosevka/master/images/languages.png)

<!-- BEGIN Section-Language-List -->
<!-- THIS SECTION IS AUTOMATICALLY GENERATED. DO NOT EDIT. -->

162 Supported Languages: 

Afrikaans, Aghem, Akan, Albanian, Asturian, Asu, Azerbaijani, Bafia, Bambara, Basaa, Basque, Belarusian, Bemba, Bena, Bosnian, Breton, Bulgarian, Catalan, Cebuano, Central Atlas Tamazight, Chechen, Chiga, Colognian, Cornish, Croatian, Czech, Danish, Duala, Dutch, Embu, English, Esperanto, Estonian, Ewe, Ewondo, Faroese, Filipino, Finnish, French, Friulian, Fulah, Galician, Ganda, German, Greek, Gusii, Hausa, Hawaiian, Hungarian, Icelandic, Igbo, Inari Sami, Indonesian, Interlingua, Irish, Italian, Javanese, Jola-Fonyi, Kabuverdianu, Kabyle, Kako, Kalaallisut, Kalenjin, Kamba, Kazakh, Kikuyu, Kinyarwanda, Koyra Chiini, Koyraboro Senni, Kurdish, Kwasio, Kyrgyz, Lakota, Langi, Latvian, Lingala, Lithuanian, Low German, Lower Sorbian, Luba-Katanga, Luo, Luxembourgish, Luyia, Macedonian, Machame, Makhuwa-Meetto, Makonde, Malagasy, Malay, Maltese, Manx, Maori, Masai, Meru, Metaʼ, Mongolian, Morisyen, Mundang, Nama, Ngiemboon, Nigerian Pidgin, North Ndebele, Northern Sami, Norwegian Bokmål, Norwegian Nynorsk, Nuer, Nyankole, Oromo, Ossetic, Polish, Portuguese, Prussian, Quechua, Romanian, Romansh, Rombo, Rundi, Russian, Rwa, Sakha, Samburu, Sango, Sangu, Scottish Gaelic, Sena, Serbian, Shambala, Shona, Slovak, Slovenian, Soga, Somali, Spanish, Sundanese, Swahili, Swedish, Swiss German, Tachelhit (shi_latn), Taita, Tajik, Tasawaq, Tatar, Teso, Tongan, Turkish, Turkmen, Ukrainian, Upper Sorbian, Uzbek, Vai (vai_latn), Vietnamese, Volapük, Vunjo, Walser, Welsh, Western Frisian, Wolof, Xhosa, Yangben, Yoruba, Zarma, Zulu

<!-- END Section-Language-List -->



Iosevka supports accessing all letter variants using OpenType features.

![Style Sets](https://raw.githubusercontent.com/be5invis/Iosevka/master/images/stylesets.png)

![Character Variants](https://raw.githubusercontent.com/be5invis/Iosevka/master/images/charvars.png)

### Ligations

![Ligations Sample](https://raw.githubusercontent.com/be5invis/Iosevka/master/images/ligations.png)

Iosevka’s default ligation set is assigned to `calt` feature, though not all of them are enabled by default.

Iosevka supports Language-Specific Ligations, which is the ligation set enabled only under certain languages. These ligation sets are assigned to custom feature tags, like `CLIK`.

## Building from Source

To build Iosevka you should:

1. Ensure that [`nodejs`](http://nodejs.org) (≥ 12.16.0), [`ttfautohint`](http://www.freetype.org/ttfautohint/), [`otfcc`](https://github.com/caryll/otfcc) (≥ 0.10.3-alpha) and [`otf2otc`](https://github.com/adobe-type-tools/afdko) are present.
2. Install necessary libs by `npm install`. If you’ve installed them, upgrade to the latest.
3. `npm run build -- contents::iosevka`.

You will find TTFs, as well as WOFF(2) web fonts and one Webfont CSS in the `dist/` directory.

### Using a Docker container

Refer to these [instructions.](https://github.com/ejuarezg/containers/tree/master/iosevka_font#container-method)

## Build Your Own Style

Since version 2.0, Iosevka would no longer support building via `makefile`. To initialize a custom build, you need:

1. Create `private-build-plans.toml` file.

2. Add a build plan into `private-build-plans.toml`, following this format:

	<!-- BEGIN Section-Private-Build-Plan-Sample -->
	<!-- THIS SECTION IS AUTOMATICALLY GENERATED. DO NOT EDIT. -->
	
		[buildPlans.iosevka-custom]               # <iosevka-custom> is your plan name
		family = "Iosevka Custom"                 # Font menu family name
		design = ["v-i-hooky", "v-l-hooky"]       # Customize styles
		# upright = ["upright-styles"]            # Uncomment this line to set styles for upright only
		# italic = ["italic-styles"]              # Uncomment this line to set styles for italic only
		# oblique = ["oblique-styles"]            # Uncomment this line to set styles for oblique only
		# hintParams = ["-a", "sss"]              # Optional custom parameters for ttfautohint
		
		###################################################################################################
		# Override default building weights
		# When buildPlans.<plan name>.weights is absent, all weights would built and mapped to
		# default values.
		# IMPORTANT : Currently "menu" and "css" property only support numbers between 0 and 1000.
		#             and "shape" properly only supports number between 100 and 900 (inclusive).
		#             If you decide to use custom weights you have to define all the weights you
		#             plan to use otherwise they will not be built.
		[buildPlans.iosevka-custom.weights.regular]
		shape = 400  # Weight for glyph shapes.
		menu  = 400  # Weight for the font's names.
		css   = 400  # Weight for webfont CSS.
		
		[buildPlans.iosevka-custom.weights.book]
		shape = 450
		menu  = 450  # Use 450 here to name the font's weight "Book"
		css   = 450
		
		[buildPlans.iosevka-custom.weights.bold]
		shape = 700
		menu  = 700
		css   = 700
		
		# End weight section
		###################################################################################################
		
		###################################################################################################
		# Override default building slope sets
		# Format: <upright|italic|oblique> = <"normal"|"italic"|"oblique">
		# When this section is absent, all slopes would be built.
		
		[buildPlans.iosevka-custom.slopes]
		upright = "normal"
		italic = "italic"
		oblique = "oblique"
		
		# End slope section
		###################################################################################################
		
		###################################################################################################
		# Override default building widths
		# When buildPlans.<plan name>.widths is absent, all widths would built and mapped to
		# default values.
		# IMPORTANT : Currently "shape" property only supports numbers between 434 and 664 (inclusive),
		#             while "menu" only supports integers between 1 and 9 (inclusive).
		#             The "shape" parameter specifies the unit width, measured in 1/1000 em. The glyphs'
		#             width are equal to, or a simple multiple of the unit width.
		#             If you decide to use custom widths you have to define all the widths you plan to use,
		#             otherwise they will not be built.
		
		[buildPlans.iosevka-custom.widths.normal]
		shape = 500        # Unit Width, measured in 1/1000 em.
		menu  = 5          # Width grade for the font's names.
		css   = "normal"   # "font-stretch' property of webfont CSS.
		
		[buildPlans.iosevka-custom.widths.extended]
		shape = 576
		menu  = 7
		css   = "expanded"
		
		# End width section
		###################################################################################################
		
		###################################################################################################
		# Character Exclusion
		# Specify character ranges in the section below to exclude certain characters from the font being
		# built. Remove this section when this feature is not needed.
		
		[buildPlans.iosevka-custom.exclude-chars]
		ranges = [[10003, 10008]]
		
		# End character exclusion
		###################################################################################################
		
		###################################################################################################
		# Compatibility Ligatures
		# Certain applications like Emacs does not support proper programming liagtures provided by
		# OpenType, but can support ligatures provided by PUA codepoints. Therefore you can edit the
		# following section to build PUA characters that are generated from the OpenType ligatures.
		# Remove this section when compatibility ligatures are not needed.
		
		[[buildPlans.iosevka-custom.compatibility-ligatures]]
		unicode = 57600 # 0xE100
		featureTag = 'calt'
		sequence = '<*>'
		
		# End compatibility ligatures section
		###################################################################################################
		
		###################################################################################################
		# Metric overrides
		# Certain metrics like line height (leading) could be overridden in your build plan file.
		# Edit the values to change the metrics. Remove this section when overriding is not needed.
		
		[buildPlans.iosevka-custom.metric-override]
		leading = 1250
		winMetricAscenderPad = 0
		winMetricDescenderPad = 0
		powerlineScaleY = 1
		powerlineScaleX = 1
		powerlineShiftY = 0
		powerlineShiftX = 0
		
		# End metric override section
		###################################################################################################
		
	
	<!-- END Section-Private-Build-Plan-Sample -->
																																																																																																	
	
3. Run `npm run build -- contents::<your plan name>` and the built fonts would be avaliable in `dist/`. Aside from `contents::<plan>`, other options are:

   1. `contents::<plan>` : TTF (Hinted and Unhinted), WOFF(2) and Webfont CSS;
   2. `ttf::<plan>` : TTF;
   3. `ttf-unhinted::<plan>` : Unhinted TTF only;
   4. `woff::<plan>` : TTF and WOFF only;
   5. `woff2::<plan>` : TTF and WOFF2 only;
      - Note: Since version 2.2.0, we are using two colons (`::`) in the build target names.

The current available styles for `design`/`upright`/`italic`/`oblique` options are:

* Styles for general shape:

  * `sans` : Sans serif (default).
  * `slab` : Slab serif.

* Styles related to ligations and spacing:

  - `no-ligation` : Disable ligations.
  - `no-cv-ss` : Prevent generation of `cv##` and `ss##` features.
  - `sp-term` : Make the symbols' width suitable for terminal emulators. Arrows and geometric symbols will become narrower.
  - `sp-force-monospace`: Apply `sp-term` and further:
    - Completely remove wide glyphs. All non-combining glyphs will be exactly the same width.
	- Remove `NWID` and `WWID` OpenType feature.
	- Recommended for Linux users who customize for their terminal fonts: certain applications, including FontConfig, recognizes a font as monospace if and only if its every non-combining glyphs having the same width.
  - `sp-fixed` : Apply `sp-force-monospace` and `no-ligation` together.

* Style for controlling digits' (figures') style:
  - `default-to-old-style-figures`, `default-to-old-style-digits`: Default digit figures to old-style.
  - `default-to-lining-figures`, `default-to-lining-digits`: Default digit figures to lining.

<!-- BEGIN Section-Cherry-Picking-Predefined -->
<!-- THIS SECTION IS AUTOMATICALLY GENERATED. DO NOT EDIT. -->

* Styles for ligation sets, include:

  * `ligset-dlig`: Default ligation set would be assigned to Discretionary ligatures.
  * `ligset-clike`: Default ligation set would be assigned to C-Like.
  * `ligset-javascript`: Default ligation set would be assigned to JavaScript.
  * `ligset-php`: Default ligation set would be assigned to PHP.
  * `ligset-ml`: Default ligation set would be assigned to ML.
  * `ligset-fsharp`: Default ligation set would be assigned to F#.
  * `ligset-fstar`: Default ligation set would be assigned to F*.
  * `ligset-haskell`: Default ligation set would be assigned to Haskell.
  * `ligset-idris`: Default ligation set would be assigned to Idris.
  * `ligset-elm`: Default ligation set would be assigned to Elm.
  * `ligset-purescript`: Default ligation set would be assigned to PureScript.
  * `ligset-swift`: Default ligation set would be assigned to Swift.
  * `ligset-coq`: Default ligation set would be assigned to Coq.
  * `ligset-matlab`: Default ligation set would be assigned to Matlab.
  * `ligset-wolfram`: Default ligation set would be assigned to Wolfram Language (Mathematica).

<!-- END Section-Cherry-Picking-Predefined -->


<!-- BEGIN Section-Cherry-Picking-Ligation-Sets -->
<!-- THIS SECTION IS AUTOMATICALLY GENERATED. DO NOT EDIT. -->

* Styles for customizing the default (`calt`) ligation set. By choosing one or multiple items listed below, the ligation set of `calt` will *only* contain the corresponded ligations of the selectors you used.

  * `calt-center-ops`: Vertically align some of the operators (like `*`) to the center position it is before or after a "center" operator (like `+`).
  * `calt-arrow`: Enable ligation set that forms arrows.
  * `calt-arrow2`: Enable ligation for more arrows, like `>>=`.
  * `calt-trig`: Enable ligation for `<|`, `|>` , `<||`, and other bar-and-angle-bracket symbols.
  * `calt-eqeqeq`: Enable special ligation for `===` with triple lines.
  * `calt-eqeq`: Enable ligation for `==` and `===`.
  * `calt-ineq`: Enable ligation for `<=` and `>=`.
  * `calt-exeqeq`: Enable special ligation for `!==` with triple lines.
  * `calt-eqexeq`: Enable special ligation for `=!=` with triple lines.
  * `calt-eqexeq-dl`: Enable special ligation for `=!=` with double lines.
  * `calt-exeq`: Enable ligation for `!=` and `!==`.
  * `calt-exeq-alt-1`: Enable ligation for `!=` and `!==` with a dot at below for distinction.
  * `calt-tildeeq`: Enable ligation for `~=` as inequality.
  * `calt-eqslasheq`: Enable special triple-line ligation for `=/=` as inequality.
  * `calt-slasheq`: Enable ligation for `/=` and `=/=` as inequality.
  * `calt-ltgt-ne`: Enable ligation for `<>` as inequality.
  * `calt-ltgt-diamond`: Enable ligation for `<>` as diamond.
  * `calt-brst`: Center asterisk in `(*` and `*)`.
  * `calt-plusplus`: Enable ligation for `++` and further plus-chaining.
  * `calt-kern-dotty`: Move connecting dotty punctuations closer, like for `::`, `:::` and `...`.
  * `calt-logic`: Enable ligation for `/\` and `\/`.
  * `calt-llgg`: Enable ligation for `<<`, `>>` and other angle-bracket chaining.
  * `calt-llggeq`: Enable ligation for `<<=`, `>>=` as shift operator.
  * `calt-dotoper`: Treat dot (`.`) as operator and perform chained centering.
  * `calt-arrowZALE`: Treat `<=` as arrow.
  * `calt-arrowZAGE`: Treat `>=` as co-arrow.
  * `calt-html-comment`: Enable ligation for `<!--` and `<!---`.
  * `calt-colon-greater-as-colon-arrow`: Transform `:>` into `:` and a narrow arrow..

<!-- END Section-Cherry-Picking-Ligation-Sets -->


<!-- BEGIN Section-Stylistic-Sets -->
<!-- THIS SECTION IS AUTOMATICALLY GENERATED. DO NOT EDIT. -->

* Styles as stylistic sets:

  * `ss01`: Set character variant to “Andale Mono Style”.
  * `ss02`: Set character variant to “Anonymous Pro Style”.
  * `ss03`: Set character variant to “Consolas Style”.
  * `ss04`: Set character variant to “Menlo Style”.
  * `ss05`: Set character variant to “Fira Mono Style”.
  * `ss06`: Set character variant to “Liberation Mono Style”.
  * `ss07`: Set character variant to “Monaco Style”.
  * `ss08`: Set character variant to “Pragmata Pro Style”.
  * `ss09`: Set character variant to “Source Code Pro Style”.
  * `ss10`: Set character variant to “Envy Code R Style”.
  * `ss11`: Set character variant to “X Window Style”.
  * `ss12`: Set character variant to “Ubuntu Mono Style”.
  * `ss13`: Set character variant to “Lucida Style”.
  * `ss14`: Set character variant to “JetBrains Mono Style”.
  * `ss20`: Set character variant to “Curly Style”.

<!-- END Section-Stylistic-Sets -->


<!-- BEGIN Section-Cherry-Picking-Styles -->
<!-- THIS SECTION IS AUTOMATICALLY GENERATED. DO NOT EDIT. -->

* Styles for individual characters. They are easy-to-understand names of the `cv##` styles, including:

  * Styles for `a`:
    * `v-a-doublestorey`, `cv01`: Double-storey `a` (default for Upright).
    * `v-a-singlestorey`, `cv02`: Single-storey `a`.
    * `v-a-singlestorey-tailed`, `VXBS`: Single-storey `a` with curly tail (default for Italic).
    * `v-a-doublestorey-tailed`, `VXBU`: Double-storey `a` with curly tail.
    * `v-a-singlestorey-earless-corner`, `VXCL`: Earless (cornered top-right) single-storey `a`.
    * `v-a-singlestorey-earless-corner-tailed`, `VXCM`: Earless (cornered top-right) single-storey `a` with curly tail.
    * `v-a-singlestorey-earless-rounded`, `VXCN`: Earless (rounded top-right) single-storey `a`.
    * `v-a-singlestorey-earless-rounded-tailed`, `VXCO`: Earless (rounded top-right) single-storey `a` with curly tail.
    * `v-a-doublestorey-toothless-corner`, `VXDM`: Toothless (cornered bottom-right) double-storey `a`.
    * `v-a-doublestorey-toothless-rounded`, `VXDN`: Toothless (rounded bottom-right) double-storey `a`.
  * Styles for `b`:
    * `v-b-toothed`, `VXBK`: `b` with bottom-left tooth (default).
    * `v-b-toothless-corner`, `VXBL`: `b` without bottom-left tooth, with a corner transition.
    * `v-b-toothless-rounded`, `VXBM`: `b` without bottom-left tooth, with a rounded transition.
  * Styles for `d`:
    * `v-d-toothed`, `VXBN`: `d` with bottom-right tooth (default for Upright).
    * `v-d-toothless-corner`, `VXBO`: `d` without bottom-right tooth, with a corner transition.
    * `v-d-toothless-rounded`, `VXBP`: `d` without bottom-right tooth, with a rounded transition.
    * `v-d-tailed`, `VXBQ`: `d` with a slightly tail bottom-right tail (default for Italic).
  * Styles for `f`:
    * `v-f-straight`, `cv52`: `f` without bottom hook (default for Sans Upright).
    * `v-f-tailed`, `cv53`: `f` with a leftward bottom hook (default for Italic).
    * `v-f-serifed`, `cv84`: `f` with bottom serif (default for Slab Upright).
    * `v-f-straight-tailed`, `VXAD`: `f` with straight tail.
    * `v-f-flat-hook`, `VXDD`: `f` with flat hook.
    * `v-f-flat-hook-crossbar-at-x-height`, `VXEG`: `f` with flat hook and crossbar placed right at X-height.
    * `v-f-flat-hook-serifed`, `VXEV`: `f` with flat hook and bottom serif.
    * `v-f-flat-hook-serifed-crossbar-at-x-height`, `VXEW`: `f` with flat hook, bottom serif, and crossbar placed right at X-height.
  * Styles for `g`:
    * `v-g-doublestorey`, `cv11`: Double-storey `g`.
    * `v-g-singlestorey`, `cv12`: Single-storey `g` (default).
    * `v-g-opendoublestorey`, `cv24`: Open Double-storey `g`, like Trebuchet MS or Fira Code.
    * `v-g-earless-corner`, `VXCW`: Earless (cornered top-right) single-storey `g`.
    * `v-g-earless-rounded`, `VXCX`: Earless (rounded top-right) single-storey `g`.
  * Styles for `h`:
    * `v-h-straight`, `VXCB`: `h` with straight ending (default).
    * `v-h-tailed`, `VXCC`: `h` with curly tailed ending.
    * `v-h-motion-serifed-straight`, `VXEK`: `h` with straight ending.
    * `v-h-motion-serifed-tailed`, `VXEL`: `h` with curly tailed ending.
  * Styles for `i`:
    * `v-i-serifed`, `cv03`: Serifed `i` (default for Upright).
    * `v-i-italic`, `cv04`: Italic `i` (default for Italic).
    * `v-i-hooky`, `cv05`: Hooky `i`.
    * `v-i-zshaped`, `cv06`: Z-shaped `i`.
    * `v-i-line`, `cv56`: `i` like a straight line.
    * `v-i-tailed`, `cv88`: Tailed `i`.
    * `v-i-hookybottom`, `VXAA`: `i` with a straight tail.
    * `v-i-serifed-asymmetric`, `VXDK`: `i` with shorter top serif and full bottom serif.
  * Styles for `j`:
    * `v-j-line`, `cv57`: `j` like a straight line.
    * `v-j-serifed`, `cv58`: `j` with top serif (default).
    * `v-j-straight`, `cv98`: `j` without serif.
    * `v-j-flat-hook-serifed`, `VXDE`: undefined.
    * `v-j-flat-hook-serifless`, `VXDF`: undefined.
  * Styles for `k`, `K`:
    * `v-k-straight`, `cv68`: `k` and `K` with standard shape (default for Upright).
    * `v-k-curly`, `cv69`: Slightly curly `k` and `K`, like Iosevka 2.x.
    * `v-k-cursive`, `cv70`: `k` with a cursive loop, and `K` with standard shape (default for Italic).
    * `v-k-curly-cursive`, `VXBR`: `k` with a cursive loop, and `K` with curly shape.
  * Styles for `l`:
    * `v-l-serifed`, `cv07`: Serifed `l` (default for Upright).
    * `v-l-italic`, `cv08`: Italic, cursive `l` (default for Italic).
    * `v-l-hooky`, `cv09`: Hooky `l`.
    * `v-l-zshaped`, `cv10`: Z-shaped `l`.
    * `v-l-tailed`, `cv27`: `l` with a curved tail.
    * `v-l-hookybottom`, `cv28`: `l` with a straight tail.
    * `v-l-line`, `cv59`: `l` like a straight line.
    * `v-l-serifed-asymmetric`, `VXDL`: `l` with shorter top serif and full bottom serif.
  * Styles for `m`:
    * `v-m-normal`, `cv25`: `m` with normal middle leg, touching the baseline (default).
    * `v-m-shortleg`, `cv26`: `m` with shorter middle leg, like Ubuntu Mono.
    * `v-m-tailed`, `VXCD`: `m` with normal middle leg, touching the baseline, and a curly tail.
    * `v-m-shortleg-tailed`, `VXCE`: `m` with shorter middle leg, like Ubuntu Mono, and a curly tail.
    * `v-m-earless-corner-double-arch`, `VXDU`: Earless (corner top-left) `m` with normal middle leg touching baseline.
    * `v-m-earless-corner-double-arch-shortleg`, `VXDV`: Earless (corner top-left) `m` with a shorter middle leg like Ubuntu Mono.
    * `v-m-earless-corner-double-arch-tailed`, `VXDW`: Earless (corner top-left) `m` with normal middle leg touching baseline, and a curly tail.
    * `v-m-earless-corner-double-arch-shortleg-tailed`, `VXDX`: Earless (corner top-left) `m` with a shorter middle leg like Ubuntu Mono, and a curly tail.
    * `v-m-earless-rounded-double-arch`, `VXDY`: Earless (rounded top-left) `m` with normal middle leg touching baseline.
    * `v-m-earless-rounded-double-arch-shortleg`, `VXDZ`: Earless (rounded top-left) `m` with a shorter middle leg like Ubuntu Mono.
    * `v-m-earless-rounded-double-arch-tailed`, `VXEA`: Earless (rounded top-left) `m` with normal middle leg touching baseline, and a curly tail.
    * `v-m-earless-rounded-double-arch-shortleg-tailed`, `VXEB`: Earless (rounded top-left) `m` with a shorter middle leg like Ubuntu Mono, and a curly tail.
    * `v-m-earless-single-arch`, `VXEC`: Earless (single-arch) `m` with normal middle leg touching baseline.
    * `v-m-earless-single-arch-shortleg`, `VXED`: Earless (single-arch) `m` with a shorter middle leg like Ubuntu Mono.
    * `v-m-earless-single-arch-tailed`, `VXEE`: Earless (single-arch) `m` with normal middle leg touching baseline, and a curly tail.
    * `v-m-earless-single-arch-shortleg-tailed`, `VXEF`: Earless (single-arch) `m` with a shorter middle leg like Ubuntu Mono, and a curly tail.
    * `v-m-motion-serifed`, `VXEM`: `m` with motion serifs, normal middle leg touching baseline.
    * `v-m-motion-serifed-shortleg`, `VXEN`: `m` with motion serifs, a shorter middle leg like Ubuntu Mono.
    * `v-m-motion-serifed-tailed`, `VXEO`: `m` with motion serifs, normal middle leg touching baseline, and a curly tail.
    * `v-m-motion-serifed-shortleg-tailed`, `VXEP`: `m` with motion serifs, a shorter middle leg like Ubuntu Mono, and a curly tail.
  * Styles for `n`:
    * `v-n-straight`, `VXCF`: `n` with straight ending (default).
    * `v-n-tailed`, `VXCG`: `n` with a curly tail.
    * `v-n-earless-corner-straight`, `VXDO`: Earless (corner top-left) `n` with straight ending.
    * `v-n-earless-corner-tailed`, `VXDP`: Earless (corner top-left) `n` with a curly tail.
    * `v-n-earless-rounded-straight`, `VXDQ`: Earless (rounded top-left) `n` with straight ending.
    * `v-n-earless-rounded-tailed`, `VXDR`: Earless (rounded top-left) `n` with a curly tail.
    * `v-n-motion-serifed-straight`, `VXEQ`: `n` with motion serifs and straight ending.
    * `v-n-motion-serifed-tailed`, `VXER`: `n` with motion serifs and a curly tail.
  * Styles for `p`:
    * `v-p-eared`, `VXCP`: `p` with top-left ear (default).
    * `v-p-earless-corner`, `VXCQ`: `p` without top-left ear (corner).
    * `v-p-earless-rounded`, `VXCR`: `p` without top-left ear (rounded).
    * `v-p-motion-serifed`, `VXES`: `p` with motion serifs.
  * Styles for `q`:
    * `v-q-straight`, `VXAZ`: `q` with straight bar (default).
    * `v-q-tailed`, `VXBA`: `q` with tail.
    * `v-q-earless-corner`, `VXCS`: Earless (cornered top-left) single-storey `q`.
    * `v-q-earless-corner-tailed`, `VXCT`: Earless (cornered top-left) single-storey `q` with curly tail.
    * `v-q-earless-rounded`, `VXCU`: Earless (rounded top-left) single-storey `q`.
    * `v-q-earless-rounded-tailed`, `VXCV`: Earless (rounded top-left) single-storey `q` with curly tail.
  * Styles for `r`:
    * `v-r-straight`, `cv85`: Straight, serif-less `r` (default for Sans).
    * `v-r-serifed`, `cv86`: `r` with serif at both top and bottom (default for Slab Upright).
    * `v-r-top-serifed`, `cv87`: `r` with serifs at top-left only (default for Slab Italic).
    * `v-r-earless-corner`, `VXDS`: Earless (corner top-left), serif-less `r`.
    * `v-r-earless-rounded`, `VXDT`: Earless (rounded top-left), serif-less `r`.
  * Styles for `t`:
    * `v-t-standard`, `cv40`: Standard `t` shape (default).
    * `v-t-cross`, `cv41`: Futura-like `t` shape.
    * `v-t-flat-hook`, `VXDC`: `t` with flat hook.
    * `v-t-hookless-asymmetric`, `VXEH`: `t` without hook and ony half the cross bar.
    * `v-t-flat-hook-short-neck`, `VXEI`: `t` with flat hook and a slightly shorter neck.
    * `v-t-flat-hook-short-neck2`, `VXEJ`: `t` with flat hook and a more shorter neck.
  * Styles for `u`:
    * `v-u-with-bar`, `cv89`: Normal `u` with right bar (default for Upright).
    * `v-u-without-bar`, `cv90`: Normal `u` without right bar, like a smaller uppercase `U`.
    * `v-u-tailed`, `VXBT`: `u` with right bar and a slightly curly tail (default for Italic).
    * `v-u-motion-serifed`, `VXET`: Normal `u` with right bar and motion serifs.
    * `v-u-motion-serifed-tailed`, `VXEU`: `u` with right bar, motion serifs and a slightly curly tail.
  * Styles for `v`, `V`:
    * `v-v-straight`, `cv71`: Standard, straight `V` and `v` (default).
    * `v-v-curly`, `cv72`:  Slightly curly `V` and `v`, like Iosevka 2.x.
  * Styles for `w`, `W`:
    * `v-w-straight`, `cv75`: Standard, straight `W` and `w` (default).
    * `v-w-curly`, `cv76`: Slightly curly `W` and `w`, like Iosevka 2.x.
    * `v-w-straight-flat-top`, `VXCH`: Standard, straight `W` and `w`, and the middle is forced to be aligned the top.
  * Styles for `x`, `X`:
    * `v-x-straight`, `cv77`: Standard, straight `X` and `x` (default).
    * `v-x-curly`, `cv78`: Slightly curly `X` and `x`, like Iosevka 2.x.
  * Styles for `y`:
    * `v-y-straight`, `cv48`: Letter `y` that is fully straight (default for Sans Upright).
    * `v-y-cursive`, `cv49`: Cursive-like `y` (default for Italic).
    * `v-y-curly`, `cv79`: More curly letter `y`, like Iosevka 2.x.
    * `v-y-straight-turn`, `VXBF`: Letter `y` with straight upper and a tail turns leftward (default for Slab Upright).
  * Styles for `z`:
    * `v-z-standard`, `VXBD`: Standard `Z` and `z` (default).
    * `v-z-with-crossbar`, `VXBE`: `Z` and `z` with a diagonal cross bar for better dsitinction with `2`.
    * `v-z-with-horizontal-crossbar`, `VXBX`: `Z` and `z` with a horizontal cross bar for better dsitinction with `2`.
  * Styles for `A`, `Λ`, `Δ`:
    * `v-turn-v-straight`, `cv73`: Standard, straight `A`, `Λ`, `Δ` (default).
    * `v-turn-v-curly`, `cv74`: Slightly curly `A`, `Λ`, `Δ`, like Iosevka 2.x.
  * Styles for `B`:
    * `v-capital-b-standard`, `VXAP`: Standard `B` (default).
    * `v-capital-b-more-asymmetric`, `VXAQ`: More asymmetric `B` to differentiate with `8`.
  * Styles for `D`:
    * `v-capital-d-standard`, `VXBG`: Standard `D` (default).
    * `v-capital-d-more-rounded`, `VXBH`: More rounded `D` to differentiate with `O`.
  * Styles for `G`:
    * `v-capital-g-tooth`, `cv91`: Toothed G (default).
    * `v-capital-g-toothless`, `cv92`: Toothless G.
  * Styles for `J`:
    * `v-capital-j-serifless`, `VXBY`: J without top serif.
    * `v-capital-j-serifed`, `VXBZ`: J with top serif at left side (default).
    * `v-capital-j-serifed-both-sides`, `VXDA`: J with symmetric at both sides.
    * `v-capital-j-serifed-symmetric`, `VXDB`: J with symmetric at both sides and is symmetric.
  * Styles for `M`:
    * `v-capital-m-hanging`, `VXCI`: `M` with middle being hanging off baseline (default).
    * `v-capital-m-flat-bottom`, `VXCJ`: `M` with middle aligned to baseline.
  * Styles for `Q`:
    * `v-capital-q-taily`, `cv42`: `Q` with a curly tail (default).
    * `v-capital-q-straight`, `cv43`: `Q` with a straight tail like in the old versions.
    * `v-capital-q-crossing`, `VXCA`: `Q` with a tail crossing the ring.
  * Styles for `R`:
    * `v-capital-r-straight`, `cv82`: Standard, straight-leg `R` (default).
    * `v-capital-r-curly`, `cv83`:  Slightly curly-legged `R`, like Iosevka 2.x.
  * Styles for `Y`:
    * `v-capital-y-straight`, `cv80`: Standard, straight `Y` (default).
    * `v-capital-y-curly`, `cv81`: Slightly curly `Y`, like Iosevka 2.x.
  * Styles for `0`:
    * `v-zero-slashed`, `cv13`: Slashed Zero `0` (default).
    * `v-zero-dotted`, `cv14`: Dotted Zero `0`.
    * `v-zero-unslashed`, `cv15`: O-like `0`.
    * `v-zero-reverse-slashed`, `cv93`: Reverse-slashed `0`.
    * `v-zero-long-dotted`, `VXAB`: Long-dotted Zero `0` like Hack.
  * Styles for `1`:
    * `v-one-nobase`, `cv50`: `1` with bottom serif (default for Sans).
    * `v-one-base`, `cv51`: `1` without bottom serif (default for Slab).
    * `v-one-line`, `VXAM`: `1` drawn just like a straight line.
  * Styles for `3`:
    * `v-three-flattop`, `cv46`: Flat top `3` (Like Museo Sans / Montserrat).
    * `v-three-twoarcs`, `cv47`: Arched top `3` (default).
  * Styles for `4`:
    * `v-four-closed`, `VXAR`: `4` with closed contour (default).
    * `v-four-closed-non-crossing`, `VXAS`: `4` with closed contour but the horizontal bar does not overflow the vertical bar.
    * `v-four-semi-open`, `VXAT`: `4` with semi-open contour.
    * `v-four-semi-open-non-crossing`, `VXAU`: `4` with semi-open contour but the horizontal bar does not overflow the vertical bar.
    * `v-four-open`, `VXAV`: `4` with open contour.
    * `v-four-open-non-crossing`, `VXAW`: `4` with open contour but the horizontal bar does not overflow the vertical bar.
  * Styles for `6`:
    * `v-six-closed-contour`, `VXAE`: `6` with a more closed contour.
    * `v-six-open-contour`, `VXAF`: `6` with a more open contour.
    * `v-six-straight-bar`, `VXBB`: `6` with a straight bar (default).
  * Styles for `7`:
    * `v-seven-noserif`, `cv64`: `7` without serif (default for Sans).
    * `v-seven-serifed`, `cv65`: `7` with initial serif (default for Slab).
    * `v-seven-crossbar`, `VXAX`: `7` with crossbar.
    * `v-seven-crossbar-serifed`, `VXAY`: `7` with crossbar and initial serif.
  * Styles for `9`:
    * `v-nine-closed-contour`, `cv96`: `9` with a more closed contour.
    * `v-nine-open-contour`, `cv97`: `9` with a more open contour.
    * `v-nine-straight-bar`, `VXBC`: `9` with a straight bar (default).
  * Styles for `ß`:
    * `v-eszet-traditional`, `cv34`: Traditional, Fraktur-like Eszet.
    * `v-eszet-sulzbacher`, `cv35`: A more modern, beta-like Eszet (default).
    * `v-eszet-longs-s-lig`, `VXAC`: An Eszet shown as a ligature of long-S (`ſ`) and `s`.
  * Styles for `λ`:
    * `v-lambda-straight`, `cv94`: More-straight letter `λ` (default).
    * `v-lambda-curly`, `cv95`: More curly letter `λ`, like Iosevka 2.x.
  * Styles for `~`:
    * `v-tilde-high`, `cv16`: Higher tilde `~`.
    * `v-tilde-low`, `cv17`: Lower tilde `~` (default).
  * Styles for `*`:
    * `v-asterisk-high`, `cv18`: Higher five-pointed asterisk `*` (default).
    * `v-asterisk-low`, `cv19`: Lower five-pointed asterisk `*`.
    * `v-asterisk-hexhigh`, `cv60`: Higher six-pointed asterisk `*`.
    * `v-asterisk-hexlow`, `cv61`: Lower six-pointed asterisk `*`.
    * `v-asterisk-flip-penta-high`, `VXBV`: Higher five-pointed and turned asterisk `*`.
    * `v-asterisk-flip-penta-low`, `VXBW`: Lower five-pointed and turned asterisk `*`.
  * Styles for `_`:
    * `v-underscore-high`, `cv20`: Higher underscore `_`, placed right below baseline (default).
    * `v-underscore-low`, `cv21`: Lower underscore `_`, placed right above descender line.
    * `v-underscore-above-baseline`, `cv99`: Extra-high `_`, placed right below baseline.
  * Styles for `¶`:
    * `v-paragraph-high`, `cv22`: Higher paragraph symbol `¶` (default).
    * `v-paragraph-low`, `cv23`: Lower paragraph symbol `¶`.
  * Styles for `^`:
    * `v-caret-high`, `cv29`: Higher circumflex `^` (default).
    * `v-caret-low`, `cv30`: Lower circumflex `^`.
  * Styles for `(`, `)`:
    * `v-paren-normal`, `VXAN`: Parenthesis with normal contour (default).
    * `v-paren-large-contour`, `VXAO`: Parenthesis with larger contour, like that in Monaco.
  * Styles for `{`, `}`:
    * `v-brace-straight`, `cv36`: More straight braces.
    * `v-brace-curly`, `cv37`: More curly braces (default).
  * Styles for `#`:
    * `v-numbersign-upright`, `cv44`: Number sign with vertical bars (default).
    * `v-numbersign-slanted`, `cv45`: Number sign with slanted bars.
    * `v-numbersign-upright-open`, `VXBI`: Number sign with vertical bars and open inner.
    * `v-numbersign-slanted-open`, `VXBJ`: Number sign with slanted bars and open inner.
  * Styles for `&`:
    * `v-ampersand-closed`, `VXAG`: Ampersand (`&`) with a closed contour (default).
    * `v-ampersand-upper-open`, `VXAH`: Ampersand (`&`) with an open contour at upper half.
    * `v-ampersand-lower-open`, `VXAI`: Ampersand (`&`) with an open contour at lower half.
    * `v-ampersand-et`, `VXAJ`: Ampersand (`&`) drawn like a ligature of Ɛ and t.
    * `v-ampersand-et-toothed`, `VXAK`: Ampersand (`&`) drawn like a ligature of Ɛ and t with tooth.
    * `v-ampersand-flat-top`, `VXAL`: Ampersand (`&`) drawn with a flat top.
  * Styles for `@`:
    * `v-at-threefold`, `cv31`: The long, three-fold At symbol (`@`) (default).
    * `v-at-fourfold`, `cv32`: The traditional, four-fold At symbol (`@`).
    * `v-at-short`, `cv33`: The shorter, Fira-like At symbol (`@`).
  * Styles for `$`:
    * `v-dollar-open`, `cv38`: Dollar symbol with open contour.
    * `v-dollar-through`, `cv39`: Dollar symbol with strike-through vertical bar (default).
    * `v-dollar-opencap`, `cv54`: Dollar symbol with open contour, not exceeding baseline and ascender.
    * `v-dollar-throughcap`, `cv55`: Dollar symbol with strike-through vertical bar, not exceeding baseline and ascender.
  * Styles for `%`:
    * `v-percent-dots`, `cv62`: Percent `%`, Per-mille `‰` and basis point `‱` using rectangular dots.
    * `v-percent-rings`, `cv63`: Percent `%` with rings and broken bar; Per-mille `‰` and basis point `‱` with rings (default).
    * `v-percent-rings-connected`, `VXCK`: Percent `%`, Per-mille `‰` and basis point `‱` using rings and continuous bar.
  * Styles for `|`:
    * `v-bar-natural-slope`, `VXCY`: Bar punctuations (`|`) has a natural slope under italics and oblique (default).
    * `v-bar-force-upright`, `VXCZ`: Bar punctuations (`|`) is forced upright under italics and oblique.
  * Styles for `<=`, `>=`:
    * `v-lig-ltgteq-flat`, `cv66`: The lower bar of `<=` and `>=` ligation is flat (default).
    * `v-lig-ltgteq-slanted`, `cv67`: The lower bar of `<=` and `>=` ligation is slanted.
  * Styles for `'`:
    * `v-ascii-quote-straight`, `VXDG`: Show ASCII quote (`'`) as short vertical straight bar. (default).
    * `v-ascii-quote-raised-comma`, `VXDH`: Show ASCII quote (`'`) as raised comma..
  * Styles for ```:
    * `v-ascii-grave-straight`, `VXDI`: Show ASCII grave (`` ` ``) as short diagonal straight bar. (default).
    * `v-ascii-grave-raised-inverse-comma`, `VXDJ`: Show ASCII grave (`` ` ``) as raised comma..

<!-- END Section-Cherry-Picking-Styles -->

### Using Docker

Refer to these [instructions.](https://github.com/ejuarezg/containers/tree/master/iosevka_font#container-method-1)

## For Chinese and Japanese users...

→ [Sarasa Gothic](https://github.com/be5invis/Sarasa-Gothic).

---

![Family Matrix](https://raw.githubusercontent.com/be5invis/Iosevka/master/images/matrix.png)
