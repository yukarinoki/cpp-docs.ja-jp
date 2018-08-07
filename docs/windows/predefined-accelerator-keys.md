---
title: 定義済みのアクセラレータ キー |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.accelerator
dev_langs:
- C++
helpviewer_keywords:
- accelerator keys
- keyboard shortcuts
- keyboard shortcuts, predefined
ms.assetid: f234c5f2-4ec3-4c9e-834a-b5dd297625b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 42f1151f90fa6a418564f30b9ec6570645a91b42
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608418"
---
# <a name="predefined-accelerator-keys"></a>定義済みのアクセラレータ キー
Windows アプリケーション プロジェクトの一部として使用できるいくつかの定義済みのアクセラレータ キーがあります。 これらの仮想キーの一部は、Windows 環境用です。 その他の仮想キーは、ブラウザーや Unicode アプリケーションで使用できます。 どのアクセラレータでもこれらのキーを使用できます。  
  
|キー|説明|  
|---------|-----------------|  
|VK_ACCEPT|IME 使用可能|  
|VK_BROWSER_BACK|Windows: ブラウザーの戻るキー|  
|VK_BROWSER_FAVORITES|Windows: ブラウザーのお気に入りキー|  
|VK_BROWSER_FORWARD|Windows: ブラウザーの進むキー|  
|VK_BROWSER_HOME|Windows: ブラウザーのスタートとホーム キー|  
|VK_BROWSER_REFRESH|Windows: ブラウザーの更新キー|  
|VK_BROWSER_SEARCH|Windows: ブラウザーの検索キー|  
|VK_BROWSER_STOP|Windows: ブラウザーの停止キー|  
|VK_CONVERT|IME 変換|  
|VK_FINAL|IME Final モード|  
|VK_HANGUEL|IME ハングル モード (互換性のために残されています。VK_HANGUL を使用してください) |  
|VK_HANGUL|IME ハングル モード|  
|VK_HANJA|IME Hanja モード|  
|VK_JUNJA|IME Junja モード|  
|VK_KANA|IME かなモード|  
|VK_KANJI|IME 漢字モード|  
|VK_LAUNCH_APP1|Windows: アプリケーション 1 の起動キー|  
|VK_LAUNCH_APP2|Windows: アプリケーション 2 の起動キー|  
|VK_LAUNCH_MAIL|Windows: メールの起動キー|  
|VK_LAUNCH_MEDIA_SELECT|Windows: メディアの選択キー|  
|VK_LCONTROL|左 Ctrl キー|  
|VK_LMENU|左 Alt キー|  
|VK_LSHIFT|左 Shift キー|  
|VK_MEDIA_NEXT_TRACK|Windows: 次のトラック キー|  
|VK_MEDIA_PLAY_PAUSE|Windows: メディアの再生/一時停止キー|  
|VK_MEDIA_PREV_TRACK|Windows: 前のトラック キー|  
|VK_MEDIA_STOP|Windows: メディアの停止キー|  
|VK_MODECHANGE|IME モード変更要求|  
|VK_NONCONVERT|IME 無変換|  
|VK_OEM_1|Windows: 標準的な US キーボードの ";:" キー|  
|VK_OEM_102|Windows: RT 102 Key キーボードの山かっこキーまたはバックスラッシュ キー|  
|VK_OEM_2|Windows: 米国標準キーボードの「/?」 key|  
|VK_OEM_3|Windows: 標準的な US キーボードの "`~" キー|  
|VK_OEM_4|Windows: 標準的な US キーボードの "[{" キー|  
|VK_OEM_5|Windows: 米国標準キーボードの '\\&#124;' キー|  
|VK_OEM_6|Windows: 標準的な US キーボードの "]}" キー|  
|VK_OEM_7|Windows: 標準的な US キーボードの "単一の引用符と二重引用符" キー|  
|VK_OEM_COMMA|Windows: すべての国/地域の "," キー|  
|VK_OEM_MINUS|Windows: すべての国/地域の "-" キー|  
|VK_OEM_PERIOD|Windows: すべての国/地域の "." キー|  
|VK_OEM_PLUS|Windows: すべての国/地域の "+" キー|  
|VK_PACKET|Windows: Unicode 文字をキーストロークであるかのように渡すために使用|  
|VK_RCONTROL|右 Ctrl キー|  
|VK_RMENU|右 Alt キー|  
|VK_RSHIFT|右 Shift キー|  
|VK_SLEEP|コンピューターのスリープ キー|  
|VK_VOLUME_DOWN|Windows: 音量下げるキー|  
|VK_VOLUME_MUTE|Windows: 音量ミュート キー|  
|VK_VOLUME_UP|Windows: 音量上げるキー|  
|VK_XBUTTON1|Windows: X1 マウス ボタン|  
|VK_XBUTTON2|Windows: X2 マウス ボタン|  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [アクセラレータ エディター](../windows/accelerator-editor.md)   
 [リソース エディター](../windows/resource-editors.md)