---
description: '詳細情報: CAtlPreviewCtrlImpl クラス'
title: CAtlPreviewCtrlImpl クラス
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
ms.openlocfilehash: 52263a4c65af1b791ca5da64eff235e93006ab52
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147213"
---
# <a name="catlpreviewctrlimpl-class"></a>CAtlPreviewCtrlImpl クラス

このクラスは、リッチプレビュー用のシェルによって提供されるホストウィンドウに配置されるウィンドウの ATL 実装です。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```cpp
class CAtlPreviewCtrlImpl : public CWindowImpl<CAtlPreviewCtrlImpl>, public IPreviewCtrl;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAtlPreviewCtrlImpl:: ~ CAtlPreviewCtrlImpl](#dtor)|Preview コントロールオブジェクトを Destructs します。|
|[CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl](#catlpreviewctrlimpl)|プレビューコントロールオブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAtlPreviewCtrlImpl:: Create](#create)|Windows ウィンドウを作成するためのリッチプレビューハンドラーによって呼び出されます。|
|[CAtlPreviewCtrlImpl::D estroy](#destroy)|このコントロールを破棄する必要がある場合に、リッチプレビューハンドラーによって呼び出されます。|
|[CAtlPreviewCtrlImpl:: Focus](#focus)|このコントロールに入力フォーカスを設定します。|
|[CAtlPreviewCtrlImpl:: OnPaint](#onpaint)|WM_PAINT メッセージを処理します。|
|[CAtlPreviewCtrlImpl:: 再描画](#redraw)|このコントロールに再描画を指示します。|
|[CAtlPreviewCtrlImpl:: SetHost](#sethost)|このコントロールの新しい親を設定します。|
|[CAtlPreviewCtrlImpl:: Setプレビュービジュアル](#setpreviewvisuals)|リッチプレビューコンテンツのビジュアルを設定する必要がある場合に、豊富なプレビューハンドラーによって呼び出されます。|
|[CAtlPreviewCtrlImpl::SetRect](#setrect)|このコントロールの新しい外接する四角形を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CAtlPreviewCtrlImpl::D oPaint](#dopaint)|プレビューを表示するためにフレームワークによって呼び出されます。|

### <a name="protected-constants"></a>プロテクト定数

|名前|説明|
|----------|-----------------|
|[CAtlPreviewCtrlImpl:: m_plf](#m_plf)|プレビューウィンドウでテキストを表示するために使用されるフォントです。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CAtlPreviewCtrlImpl:: m_clrBack](#m_clrback)|プレビューウィンドウの背景色です。|
|[CAtlPreviewCtrlImpl:: m_clrText](#m_clrtext)|プレビューウィンドウのテキストの色。|

## <a name="remarks"></a>解説

## <a name="inheritance-hierarchy"></a>継承階層

`TBase`

`ATL::CMessageMap`

`ATL::CWindowImplRoot<TBase>`

`ATL::CWindowImplBaseT<TBase,TWinTraits>`

[ATL:: CWindowImpl\<CAtlPreviewCtrlImpl>](../../atl/reference/cwindowimpl-class.md)

`IPreviewCtrl`

`ATL::CAtlPreviewCtrlImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlプレビュー ctrlimpl. h

## <a name="catlpreviewctrlimplcatlpreviewctrlimpl"></a><a name="catlpreviewctrlimpl"></a> CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl

プレビューコントロールオブジェクトを構築します。

```cpp
CAtlPreviewCtrlImpl(void) : m_clrText(0),
   m_clrBack(RGB(255, 255, 255)), m_plf(NULL);
```

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplcatlpreviewctrlimpl"></a><a name="dtor"></a> CAtlPreviewCtrlImpl:: ~ CAtlPreviewCtrlImpl

Preview コントロールオブジェクトを Destructs します。

```cpp
virtual ~CAtlPreviewCtrlImpl(void);
```

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplcreate"></a><a name="create"></a> CAtlPreviewCtrlImpl:: Create

Windows ウィンドウを作成するためのリッチプレビューハンドラーによって呼び出されます。

```cpp
virtual BOOL Create(HWND hWndParent, const RECT* prc);
```

### <a name="parameters"></a>パラメーター

*hWndParent*<br/>
リッチプレビューのためにシェルによって提供されるホストウィンドウへのハンドル。

*中国語*<br/>
ウィンドウの初期サイズと位置を指定します。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimpldestroy"></a><a name="destroy"></a> CAtlPreviewCtrlImpl::D estroy

このコントロールを破棄する必要がある場合に、リッチプレビューハンドラーによって呼び出されます。

```cpp
virtual void Destroy();
```

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimpldopaint"></a><a name="dopaint"></a> CAtlPreviewCtrlImpl::D oPaint

プレビューを表示するためにフレームワークによって呼び出されます。

```cpp
virtual void DoPaint(HDC hdc);
```

### <a name="parameters"></a>パラメーター

*hdc*<br/>
描画用のデバイスコンテキストを処理するハンドル。

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplfocus"></a><a name="focus"></a> CAtlPreviewCtrlImpl:: Focus

このコントロールに入力フォーカスを設定します。

```cpp
virtual void Focus();
```

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplm_clrback"></a><a name="m_clrback"></a> CAtlPreviewCtrlImpl:: m_clrBack

プレビューウィンドウの背景色です。

```cpp
COLORREF m_clrBack;
```

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplm_clrtext"></a><a name="m_clrtext"></a> CAtlPreviewCtrlImpl:: m_clrText

プレビューウィンドウのテキストの色。

```cpp
COLORREF m_clrText;
```

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplm_plf"></a><a name="m_plf"></a> CAtlPreviewCtrlImpl:: m_plf

プレビューウィンドウでテキストを表示するために使用されるフォントです。

```cpp
const LOGFONTW* m_plf;
```

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplonpaint"></a><a name="onpaint"></a> CAtlPreviewCtrlImpl:: OnPaint

WM_PAINT メッセージを処理します。

```cpp
LRESULT OnPaint(
    UINT nMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```

### <a name="parameters"></a>パラメーター

*nMsg*<br/>
を WM_PAINT に設定します。

*wParam*<br/>
このパラメーターは使用されません。

*lParam*<br/>
このパラメーターは使用されません。

*bHandled*<br/>
この関数から制御が戻るときに、TRUE が格納されます。

### <a name="return-value"></a>戻り値

常に 0 を返します。

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplredraw"></a><a name="redraw"></a> CAtlPreviewCtrlImpl:: 再描画

このコントロールに再描画を指示します。

```cpp
virtual void Redraw();
```

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplsethost"></a><a name="sethost"></a> CAtlPreviewCtrlImpl:: SetHost

このコントロールの新しい親を設定します。

```cpp
virtual void SetHost(HWND hWndParent);
```

### <a name="parameters"></a>パラメーター

*hWndParent*<br/>
新しい親ウィンドウへのハンドル。

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplsetpreviewvisuals"></a><a name="setpreviewvisuals"></a> CAtlPreviewCtrlImpl:: Setプレビュービジュアル

リッチプレビューコンテンツのビジュアルを設定する必要がある場合に、豊富なプレビューハンドラーによって呼び出されます。

```cpp
virtual void SetPreviewVisuals(
    COLORREF clrBack,
    COLORREF clrText,
    const LOGFONTW* plf);
```

### <a name="parameters"></a>パラメーター

*clrBack*<br/>
プレビューウィンドウの背景色です。

*clrText*<br/>
プレビューウィンドウのテキストの色。

*plf*<br/>
プレビューウィンドウでテキストを表示するために使用されるフォントです。

### <a name="remarks"></a>解説

## <a name="catlpreviewctrlimplsetrect"></a><a name="setrect"></a> CAtlPreviewCtrlImpl::SetRect

このコントロールの新しい外接する四角形を設定します。

```cpp
virtual void SetRect(const RECT* prc, BOOL bRedraw);
```

### <a name="parameters"></a>パラメーター

*中国語*<br/>
プレビューコントロールの新しいサイズと位置を指定します。

*より描画*<br/>
コントロールを再描画する必要があるかどうかを指定します。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)
