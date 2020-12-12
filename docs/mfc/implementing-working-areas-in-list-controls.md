---
description: 詳細については、「リストコントロールでの作業領域の実装」を参照してください。
title: リスト コントロールの作業領域の実装
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [MFC], working areas
- working areas in list control [MFC]
ms.assetid: fbbb356b-3359-4348-8603-f1cb114cadde
ms.openlocfilehash: 04eb935531dff0ac1ee240dec8690bd7ce1378a2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290077"
---
# <a name="implementing-working-areas-in-list-controls"></a>リスト コントロールの作業領域の実装

既定では、リストコントロールはすべての項目を標準のグリッド形式で整列します。 ただし、リスト項目を四角形のグループに配置する別の方法 (作業領域) がサポートされています。 作業領域を実装するリストコントロールのイメージについては、「Windows SDK での List-View コントロールの使用」を参照してください。

> [!NOTE]
> 作業領域は、リストコントロールがアイコンまたは小さいアイコンモードの場合にのみ表示されます。 ただし、ビューをレポートモードまたはリストモードに切り替えた場合、現在の作業領域は維持されます。

作業領域を使用すると、アイテムの左側、上部、または右側に空の境界線を表示したり、通常とは異なり、水平スクロールバーが表示されるようにすることができます。 もう1つの一般的な使用方法は、アイテムを移動または削除できる複数の作業領域を作成することです。 この方法では、異なる意味を持つ領域を1つのビューで作成できます。 ユーザーは、別の領域に項目を配置することで、項目を分類できます。 この例として、読み取り/書き込みファイルの領域があり、読み取り専用ファイル用の別の領域を持つファイルシステムのビューがあります。 ファイル項目が読み取り専用領域に移動された場合、その項目は自動的に読み取り専用になります。 読み取り専用領域から読み取り/書き込み領域にファイルを移動すると、ファイルの読み取り/書き込みが実行されます。

`CListCtrl` には、リストコントロール内の作業領域を作成および管理するためのメンバー関数がいくつか用意されています。 [Getworking areas](reference/clistctrl-class.md#getworkareas) と [setworking areas](reference/clistctrl-class.md#setworkareas) `CRect` は `RECT` 、リストコントロールの現在実装されている作業領域を格納するオブジェクト (または構造体) の配列を取得して設定します。 さらに、 [Getnumberofworking areas](reference/clistctrl-class.md#getnumberofworkareas) は、リストコントロールの現在の作業領域の数を取得します (既定ではゼロ)。

## <a name="items-and-working-areas"></a>項目と作業領域

作業領域が作成されると、作業領域内にある項目がその領域のメンバーになります。 同様に、作業領域に移動した項目は、移動先の作業領域のメンバーになります。 作業領域内に存在しないアイテムは、自動的に最初の (インデックス 0) 作業領域のメンバーになります。 項目を作成して特定の作業領域内に配置する場合は、項目を作成し、 [SetItemPosition](reference/clistctrl-class.md#setitemposition)の呼び出しを使用して目的の作業領域に移動する必要があります。 次の2番目の例は、この手法を示しています。

次の例では、4つの作業領域 ( `rcWorkAreas` ) を実装しています。これは、リストコントロール () 内の各作業領域の周囲に10ピクセル幅の境界線が付いた、同じサイズです `m_WorkAreaListCtrl` 。

[!code-cpp[NVC_MFCControlLadenDialog#20](codesnippet/cpp/implementing-working-areas-in-list-controls_1.cpp)]

[ApproximateViewRect](reference/clistctrl-class.md#approximateviewrect)を呼び出すと、1つの地域のすべての項目を表示するために必要な合計領域の見積もりが作成されました。 この推定値は、4つの領域に分割され、5ピクセル幅の境界線で埋められます。

次の例では、既存のリスト項目を各グループに割り当て ( `rcWorkAreas` )、コントロールビュー () を更新して効果を完成させ `m_WorkAreaListCtrl` ます。

[!code-cpp[NVC_MFCControlLadenDialog#21](codesnippet/cpp/implementing-working-areas-in-list-controls_2.cpp)]

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](using-clistctrl.md)<br/>
[コントロール](controls-mfc.md)
