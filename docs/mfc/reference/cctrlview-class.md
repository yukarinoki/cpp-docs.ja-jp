---
title: CCtrlView クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCtrlView
- AFXWIN/CCtrlView
- AFXWIN/CCtrlView::CCtrlView
- AFXWIN/CCtrlView::OnDraw
- AFXWIN/CCtrlView::PreCreateWindow
- AFXWIN/CCtrlView::m_dwDefaultStyle
- AFXWIN/CCtrlView::m_strClass
dev_langs:
- C++
helpviewer_keywords:
- CCtrlView [MFC], CCtrlView
- CCtrlView [MFC], OnDraw
- CCtrlView [MFC], PreCreateWindow
- CCtrlView [MFC], m_dwDefaultStyle
- CCtrlView [MFC], m_strClass
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3503f59096d3879f986b2a8c99bdb9823ef4e24
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cctrlview-class"></a>CCtrlView クラス
Windows 98 および Windows NT Version 3.51 以降がサポートするコモン コントロールにドキュメント/ビュー アーキテクチャを適合させます。  
  
## <a name="syntax"></a>構文  
  
```  
class CCtrlView : public CView  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CCtrlView::CCtrlView](#cctrlview)|`CCtrlView` オブジェクトを構築します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CCtrlView::OnDraw](#ondraw)|指定したデバイス コンテキストを使用して描画するためにフレームワークによって呼び出されます。|  
|[CCtrlView::PreCreateWindow](#precreatewindow)|`CCtrlView` オブジェクトに関連付けられている Windows のウィンドウが作成される前に呼び出されます。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CCtrlView::m_dwDefaultStyle](#m_dwdefaultstyle)|ビュー クラスの既定のスタイルが含まれています。|  
|[CCtrlView::m_strClass](#m_strclass)|ビュー クラスの Windows クラス名が含まれています。|  
  
## <a name="remarks"></a>コメント  
 クラス`CCtrlView`とその派生[CEditView](../../mfc/reference/ceditview-class.md)、 [CListView](../../mfc/reference/clistview-class.md)、 [CTreeView](../../mfc/reference/ctreeview-class.md)、および[CRichEditView](../../mfc/reference/cricheditview-class.md)、改変、Windows 95/98 および Windows NT version 3.51 以降でサポートされる新しいコモン コントロールにドキュメント/ビュー アーキテクチャ。 ドキュメント/ビュー アーキテクチャの詳細については、次を参照してください。[ドキュメント/ビュー アーキテクチャ](../../mfc/document-view-architecture.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CCtrlView`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cctrlview"></a>  CCtrlView::CCtrlView  
 `CCtrlView` オブジェクトを構築します。  
  
```  
CCtrlView(
    LPCTSTR lpszClass,  
    DWORD dwStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszClass`  
 ビュー クラスのウィンドウ クラス名。  
  
 `dwStyle`  
 ビュー クラスのスタイルです。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、新しいフレーム ウィンドウが作成されるか、ウィンドウを分割時に、コンス トラクターを呼び出します。 オーバーライド[:oninitialupdate](../../mfc/reference/cview-class.md#oninitialupdate)ドキュメントをアタッチした後、ビューを初期化します。 呼び出す[cwnd::create](../../mfc/reference/cwnd-class.md#create)または[とき](../../mfc/reference/cwnd-class.md#createex)Windows オブジェクトを作成します。  
  
##  <a name="m_strclass"></a>  CCtrlView::m_strClass  
 ビュー クラスの Windows クラス名が含まれています。  
  
```  
CString m_strClass;  
```  
  
##  <a name="m_dwdefaultstyle"></a>  CCtrlView::m_dwDefaultStyle  
 ビュー クラスの既定のスタイルが含まれています。  
  
```  
DWORD m_dwDefaultStyle;  
```  
  
### <a name="remarks"></a>コメント  
 ウィンドウの作成時に、このスタイルが適用されます。  
  
##  <a name="ondraw"></a>  CCtrlView::OnDraw  
 内容を描画するためにフレームワークによって呼び出される、`CCtrlView`オブジェクトの指定したデバイス コンテキストを使用します。  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 図面が発生しているデバイス コンテキストへのポインター。  
  
### <a name="remarks"></a>コメント  
 `OnDraw` 画面の表示で指定した画面デバイス コンテキストを渡すことは通常呼び出されます`pDC`です。  
  
##  <a name="precreatewindow"></a>  CCtrlView::PreCreateWindow  
 `CWnd` オブジェクトに関連付けられている Windows のウィンドウが作成される前に呼び出されます。  
  
```  
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### <a name="parameters"></a>パラメーター  
 *cs*  
 A [CREATESTRUCT](http://msdn.microsoft.com/library/windows/desktop/ms632603)構造体。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウの作成を続行する必要があります。 場合は 0 以外。作成エラーを示すために 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数を直接呼び出すことはありません。  
  
 この関数の既定の実装、 **NULL**ウィンドウ クラス名を適切な既定値を置き換えます。 変更するには、このメンバー関数をオーバーライドします`CREATESTRUCT`ウィンドウが作成される前に構造体します。  
  
 各クラスから派生した`CCtrlView`そのオーバーライドの独自の機能が追加`PreCreateWindow`です。 仕様では、これらの派生`PreCreateWindow`記載されていません。 各クラスとスタイルの間の相互依存関係に適切なスタイルを決定するには、アプリケーションの基本クラスの MFC ソース コードを調べることができます。 オーバーライドする場合`PreCreateWindow`アプリケーションの基本クラスで使用するスタイルが MFC のソース コードから収集された情報を使用して、必要な機能を提供するかどうかを判断できます。  
  
 ウィンドウ スタイルを変更する方法の詳細については、次を参照してください。、 [MFC で作成したウィンドウのスタイルを変更する](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CView クラス](../../mfc/reference/cview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CTreeView クラス](../../mfc/reference/ctreeview-class.md)   
 [CListView クラス](../../mfc/reference/clistview-class.md)   
 [CRichEditView クラス](../../mfc/reference/cricheditview-class.md)
