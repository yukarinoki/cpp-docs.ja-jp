---
title: CStatusBarCtrl オブジェクトでのツール ヒントの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
ms.openlocfilehash: 29d326c708743424686d616bbaf172ccd72481ce
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374695"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>CStatusBarCtrl オブジェクトでのツール ヒントの使い方

ステータス バー コントロールのツールヒントを有効にするには、SBT_TOOLTIPS スタイルを使用して`CStatusBarCtrl`オブジェクトを作成します。

> [!NOTE]
> オブジェクトを使用してステータス`CStatusBar`バーを実装する場合は、この`CStatusBar::CreateEx`関数を使用します。 このダイアログ ボックスでは、埋め込み`CStatusBarCtrl`オブジェクトの追加のスタイルを指定できます。

オブジェクトが`CStatusBarCtrl`正常に作成されたら、特定のペインのヒント テキストを設定および取得するには[、CStatusBarCtrl:::セットヒント](../mfc/reference/cstatusbarctrl-class.md#settiptext)テキストと[CStatusBarCtrl を](../mfc/reference/cstatusbarctrl-class.md#gettiptext)使用します。

ツール ヒントを設定すると、パーツにアイコンが付いており、テキストが表示されていない場合、またはすべてのテキストをパーツ内に表示できない場合にのみ表示されます。 ツール ヒントは、単純モードではサポートされていません。

## <a name="see-also"></a>関連項目

[CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
