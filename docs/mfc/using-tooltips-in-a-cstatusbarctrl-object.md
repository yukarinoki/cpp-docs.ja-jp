---
description: 詳細については、CStatusBarCtrl オブジェクトでのツールヒントの使用に関するページを参照してください。
title: CStatusBarCtrl オブジェクトでのツール ヒントの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
ms.openlocfilehash: d77610a511698000dc70a1aa1cb1edb22fb3eb7a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143248"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>CStatusBarCtrl オブジェクトでのツール ヒントの使い方

ステータスバーコントロールのツールヒントを有効にするには、 `CStatusBarCtrl` SBT_TOOLTIPS スタイルを使用してオブジェクトを作成します。

> [!NOTE]
> オブジェクトを使用してステータスバーを実装する場合は、 `CStatusBar` 関数を使用し `CStatusBar::CreateEx` ます。 埋め込みオブジェクトの追加のスタイルを指定でき `CStatusBarCtrl` ます。

`CStatusBarCtrl`オブジェクトが正常に作成されたら、 [CStatusBarCtrl:: SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext)と[CStatusBarCtrl:: GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext)を使用して、特定のペインのヒントテキストを設定および取得します。

ツールヒントが設定されると、パーツにアイコンが表示され、テキストがない場合、またはすべてのテキストがそのパーツ内に表示されない場合にのみ表示されます。 ツールヒントは、簡易モードではサポートされていません。

## <a name="see-also"></a>関連項目

[CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
