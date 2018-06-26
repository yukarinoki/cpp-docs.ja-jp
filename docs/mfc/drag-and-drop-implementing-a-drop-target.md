---
title: 'ドラッグ アンド ドロップ: ドロップ ターゲットの実装 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE drag and drop [MFC], implementing drop targets
- OLE drag and drop [MFC], drop target
- drag and drop [MFC], drop target
ms.assetid: 0689f1ec-5326-4008-b226-4b373c881358
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 33088477c579cbdfe48140b806c6376b520e470c
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928919"
---
# <a name="drag-and-drop-implementing-a-drop-target"></a>ドラッグ アンド ドロップ: ドロップ ターゲットの実装
この記事では、ドロップ ターゲット アプリケーションを作成する方法について説明します。 ドロップ ソースを実装するよりも少し多い作業を受け取るドロップ ターゲットの実装が、それでも比較的簡単です。 これらの手法は、非 OLE アプリケーションにも適用されます。  
  
#### <a name="to-implement-a-drop-target"></a>ドロップ ターゲットを実装するには  
  
1.  ドロップ ターゲットにする、アプリケーション内の各ビューにメンバー変数を追加します。 このメンバー変数は、型でなければなりません`COleDropTarget`またはその派生クラス。  
  
2.  処理するビュー クラスの関数から、 **WM_CREATE**メッセージ (通常`OnCreate`)、新しいメンバー変数の`Register`メンバー関数。 `Revoke` に対して呼び出されるは自動的にする、ビューが破棄されるとします。  
  
3.  次の関数をオーバーライドします。 アプリケーション全体で同じ動作をする場合は、ビュー クラスでこれらの関数をオーバーライドします。 特殊なケースでの動作を変更またはにドロップすることではないを有効にする場合`CView`、windows でこれらの関数のオーバーライド、 `COleDropTarget`-クラスを派生します。  
  
    |オーバーライド|許可するには|  
    |--------------|--------------|  
    |`OnDragEnter`|ウィンドウで発生する操作を削除します。 カーソルがウィンドウを最初に入ったときに呼び出されます。|  
    |`OnDragLeave`|ドラッグ操作が指定されたウィンドウを離れるとの特別な動作です。|  
    |`OnDragOver`|ウィンドウで発生する操作を削除します。 カーソルがウィンドウの間でドラッグされているときに呼び出されます。|  
    |`OnDrop`|指定されたウィンドウにドロップされたデータを処理しています。|  
    |`OnScrollBy`|スクロールがの場合に必要なターゲット ウィンドウの特別な動作です。|  
  
 MAINVIEW を参照してください。CPP MFC OLE サンプルの一部であるファイル[OCLIENT](../visual-cpp-samples.md)これらの関数の動作の例についてはします。  
  
 詳細については次を参照してください:  
  
-   [ドロップ ソースの実装](../mfc/drag-and-drop-implementing-a-drop-source.md)  
  
-   [作成と破棄 OLE データ オブジェクトとデータ ソース](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [OLE データ オブジェクトとデータ ソースを操作します。](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## <a name="see-also"></a>関連項目  
 [ドラッグ アンド ドロップ (OLE)](../mfc/drag-and-drop-ole.md)   
 [COleDropTarget クラス](../mfc/reference/coledroptarget-class.md)
