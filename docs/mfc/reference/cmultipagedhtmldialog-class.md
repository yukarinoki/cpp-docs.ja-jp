---
title: 関数クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog
dev_langs:
- C++
helpviewer_keywords:
- CMultiPageDHtmlDialog [MFC], CMultiPageDHtmlDialog
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2be83e3791121bdea4d7f650f7d6801517df31ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmultipagedhtmldialog-class"></a>関数クラス
マルチページ ダイアログは、複数の HTML ページを順番に表示し、各ページのイベントを処理します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMultiPageDHtmlDialog : public CDHtmlDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](#cmultipagedhtmldialog)|マルチページ (ウィザード スタイル) DHTML dialog オブジェクトを構築します。|  
|[関数:: ~ 関数](#cmultipagedhtmldialog__~cmultipagedhtmldialog)|マルチページ DHTML dialog オブジェクトを破棄します。|  
  
## <a name="remarks"></a>コメント  
 これを行うためのメカニズムは、 [DHTML と URL のイベント マップ](dhtml-event-maps.md)、各ページのイベントのマップが埋め込まれているが含まれています。  
  
## <a name="example"></a>例  
 このマルチページのダイアログ ボックスには、簡単なウィザードのような機能を定義する 3 つの HTML リソースが想定しています。 最初のページには、`Next`ボタン、もう 1 つ、 **Prev**と`Next` ボタン、および 3 番目、 **Prev**ボタンをクリックします。 ハンドラー関数を呼び出すボタンが押されると[CDHtmlDialog::LoadFromResource](../../mfc/reference/cdhtmldialog-class.md#loadfromresource)適切な新しいページを読み込みます。  
  
 (CMyMultiPageDlg.h) で、クラス宣言の関連部分。  
  
 [!code-cpp[NVC_MFCDocView#181](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_1.h)]  
  
 クラスの実装 (CMyMultipageDlg.cpp) 内の関連部分:  
  
 [!code-cpp[NVC_MFCDocView#182](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDHtmlSinkHandlerBase2`  
  
 `CDHtmlSinkHandlerBase1`  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDHtmlSinkHandler`  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDHtmlEventSink`  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)  
  
 `CMultiPageDHtmlDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdhtml.h  
  
##  <a name="cmultipagedhtmldialog"></a>  CMultiPageDHtmlDialog::CMultiPageDHtmlDialog  
 マルチページ (ウィザード スタイル) DHTML dialog オブジェクトを構築します。  
  
```  
CMultiPageDHtmlDialog(
    LPCTSTR lpszTemplateName,  
    LPCTSTR szHtmlResID = NULL,  
    CWnd* pParentWnd = NULL);

 
CMultiPageDHtmlDialog(
    UINT nIDTemplate,  
    UINT nHtmlResID = 0,  
    CWnd* pParentWnd = NULL);  
  
CMultiPageDHtmlDialog();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszTemplateName`  
 ダイアログ テンプレート リソースの名前を表す null で終わる文字列。  
  
 `szHtmlResID`  
 HTML リソースの名前を表す null で終わる文字列。  
  
 `pParentWnd`  
 親またはオーナー ウィンドウのオブジェクトへのポインター (型の[CWnd](../../mfc/reference/cwnd-class.md)) ダイアログ オブジェクトが属しています。 場合は**NULL**、ダイアログ オブジェクトの親ウィンドウがアプリケーションのメイン ウィンドウに設定します。  
  
 `nIDTemplate`  
 ダイアログ テンプレート リソースの ID 番号が含まれています。  
  
 `nHtmlResID`  
 HTML リソースの ID 番号が含まれています。  
  
##  <a name="_dtorcmultipagedhtmldialog"></a>  関数:: ~ 関数  
 マルチページ DHTML dialog オブジェクトを破棄します。  
  
```  
virtual ~CMultiPageDHtmlDialog();
```  
  
## <a name="see-also"></a>関連項目  
 [CDHtmlDialog クラス](../../mfc/reference/cdhtmldialog-class.md)
