---
title: 設定、ツール ヒント コントロール |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], activating
- CToolTipCtrl class [MFC], settings
ms.assetid: ff8c5c46-2047-403a-bd98-ffec3d21ee3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d0adfd1c7a7ae1e1f36fa8dd53610d19ad8e7b2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379555"
---
# <a name="settings-for-the-tool-tip-control"></a>ツール ヒント コントロールの設定値

ツール ヒント コントロール ([CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)) は、アクティブまたは非アクティブに設定できます。 アクティブに設定すると、ツールの上にカーソルがあるときにツール ヒント コントロールが表示されます。 非アクティブに設定すると、ツールの上にカーソルがあってもツール ヒント コントロールは表示されません。 [Activate](../mfc/reference/ctooltipctrl-class.md#activate) を呼び出し、ツール ヒント コントロールをアクティブまたは非アクティブにします。

ツール ヒント コントロールのオーナー ウィンドウは、アクティブまたは非アクティブ、TTS_ALWAYSTIP スタイルを使用しているかどうかを示すようなツールを上にカーソルがときに、ツール ヒントを表示するアクティブなツールヒントを設定することができます。 このスタイルを使用しない場合、ツール ヒントはツールのオーナー ウィンドウがアクティブのときには表示されますが、ウィンドウが非アクティブのときには表示されません。

ほとんどのアプリケーションには、メニュー コマンドに対応するツールを組み込んだツールバーがあります。 このようなツールには、対応するメニュー項目と同じテキストのツール ヒント コントロールを表示すると便利です。 コントロールに TTS_NOPREFIX スタイルに、アンパサンド (&) アクセラレータの文字のすべての文字列から、ツール ヒント コントロールに渡されるシステム自動的に削除します。

## <a name="see-also"></a>関連項目

[CToolTipCtrl の使い方](../mfc/using-ctooltipctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

