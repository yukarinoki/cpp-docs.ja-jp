---
title: CMFCPreviewCtrlImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl::Create
- AFXWIN/CMFCPreviewCtrlImpl::Destroy
- AFXWIN/CMFCPreviewCtrlImpl::Focus
- AFXWIN/CMFCPreviewCtrlImpl::GetDocument
- AFXWIN/CMFCPreviewCtrlImpl::Redraw
- AFXWIN/CMFCPreviewCtrlImpl::SetDocument
- AFXWIN/CMFCPreviewCtrlImpl::SetHost
- AFXWIN/CMFCPreviewCtrlImpl::SetPreviewVisuals
- AFXWIN/CMFCPreviewCtrlImpl::SetRect
- AFXWIN/CMFCPreviewCtrlImpl::DoPaint
- AFXWIN/CMFCPreviewCtrlImpl::m_clrBackColor
- AFXWIN/CMFCPreviewCtrlImpl::m_clrTextColor
- AFXWIN/CMFCPreviewCtrlImpl::m_font
- AFXWIN/CMFCPreviewCtrlImpl::m_pDocument
dev_langs:
- C++
helpviewer_keywords:
- CMFCPreviewCtrlImpl [MFC], CMFCPreviewCtrlImpl
- CMFCPreviewCtrlImpl [MFC], Create
- CMFCPreviewCtrlImpl [MFC], Destroy
- CMFCPreviewCtrlImpl [MFC], Focus
- CMFCPreviewCtrlImpl [MFC], GetDocument
- CMFCPreviewCtrlImpl [MFC], Redraw
- CMFCPreviewCtrlImpl [MFC], SetDocument
- CMFCPreviewCtrlImpl [MFC], SetHost
- CMFCPreviewCtrlImpl [MFC], SetPreviewVisuals
- CMFCPreviewCtrlImpl [MFC], SetRect
- CMFCPreviewCtrlImpl [MFC], DoPaint
- CMFCPreviewCtrlImpl [MFC], m_clrBackColor
- CMFCPreviewCtrlImpl [MFC], m_clrTextColor
- CMFCPreviewCtrlImpl [MFC], m_font
- CMFCPreviewCtrlImpl [MFC], m_pDocument
ms.assetid: 06257fa0-54c9-478d-9d68-c9698c3f93ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb1ef84aabed69554ded868bbe9092c3e8b7082f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcpreviewctrlimpl-class"></a>CMFCPreviewCtrlImpl クラス
このクラスは、リッチ プレビュー用にシェルによって提供されるホスト ウィンドウに配置されているウィンドウを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCPreviewCtrlImpl : public CWnd;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl:: ~ CMFCPreviewCtrlImpl](#dtor)|プレビュー コントロール オブジェクトを破棄します。|  
|[CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl](#cmfcpreviewctrlimpl)|プレビュー コントロール オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::Create](#create)|オーバーロードされます。 Windows のウィンドウを作成する豊富なプレビュー ハンドラーによって呼び出されます。|  
|[CMFCPreviewCtrlImpl::Destroy](#destroy)|このコントロールを破棄する必要があるときに、豊富なプレビュー ハンドラーによって呼び出されます。|  
|[CMFCPreviewCtrlImpl::Focus](#focus)|このコントロールにフォーカスが入力を設定します。|  
|[CMFCPreviewCtrlImpl::GetDocument](#getdocument)|このプレビュー コントロールに接続されているドキュメントを返します。|  
|[CMFCPreviewCtrlImpl::Redraw](#redraw)|このコントロールを再描画するように指示します。|  
|[CMFCPreviewCtrlImpl::SetDocument](#setdocument)|ドキュメント実装とプレビュー コントロール間のリレーションシップを作成、プレビュー ハンドラーによって呼び出されます。|  
|[CMFCPreviewCtrlImpl::SetHost](#sethost)|このコントロールの新しい親を設定します。|  
|[CMFCPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|によって呼び出されますリッチ プレビュー ハンドラーのリッチ プレビューでのビジュアルを設定する必要があるときにコンテンツ。|  
|[CMFCPreviewCtrlImpl::SetRect](#setrect)|このコントロールの新しい外接する四角形を設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::DoPaint](#dopaint)|プレビューを表示するためにフレームワークによって呼び出されます。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::m_clrBackColor](#m_clrbackcolor)|プレビュー ウィンドウの背景色です。|  
|[CMFCPreviewCtrlImpl::m_clrTextColor](#m_clrtextcolor)|プレビュー ウィンドウのテキストの色。|  
|[CMFCPreviewCtrlImpl::m_font](#m_font)|プレビュー ウィンドウでテキストを表示するために使用するフォントです。|  
|[CMFCPreviewCtrlImpl::m_pDocument](#m_pdocument)|コントロールにコンテンツを持つがプレビューされているドキュメントへのポインター。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h    
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPreviewCtrlImpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)

## <a name="cmfcpreviewctrlimpl"></a> CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl
プレビュー コントロール オブジェクトを構築します。

### <a name="syntax"></a>構文
CMFCPreviewCtrlImpl() です。  

## <a name="create"></a> CMFCPreviewCtrlImpl::Create
オーバーロードされます。 Windows のウィンドウを作成する豊富なプレビュー ハンドラーによって呼び出されます。  
  
### <a name="syntax"></a>構文  
  
```  
virtual BOOL Create(  
   HWND hWndParent,  
   const RECT* prc  
);  
virtual BOOL Create(  
   HWND hWndParent,  
   const RECT* prc,  
   CCreateContext* pContext  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 リッチ プレビュー用にシェルによって提供される、ホスト ウィンドウへのハンドル。  
  
 `prc`  
 初期サイズとウィンドウの位置を指定します。  
  
 `pContext`  
 コンテキストの作成へのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 作成が成功した場合それ以外の場合`FALSE`です。  
  
## <a name="destroy"></a> CMFCPreviewCtrlImpl::Destroy
このコントロールを破棄する必要があるときに、豊富なプレビュー ハンドラーによって呼び出されます。  
  
### <a name="syntax"></a>構文  
  
```  
virtual void Destroy();  
```  
  
## <a name="dopaint"></a> CMFCPreviewCtrlImpl::DoPaint  
プレビューを表示するためにフレームワークによって呼び出されます。  
  
### <a name="syntax"></a>構文  
  
```  
virtual void DoPaint(  
   CPaintDC* pDC  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 描画のデバイス コンテキストへのポインター。  


## <a name="focus"></a> CMFCPreviewCtrlImpl::Focus  
このコントロールにフォーカスが入力を設定します。  
  
### <a name="syntax"></a>構文  
  
```  
virtual void Focus();  
```  
## <a name="getdocument"></a> CMFCPreviewCtrlImpl::GetDocument
このプレビュー コントロールに接続されているドキュメントを返します。  
  
### <a name="syntax"></a>構文  
  
```  
ATL::IDocument* GetDocument();  
```  
  
### <a name="return-value"></a>戻り値  
 コントロールにコンテンツを持つがプレビューされているドキュメントへのポインター。

## <a name="m_clrbackcolor"></a> CMFCPreviewCtrlImpl::m_clrBackColor  
プレビュー ウィンドウの背景色です。  
  
### <a name="syntax"></a>構文  
  
```  
COLORREF m_clrBackColor;  
```  

## <a name="m_clrtextcolor"></a> CMFCPreviewCtrlImpl::m_clrTextColor
プレビュー ウィンドウのテキストの色。  
  
### <a name="syntax"></a>構文  
  
```  
COLORREF m_clrTextColor;  
```  
## <a name="m_font"></a> CMFCPreviewCtrlImpl::m_font フォントが、プレビュー ウィンドウのテキストを表示するために使用します。  
  
### <a name="syntax"></a>構文  
  
```  
CFont m_font;  
```  
## <a name="m_pdocument"></a> CMFCPreviewCtrlImpl::m_pDocument  
コントロールにコンテンツを持つがプレビューされているドキュメントへのポインター。  
  
### <a name="syntax"></a>構文  
  
```  
ATL::IDocument* m_pDocument;  
```  

## <a name="redraw"></a> CMFCPreviewCtrlImpl::Redraw  
このコントロールを再描画するように指示します。  
  
### <a name="syntax"></a>構文  
  
```  
virtual void Redraw();  
```  
## <a name="setdocument"></a> CMFCPreviewCtrlImpl::SetDocument 
ドキュメント実装とプレビュー コントロール間のリレーションシップを作成、プレビュー ハンドラーによって呼び出されます。  
  
### <a name="syntax"></a>構文  
  
```  
void SetDocument(  
   IDocument* pDocument  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDocument`  
 ドキュメント実装へのポインター。  

## <a name="sethost"></a> CMFCPreviewCtrlImpl::SetHost  
このコントロールの新しい親を設定します。  
  
### <a name="syntax"></a>構文  
  
```  
virtual void SetHost(  
   HWND hWndParent  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 新しい親ウィンドウへのハンドル。  

## <a name="setpreviewvisuals"></a> CMFCPreviewCtrlImpl::SetPreviewVisuals  
によって呼び出されますリッチ プレビュー ハンドラーのリッチ プレビューでのビジュアルを設定する必要があるときにコンテンツ。  
  
### <a name="syntax"></a>構文  
  
```  
virtual void SetPreviewVisuals(  
   COLORREF clrBack,  
   COLORREF clrText,  
   const LOGFONTW *plf  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `clrBack`  
 プレビュー ウィンドウの背景色です。  
  
 `clrText`  
 プレビュー ウィンドウのテキストの色。  
  
 `plf`  
 プレビュー ウィンドウでテキストを表示するために使用するフォントです。 

##  <a name="setrect"></a> CMFCPreviewCtrlImpl::SetRect  
このコントロールの新しい外接する四角形を設定します。  
  
### <a name="syntax"></a>構文  
  
```  
virtual void SetRect(  
   const RECT* prc,  
   BOOL bRedraw  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `prc`  
 新しいサイズとプレビュー コントロールの位置を指定します。  
  
 `bRedraw`  
 コントロールを再描画されるかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 通常、ホスト コントロールがサイズ変更されると、新しい外接する四角形が設定されます。  

## <a name="dtor"></a> CMFCPreviewCtrlImpl:: ~ CMFCPreviewCtrlImpl  
プレビュー コントロール オブジェクトを破棄します。  
  
### <a name="syntax"></a>構文  
  
```  
virtual ~CMFCPreviewCtrlImpl();  
```  
  
