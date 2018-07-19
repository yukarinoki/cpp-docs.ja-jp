---
title: COleUpdateDialog クラス |Microsoft Docs
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
ms.openlocfilehash: fc5d51bfeb18b51be5a54c51046e3cd420fb1cb8
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852108"
---
# <a name="coleupdatedialog-class"></a>COleUpdateDialog クラス
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
|[COleUpdateDialog::DoModal](#domodal)|表示、**リンクの編集**更新モードでのダイアログ ボックス。|  
  
## <a name="remarks"></a>Remarks  
 OLE に固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)します。  
  
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
 更新が必要なリンクを含むドキュメントを指します。  
  
 *bUpdateLinks*  
 リンク オブジェクトを更新するかどうかを決定するフラグ。  
  
 *bUpdateEmbeddings*  
 埋め込みオブジェクトを更新するかどうかを決定するフラグ。  
  
 *pParentWnd*  
 親またはオーナー ウィンドウのオブジェクトを指し示す (型の`CWnd`) ダイアログ オブジェクトが属しています。 NULL の場合、ダイアログ ボックスの親ウィンドウは、メイン アプリケーション ウィンドウに設定されます。  
  
### <a name="remarks"></a>Remarks  
 この関数の作成のみを`COleUpdateDialog`オブジェクト。 ダイアログ ボックスを表示するには、呼び出す[DoModal](../../mfc/reference/colelinksdialog-class.md#domodal)します。 このクラスは、の代わりに使用する必要があります`COleLinksDialog`リンクまたは埋め込みアイテムの既存ののみを更新する場合。  
  
##  <a name="domodal"></a>  COleUpdateDialog::DoModal  
 モードを更新するリンクの編集 ダイアログ ボックスが表示されます。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスの完了ステータス。 次のいずれかの値です。  
  
- IDOK ダイアログ ボックスが正常に返された場合。  
  
- 現在のドキュメントでリンクまたは埋め込み項目を更新する必要がある場合は IDCANCEL。  
  
- IDABORT 場合は、エラーが発生しました。 IDABORT が返される場合、 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror)発生したエラーの種類に関する詳細を取得します。 考えられるエラーの一覧については、次を参照してください。、[される](http://msdn.microsoft.com/library/windows/desktop/ms679703)Windows SDK 内の関数。  
  
### <a name="remarks"></a>Remarks  
 ユーザーが [キャンセル] ボタンを選択しない限り、すべてのリンクや埋め込みが更新されます。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの OCLIENT](../../visual-cpp-samples.md)   
 [COleLinksDialog クラス](../../mfc/reference/colelinksdialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleLinksDialog クラス](../../mfc/reference/colelinksdialog-class.md)
