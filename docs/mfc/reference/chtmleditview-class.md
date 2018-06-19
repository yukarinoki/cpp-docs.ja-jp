---
title: CHtmlEditView クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHtmlEditView
- AFXHTML/CHtmlEditView
- AFXHTML/CHtmlEditView::CHtmlEditView
- AFXHTML/CHtmlEditView::Create
- AFXHTML/CHtmlEditView::GetDHtmlDocument
- AFXHTML/CHtmlEditView::GetStartDocument
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditView [MFC], CHtmlEditView
- CHtmlEditView [MFC], Create
- CHtmlEditView [MFC], GetDHtmlDocument
- CHtmlEditView [MFC], GetStartDocument
ms.assetid: 166c8ba8-3fb5-4dd7-a9ea-5bca662d00f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 10f474ce860bf5d9071a93f17654123f4777efa7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367345"
---
# <a name="chtmleditview-class"></a>CHtmlEditView クラス
MFC のドキュメント/ビュー アーキテクチャのコンテキストで WebBrowser 編集プラットフォームの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase<CHtmlEditView>  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CHtmlEditView::CHtmlEditView](#chtmleditview)|`CHtmlEditView` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CHtmlEditView::Create](#create)|新しいウィンドウ オブジェクトを作成します。|  
|[CHtmlEditView::GetDHtmlDocument](#getdhtmldocument)|返します、 **IHTMLDocument2**現在のドキュメントに対するインターフェイスです。|  
|[CHtmlEditView::GetStartDocument](#getstartdocument)|このビューの既定のドキュメントの名前を取得します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 [CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)  
  
 [CHtmlView](../../mfc/reference/chtmlview-class.md)  
  
 `CHtmlEditView`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxhtml.h  
  
##  <a name="chtmleditview"></a>  CHtmlEditView::CHtmlEditView  
 `CHtmlEditView` オブジェクトを構築します。  
  
```  
CHtmlEditView();
```  
  
##  <a name="create"></a>  CHtmlEditView::Create  
 新しいウィンドウ オブジェクトを作成します。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszClassName`  
 Windows クラスの名前を null で終わる文字列へのポインター。 クラス名に登録されている任意の名前を指定できます、 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)グローバル関数または**RegisterClass** Windows の機能です。 場合**NULL**、定義済みの既定値を使用して[CFrameWnd](../../mfc/reference/cframewnd-class.md)属性。  
  
 `lpszWindowName`  
 ウィンドウの名前を表す文字の null で終わる文字列へのポインター。  
  
 `dwStyle`  
 ウィンドウのスタイル属性を指定します。 既定では、 **WS_VISIBLE**と**WS_CHILD**ウィンドウ スタイルが設定されます。  
  
 `rect`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体のサイズとウィンドウの位置を指定します。 `rectDefault`値により、Windows を新しいウィンドウの位置とサイズを指定します。  
  
 `pParentWnd`  
 コントロールの親ウィンドウへのポインター。  
  
 `nID`  
 ビューの ID 番号。 既定では、' éý ' **AFX_IDW_PANE_FIRST**です。  
  
 `pContext`  
 ポインター、 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)です。 **NULL**既定です。  
  
### <a name="remarks"></a>コメント  
 このメソッドが含まれている WebBrowser の呼び出すことも**移動**を既定のドキュメントを読み込む方法 (を参照してください[CHtmlEditView::GetStartDocument](#getstartdocument))。  
  
##  <a name="getdhtmldocument"></a>  CHtmlEditView::GetDHtmlDocument  
 返します、 **IHTMLDocument2**現在のドキュメントに対するインターフェイスです。  
  
```  
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `ppDocument`  
 [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx)インターフェイスです。  
  
##  <a name="getstartdocument"></a>  CHtmlEditView::GetStartDocument  
 このビューの既定のドキュメントの名前を取得します。  
  
```  
virtual LPCTSTR GetStartDocument();
```  
  
## <a name="see-also"></a>関連項目  
 [HTMLEdit サンプル](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)


