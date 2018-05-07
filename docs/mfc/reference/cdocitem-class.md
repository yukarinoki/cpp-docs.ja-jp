---
title: CDocItem クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDocItem
- AFXOLE/CDocItem
- AFXOLE/CDocItem::GetDocument
- AFXOLE/CDocItem::IsBlank
dev_langs:
- C++
helpviewer_keywords:
- CDocItem [MFC], GetDocument
- CDocItem [MFC], IsBlank
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 724e5017f51a3527e2ad81bcf707179053cc3e88
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdocitem-class"></a>CDocItem クラス
ドキュメント アイテムの基底クラスであり、ドキュメント データのコンポーネントです。  
  
## <a name="syntax"></a>構文  
  
```  
class CDocItem : public CCmdTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDocItem::GetDocument](#getdocument)|項目を含むドキュメントを返します。|  
|[CDocItem::IsBlank](#isblank)|項目が情報を格納しているかどうかを判断します。|  
  
## <a name="remarks"></a>コメント  
 `CDocItem` オブジェクトは、クライアントとサーバーの両方のドキュメントで OLE 項目を表すために使用されます。  
  
 詳細については、記事を参照してください。[コンテナー: コンテナーの実装](../../mfc/containers-implementing-a-container.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocItem`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="getdocument"></a>  CDocItem::GetDocument  
 この関数では、項目を含むドキュメントを取得します。  
  
```  
CDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>戻り値  
 項目を含むドキュメントへのポインター**NULL**アイテムは、ドキュメントの一部ではない場合は、します。  
  
### <a name="remarks"></a>コメント  
 この関数は、派生クラスでオーバーライドされる[COleClientItem](../../mfc/reference/coleclientitem-class.md)と[COleServerItem](../../mfc/reference/coleserveritem-class.md)、いずれかにポインターを返す、 [COleDocument](../../mfc/reference/coledocument-class.md)、 [直接](../../mfc/reference/colelinkingdoc-class.md)、または[COleServerDoc](../../mfc/reference/coleserverdoc-class.md)オブジェクト。  
  
##  <a name="isblank"></a>  CDocItem::IsBlank  
 既定のシリアル化が発生したときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アイテムに情報が含まれていない場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定では、`CDocItem`オブジェクトは空ではありません。 [COleClientItem](../../mfc/reference/coleclientitem-class.md)オブジェクトから直接派生するためにも空白`CDocItem`です。 ただし、 [COleServerItem](../../mfc/reference/coleserveritem-class.md)オブジェクトが空では常にします。 既定では、OLE アプリケーションが含まれている`COleClientItem`x または y がないオブジェクトをエクステントがシリアル化します。 返すことによってこれは、 **TRUE**のオーバーライドから`IsBlank`ときに、項目を持たない x または y エクステントです。  
  
 シリアル化中に他のアクションを実装する場合は、この関数をオーバーライドします。  
  
## <a name="see-also"></a>関連項目  
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDocument クラス](../../mfc/reference/coledocument-class.md)   
 [COleServerItem クラス](../../mfc/reference/coleserveritem-class.md)   
 [COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)
