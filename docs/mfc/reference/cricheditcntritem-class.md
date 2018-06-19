---
title: CRichEditCntrItem クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRichEditCntrItem
- AFXRICH/CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::SyncToRichEditObject
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCntrItem [MFC], CRichEditCntrItem
- CRichEditCntrItem [MFC], SyncToRichEditObject
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a64950bcb0cc931b4528276e85f5d60e3b5cb08
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368421"
---
# <a name="cricheditcntritem-class"></a>CRichEditCntrItem クラス
[CRichEditView](../../mfc/reference/cricheditview-class.md)と[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)MFC のドキュメント ビュー アーキテクチャのコンテキストでリッチ エディット コントロールの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CRichEditCntrItem : public COleClientItem  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CRichEditCntrItem::CRichEditCntrItem](#cricheditcntritem)|`CRichEditCntrItem` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRichEditCntrItem::SyncToRichEditObject](#synctoricheditobject)|別の種類として、項目をアクティブにします。|  
  
## <a name="remarks"></a>コメント  
 「リッチ エディット コントロール」は、ユーザーを入力し、テキストを編集するウィンドウです。 テキストは、文字と段落の書式に割り当てることができるし、埋め込み OLE オブジェクトを含めることができます。 リッチ エディット コントロールでは、テキストの書式設定のプログラミング インターフェイスを提供します。 ただし、アプリケーションでは、書式設定操作をユーザーに使用できるようにするために必要なすべてのユーザー インターフェイス コンポーネントを実装する必要があります。  
  
 `CRichEditView` テキストとテキストの書式設定特性を保持します。 `CRichEditDoc` ビューでは OLE クライアント アイテムの一覧を保持します。 `CRichEditCntrItem` コンテナー側 OLE クライアント アイテムへのアクセスを提供します。  
  
 この Windows コモン コントロール (および、 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)および関連クラス) は、Windows 95/98 および Windows NT version 3.51 の下で実行されているプログラムにのみ使用可能な以降。  
  
 リッチ エディット コンテナー アイテムを使用して MFC アプリケーションでの例は、次を参照してください。、[ワードパッド](../../visual-cpp-samples.md)サンプル アプリケーションです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `CRichEditCntrItem`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrich.h  
  
##  <a name="cricheditcntritem"></a>  CRichEditCntrItem::CRichEditCntrItem  
 作成するには、この関数を呼び出して、`CRichEditCntrItem`オブジェクトおよびコンテナーのドキュメントに追加します。  
  
```  
CRichEditCntrItem(
    REOBJECT* preo = NULL,  
    CRichEditDoc* pContainer = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *preo*  
 ポインター、 [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) OLE 項目を記述する構造体。 新しい`CRichEditCntrItem`この OLE アイテム オブジェクトを構築します。 場合*preo*は**NULL**クライアントのアイテムは空にします。  
  
 `pContainer`  
 この項目を格納するコンテナーのドキュメントへのポインター。 場合`pContainer`は**NULL**、明示的に呼び出す必要があります[COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem)ドキュメントにこのクライアントの項目を追加します。  
  
### <a name="remarks"></a>コメント  
 この関数では、OLE の初期化は実行されません。  
  
 詳細については、次を参照してください。、 [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) Windows SDK 内の構造。  
  
##  <a name="synctoricheditobject"></a>  CRichEditCntrItem::SyncToRichEditObject  
 デバイスの側面を同期するためには、この関数を呼び出す[型](http://msdn.microsoft.com/library/windows/desktop/ms690318)、この**CRichEditCntrltem**によって指定される*reo*です。  
  
```  
void SyncToRichEditObject(REOBJECT& reo);
```  
  
### <a name="parameters"></a>パラメーター  
 *reo*  
 参照、 [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) OLE 項目を記述する構造体。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[型](http://msdn.microsoft.com/library/windows/desktop/ms690318)Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル ワードパッド](../../visual-cpp-samples.md)   
 [COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc クラス](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditView クラス](../../mfc/reference/cricheditview-class.md)
