# fabglKeyboardJapaneseLayout
Add Japanese keyboard layout to fabgl library

3つのファイルを改定します。

1. Arduino/libraries/FabGL/src/fabutils.h

    1323 VK_MU,              /**< Mu         : µ */  
    1324    
    1325  VK_HANKAKU_ZENKAKU_KANJI,  
    1326                      /**< 半角/全角/漢字 */  
    1327  VK_YEN,             /**< YEN: ￥ */  
    1328  VK_MUHENKAN,        /**< 無変換 */  
    1329  VK_HENKAN,          /**< 変換 */  
    1330  VK_KATAKANA_HIRAGANA_ROMAJI,  
    1331                      /**< カタカナ/ひらがな/ローマ字 */  
  
2. Arduino/libraries/FabGL/src/devdrivers/kbdlayouts.h

    114 /** @brief Belgian keyboard layout */  
    115 extern const KeyboardLayout BelgianLayout;  
    116  
    117 /** @brief Japanese keyboard layout */  
    118 extern const KeyboardLayout JapaneseLayout;  
    119  
    120  
    121 struct SupportedLayouts {  
    122 
    123 static constexpr int LAYOUTSCOUNT = 8;  
    124  
    125 static int count()               { return LAYOUTSCOUNT; }  
    126  
    127 static char const * * names() {  
    128 static char const * NAMES[LAYOUTSCOUNT] =  {  
    129     GermanLayout.desc,  
    130     ItalianLayout.desc,  
    131     UKLayout.desc,  
    132     USLayout.desc,  
    133     SpanishLayout.desc,  
    134     FrenchLayout.desc,  
    135     BelgianLayout.desc,  
    136     JapaneseLayout.desc,  
    137 };  
    138 return NAMES;  
    139 }  
    140  
    141 static char const * * shortNames() {  
    142 static char const * SNAMES[LAYOUTSCOUNT] = {  
    143     GermanLayout.name,  
    144     ItalianLayout.name,  
    145     UKLayout.name,  
    146     USLayout.name,  
    147     SpanishLayout.name,  
    148     FrenchLayout.name,  
    149     BelgianLayout.name,  
    150     JapaneseLayout.name,  
    151 };  
    152 return SNAMES;  
    153 }  
    154  
    155 static const KeyboardLayout * * layouts() {  
    156     static KeyboardLayout const * LAYOUTS[LAYOUTSCOUNT] = {  
    157     &GermanLayout,  
    158     &ItalianLayout,  
    159     &UKLayout,  
    160     &USLayout,  
    161     &SpanishLayout,  
    162     &FrenchLayout,  
    163     &BelgianLayout,  
    164     &JapaneseLayout,  
    165 };  
    166 return LAYOUTS;  
    167 }  
   
