---
title: 関数クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleUpdateDialog
- AFXODLGS/COleUpdateDialog
- AFXODLGS/COleUpdateDialog::COleUpdateDialog
- AFXODLGS/COleUpdateDialog::DoModal
dev_langs:
- C++
helpviewer_keywords:
- COleUpdateDialog [MFC], COleUpdateDialog
- COleUpdateDialog [MFC], DoModal
ms.assetid: 699ca980-52b1-4cf8-9ab1-ac6767ad5b0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0208a24b69c1884d72c0ae525ce95b3d3258271
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079975"
---
# <a name="coleupdatedialog-class"></a>関数クラス
OLE の [リンクの編集] ダイアログ ボックスを使って、ドキュメント内の既存のリンク オブジェクトや埋め込みオブジェクトの更新のみを行います。これは、OLE の [リンクの編集] ダイアログ ボックスの特別な使い方です。  
  
## <a name="syntax"></a>構文  
  
```  
class COleUpdateDialog : public COleLinksDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleUpdateDialog::COleUpdateDialog](#coleupdatedialog)|`COleUpdateDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleUpdateDialog::DoModal](#domodal)|表示、**リンクの編集**更新モード ダイアログ ボックス。|  
  
## <a name="remarks"></a>Remarks  
 OLE に固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)  
  
 `COleUpdateDialog`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxodlgs.h  
  
##  <a name="coleupdatedialog"></a>  COleUpdateDialog::COleUpdateDialog  
 `COleUpdateDialog` オブジェクトを構築します。  
  
```  
explicit COleUpdateDialog(
    COleDocument* pDoc,  
    BOOL bUpdateLinks = TRUE,  
    BOOL bUpdateEmbeddings = FALSE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDoc*  
 更新が必要なリンクを含むドキュメントへのポインター。  
  
 *bUpdateLinks*  
 リンク オブジェクトを更新するかどうかを決定するフラグ。  
  
 *bUpdateEmbeddings*  
 埋め込みオブジェクトを更新するかどうかを決定するフラグ。  
  
 *pParentWnd*  
 親またはオーナー ウィンドウ オブジェクトを指し示す (型の`CWnd`) ダイアログ オブジェクトが属しています。 場合は**NULL**、ダイアログ ボックスの親ウィンドウは、アプリケーションのメイン ウィンドウに設定されます。  
  
### <a name="remarks"></a>Remarks  
 この関数はのみ、`COleUpdateDialog`オブジェクト。 ダイアログ ボックスを表示するには、呼び出す[DoModal](../../mfc/reference/colelinksdialog-class.md#domodal)です。 このクラスは、の代わりに使用する必要があります`COleLinksDialog`リンクまたは埋め込みアイテムの既存ののみを更新する場合。  
  
##  <a name="domodal"></a>  COleUpdateDialog::DoModal  
 リンクの編集 ダイアログ ボックスに表示は更新モードです。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスの終了ステータスです。 次のいずれかの値です。  
  
- **IDOK**  ダイアログ ボックスが正常に返された場合。  
  
- **IDCANCEL**更新が必要な現在のドキュメントにリンクまたは埋め込み項目はどれもかどうか。  
  
- **IDABORT**場合はエラーが発生しました。 場合**IDABORT**は呼び出し、返される、 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror)の詳細については、発生したエラーの種類を取得します。 考えられるエラーの一覧については、次を参照してください。、[される](http://msdn.microsoft.com/library/windows/desktop/ms679703)Windows SDK 内の関数。  
  
### <a name="remarks"></a>Remarks  
 ユーザーは [キャンセル] ボタンを選択しない限り、すべてのリンクや埋め込みが更新されます。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル OCLIENT](../../visual-cpp-samples.md)   
 [関数クラス](../../mfc/reference/colelinksdialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleLinksDialog クラス](../../mfc/reference/colelinksdialog-class.md)
