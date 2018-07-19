---
title: 'コンテナー: クライアント アイテム通知 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], container client item
- OLE containers [MFC], client-item notifications
- client items and OLE containers
ms.assetid: e1f1c427-01f5-45f2-b496-c5bce3d76340
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d76717e68e37769cf55dceb4492ed78031c49e10
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928225"
---
# <a name="containers-client-item-notifications"></a>コンテナー : クライアント アイテムへの通知
この記事では、オーバーライド可能なサーバー アプリケーションがクライアント アプリケーションのドキュメント内の項目を変更、MFC フレームワークによって呼び出される関数について説明します。  
  
 [COleClientItem](../mfc/reference/coleclientitem-class.md)サーバー アプリケーションとも呼ばれるコンポーネントのアプリケーションからの要求に対する応答と呼ばれるいくつかのオーバーライド可能な関数を定義します。 これらのオーバーライド可能な関数は、通常、通知として機能します。 コンテナー アプリケーションのスクロール、アクティベーションなどのさまざまなイベントや、ユーザーが編集またはそれ以外の場合、項目を操作するときに変更および位置の変更を通知します。  
  
 フレームワークは、コンテナー アプリケーションへの呼び出しを使用して変更の`COleClientItem::OnChange`関数の実装が必要です。 この保護された関数は、2 つの引数を受け取ります。 1 つ目は、サーバーが、項目を変更した理由を指定します。  
  
|通知|説明|  
|------------------|-------------|  
|**OLE_CHANGED**|OLE 項目の外観が変更されました。|  
|**で**|OLE 項目が保存されました。|  
|**OLE_CLOSED**|OLE 項目が閉じられました。|  
|**OLE_RENAMED**|OLE 項目を格納しているサーバーのドキュメントが変更されています。|  
|**OLE_CHANGED_STATE**|OLE 項目は、別の 1 つの状態から変更されました。|  
|**OLE_CHANGED_ASPECT**|OLE アイテムの描画のアスペクト比は、フレームワークによって変更されました。|  
  
 これらの値は、 **OLE_NOTIFICATION** AFXOLE で定義されている列挙します。H.  
  
 この関数の 2 番目の引数は、アイテムがどのように変更されたか、またはが入力の状態を指定します。  
  
|最初の引数|2 番目の引数|  
|----------------------------|---------------------|  
|**OLE_SAVED**または**OLE_CLOSED**|使用されません。|  
|**OLE_CHANGED**|OLE 項目が変更されたことの縦横比を指定します。|  
|**OLE_CHANGED_STATE**|入力されている状態を表します (*これ*、 *loadedState*、 *openState*、 *activeState*、または*activeUIState*)。|  
  
 クライアント アイテムの状態の詳細については、次を参照してください。[コンテナー: クライアント アイテムの状態](../mfc/containers-client-item-states.md)です。  
  
 フレームワークによって`COleClientItem::OnGetItemPosition`で埋め込み先編集の項目をアクティブ化するとします。 実装は、インプレース編集をサポートするアプリケーションで必要です。 MFC アプリケーション ウィザードを提供する、項目の座標を割り当てます、基本的な実装、`CRect`オブジェクトへの引数として渡される`OnGetItemPosition`です。  
  
 OLE 項目の位置またはサイズ変更された場合、インプレース編集中に、アイテムの位置とクリッピング四角形のコンテナーの情報を更新する必要があり、サーバーは、その変更に関する情報を受け取る必要があります。 フレームワークによって`COleClientItem::OnChangeItemPosition`この目的のためです。 MFC アプリケーション ウィザードでは、基本クラスの関数を呼び出している上書きを提供します。 アプリケーション ウィザードで生成する関数を編集する必要があります、 `COleClientItem`-関数は、クライアント アイテム オブジェクトによって保持される情報を更新するようにクラスを派生します。  
  
## <a name="see-also"></a>関連項目  
 [コンテナー](../mfc/containers.md)   
 [コンテナー: クライアント アイテムの状態](../mfc/containers-client-item-states.md)   
 [に](../mfc/reference/coleclientitem-class.md#onchangeitemposition)

