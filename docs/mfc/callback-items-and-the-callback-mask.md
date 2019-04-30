---
title: コールバック項目とコールバック マスク
ms.date: 11/04/2016
helpviewer_keywords:
- callback items in CListCtrl class [MFC]
- CListCtrl class [MFC], callback item and callback mask
ms.assetid: 67c1f76f-6144-453e-9376-6712f89430ae
ms.openlocfilehash: 35967f128c6cc59bc9cea90da559b32c51fb38d1
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344278"
---
# <a name="callback-items-and-the-callback-mask"></a>コールバック項目とコールバック マスク

その項目ごとに、リスト ビュー コントロールは通常、ラベルのテキスト項目のアイコンのイメージ リスト インデックスを格納し、一連のビット フラグの項目の状態。 個々 の項目は、既にアプリケーションがいくつかの項目の情報を格納する場合に便利ですが、コールバック項目として定義できます。

適切な値を指定することによってコールバック項目として項目を定義する、`pszText`と`iImage`のメンバー、 **LV_ITEM**構造 (を参照してください[CListCtrl::GetItem](../mfc/reference/clistctrl-class.md#getitem))。 項目のまたはサブ項目のテキストを保持する場合は、指定、**保持するようにする**値、`pszText`メンバー。 場合は、アプリケーションの追跡項目のアイコンを指定、**番号**値、`iImage`メンバー。

コールバック アイテムを定義するだけでなく、コントロールのコールバック マスクを変更することもできます。 このマスクには、コントロールではなく、アプリケーションに現在のデータが格納されますアイテムの状態を指定するビット フラグのセットです。 コールバック マスクは、すべての特定の項目に適用されるコールバック項目の指定とは異なり、コントロールの項目に適用されます。 コールバック マスクは、既定では、コントロールがすべての項目の状態を追跡することを意味し、ゼロです。 この既定の動作を変更するには、次の値の任意の組み合わせにマスクを初期化します。

- **LVIS_CUT**カット アンド ペースト操作を項目は設定されています。

- **LVIS_DROPHILITED**項目がドラッグ アンド ドロップのターゲットとして強調表示されます。

- **LVIS_FOCUSED**項目にフォーカスがあります。

- **LVIS_SELECTED**項目を選択します。

- **LVIS_OVERLAYMASK**アプリケーションの各アイテムの現在のオーバーレイ画像のイメージ リスト インデックスを格納します。

- **LVIS_STATEIMAGEMASK**アプリケーションの各項目の現在の状態イメージのイメージ リスト インデックスを格納します。

取得して、このマスクの設定の詳細については、次を参照してください。 [CListCtrl::GetCallbackMask](../mfc/reference/clistctrl-class.md#getcallbackmask)と[CListCtrl::SetCallbackMask](../mfc/reference/clistctrl-class.md#setcallbackmask)します。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](../mfc/using-clistctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
