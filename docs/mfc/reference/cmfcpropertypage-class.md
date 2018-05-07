---
title: CMFCPropertyPage クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage::CMFCPropertyPage
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyPage [MFC], CMFCPropertyPage
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3352841b1b495d1718ffa6be034239ecd7e50c6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcpropertypage-class"></a>CMFCPropertyPage クラス
`CMFCPropertyPage`クラスは、プロパティ ページでのポップアップ メニューの表示をサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCPropertyPage : public CPropertyPage  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPropertyPage::CMFCPropertyPage](#cmfcpropertypage)|`CMFCPropertyPage` オブジェクトを構築します。|  
|`CMFCPropertyPage::~CMFCPropertyPage`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCPropertyPage::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|`CMFCPropertyPage::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|`CMFCPropertyPage::OnSetActive`|このメンバー関数はページがユーザーによって選択され、アクティブになったときに、フレームワークによって呼び出されます。 (上書き[CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive))。|  
|`CMFCPropertyPage::PreTranslateMessage`|ディスパッチされる前に、ウィンドウ メッセージを変換、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数。 詳細とメソッドの構文は、次を参照してください。 [cwnd::pretranslatemessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)です。 (`CPropertyPage::PreTranslateMessage` をオーバーライドします)。|  
  
## <a name="remarks"></a>コメント  
 `CMFCPropertyPage`クラスは、[タブ] ダイアログ ボックスとして知られている、プロパティ シートの各ページを表します。  
  
 使用して、`CMFCPropertyPage`クラスと共に、 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)クラスです。 [プロパティ] ページのメニューを使用するすべて置換の`CPropertyPage`クラス、`CMFCPropertyPage`クラスです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxpropertypage.h  
  
##  <a name="cmfcpropertypage"></a>  CMFCPropertyPage::CMFCPropertyPage  
 `CMFCPropertyPage` オブジェクトを構築します。  
  
```  
CMFCPropertyPage(
    UINT nIDTemplate,  
    UINT nIDCaption=0);

 
CMFCPropertyPage(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption=0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDTemplate`  
 このページのテンプレートのリソース ID です。  
  
 `nIDCaption`  
 このページのタブにラベルのリソース ID。 0 の場合、このページのダイアログ ボックス テンプレートから、名前を取得します。 既定値は 0 です。  
  
 `lpszTemplateName`  
 このページのテンプレートの名前を指します。 ことはできません`NULL`です。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 コンス トラクターのパラメーターの詳細については、次を参照してください。 [CPropertyPage::CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage)です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertySheet クラス](../../mfc/reference/cmfcpropertysheet-class.md)
