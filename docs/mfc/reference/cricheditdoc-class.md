---
title: CRichEditDoc クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRichEditDoc
- AFXRICH/CRichEditDoc
- AFXRICH/CRichEditDoc::CreateClientItem
- AFXRICH/CRichEditDoc::GetStreamFormat
- AFXRICH/CRichEditDoc::GetView
- AFXRICH/CRichEditDoc::m_bRTF
dev_langs:
- C++
helpviewer_keywords:
- CRichEditDoc [MFC], CreateClientItem
- CRichEditDoc [MFC], GetStreamFormat
- CRichEditDoc [MFC], GetView
- CRichEditDoc [MFC], m_bRTF
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 28b84747a694a62139546f3105f84c9e799b292a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cricheditdoc-class"></a>CRichEditDoc クラス
[CRichEditView](../../mfc/reference/cricheditview-class.md)と[CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)MFC のドキュメント ビュー アーキテクチャのコンテキストでリッチ エディット コントロールの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CRichEditDoc : public COleServerDoc  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRichEditDoc::CreateClientItem](#createclientitem)|ドキュメントのクリーンアップを実行するには、呼び出されます。|  
|[CRichEditDoc::GetStreamFormat](#getstreamformat)|ストリーム入力と出力が書式設定情報を含めるかどうかを示します。|  
|[CRichEditDoc::GetView](#getview)|取得、関連付けられている[CRichEditView](../../mfc/reference/cricheditview-class.md)オブジェクト。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[:M_brtf](#m_brtf)|ストリーム入出力が書式設定を含めるかどうかを示します。|  
  
## <a name="remarks"></a>コメント  
 「リッチ エディット コントロール」は、ユーザーを入力し、テキストを編集するウィンドウです。 テキストは、文字と段落の書式に割り当てることができるし、埋め込み OLE オブジェクトを含めることができます。 リッチ エディット コントロールでは、テキストの書式設定のプログラミング インターフェイスを提供します。 ただし、アプリケーションでは、書式設定操作をユーザーに使用できるようにするために必要なすべてのユーザー インターフェイス コンポーネントを実装する必要があります。  
  
 `CRichEditView` テキストとテキストの書式設定特性を保持します。 `CRichEditDoc` ビューにあるクライアント項目の一覧を保持します。 `CRichEditCntrItem` コンテナー側 OLE クライアント アイテムへのアクセスを提供します。  
  
 この Windows コモン コントロール (および、 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)および関連クラス) は、Windows 95/98 および Windows NT version 3.51 の下で実行されているプログラムにのみ使用可能な以降。  
  
 リッチ エディット ドキュメントを使用して MFC アプリケーションでの例は、次を参照してください。、[ワードパッド](../../visual-cpp-samples.md)サンプル アプリケーションです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [直接](../../mfc/reference/colelinkingdoc-class.md)  
  
 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md)  
  
 `CRichEditDoc`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrich.h  
  
##  <a name="createclientitem"></a>  CRichEditDoc::CreateClientItem  
 作成するには、この関数を呼び出して、`CRichEditCntrItem`オブジェクトし、このドキュメントに追加します。  
  
```  
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 *preo*  
 ポインター、 [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) OLE 項目を記述する構造体。 新しい`CRichEditCntrItem`この OLE アイテム オブジェクトを構築します。 場合*preo*は**NULL**、新しい項目のクライアントが空です。  
  
### <a name="return-value"></a>戻り値  
 新しいへのポインター [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)このドキュメントに追加されているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 この関数では、OLE の初期化は実行されません。  
  
 詳細については、次を参照してください。、 [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) Windows SDK 内の構造。  
  
##  <a name="getstreamformat"></a>  CRichEditDoc::GetStreamFormat  
 この関数では、豊富な編集のコンテンツをストリームのテキスト形式を特定します。  
  
```  
int GetStreamFormat() const;  
```  
  
### <a name="return-value"></a>戻り値  
 次のフラグのいずれかです。  
  
- `SF_TEXT` リッチ エディット コントロールでの書式情報が保持されないことを示します。  
  
- `SF_RTF` リッチ エディット コントロールはの書式情報を保持することを示します。  
  
### <a name="remarks"></a>コメント  
 戻り値がに基づいて、 [m_bRTF](#m_brtf)データ メンバーです。 この関数を返します`SF_RTF`場合`m_bRTF`は**TRUE**、それ以外の`SF_TEXT`します。  
  
##  <a name="getview"></a>  CRichEditDoc::GetView  
 この関数にアクセスする、 [CRichEditView](../../mfc/reference/cricheditview-class.md)オブジェクトに関連付けられた`CRichEditDoc`オブジェクト。  
  
```  
virtual CRichEditView* GetView() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CRichEditView`ドキュメントに関連付けられているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 テキストと書式設定情報内に含まれる、`CRichEditView`オブジェクト。 `CRichEditDoc`オブジェクトはシリアル化のための OLE 項目を保持します。 1 つだけあります`CRichEditView`各`CRichEditDoc`です。  
  
##  <a name="m_brtf"></a>  :M_brtf  
 ときに**TRUE**、ことを示します[CRichEditCtrl::StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin)と[CRichEditCtrl::StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout)段落と文字の書式設定特性を格納する必要があります。  
  
```  
BOOL m_bRTF;  
```  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル ワードパッド](../../visual-cpp-samples.md)   
 [COleServerDoc クラス](../../mfc/reference/coleserverdoc-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRichEditView クラス](../../mfc/reference/cricheditview-class.md)   
 [CRichEditCntrItem クラス](../../mfc/reference/cricheditcntritem-class.md)   
 [COleDocument クラス](../../mfc/reference/coledocument-class.md)   
 [CRichEditCtrl クラス](../../mfc/reference/cricheditctrl-class.md)
