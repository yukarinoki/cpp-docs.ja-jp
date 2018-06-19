---
title: プロパティ シートへのコントロールの追加 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8437fcdaa04ce7dd2b0a214e4bd3a63ca421d014
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341092"
---
# <a name="adding-controls-to-a-property-sheet"></a>プロパティ シートへのコントロールの追加
既定では、プロパティ シートは、プロパティ ページ、タブ インデックス、および、ok、キャンセル、適用ボタンをウィンドウ領域を割り当てます。 (モードレス プロパティ シートが [ok]、キャンセル、およびボタンを適用します。)プロパティ シートには、その他のコントロールを追加できます。 たとえば、現在の設定は外部のオブジェクトに適用される場合のようになりますが、ユーザーを表示するプロパティ ページの領域の右側にプレビュー ウィンドウを追加できます。  
  
 プロパティ シート ダイアログ ボックスにコントロールを追加することができます、`OnCreate`ハンドラー。 その他のコントロールに通常対応するには、プロパティ シート ダイアログ ボックスのサイズを拡張する必要があります。 基本クラスの呼び出し後に**CPropertySheet::OnCreate**、呼び出す[GetWindowRect](../mfc/reference/cwnd-class.md#getwindowrect)現在割り当てられているプロパティ シート ウィンドウの高さと幅を取得するには、展開、四角形のディメンション、および呼び出し[MoveWindow](../mfc/reference/cwnd-class.md#movewindow)プロパティ シート ウィンドウのサイズを変更します。  
  
## <a name="see-also"></a>関連項目  
 [プロパティ シート](../mfc/property-sheets-mfc.md)   
 [CPropertyPage クラス](../mfc/reference/cpropertypage-class.md)   
 [CPropertySheet クラス](../mfc/reference/cpropertysheet-class.md)
