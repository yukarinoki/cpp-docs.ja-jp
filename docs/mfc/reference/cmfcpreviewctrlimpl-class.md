---
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
ms.openlocfilehash: 060e601901fa5725d7ca62f244f66784af3dc11d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375333"
---
# <a name="cmfcpreviewctrlimpl-class"></a>CMFCPreviewCtrlImpl クラス

このクラスは、シェルによって提供されるホスト ウィンドウに配置されるウィンドウを実装リッチ プレビューします。

## <a name="syntax"></a>構文

```
class CMFCPreviewCtrlImpl : public CWnd;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[次の項目を返します。](#dtor)|プレビュー コントロール オブジェクトを破棄します。|
|[を返す](#cmfcpreviewctrlimpl)|プレビュー コントロール オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をクリックします。](#create)|オーバーロードされます。 リッチ プレビュー ハンドラーによって呼び出され、ウィンドウを作成します。|
|[CMFCプレビューCtrlImpl::Dエストロイ](#destroy)|このコントロールを破棄する必要があるときにリッチ プレビュー ハンドラーによって呼び出されます。|
|[CMFCプレビューCtrlImpl::フォーカス](#focus)|このコントロールに入力フォーカスを設定します。|
|[を返す](#getdocument)|このプレビュー コントロールに接続されているドキュメントを返します。|
|[再描画](#redraw)|このコントロールに再描画を指示します。|
|[をクリックします。](#setdocument)|ドキュメント実装とプレビュー コントロールの間のリレーションシップを作成するために、プレビュー ハンドラーによって呼び出されます。|
|[をクリックします。](#sethost)|このコントロールの新しい親を設定します。|
|[ビジュアルを設定します。](#setpreviewvisuals)|リッチ プレビュー コンテンツのビジュアルを設定する必要がある場合に、リッチ プレビュー ハンドラーによって呼び出されます。|
|[を返す](#setrect)|このコントロールの新しい外接する四角形を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMFCプレビューCtrlImpl::Doペイント](#dopaint)|プレビューをレンダリングするために、フレームワークによって呼び出されます。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[をクリックして、次の点を m_clrBackColor確認します。](#m_clrbackcolor)|プレビュー ウィンドウの背景色です。|
|[をクリックして、次の m_clrTextColor点を確認します。](#m_clrtextcolor)|プレビュー ウィンドウのテキストの色です。|
|[CMFCプレビューCtrlImpl::m_font](#m_font)|プレビュー ウィンドウにテキストを表示するために使用するフォントです。|
|[をクリックして、次の m_pDocument点を確認します。](#m_pdocument)|コントロール内でコンテンツがプレビューされるドキュメントへのポインター。|

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[をクリックします。](../../mfc/reference/cmfcpreviewctrlimpl-class.md)

## <a name="cmfcpreviewctrlimplcmfcpreviewctrlimpl"></a><a name="cmfcpreviewctrlimpl"></a>を返す

プレビュー コントロール オブジェクトを構築します。

### <a name="syntax"></a>構文

をクリックします。

## <a name="cmfcpreviewctrlimplcreate"></a><a name="create"></a>をクリックします。

オーバーロードされます。 リッチ プレビュー ハンドラーによって呼び出され、ウィンドウを作成します。

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

*スーンドペアレント*<br/>
シェルによってリッチ プレビュー用に提供されるホスト ウィンドウへのハンドル。

*Prc*<br/>
ウィンドウの初期サイズと位置を指定します。

*pContext*<br/>
作成コンテキストへのポインター。

### <a name="return-value"></a>戻り値

作成が成功した場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcpreviewctrlimpldestroy"></a><a name="destroy"></a>CMFCプレビューCtrlImpl::Dエストロイ

このコントロールを破棄する必要があるときにリッチ プレビュー ハンドラーによって呼び出されます。

### <a name="syntax"></a>構文

```
virtual void Destroy();
```

## <a name="cmfcpreviewctrlimpldopaint"></a><a name="dopaint"></a>CMFCプレビューCtrlImpl::Doペイント

プレビューをレンダリングするために、フレームワークによって呼び出されます。

### <a name="syntax"></a>構文

```
virtual void DoPaint(
   CPaintDC* pDC
);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
描画用のデバイス コンテキストへのポインター。

## <a name="cmfcpreviewctrlimplfocus"></a><a name="focus"></a>CMFCプレビューCtrlImpl::フォーカス

このコントロールに入力フォーカスを設定します。

### <a name="syntax"></a>構文

```
virtual void Focus();
```

## <a name="cmfcpreviewctrlimplgetdocument"></a><a name="getdocument"></a>を返す

このプレビュー コントロールに接続されているドキュメントを返します。

### <a name="syntax"></a>構文

```
ATL::IDocument* GetDocument();
```

### <a name="return-value"></a>戻り値

コントロール内でコンテンツがプレビューされるドキュメントへのポインター。

## <a name="cmfcpreviewctrlimplm_clrbackcolor"></a><a name="m_clrbackcolor"></a>をクリックして、次の点を m_clrBackColor確認します。

プレビュー ウィンドウの背景色です。

### <a name="syntax"></a>構文

```
COLORREF m_clrBackColor;
```

## <a name="cmfcpreviewctrlimplm_clrtextcolor"></a><a name="m_clrtextcolor"></a>をクリックして、次の m_clrTextColor点を確認します。

プレビュー ウィンドウのテキストの色です。

### <a name="syntax"></a>構文

```
COLORREF m_clrTextColor;
```

## <a name="cmfcpreviewctrlimplm_font--font-used-to-display-text-in-the-preview-window"></a><a name="m_font"></a>プレビュー ウィンドウ m_fontにテキストを表示するために使用されるフォント。

### <a name="syntax"></a>構文

```
CFont m_font;
```

## <a name="cmfcpreviewctrlimplm_pdocument"></a><a name="m_pdocument"></a>をクリックして、次の m_pDocument点を確認します。

コントロール内でコンテンツがプレビューされるドキュメントへのポインター。

### <a name="syntax"></a>構文

```
ATL::IDocument* m_pDocument;
```

## <a name="cmfcpreviewctrlimplredraw"></a><a name="redraw"></a>再描画

このコントロールに再描画を指示します。

### <a name="syntax"></a>構文

```
virtual void Redraw();
```

## <a name="cmfcpreviewctrlimplsetdocument"></a><a name="setdocument"></a>をクリックします。

ドキュメント実装とプレビュー コントロールの間のリレーションシップを作成するために、プレビュー ハンドラーによって呼び出されます。

### <a name="syntax"></a>構文

```
void SetDocument(
   IDocument* pDocument
);
```

### <a name="parameters"></a>パラメーター

*ドキュメント*<br/>
ドキュメントの実装へのポインター。

## <a name="cmfcpreviewctrlimplsethost"></a><a name="sethost"></a>をクリックします。

このコントロールの新しい親を設定します。

### <a name="syntax"></a>構文

```
virtual void SetHost(
   HWND hWndParent
);
```

### <a name="parameters"></a>パラメーター

*スーンドペアレント*<br/>
新しい親ウィンドウへのハンドル。

## <a name="cmfcpreviewctrlimplsetpreviewvisuals"></a><a name="setpreviewvisuals"></a>ビジュアルを設定します。

リッチ プレビュー コンテンツのビジュアルを設定する必要がある場合に、リッチ プレビュー ハンドラーによって呼び出されます。

### <a name="syntax"></a>構文

```
virtual void SetPreviewVisuals(
   COLORREF clrBack,
   COLORREF clrText,
   const LOGFONTW *plf
);
```

### <a name="parameters"></a>パラメーター

*clrバック*<br/>
プレビュー ウィンドウの背景色です。

*clrText*<br/>
プレビュー ウィンドウのテキストの色です。

*プルフ*<br/>
プレビュー ウィンドウにテキストを表示するために使用するフォントです。

## <a name="cmfcpreviewctrlimplsetrect"></a><a name="setrect"></a>を返す

このコントロールの新しい外接する四角形を設定します。

### <a name="syntax"></a>構文

```
virtual void SetRect(
   const RECT* prc,
   BOOL bRedraw
);
```

### <a name="parameters"></a>パラメーター

*Prc*<br/>
プレビュー コントロールの新しいサイズと位置を指定します。

*引き出し*<br/>
コントロールを再描画するかどうかを指定します。

### <a name="remarks"></a>解説

通常、ホスト コントロールのサイズを変更すると、新しい外接する四角形が設定されます。

## <a name="cmfcpreviewctrlimplcmfcpreviewctrlimpl"></a><a name="dtor"></a>次の項目を返します。

プレビュー コントロール オブジェクトを破棄します。

### <a name="syntax"></a>構文

```
virtual ~CMFCPreviewCtrlImpl();
```
