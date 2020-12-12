---
description: '詳細情報: ツールヒントコントロールの設定'
title: ツール ヒント コントロールの設定値
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], activating
- CToolTipCtrl class [MFC], settings
ms.assetid: ff8c5c46-2047-403a-bd98-ffec3d21ee3a
ms.openlocfilehash: 789f33a7e8e960f52589588bcda49a12889fa0d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217030"
---
# <a name="settings-for-the-tool-tip-control"></a>ツール ヒント コントロールの設定値

ツール ヒント コントロール ([CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)) は、アクティブまたは非アクティブに設定できます。 アクティブに設定すると、ツールの上にカーソルがあるときにツール ヒント コントロールが表示されます。 非アクティブに設定すると、ツールの上にカーソルがあってもツール ヒント コントロールは表示されません。 [Activate](../mfc/reference/ctooltipctrl-class.md#activate) を呼び出し、ツール ヒント コントロールをアクティブまたは非アクティブにします。

ツール ヒント コントロールのオーナー ウィンドウがアクティブか非アクティブかに関係なく、ツールの上にカーソルがあるときにツール ヒントを表示するには、TTS_ALWAYSTIP スタイルを使用してツール ヒントをアクティブに設定します。 このスタイルを使用しない場合、ツール ヒントはツールのオーナー ウィンドウがアクティブのときには表示されますが、ウィンドウが非アクティブのときには表示されません。

ほとんどのアプリケーションには、メニュー コマンドに対応するツールを組み込んだツールバーがあります。 このようなツールには、対応するメニュー項目と同じテキストのツール ヒント コントロールを表示すると便利です。 コントロールに TTS_NOPREFIX スタイルがなければ、ツール ヒント コントロールに渡されるすべての文字列からアンパサンド (&) アクセラレータの文字が自動的に取り除かれます。

## <a name="see-also"></a>関連項目

[CToolTipCtrl の使い方](../mfc/using-ctooltipctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
