---
title: リスト コントロールの作業領域の実装
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [MFC], working areas
- working areas in list control [MFC]
ms.assetid: fbbb356b-3359-4348-8603-f1cb114cadde
ms.openlocfilehash: 91577203163247bd230fecb083cf1c50e2875b98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377222"
---
# <a name="implementing-working-areas-in-list-controls"></a>リスト コントロールの作業領域の実装

既定では、リスト コントロールはすべての項目を標準グリッドの方法で整列します。 ただし、リスト項目を長方形のグループに配置する別の方法がサポートされています。 作業領域を実装するリスト コントロールのイメージについては、Windows SDK の「リスト ビュー コントロールの使用」を参照してください。

> [!NOTE]
> 作業領域は、リスト コントロールがアイコン モードまたは小さいアイコン モードの場合にのみ表示されます。 ただし、ビューがレポートモードまたはリストモードに切り替えられた場合、現在の作業領域は維持されます。

作業領域を使用して、空の境界線 (項目の左、上、右)を表示したり、通常は表示されない場合は水平スクロール バーを表示したりできます。 もう 1 つの一般的な用途は、アイテムを移動または削除できる複数の作業領域を作成することです。 この方法では、異なる意味を持つ 1 つのビューに領域を作成できます。 ユーザーは、別の領域に配置することで、項目を分類できます。 たとえば、読み取り/書き込みファイル用の領域と、読み取り専用ファイル用の別の領域を持つファイル システムのビューがあります。 ファイル項目が読み取り専用領域に移動された場合、自動的に読み取り専用になります。 読み取り専用領域から読み取り/書き込み領域にファイルを移動すると、ファイルは読み取り/書き込み可能になります。

`CListCtrl`には、リスト コントロールの作業領域を作成および管理するための複数のメンバー関数が用意されています。 [GetWorkAreas](../mfc/reference/clistctrl-class.md#getworkareas)と[SetWorkAreas は](../mfc/reference/clistctrl-class.md#setworkareas)、リスト`CRect`コントロールに`RECT`現在実装されている作業領域を格納するオブジェクト (または構造体) の配列を取得および設定します。 さらに、[リスト](../mfc/reference/clistctrl-class.md#getnumberofworkareas)コントロールの現在の作業領域の数 (既定では 0) を取得します。

## <a name="items-and-working-areas"></a>アイテムと作業領域

作業領域が作成されると、作業領域内にあるアイテムがそのメンバーになります。 同様に、項目が作業領域に移動されると、その項目は移動先の作業領域のメンバーになります。 項目が作業領域内にない場合、項目は自動的に最初の (インデックス 0) 作業領域のメンバーになります。 アイテムを作成し、特定の作業領域内に配置する場合は、その項目を作成し[、SetItemPosition](../mfc/reference/clistctrl-class.md#setitemposition)を呼び出して目的の作業領域に移動する必要があります。 次の 2 番目の例では、この手法を示します。

次の例では、リスト コントロール`rcWorkAreas`( ) の各作業領域の周囲に 10 ピクセル幅の境界線を持つ`m_WorkAreaListCtrl`4 つの作業領域 ( ) を実装しています。

[!code-cpp[NVC_MFCControlLadenDialog#20](../mfc/codesnippet/cpp/implementing-working-areas-in-list-controls_1.cpp)]

1 つの領域内のすべての項目を表示するために必要な合計領域の見積もりを取得するために[、EstimateViewRect](../mfc/reference/clistctrl-class.md#approximateviewrect)への呼び出しが行われました。 この推定値は 4 つの領域に分割され、5 ピクセル幅の境界が埋め込まれます。

次の例では、既存のリスト項目を各グループ`rcWorkAreas`( ) に割り当`m_WorkAreaListCtrl`て、コントロール ビュー ( ) を更新して効果を完了します。

[!code-cpp[NVC_MFCControlLadenDialog#21](../mfc/codesnippet/cpp/implementing-working-areas-in-list-controls_2.cpp)]

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](../mfc/using-clistctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
