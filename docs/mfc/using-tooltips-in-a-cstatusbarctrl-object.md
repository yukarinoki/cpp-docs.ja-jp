---
title: CStatusBarCtrl オブジェクトでのツール ヒントの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
ms.openlocfilehash: a607a5fb8c9470df42d12c771865b924891b2dac
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442541"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>CStatusBarCtrl オブジェクトでのツール ヒントの使い方

ステータスバーコントロールのツールヒントを有効にするには、SBT_TOOLTIPS スタイルを使用して `CStatusBarCtrl` オブジェクトを作成します。

> [!NOTE]
>  `CStatusBar` オブジェクトを使用してステータスバーを実装している場合は、`CStatusBar::CreateEx` 関数を使用します。 埋め込み `CStatusBarCtrl` オブジェクトの追加のスタイルを指定できます。

`CStatusBarCtrl` オブジェクトが正常に作成されたら、 [CStatusBarCtrl:: SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext)と[CStatusBarCtrl:: GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext)を使用して、特定のペインのヒントテキストを設定および取得します。

ツールヒントが設定されると、パーツにアイコンが表示され、テキストがない場合、またはすべてのテキストがそのパーツ内に表示されない場合にのみ表示されます。 ツールヒントは、簡易モードではサポートされていません。

## <a name="see-also"></a>参照

[CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
