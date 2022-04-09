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
4. Arduino/libraries/FabGL/src/devdrivers/kbdlayouts.cpp

