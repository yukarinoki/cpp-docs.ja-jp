---
description: 詳細については、「ヘッダーコントロールでの項目の順序付け」を参照してください。
title: ヘッダー コントロールの項目の並べ替え
ms.date: 11/04/2016
f1_keywords:
- DS_DRAGDROP
helpviewer_keywords:
- sequence [MFC]
- sequence [MFC], header control items
- OrderToIndex method [MFC]
- DS_DRAGDROP notification [MFC]
- GetOrderArray method [MFC]
- SetOrderArray method [MFC]
- header controls [MFC], ordering items
ms.assetid: 5aaef872-75b5-49c5-8fed-6f9a81fca812
ms.openlocfilehash: 6f6db7b134121c4084d9406ad537bf0ce5dc12cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330123"
---
# <a name="ordering-items-in-the-header-control"></a>ヘッダー コントロールの項目の並べ替え

[項目をヘッダーコントロールに追加](adding-items-to-the-header-control.md)すると、次の関数を使用して、その順序に関する情報を操作したり取得したりできます。

- [CHeaderCtrl:: getorderarray](reference/cheaderctrl-class.md#getorderarray) と [CHeaderCtrl:: setorderarray](reference/cheaderctrl-class.md#setorderarray)

   ヘッダー項目の左から右の順序を取得および設定します。

- [CHeaderCtrl:: OrderToIndex](reference/cheaderctrl-class.md#ordertoindex)。

   特定のヘッダー項目のインデックス値を取得します。

HDS_DRAGDROP スタイルでは、前のメンバー関数に加えて、ヘッダーコントロール内のヘッダー項目をドラッグアンドドロップすることができます。 詳細については、「 [ヘッダー項目に対するドラッグアンドドロップのサポートの提供](providing-drag-and-drop-support-for-header-items.md)」を参照してください。

## <a name="see-also"></a>関連項目

[CHeaderCtrl の使い方](using-cheaderctrl.md)
