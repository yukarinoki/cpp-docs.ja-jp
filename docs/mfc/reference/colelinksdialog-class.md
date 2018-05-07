---
title: 関数クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleLinksDialog
- AFXODLGS/COleLinksDialog
- AFXODLGS/COleLinksDialog::COleLinksDialog
- AFXODLGS/COleLinksDialog::DoModal
- AFXODLGS/COleLinksDialog::m_el
dev_langs:
- C++
helpviewer_keywords:
- COleLinksDialog [MFC], COleLinksDialog
- COleLinksDialog [MFC], DoModal
- COleLinksDialog [MFC], m_el
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e190c8b8cb11fefccb2847214dcaebf713f35dc4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="colelinksdialog-class"></a>関数クラス
OLE の [リンクの編集] ダイアログ ボックスに使用します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleLinksDialog : public COleDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleLinksDialog::COleLinksDialog](#colelinksdialog)|`COleLinksDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleLinksDialog::DoModal](#domodal)|OLE の [リンクの編集] ダイアログ ボックスが表示されます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleLinksDialog::m_el](#m_el)|型の構造体**される** ダイアログ ボックスの動作を制御します。|  
  
## <a name="remarks"></a>コメント  
 クラスのオブジェクトを作成`COleLinksDialog`をこのダイアログ ボックスを呼び出したいとします。 後に、`COleLinksDialog`オブジェクトが構築された、使用することができます、[各](#m_el)値やダイアログ ボックスのコントロールの状態を初期化するためにします。 `m_el`構造体は型**される**です。 このダイアログ ボックスの使い方の詳細については、次を参照してください。、 [DoModal](#domodal)メンバー関数。  
  
> [!NOTE]
>  アプリケーション コンテナーのウィザードで生成されたコードでは、このクラスを使用します。  
  
 詳細については、次を参照してください。、[される](http://msdn.microsoft.com/library/windows/desktop/ms678492)Windows SDK 内の構造。  
  
 OLE に固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleLinksDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxodlgs.h  
  
##  <a name="domodal"></a>  COleLinksDialog::DoModal  
 OLE の [リンクの編集] ダイアログ ボックスが表示されます。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスの終了ステータスです。 次のいずれかの値です。  
  
- **IDOK**  ダイアログ ボックスが正常に表示された場合。  
  
- **IDCANCEL**場合は、ユーザーがダイアログ ボックスをキャンセルします。  
  
- **IDABORT**場合はエラーが発生しました。 場合**IDABORT**は呼び出し、返される、`COleDialog::GetLastError`の詳細については、発生したエラーの種類を取得します。 考えられるエラーの一覧については、次を参照してください。、[される](http://msdn.microsoft.com/library/windows/desktop/ms679703)Windows SDK 内の関数。  
  
### <a name="remarks"></a>コメント  
 メンバーを設定してさまざまなダイアログ ボックスのコントロールを初期化する場合、[各](#m_el)構造体、行う必要があります、呼び出す前に`DoModal`はダイアログ オブジェクトを構築します。  
  
##  <a name="colelinksdialog"></a>  COleLinksDialog::COleLinksDialog  
 `COleLinksDialog` オブジェクトを構築します。  
  
```  
COleLinksDialog (
    COleDocument* pDoc,  
    CView* pView,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDoc`  
 編集しようとするリンクを含む OLE ドキュメントへのポインター。  
  
 `pView`  
 上の現在のビューを指す`pDoc`です。  
  
 `dwFlags`  
 作成フラグは、0 を格納または**ELF_SHOWHELP**  ダイアログ ボックスが表示されたら、ヘルプ ボタンが表示されるかどうかを指定します。  
  
 `pParentWnd`  
 親またはオーナー ウィンドウ オブジェクトを指し示す (型の`CWnd`) ダイアログ オブジェクトが属しています。 場合は**NULL**、ダイアログ ボックスの親ウィンドウがアプリケーションのメイン ウィンドウに設定します。  
  
### <a name="remarks"></a>コメント  
 この関数はのみ、`COleLinksDialog`オブジェクト。 ダイアログ ボックスを表示するには[DoModal](#domodal)関数。  
  
##  <a name="m_el"></a>  COleLinksDialog::m_el  
 型の構造体**される**リンクの編集 ダイアログ ボックスの動作を制御するために使用します。  
  
```  
OLEUIEDITLINKS m_el;  
```  
  
### <a name="remarks"></a>コメント  
 この構造体のメンバーは、直接またはメンバー関数のいずれかに変更できます。  
  
 詳細については、次を参照してください。、[される](http://msdn.microsoft.com/library/windows/desktop/ms678492)Windows SDK 内の構造。  
  
## <a name="see-also"></a>関連項目  
 [関数クラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)
