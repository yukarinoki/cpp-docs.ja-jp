---
title: ヘッダー項目をカスタマイズする&#39;外観
ms.date: 11/04/2016
helpviewer_keywords:
- header controls [MFC], customization of items
- CHeaderCtrl class [MFC], customizing the items
- HDS_ styles
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
ms.openlocfilehash: 081260bd5c1cf6335d398a4fd773c9590dbc8030
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268838"
---
# <a name="customizing-the-header-item39s-appearance"></a>ヘッダー項目をカスタマイズする&#39;外観

設定して、 *dwStyle*パラメーター ヘッダー コントロールを最初に作成したとき ([CHeaderCtrl::Create](../mfc/reference/cheaderctrl-class.md#create)) の外観を定義する、およびヘッダーの動作は、項目またはヘッダーのコントロール自体。

サンプリングのスタイルを設定して、その目的を次に示します。

- プッシュ ボタンのようにヘッダー項目を使用、 **HDS_BUTTONS**スタイル。

   Microsoft Outlook で行われるように、特定の列でデータを並べ替えなどのヘッダー アイテムでは、マウス クリックに応答アクションを実行する場合は、このスタイルを使用します。

- ヘッダー項目を「ホット トラッキング」表示上にマウス カーソルが成功したとき、使用、**するとき**スタイル。

   ポインターは、それ以外の場合、フラットでアイテムがホット トラッキングが 3D のアウトラインを表示バー。

- ヘッダー コントロールを非表示にすることを示すを使用して、 **HDS_HIDDEN**スタイル。

   **HDS_HIDDEN**スタイルでは、ヘッダー コントロールがデータ コンテナーとビジュアル コントロールではなくとして使用するものであることを示します。 このスタイルはコントロールが自動的に非表示されませんが、代わりの動作に影響`CHeaderCtrl::Layout`します。 返される値、 *cy*のメンバー、`WINDOWPOS`される構造は 0 をコントロールは、ユーザーに表示できないする必要があります。

これらのプロパティの詳細については、次を参照してください。[項目](/windows/desktop/Controls/header-controls)Windows SDK に含まれています。 ヘッダー コントロールに項目を追加する方法の詳細については、[ヘッダー コントロールへの項目の追加](../mfc/adding-items-to-the-header-control.md)を参照してください。

## <a name="see-also"></a>関連項目

[CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
