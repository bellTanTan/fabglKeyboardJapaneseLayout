# fabglKeyboardJapaneseLayout
Add Japanese keyboard layout to fabgl library

3つのファイルを改定します。

1. Arduino/libraries/FabGL/src/fabutils.h

	$ diff fabutils.h fabutils.h.org
	1314,1321d1313
	<   VK_HANKAKU_ZENKAKU_KANJI,
	<                       /**< 半角/全角/漢字 */
	<   VK_YEN,             /**< YEN: ￥ */
	<   VK_MUHENKAN,        /**< 無変換 */
	<   VK_HENKAN,          /**< 変換 */
	<   VK_KATAKANA_HIRAGANA_ROMAJI,
	<                       /**< カタカナ/ひらがな/ローマ字 */

3. Arduino/libraries/FabGL/src/devdrivers/kbdlayouts.h
4. Arduino/libraries/FabGL/src/devdrivers/kbdlayouts.cpp

