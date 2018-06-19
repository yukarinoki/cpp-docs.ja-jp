---
title: CDocObjectServerItem クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::GetDocument
- AFXDOCOB/CDocObjectServerItem::OnHide
- AFXDOCOB/CDocObjectServerItem::OnShow
dev_langs:
- C++
helpviewer_keywords:
- CDocObjectServerItem [MFC], CDocObjectServerItem
- CDocObjectServerItem [MFC], GetDocument
- CDocObjectServerItem [MFC], OnHide
- CDocObjectServerItem [MFC], OnShow
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8c6f990a00fb96195a54ee7ed6906068985b052f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367049"
---
# <a name="cdocobjectserveritem-class"></a>CDocObjectServerItem クラス
OLE サーバー動詞を DocObject サーバー用に実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDocObjectServerItem : public COleServerItem  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDocObjectServerItem::CDocObjectServerItem](#cdocobjectserveritem)|`CDocObjectServerItem` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDocObjectServerItem::GetDocument](#getdocument)|項目を含むドキュメントへのポインターを取得します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDocObjectServerItem::OnHide](#onhide)|フレームワーク DocObject 項目を非表示しようとする場合は、例外をスローします。|  
|[CDocObjectServerItem::OnShow](#onshow)|DocObject アイテムの埋め込みを行うために、フレームワークによって呼び出されますアクティブです。 項目がない場合、DocObject、呼び出します[COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow)です。|  
  
## <a name="remarks"></a>コメント  
 `CDocObjectServerItem` オーバーライド可能なメンバー関数を定義します。 [OnHide](#onhide)、 [OnOpen](http://msdn.microsoft.com/en-us/7a9b1363-6ad8-4732-9959-4e35c07644fd)、および[OnShow](#onshow)です。  
  
 使用する`CDocObjectServerItem`、確実、 [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem)内の上書き、 `COleServerDoc`-派生クラスが新しいを返します`CDocObjectServerItem`オブジェクト。 アイテムでの機能を変更する必要がある場合は、独自の新しいインスタンスを作成することができます`CDocObjectServerItem`-クラスを派生します。  
  
 DocObjects については、次を参照してください。[関数](../../mfc/reference/cdocobjectserver-class.md)と[COleCmdUI](../../mfc/reference/colecmdui-class.md)で、 *『 MFC リファレンス*です。 参照してください[インターネットの最初の手順: Active ドキュメント](../../mfc/active-documents-on-the-internet.md)と[アクティブ ドキュメント](../../mfc/active-documents-on-the-internet.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleServerItem](../../mfc/reference/coleserveritem-class.md)  
  
 `CDocObjectServerItem`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdocob.h  
  
##  <a name="cdocobjectserveritem"></a>  CDocObjectServerItem::CDocObjectServerItem  
 `CDocObjectServerItem` オブジェクトを構築します。  
  
```  
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>パラメーター  
 `pServerDoc`  
 新しい項目の DocObject を格納するドキュメントへのポインター。  
  
 `bAutoDelete`  
 リンクがリリースされたときに、オブジェクトを削除するかどうかを示します。 引数に設定**FALSE**場合、`CDocObjectServerItem`オブジェクトは、ドキュメントのデータの重要な一部です。 設定**TRUE**場合は、オブジェクトは、二次的な構造を削除するには、フレームワークをドキュメントのデータの範囲を識別するために使用します。  
  
##  <a name="getdocument"></a>  CDocObjectServerItem::GetDocument  
 項目を含むドキュメントへのポインターを取得します。  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>戻り値  
 項目を含むドキュメントへのポインター**NULL**場合は、項目は、ドキュメントの一部ではありません。  
  
### <a name="remarks"></a>コメント  
 これによりへの引数として渡されたサーバー ドキュメントへのアクセス、 [CDocObjectServerItem](#cdocobjectserveritem)コンス トラクターです。  
  
##  <a name="onhide"></a>  CDocObjectServerItem::OnHide  
 アイテムを非表示にするためにフレームワークによって呼び出されます。  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装は、項目が DocObject 場合に例外をスローします。 ビュー全体を受け取るためには、アクティブな DocObject 項目を非表示にすることはできません。 非表示にする DocObject アイテムを非アクティブ化する必要があります。 項目が DocObject でない場合は、既定の実装を呼び出す[COleServerItem::OnHide](../../mfc/reference/coleserveritem-class.md#onhide)です。  
  
##  <a name="onshow"></a>  CDocObjectServerItem::OnShow  
 DocObject をアイテムの埋め込みをサーバー アプリケーションに指示するためにフレームワークによって呼び出されますアクティブです。  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>コメント  
 項目が DocObject でない場合は、既定の実装を呼び出す[COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onopen)です。 特別な DocObject アイテムを開くときの処理を実行する場合は、この関数をオーバーライドします。  
  
## <a name="see-also"></a>関連項目  
 [COleServerItem クラス](../../mfc/reference/coleserveritem-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数クラス](../../mfc/reference/cdocobjectserver-class.md)   
 [COleDocObjectItem クラス](../../mfc/reference/coledocobjectitem-class.md)
