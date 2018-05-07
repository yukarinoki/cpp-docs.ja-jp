---
title: CMFCRibbonCustomizeDialog クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCustomizeDialog [MFC], CMFCRibbonCustomizeDialog
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d195b2888c47a318369df13c371f85b21cc7bf84
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcribboncustomizedialog-class"></a>CMFCRibbonCustomizeDialog クラス
リボンが表示されます**カスタマイズ**ページ。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonCustomizeDialog : public CMFCPropertySheet  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog](#cmfcribboncustomizedialog)|`CMFCRibbonCustomizeDialog` オブジェクトを構築します。|  
|`CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCRibbonCustomizeDialog::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
  
## <a name="remarks"></a>コメント  
 AFX_WM_ON_RIBBON_CUSTOMIZE メッセージを処理しない場合、またはメッセージ ハンドラーから 0 を返した場合、MFC を自動的にこのクラスをインスタンス化します。  
  
 アプリケーションで、リボンを表示するこのクラスを使用するかどうかは**カスタマイズ** ダイアログ ボックスでのみインスタンス化し、呼び出し、`DoModal`メソッドです。  
  
 このクラスから派生ため[CMFCPropertySheet クラス](../../mfc/reference/cmfcpropertysheet-class.md)を使用してカスタム ページを追加することができます、 `CMFCPropertySheet` API です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
 [CMFCRibbonCustomizeDialog](../../mfc/reference/cmfcribboncustomizedialog-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxribboncustomizedialog.h  
  
##  <a name="cmfcribboncustomizedialog"></a>  CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog  
 `CMFCRibbonCustomizeDialog` オブジェクトを構築します。  
  
```  
CMFCRibbonCustomizeDialog(
    CWnd* pWndParent,  
    CMFCRibbonBar* pRibbon);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndParent`  
 親ウィンドウ (通常はメイン フレーム) へのポインター。  
  
 [入力] `pRibbon`  
 ポインター、`CMFCRibbonBar`カスタマイズができます。  
  
### <a name="example"></a>例  
 次の例で作成する方法、`CMFCRibbonCustomizeDialog`オブジェクト。  
  
 [!code-cpp[NVC_MFC_RibbonApp#18](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizedialog-class_1.cpp)]  
  
### <a name="remarks"></a>コメント  
 コンス トラクターをインスタンス化、 [CMFCRibbonCustomizePropertyPage クラス](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)オブジェクトおよびプロパティ シート ページのコレクションに追加します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)
