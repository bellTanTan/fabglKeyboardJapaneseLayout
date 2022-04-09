# fabglKeyboardJapaneseLayout
Add Japanese keyboard layout to fabgl library

3つのファイルを改定します。

1. Arduino/libraries/FabGL/src/fabutils.h

	$ diff fabutils.h fabutils.h.org<br>
	1314,1321d1313<br>
	<   VK_HANKAKU_ZENKAKU_KANJI,<br>
	<                       /**< 半角/全角/漢字 */<br>
	<   VK_YEN,             /**< YEN: ￥ */<br>
	<   VK_MUHENKAN,        /**< 無変換 */<br>
	<   VK_HENKAN,          /**< 変換 */<br>
	<   VK_KATAKANA_HIRAGANA_ROMAJI,<br>
	<                       /**< カタカナ/ひらがな/ローマ字 */<br>

3. Arduino/libraries/FabGL/src/devdrivers/kbdlayouts.h

	$ diff kbdlayouts.h kbdlayouts.h.org<br>
	117,119d116<br>
	< /** @brief Japanese keyboard layout */<br>
	< extern const KeyboardLayout JapaneseLayout;<br>
	< <br>
	123c120<br>
	<   static constexpr int LAYOUTSCOUNT = 8;<br>
	---<br>
	>   static constexpr int LAYOUTSCOUNT = 7;<br>
	136d132<br>
	<         JapaneseLayout.desc,<br>
	150d145<br>
	<         JapaneseLayout.name,<br>
	164d158<br>
	<         &JapaneseLayout,<br>

4. Arduino/libraries/FabGL/src/devdrivers/kbdlayouts.cpp

	$ diff kbdlayouts.cpp kbdlayouts.cpp.org<br>
	939,999d938<br>
	< /**************************************************************************************/<br>
	< /* Japanese LAYOUT                                                                    */<br>
	< /**************************************************************************************/<br>
	< const KeyboardLayout JapaneseLayout {<br>
	<   // name<br>
	<   "JP",<br>
	< <br>
	<   // desc<br>
	<   "Japanese",<br>
	< <br>
	<   // inherited layout<br>
	<   &USLayout,<br>
	< 
	<   // single byte scancodes<br>
	<   {<br>
	<     { 0x0E, VK_HANKAKU_ZENKAKU_KANJI },<br>
	<     { 0x55, VK_CARET },<br>
	<     { 0x54, VK_AT },<br>
	<     { 0x5B, VK_LEFTBRACKET },<br>
	<     { 0x5D, VK_RIGHTBRACKET },<br>
	<     { 0x52, VK_COLON },<br>
	<     { 0x6A, VK_YEN },<br>
	<     { 0x51, VK_BACKSLASH },<br>
	<     { 0x67, VK_MUHENKAN },<br>
	<     { 0x64, VK_HENKAN },<br>
	<     { 0x13, VK_KATAKANA_HIRAGANA_ROMAJI },<br>
	<   },<br>
	< <br>
	<   // extended scancodes (0xE0..)<br>
	<   {<br>
	<   },<br>
	< <br>
	<   // virtual keys generated by other virtual keys combinations<br>
	<   //  in_key, { CTRL, LALT, RALT, SHIFT }, out_key<br>
	<   {<br>
	<     { VK_2,            { 0, 0, 0, 1 }, VK_QUOTEDBL },     // SHIFT "2" = """<br>
	<     { VK_6,            { 0, 0, 0, 1 }, VK_AMPERSAND },    // SHIFT "6" = "&"<br>
	<     { VK_7,            { 0, 0, 0, 1 }, VK_QUOTE },        // SHIFT "7" = "'"<br>
	<     { VK_8,            { 0, 0, 0, 1 }, VK_LEFTPAREN },    // SHIFT "8" = "("<br>
	<     { VK_9,            { 0, 0, 0, 1 }, VK_RIGHTPAREN },   // SHIFT "9" = ")"<br>
	<     { VK_0,            { 0, 0, 0, 1 }, VK_TILDE },        // SHIFT "0" = "~"<br>
	<     { VK_MINUS,        { 0, 0, 0, 1 }, VK_EQUALS },       // SHIFT "-" = "="<br>
	<     { VK_CARET,        { 0, 0, 0, 1 }, VK_TILDE },        // SHIFT "^" = "~"<br>
	<     { VK_YEN,          { 0, 0, 0, 1 }, VK_VERTICALBAR },  // SHIFT "￥" = "|"<br>
	<     { VK_AT,           { 0, 0, 0, 1 }, VK_GRAVEACCENT },  // SHIFT "@" = "`"<br>
	<     { VK_SEMICOLON,    { 0, 0, 0, 1 }, VK_PLUS },         // SHIFT ";" = "+"<br>
	<     { VK_COLON,        { 0, 0, 0, 1 }, VK_ASTERISK },     // SHIFT ":" = "*"<br>
	<     { VK_BACKSLASH,    { 0, 0, 0, 1 }, VK_UNDERSCORE },   // SHIFT "\" = "_"<br>
	<   },<br>
	< <br>
	<   // deadkeys<br>
	<   {<br>
	<   },<br>
	< <br>
	<   // deadkeys translation<br>
	<   {<br>
	<   },<br>
	< };<br>
