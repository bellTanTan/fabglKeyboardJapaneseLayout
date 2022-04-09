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

5. Arduino/libraries/FabGL/src/devdrivers/kbdlayouts.cpp

