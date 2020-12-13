---
description: 詳細については、次を参照してください。 Cmfcプレビュー Ctrlimpl クラス
title: CMFCPreviewCtrlImpl クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 09e4b8e023a55110986aafccfd2646d8e7775c31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334726"
---
# <a name="cmfcpreviewctrlimpl-class"></a>CMFCPreviewCtrlImpl クラス

このクラスは、リッチプレビュー用にシェルによって提供されるホストウィンドウに配置されるウィンドウを実装します。

## <a name="syntax"></a>構文

```
class CMFCPreviewCtrlImpl : public CWnd;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cmfcプレビュー Ctrlimpl:: ~ Cmfcプレビュー Ctrlimpl](#dtor)|Preview コントロールオブジェクトを Destructs します。|
|[Cmfcプレビュー Ctrlimpl:: Cmfcプレビュー Ctrlimpl](#cmfcpreviewctrlimpl)|プレビューコントロールオブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cmfcプレビュー Ctrlimpl:: Create](#create)|オーバーロードされます。 Windows ウィンドウを作成するためのリッチプレビューハンドラーによって呼び出されます。|
|[Cmfcプレビュー Ctrlimpl::D estroy](#destroy)|このコントロールを破棄する必要がある場合に、リッチプレビューハンドラーによって呼び出されます。|
|[Cmfcプレビュー Ctrlimpl:: フォーカス](#focus)|このコントロールに入力フォーカスを設定します。|
|[Cmfcプレビュー Ctrlimpl:: GetDocument](#getdocument)|このプレビューコントロールに接続されているドキュメントを返します。|
|[Cmfcプレビュー Ctrlimpl:: 再描画](#redraw)|このコントロールに再描画を指示します。|
|[Cmfcプレビュー Ctrlimpl:: SetDocument](#setdocument)|ドキュメント実装とプレビューコントロールの間のリレーションシップを作成するために、プレビューハンドラーによって呼び出されます。|
|[Cmfcプレビューの Ctrlimpl:: SetHost](#sethost)|このコントロールの新しい親を設定します。|
|[Cmfcプレビュー Ctrlimpl:: Setプレビュービジュアル](#setpreviewvisuals)|リッチプレビューコンテンツのビジュアルを設定する必要がある場合に、豊富なプレビューハンドラーによって呼び出されます。|
|[Cmfcプレビュー Ctrlimpl:: SetRect](#setrect)|このコントロールの新しい外接する四角形を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[Cmfcプレビュー Ctrlimpl::D oPaint](#dopaint)|プレビューを表示するためにフレームワークによって呼び出されます。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[Cmfcプレビュー Ctrlimpl:: m_clrBackColor](#m_clrbackcolor)|プレビューウィンドウの背景色です。|
|[Cmfcプレビュー Ctrlimpl:: m_clrTextColor](#m_clrtextcolor)|プレビューウィンドウのテキストの色。|
|[Cmfcプレビュー Ctrlimpl:: m_font](#m_font)|プレビューウィンドウでテキストを表示するために使用されるフォントです。|
|[Cmfcプレビュー Ctrlimpl:: m_pDocument](#m_pdocument)|コントロールでコンテンツがプレビューされているドキュメントへのポインター。|

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCPreviewCtrlImpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)

## <a name="cmfcpreviewctrlimplcmfcpreviewctrlimpl"></a><a name="cmfcpreviewctrlimpl"></a> Cmfcプレビュー Ctrlimpl:: Cmfcプレビュー Ctrlimpl

プレビューコントロールオブジェクトを構築します。

### <a name="syntax"></a>構文

Cmfcプレビュー Ctrlimpl ();

## <a name="cmfcpreviewctrlimplcreate"></a><a name="create"></a> Cmfcプレビュー Ctrlimpl:: Create

オーバーロードされます。 Windows ウィンドウを作成するためのリッチプレビューハンドラーによって呼び出されます。

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

*hWndParent*<br/>
リッチプレビューのためにシェルによって提供されるホストウィンドウへのハンドル。

*中国語*<br/>
ウィンドウの初期サイズと位置を指定します。

*pContext*<br/>
作成コンテキストへのポインター。

### <a name="return-value"></a>戻り値

作成が成功した場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcpreviewctrlimpldestroy"></a><a name="destroy"></a> Cmfcプレビュー Ctrlimpl::D estroy

このコントロールを破棄する必要がある場合に、リッチプレビューハンドラーによって呼び出されます。

### <a name="syntax"></a>構文

```
virtual void Destroy();
```

## <a name="cmfcpreviewctrlimpldopaint"></a><a name="dopaint"></a> Cmfcプレビュー Ctrlimpl::D oPaint

プレビューを表示するためにフレームワークによって呼び出されます。

### <a name="syntax"></a>構文

```
virtual void DoPaint(
   CPaintDC* pDC
);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
描画するデバイスコンテキストへのポインター。

## <a name="cmfcpreviewctrlimplfocus"></a><a name="focus"></a> Cmfcプレビュー Ctrlimpl:: フォーカス

このコントロールに入力フォーカスを設定します。

### <a name="syntax"></a>構文

```
virtual void Focus();
```

## <a name="cmfcpreviewctrlimplgetdocument"></a><a name="getdocument"></a> Cmfcプレビュー Ctrlimpl:: GetDocument

このプレビューコントロールに接続されているドキュメントを返します。

### <a name="syntax"></a>構文

```
ATL::IDocument* GetDocument();
```

### <a name="return-value"></a>戻り値

コントロールでコンテンツがプレビューされているドキュメントへのポインター。

## <a name="cmfcpreviewctrlimplm_clrbackcolor"></a><a name="m_clrbackcolor"></a> Cmfcプレビュー Ctrlimpl:: m_clrBackColor

プレビューウィンドウの背景色です。

### <a name="syntax"></a>構文

```
COLORREF m_clrBackColor;
```

## <a name="cmfcpreviewctrlimplm_clrtextcolor"></a><a name="m_clrtextcolor"></a> Cmfcプレビュー Ctrlimpl:: m_clrTextColor

プレビューウィンドウのテキストの色。

### <a name="syntax"></a>構文

```
COLORREF m_clrTextColor;
```

## <a name="cmfcpreviewctrlimplm_font--font-used-to-display-text-in-the-preview-window"></a><a name="m_font"></a> Cmfcpreview Ctrlimpl:: m_font プレビューウィンドウにテキストを表示するために使用されるフォント。

### <a name="syntax"></a>構文

```
CFont m_font;
```

## <a name="cmfcpreviewctrlimplm_pdocument"></a><a name="m_pdocument"></a> Cmfcプレビュー Ctrlimpl:: m_pDocument

コントロールでコンテンツがプレビューされているドキュメントへのポインター。

### <a name="syntax"></a>構文

```
ATL::IDocument* m_pDocument;
```

## <a name="cmfcpreviewctrlimplredraw"></a><a name="redraw"></a> Cmfcプレビュー Ctrlimpl:: 再描画

このコントロールに再描画を指示します。

### <a name="syntax"></a>構文

```
virtual void Redraw();
```

## <a name="cmfcpreviewctrlimplsetdocument"></a><a name="setdocument"></a> Cmfcプレビュー Ctrlimpl:: SetDocument

ドキュメント実装とプレビューコントロールの間のリレーションシップを作成するために、プレビューハンドラーによって呼び出されます。

### <a name="syntax"></a>構文

```cpp
void SetDocument(
   IDocument* pDocument
);
```

### <a name="parameters"></a>パラメーター

*pDocument*<br/>
ドキュメントの実装へのポインター。

## <a name="cmfcpreviewctrlimplsethost"></a><a name="sethost"></a> Cmfcプレビューの Ctrlimpl:: SetHost

このコントロールの新しい親を設定します。

### <a name="syntax"></a>構文

```
virtual void SetHost(
   HWND hWndParent
);
```

### <a name="parameters"></a>パラメーター

*hWndParent*<br/>
新しい親ウィンドウへのハンドル。

## <a name="cmfcpreviewctrlimplsetpreviewvisuals"></a><a name="setpreviewvisuals"></a> Cmfcプレビュー Ctrlimpl:: Setプレビュービジュアル

リッチプレビューコンテンツのビジュアルを設定する必要がある場合に、豊富なプレビューハンドラーによって呼び出されます。

### <a name="syntax"></a>構文

```
virtual void SetPreviewVisuals(
   COLORREF clrBack,
   COLORREF clrText,
   const LOGFONTW *plf
);
```

### <a name="parameters"></a>パラメーター

*clrBack*<br/>
プレビューウィンドウの背景色です。

*clrText*<br/>
プレビューウィンドウのテキストの色。

*plf*<br/>
プレビューウィンドウでテキストを表示するために使用されるフォントです。

## <a name="cmfcpreviewctrlimplsetrect"></a><a name="setrect"></a> Cmfcプレビュー Ctrlimpl:: SetRect

このコントロールの新しい外接する四角形を設定します。

### <a name="syntax"></a>構文

```
virtual void SetRect(
   const RECT* prc,
   BOOL bRedraw
);
```

### <a name="parameters"></a>パラメーター

*中国語*<br/>
プレビューコントロールの新しいサイズと位置を指定します。

*より描画*<br/>
コントロールを再描画する必要があるかどうかを指定します。

### <a name="remarks"></a>解説

通常、新しい外接する四角形は、ホストコントロールのサイズが変更されるときに設定されます。

## <a name="cmfcpreviewctrlimplcmfcpreviewctrlimpl"></a><a name="dtor"></a> Cmfcプレビュー Ctrlimpl:: ~ Cmfcプレビュー Ctrlimpl

Preview コントロールオブジェクトを Destructs します。

### <a name="syntax"></a>構文

```
virtual ~CMFCPreviewCtrlImpl();
```
