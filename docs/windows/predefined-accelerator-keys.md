---
title: アクセラレータキー (C++)
ms.date: 02/14/2019
helpviewer_keywords:
- accelerator keys
- keyboard shortcuts
- keyboard shortcuts [C++], predefined
- menus [C++], shortcut keys
- keyboard shortcuts [C++], menu association
ms.assetid: f234c5f2-4ec3-4c9e-834a-b5dd297625b9
ms.openlocfilehash: beb4e878138da3dc2905c86e18fedc658d7ceecf
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80215151"
---
# <a name="accelerator-keys-c"></a>アクセラレータキー (C++)

## <a name="predefined-accelerator-keys"></a>定義済みのアクセラレータ キー

Windows アプリケーション プロジェクトの一部として使用できるいくつかの定義済みのアクセラレータ キーがあります。 これらの仮想キーの一部は、Windows 環境用です。 他のユーザーは、ブラウザーまたは Unicode アプリケーションをサポートします。 どのアクセラレータでもこれらのキーを使用できます。

|Key|説明|
|---------|-----------------|
|VK_ACCEPT|(IME) accept|
|VK_BROWSER_BACK|ウィンドウブラウザー、**戻る**キー|
|VK_BROWSER_FAVORITES|ウィンドウブラウザー、**お気に入り**キー|
|VK_BROWSER_FORWARD|ウィンドウブラウザー、**転送**キー|
|VK_BROWSER_HOME|ウィンドウブラウザー、**スタート**および**ホーム**キー|
|VK_BROWSER_REFRESH|ウィンドウブラウザー、キーの**更新**|
|VK_BROWSER_SEARCH|ウィンドウブラウザー、**検索**キー|
|VK_BROWSER_STOP|ウィンドウブラウザー、**ストップ**キー|
|VK_CONVERT|(IME) 変換|
|VK_FINAL|(IME) 最終モード|
|VK_HANGUEL|英数ハングルモード (互換性のために維持され、VK_HANGUL を使用)|
|VK_HANGUL|英数ハングルモード|
|VK_HANJA|英数Hanja モード|
|VK_JUNJA|英数Junja モード|
|VK_KANA|英数かなモード|
|VK_KANJI|英数漢字モード|
|VK_LAUNCH_APP1|ウィンドウ**アプリケーション 1**キーの開始|
|VK_LAUNCH_APP2|ウィンドウ**アプリケーション 2**キーの開始|
|VK_LAUNCH_MAIL|ウィンドウ**メール**キーの開始|
|VK_LAUNCH_MEDIA_SELECT|ウィンドウ**メディア**キーの選択|
|VK_LCONTROL|**左 Ctrl**キー|
|VK_LMENU|**左側のメニュー**キー|
|VK_LSHIFT|**左シフト**キー|
|VK_MEDIA_NEXT_TRACK|ウィンドウ**次のトラック**キー|
|VK_MEDIA_PLAY_PAUSE|ウィンドウ**メディアキーの再生/一時停止**|
|VK_MEDIA_PREV_TRACK|ウィンドウ**前のトラック**キー|
|VK_MEDIA_STOP|ウィンドウ**メディア**キーの停止|
|VK_MODECHANGE|(IME) モードの変更要求|
|VK_NONCONVERT|(IME) 非変換|
|VK_OEM_1|ウィンドウ米国標準キーボードの場合 **:** キー|
|VK_OEM_102|ウィンドウRT 102-key キーボードの山かっこキーまたは円記号キーのいずれか|
|VK_OEM_2|ウィンドウ米国標準キーボードでは、 **/?** key|
|VK_OEM_3|ウィンドウ米国標準キーボードの場合、 **`~** キー|
|VK_OEM_4|ウィンドウ米国標準キーボードの場合、 **[{** キー|
|VK_OEM_5|ウィンドウ米国標準キーボードの場合、 **\\&#124;** キー|
|VK_OEM_6|ウィンドウ米国標準キーボードの場合は、 **}** キー|
|VK_OEM_7|ウィンドウ米国標準キーボードでは、' 一重引用符/二重引用符 ' キー|
|VK_OEM_COMMA|ウィンドウ任意の国/地域**の場合、キー**|
|VK_OEM_MINUS|ウィンドウ任意の国/地域について、 **-** キー|
|VK_OEM_PERIOD|ウィンドウ国/地域については、「」を使用**します。** key|
|VK_OEM_PLUS|ウィンドウ任意の国/地域について、 **+** キー|
|VK_PACKET|ウィンドウキーストロークであるかのように Unicode 文字を渡すために使用されます。|
|VK_RCONTROL|**右 Ctrl**キー|
|VK_RMENU|**右のメニュー**キー|
|VK_RSHIFT|**右シフト**キー|
|VK_SLEEP|**コンピューターのスリープ**キー|
|VK_VOLUME_DOWN|ウィンドウ**音量ダウン**キー|
|VK_VOLUME_MUTE|ウィンドウ**音量ミュート**キー|
|VK_VOLUME_UP|ウィンドウ**音量アップ**キー|
|VK_XBUTTON1|ウィンドウ**X1**マウスボタン|
|VK_XBUTTON2|ウィンドウ**X2**マウスボタン|

## <a name="accelerator-key-association"></a>アクセラレータキーの関連付け

メニュー項目とキーボードの組み合わせで同じプログラム コマンドを発行したいと思うことはよくあります。 この操作を行うには、同じリソース識別子 (ID) をメニュー項目に、アプリケーションのアクセラレータテーブルのエントリに割り当てます。 次に、メニュー項目のキャプションを編集して、アクセラレータの名前を表示します。 メニュー項目とアクセラレータキーの詳細については、「[メニューコマンド](../windows/associating-a-menu-command-with-an-accelerator-key.md)」を参照してください。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>参照

[アクセラレータ エディター](../windows/accelerator-editor.md)<br/>
