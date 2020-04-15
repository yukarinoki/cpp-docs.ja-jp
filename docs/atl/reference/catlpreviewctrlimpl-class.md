---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Create
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Destroy
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Focus
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::OnPaint
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Redraw
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetHost
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetPreviewVisuals
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetRect
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::DoPaint
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_plf
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_clrBack
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_clrText
helpviewer_keywords:
- CAtlPreviewCtrlImpl class
ms.assetid: 39b3299e-07e4-4abc-9b6e-b54bfa3b0802
ms.openlocfilehash: 1ccd01bc4d48dc088538f4799b595cce3fb910ba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321366"
---
# <a name="catlpreviewctrlimpl-class"></a>クラス

このクラスは、リッチ プレビュー用シェルによって提供されるホスト ウィンドウに配置されるウィンドウの ATL 実装です。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CAtlPreviewCtrlImpl : public CWindowImpl<CAtlPreviewCtrlImpl>, public IPreviewCtrl;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAtl プレビューCtrlImpl::~CAtl プレビューCtrlImpl](#dtor)|プレビュー コントロール オブジェクトを破棄します。|
|[CAtlプレビューCtrlImpl:::CAtlプレビューCtrlインプル](#catlpreviewctrlimpl)|プレビュー コントロール オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAtlプレビューCtrlImpl::作成](#create)|リッチ プレビュー ハンドラーによって呼び出され、ウィンドウを作成します。|
|[カトルプレビューCtrlImpl::Dエストロイ](#destroy)|このコントロールを破棄する必要があるときにリッチ プレビュー ハンドラーによって呼び出されます。|
|[CAtlプレビューCtrlImpl::フォーカス](#focus)|このコントロールに入力フォーカスを設定します。|
|[CAtlプレビューCtrlImpl::オンペイント](#onpaint)|WM_PAINT メッセージを処理します。|
|[CAtlプレビューCtrlImpl::再描画](#redraw)|このコントロールに再描画を指示します。|
|[をクリックします。](#sethost)|このコントロールの新しい親を設定します。|
|[ウィンドウズプレビューCtrlImpl::プレビュービジュアル](#setpreviewvisuals)|リッチ プレビュー コンテンツのビジュアルを設定する必要がある場合に、リッチ プレビュー ハンドラーによって呼び出されます。|
|[CAtlプレビューCtrlImpl::セットレック](#setrect)|このコントロールの新しい外接する四角形を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[ウィンドウ:DプレビューCtrlImpl:oペイント](#dopaint)|プレビューをレンダリングするために、フレームワークによって呼び出されます。|

### <a name="protected-constants"></a>保護定数

|名前|説明|
|----------|-----------------|
|[CAtl プレビューCtrlImpl::m_plf](#m_plf)|プレビュー ウィンドウにテキストを表示するために使用するフォントです。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CAtl プレビューCtrlImpl::m_clrBack](#m_clrback)|プレビュー ウィンドウの背景色です。|
|[CAtlプレビューCtrlImpl::m_clrText](#m_clrtext)|プレビュー ウィンドウのテキストの色です。|

## <a name="remarks"></a>解説

## <a name="inheritance-hierarchy"></a>継承階層

`TBase`

`ATL::CMessageMap`

`ATL::CWindowImplRoot<TBase>`

`ATL::CWindowImplBaseT<TBase,TWinTraits>`

[ATL::Cウィンドウイン\<プルCAtlプレビュープレビュー>](../../atl/reference/cwindowimpl-class.md)

`IPreviewCtrl`

`ATL::CAtlPreviewCtrlImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** アトルプレビューctrlimpl.h

## <a name="catlpreviewctrlimplcatlpreviewctrlimpl"></a><a name="catlpreviewctrlimpl"></a>CAtlプレビューCtrlImpl:::CAtlプレビューCtrlインプル

プレビュー コントロール オブジェクトを構築します。

```
CAtlPreviewCtrlImpl(void) : m_clrText(0),
   m_clrBack(RGB(255, 255, 255)), m_plf(NULL);
```

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplcatlpreviewctrlimpl"></a><a name="dtor"></a>CAtl プレビューCtrlImpl::~CAtl プレビューCtrlImpl

プレビュー コントロール オブジェクトを破棄します。

```
virtual ~CAtlPreviewCtrlImpl(void);
```

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplcreate"></a><a name="create"></a>CAtlプレビューCtrlImpl::作成

リッチ プレビュー ハンドラーによって呼び出され、ウィンドウを作成します。

```
virtual BOOL Create(HWND hWndParent, const RECT* prc);
```

### <a name="parameters"></a>パラメーター

*スーンドペアレント*<br/>
シェルによってリッチ プレビュー用に提供されるホスト ウィンドウへのハンドル。

*Prc*<br/>
ウィンドウの初期サイズと位置を指定します。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimpldestroy"></a><a name="destroy"></a>カトルプレビューCtrlImpl::Dエストロイ

このコントロールを破棄する必要があるときにリッチ プレビュー ハンドラーによって呼び出されます。

```
virtual void Destroy();
```

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimpldopaint"></a><a name="dopaint"></a>ウィンドウ:DプレビューCtrlImpl:oペイント

プレビューをレンダリングするために、フレームワークによって呼び出されます。

```
virtual void DoPaint(HDC hdc);
```

### <a name="parameters"></a>パラメーター

*Hdc*<br/>
描画用のデバイス コンテキストへのハンドル。

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplfocus"></a><a name="focus"></a>CAtlプレビューCtrlImpl::フォーカス

このコントロールに入力フォーカスを設定します。

```
virtual void Focus();
```

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplm_clrback"></a><a name="m_clrback"></a>CAtl プレビューCtrlImpl::m_clrBack

プレビュー ウィンドウの背景色です。

```
COLORREF m_clrBack;
```

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplm_clrtext"></a><a name="m_clrtext"></a>CAtlプレビューCtrlImpl::m_clrText

プレビュー ウィンドウのテキストの色です。

```
COLORREF m_clrText;
```

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplm_plf"></a><a name="m_plf"></a>CAtl プレビューCtrlImpl::m_plf

プレビュー ウィンドウにテキストを表示するために使用するフォントです。

```
const LOGFONTW* m_plf;
```

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplonpaint"></a><a name="onpaint"></a>CAtlプレビューCtrlImpl::オンペイント

WM_PAINT メッセージを処理します。

```
LRESULT OnPaint(
    UINT nMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```

### <a name="parameters"></a>パラメーター

*nMsg*<br/>
WM_PAINTに設定します。

*wParam*<br/>
このパラメーターは使用されません。

*lParam*<br/>
このパラメーターは使用されません。

*処理済み*<br/>
この関数が返されるときに、TRUE が含まれます。

### <a name="return-value"></a>戻り値

常に 0 を返します。

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplredraw"></a><a name="redraw"></a>CAtlプレビューCtrlImpl::再描画

このコントロールに再描画を指示します。

```
virtual void Redraw();
```

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplsethost"></a><a name="sethost"></a>をクリックします。

このコントロールの新しい親を設定します。

```
virtual void SetHost(HWND hWndParent);
```

### <a name="parameters"></a>パラメーター

*スーンドペアレント*<br/>
新しい親ウィンドウへのハンドル。

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplsetpreviewvisuals"></a><a name="setpreviewvisuals"></a>ウィンドウズプレビューCtrlImpl::プレビュービジュアル

リッチ プレビュー コンテンツのビジュアルを設定する必要がある場合に、リッチ プレビュー ハンドラーによって呼び出されます。

```
virtual void SetPreviewVisuals(
    COLORREF clrBack,
    COLORREF clrText,
    const LOGFONTW* plf);
```

### <a name="parameters"></a>パラメーター

*clrバック*<br/>
プレビュー ウィンドウの背景色です。

*clrText*<br/>
プレビュー ウィンドウのテキストの色です。

*プルフ*<br/>
プレビュー ウィンドウにテキストを表示するために使用するフォントです。

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplsetrect"></a><a name="setrect"></a>CAtlプレビューCtrlImpl::セットレック

このコントロールの新しい外接する四角形を設定します。

```
virtual void SetRect(const RECT* prc, BOOL bRedraw);
```

### <a name="parameters"></a>パラメーター

*Prc*<br/>
プレビュー コントロールの新しいサイズと位置を指定します。

*引き出し*<br/>
コントロールを再描画するかどうかを指定します。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)
