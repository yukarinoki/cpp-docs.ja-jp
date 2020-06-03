---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CPagerCtrl
- AFXCMN/CPagerCtrl
- AFXCMN/CPagerCtrl::CPagerCtrl
- AFXCMN/CPagerCtrl::Create
- AFXCMN/CPagerCtrl::CreateEx
- AFXCMN/CPagerCtrl::ForwardMouse
- AFXCMN/CPagerCtrl::GetBkColor
- AFXCMN/CPagerCtrl::GetBorder
- AFXCMN/CPagerCtrl::GetButtonSize
- AFXCMN/CPagerCtrl::GetButtonState
- AFXCMN/CPagerCtrl::GetDropTarget
- AFXCMN/CPagerCtrl::GetScrollPos
- AFXCMN/CPagerCtrl::IsButtonDepressed
- AFXCMN/CPagerCtrl::IsButtonGrayed
- AFXCMN/CPagerCtrl::IsButtonHot
- AFXCMN/CPagerCtrl::IsButtonInvisible
- AFXCMN/CPagerCtrl::IsButtonNormal
- AFXCMN/CPagerCtrl::RecalcSize
- AFXCMN/CPagerCtrl::SetBkColor
- AFXCMN/CPagerCtrl::SetBorder
- AFXCMN/CPagerCtrl::SetButtonSize
- AFXCMN/CPagerCtrl::SetChild
- AFXCMN/CPagerCtrl::SetScrollPos
helpviewer_keywords:
- CPagerCtrl [MFC], CPagerCtrl
- CPagerCtrl [MFC], Create
- CPagerCtrl [MFC], CreateEx
- CPagerCtrl [MFC], ForwardMouse
- CPagerCtrl [MFC], GetBkColor
- CPagerCtrl [MFC], GetBorder
- CPagerCtrl [MFC], GetButtonSize
- CPagerCtrl [MFC], GetButtonState
- CPagerCtrl [MFC], GetDropTarget
- CPagerCtrl [MFC], GetScrollPos
- CPagerCtrl [MFC], IsButtonDepressed
- CPagerCtrl [MFC], IsButtonGrayed
- CPagerCtrl [MFC], IsButtonHot
- CPagerCtrl [MFC], IsButtonInvisible
- CPagerCtrl [MFC], IsButtonNormal
- CPagerCtrl [MFC], RecalcSize
- CPagerCtrl [MFC], SetBkColor
- CPagerCtrl [MFC], SetBorder
- CPagerCtrl [MFC], SetButtonSize
- CPagerCtrl [MFC], SetChild
- CPagerCtrl [MFC], SetScrollPos
ms.assetid: 65ac58dd-4f5e-4b7e-b15c-e0d435a7e884
ms.openlocfilehash: cd27a3acf26abe39831089546df317679f2ecab6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753705"
---
# <a name="cpagerctrl-class"></a>クラス

`CPagerCtrl` クラスは、Windows のページャー コントロールをラップします。ページャー コントロールには、外側のウィンドウに収まらない内側のウィンドウをスクロールによって表示する機能があります。

## <a name="syntax"></a>構文

```
class CPagerCtrl : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CページCtrl::CページCtrl](#cpagerctrl)|`CPagerCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CPagerCtrl::作成](#create)|指定したスタイルを持つページャー コントロールを作成し、現在`CPagerCtrl`のオブジェクトにアタッチします。|
|[CPagerCtrl::作成します。](#createex)|指定した拡張スタイルを持つページャー コントロールを作成し、現在`CPagerCtrl`のオブジェクトにアタッチします。|
|[CPagerCtrl::フォワードマウス](#forwardmouse)|現在のページャー コントロールに含まれるウィンドウへの[WM_MOUSEMOVE](/windows/win32/inputdev/wm-mousemove)メッセージの転送を有効または無効にします。|
|[CPagerCtrl::ゲットブレクカラー](#getbkcolor)|現在のページャー コントロールの背景色を取得します。|
|[CPagerCtrl::ゲットボーダー](#getborder)|現在のページャー コントロールの境界線のサイズを取得します。|
|[コントロール::ボタンサイズを取得します。](#getbuttonsize)|現在のページャー コントロールのボタン サイズを取得します。|
|[ボタン状態を取得します。](#getbuttonstate)|現在のページャー コントロール内の指定したボタンの状態を取得します。|
|[CPagerCtrl::ゲットドロップターゲット](#getdroptarget)|現在のページャー コントロールの[IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget)インターフェイスを取得します。|
|[をクリックします。](#getscrollpos)|現在のページャー コントロールのスクロール位置を取得します。|
|[CPagerCtrl::イスタボタンが落ち込んだ](#isbuttondepressed)|現在のページャー コントロールの指定されたボタンが`pressed`状態かどうかを示します。|
|[CPagerCtrl::イスタボタングレイド](#isbuttongrayed)|現在のページャー コントロールの指定されたボタンが`grayed`状態かどうかを示します。|
|[CPagerCtrl::イスタテホット](#isbuttonhot)|現在のページャー コントロールの指定されたボタンが`hot`状態かどうかを示します。|
|[CPagerCtrl::アイズボタンインビジブル](#isbuttoninvisible)|現在のページャー コントロールの指定されたボタンが`invisible`状態かどうかを示します。|
|[CPagerCtrl::イスタノーマル](#isbuttonnormal)|現在のページャー コントロールの指定されたボタンが`normal`状態かどうかを示します。|
|[CPagerCtrl::レカルクサイズ](#recalcsize)|現在のページャー コントロールに、含まれているウィンドウのサイズを再計算します。|
|[CページCtrl::セットBkカラー](#setbkcolor)|現在のページャー コントロールの背景色を設定します。|
|[CPagerCtrl::セットボーダー](#setborder)|現在のページャー コントロールの境界線のサイズを設定します。|
|[コントロール::セットボタンサイズ](#setbuttonsize)|現在のページャー コントロールのボタン サイズを設定します。|
|[CPagerCtrl::セットチャイルド](#setchild)|現在のページャー コントロールのウィンドウを設定します。|
|[をクリックします。](#setscrollpos)|現在のページャー コントロールのスクロール位置を設定します。|

## <a name="remarks"></a>解説

ページャー コントロールは、格納ウィンドウよりも線形で大きい別のウィンドウを含むウィンドウです。 ページャー コントロールは、含まれているウィンドウが最も遠い範囲までスクロールされたときに自動的に非表示になる 2 つのスクロール ボタンを表示し、それ以外の場合は再表示します。 水平または垂直にスクロールするページャー コントロールを作成できます。

たとえば、アプリケーションにツールバーの幅が小さい場合は、ツールバーをページャー コントロールに割り当てることができ、ユーザーはツールバーを左または右にスクロールしてすべての項目にアクセスできます。 インターネット エクスプローラ バージョン 4.0 (commctrl.dll バージョン 4.71) では、ページャー コントロールが導入されています。

クラス`CPagerCtrl`は[、CWnd](../../mfc/reference/cwnd-class.md)クラスから派生します。 詳細とページャー コントロールの図については、「[ポケットベル コントロール](/windows/win32/Controls/pager-controls)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPagerCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

## <a name="cpagerctrlcpagerctrl"></a><a name="cpagerctrl"></a>CページCtrl::CページCtrl

`CPagerCtrl` オブジェクトを構築します。

```
CPagerCtrl();
```

### <a name="remarks"></a>解説

[CPagerCtrl::作成](#create)または[CPagerCtrl::CreateEx](#createex)メソッドを使用して、ページャー コントロールを作成し`CPagerCtrl`、オブジェクトにアタッチします。

## <a name="cpagerctrlcreate"></a><a name="create"></a>CPagerCtrl::作成

指定したスタイルを持つページャー コントロールを作成し、現在`CPagerCtrl`のオブジェクトにアタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Dwstyle*|[in]コントロールに適用する[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)と[ページャー コントロール スタイル](/windows/win32/Controls/pager-control-styles)のビットごとの組み合わせ (OR)。|
|*Rect*|[in]クライアント座標でのコントロールの位置とサイズを格納する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体への参照。|
|*pParentWnd*|[in]コントロールの親ウィンドウである[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトへのポインター。 このパラメーターは NULL にはできません。|
|*nID*|[in]コントロールの ID。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ページャー コントロールを作成するには、変数`CPagerCtrl`を宣言し、その変数に対して[CPagerCtrl::作成](#create)または[CPagerCtrl::CreateEx](#createex)メソッドを呼び出します。

### <a name="example"></a>例

次の例では、ページャー コントロールを作成し[、CPagerCtrl::SetChild](#setchild)メソッドを使用して、非常に長いボタン コントロールをページャー コントロールに関連付けます。 次に[、CPagerCtrl::SetButtonSize](#setbuttonsize)メソッドを使用してページャー コントロールの高さを 20 ピクセルに設定し[、CPagerCtrl::SetBorder](#setborder)メソッドを使用して境界線の太さを 1 ピクセルに設定します。

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

## <a name="cpagerctrlcreateex"></a><a name="createex"></a>CPagerCtrl::作成します。

指定した拡張スタイルを持つページャー コントロールを作成し、現在`CPagerCtrl`のオブジェクトにアタッチします。

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*ドウェエクススタイル*|[in]コントロールに適用する拡張スタイルのビットごとの組み合わせ。 詳細については、関数の*dwExStyle*パラメーターを参照[してください](/windows/win32/api/winuser/nf-winuser-createwindowexw)。|
|*Dwstyle*|[in]コントロールに適用する[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)と[ページャー コントロール スタイル](/windows/win32/Controls/pager-control-styles)のビットごとの組み合わせ (OR)。|
|*Rect*|[in]クライアント座標でのコントロールの位置とサイズを格納する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体への参照。|
|*pParentWnd*|[in]コントロールの親ウィンドウである[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトへのポインター。 このパラメーターは NULL にはできません。|
|*nID*|[in]コントロールの ID。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ページャー コントロールを作成するには、変数`CPagerCtrl`を宣言し、その変数に対して[CPagerCtrl::作成](#create)または[CPagerCtrl::CreateEx](#createex)メソッドを呼び出します。

## <a name="cpagerctrlforwardmouse"></a><a name="forwardmouse"></a>CPagerCtrl::フォワードマウス

現在のページャー コントロールに含まれるウィンドウへの[WM_MOUSEMOVE](/windows/win32/inputdev/wm-mousemove)メッセージの転送を有効または無効にします。

```cpp
void ForwardMouse(BOOL bForward);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*bフォワード*|[in]マウス メッセージを転送する場合は TRUE、マウス メッセージを転送しない場合は FALSE。|

### <a name="remarks"></a>解説

このメソッドは、Windows SDK に記載されている[PGM_FORWARDMOUSE](/windows/win32/Controls/pgm-forwardmouse)メッセージを送信します。

## <a name="cpagerctrlgetborder"></a><a name="getborder"></a>CPagerCtrl::ゲットボーダー

現在のページャー コントロールの境界線のサイズを取得します。

```
int GetBorder() const;
```

### <a name="return-value"></a>戻り値

現在の境界線のサイズをピクセル単位で指定します。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[PGM_GETBORDER](/windows/win32/Controls/pgm-getborder)メッセージを送信します。

### <a name="example"></a>例

次の例では[、CPagerCtrl::GetBorder](#getborder)メソッドを使用して、ページャー コントロールの境界線の太さを取得します。

[!code-cpp[NVC_MFC_CSplitButton_s2#5](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_2.cpp)]

## <a name="cpagerctrlgetbkcolor"></a><a name="getbkcolor"></a>CPagerCtrl::ゲットブレクカラー

現在のページャー コントロールの背景色を取得します。

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>戻り値

ページャー コントロールの現在の背景色を含む[COLORREF](/windows/win32/gdi/colorref)値。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK に記載されている[PGM_GETBKCOLOR](/windows/win32/Controls/pgm-getbkcolor)メッセージを送信します。

### <a name="example"></a>例

次の例では[、CPagerCtrl::SetBkColor](#setbkcolor)メソッドを使用して、ページャー コントロールの背景色を赤に設定し[、CPagerCtrl::GetBkColor](#getbkcolor)メソッドを使用して変更が行われたことを確認します。

[!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]

## <a name="cpagerctrlgetbuttonsize"></a><a name="getbuttonsize"></a>コントロール::ボタンサイズを取得します。

現在のページャー コントロールのボタン サイズを取得します。

```
int GetButtonSize() const;
```

### <a name="return-value"></a>戻り値

現在のボタンのサイズ (ピクセル単位)。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[PGM_GETBUTTONSIZE](/windows/win32/Controls/pgm-getbuttonsize)メッセージを送信します。

ページャー コントロールにPGS_HORZスタイルがある場合、ボタンのサイズによってページャー ボタンの幅が決まり、ページャー コントロールにPGS_VERTスタイルがある場合は、ボタンのサイズによってページャー ボタンの高さが決まります。 詳細については、「[ポケットベル コントロール のスタイル](/windows/win32/Controls/pager-control-styles)」を参照してください。

## <a name="cpagerctrlgetbuttonstate"></a><a name="getbuttonstate"></a>ボタン状態を取得します。

現在のページャー コントロール内の指定したスクロール ボタンの状態を取得します。

```
DWORD GetButtonState(int iButton) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Ibutton*|[in]状態を取得するボタンを示します。 ページャー コントロールのスタイルがPGS_HORZ場合は、左側のボタンのPGB_TOPORLEFTを指定し、右ボタンにPGB_BOTTOMORRIGHTします。 ページャー コントロールのスタイルがPGS_VERT場合は、上ボタンのPGB_TOPORLEFTを指定し、下ボタンにPGB_BOTTOMORRIGHTを指定します。 詳細については、「[ポケットベル コントロール のスタイル](/windows/win32/Controls/pager-control-styles)」を参照してください。|

### <a name="return-value"></a>戻り値

*iButton*パラメーターで指定されたボタンの状態。 状態は、PGF_INVISIBLE、PGF_NORMAL、PGF_GRAYED、PGF_DEPRESSED、またはPGF_HOTのいずれかです。 詳細については[、PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate)メッセージの「戻り値」セクションを参照してください。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate)メッセージを送信します。

## <a name="cpagerctrlgetdroptarget"></a><a name="getdroptarget"></a>CPagerCtrl::ゲットドロップターゲット

現在のページャー コントロールの[IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget)インターフェイスを取得します。

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>戻り値

現在のページャー`IDropTarget`コントロールのインターフェイスへのポインター。

### <a name="remarks"></a>解説

`IDropTarget`は、アプリケーションでドラッグ アンド ドロップ操作をサポートするために実装するインターフェイスの 1 つです。

このメソッドは、Windows SDK で説明されている[PGM_GETDROPTARGET](/windows/win32/Controls/pgm-getdroptarget)メッセージを送信します。 このメソッドの呼び出し元は、`Release`インターフェイスが不要になったときに[IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget)インターフェイスのメンバーを呼び出します。

## <a name="cpagerctrlgetscrollpos"></a><a name="getscrollpos"></a>をクリックします。

現在のページャー コントロールのスクロール位置を取得します。

```
int GetScrollPos() const;
```

### <a name="return-value"></a>戻り値

現在のスクロール位置 (ピクセル単位)。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK に記載されている[PGM_GETPOS](/windows/win32/Controls/pgm-getpos)メッセージを送信します。

### <a name="example"></a>例

次の例では[、CPagerCtrl::GetScrollPos](#getscrollpos)メソッドを使用して、ページャー コントロールの現在のスクロール位置を取得します。 ページャー コントロールが、左端の位置であるゼロにスクロールされていない場合、この例では[CPagerCtrl::SetScrollPos](#setscrollpos)メソッドを使用してスクロール位置を 0 に設定します。

[!code-cpp[NVC_MFC_CSplitButton_s2#7](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_4.cpp)]

## <a name="cpagerctrlisbuttondepressed"></a><a name="isbuttondepressed"></a>CPagerCtrl::イスタボタンが落ち込んだ

現在のページャー コントロールの指定されたスクロール ボタンが押された状態かどうかを示します。

```
BOOL IsButtonDepressed(int iButton) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Ibutton*|[in]状態を取得するボタンを示します。 ページャー コントロールのスタイルがPGS_HORZ場合は、左側のボタンのPGB_TOPORLEFTを指定し、右ボタンにPGB_BOTTOMORRIGHTします。 ページャー コントロールのスタイルがPGS_VERT場合は、上ボタンのPGB_TOPORLEFTを指定し、下ボタンにPGB_BOTTOMORRIGHTを指定します。 詳細については、「[ポケットベル コントロール のスタイル](/windows/win32/Controls/pager-control-styles)」を参照してください。|

### <a name="return-value"></a>戻り値

指定されたボタンが押された状態の場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate)メッセージを送信します。 次に、返される状態がPGF_DEPRESSEDかどうかをテストします。 詳細については[、PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate)メッセージの「戻り値」セクションを参照してください。

## <a name="cpagerctrlisbuttongrayed"></a><a name="isbuttongrayed"></a>CPagerCtrl::イスタボタングレイド

現在のページャー コントロールの指定されたスクロール ボタンが灰色表示かどうかを示します。

```
BOOL IsButtonGrayed(int iButton) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Ibutton*|[in]状態を取得するボタンを示します。 ページャー コントロールのスタイルがPGS_HORZ場合は、左側のボタンのPGB_TOPORLEFTを指定し、右ボタンにPGB_BOTTOMORRIGHTします。 ページャー コントロールのスタイルがPGS_VERT場合は、上ボタンのPGB_TOPORLEFTを指定し、下ボタンにPGB_BOTTOMORRIGHTを指定します。 詳細については、「[ポケットベル コントロール のスタイル](/windows/win32/Controls/pager-control-styles)」を参照してください。|

### <a name="return-value"></a>戻り値

指定したボタンが灰色の状態の場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate)メッセージを送信します。 次に、返される状態がPGF_GRAYEDかどうかをテストします。 詳細については[、PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate)メッセージの「戻り値」セクションを参照してください。

## <a name="cpagerctrlisbuttonhot"></a><a name="isbuttonhot"></a>CPagerCtrl::イスタテホット

現在のページャー コントロールの指定されたスクロール ボタンがホット状態かどうかを示します。

```
BOOL IsButtonHot(int iButton) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Ibutton*|[in]状態を取得するボタンを示します。 ページャー コントロールのスタイルがPGS_HORZ場合は、左側のボタンのPGB_TOPORLEFTを指定し、右ボタンにPGB_BOTTOMORRIGHTします。 ページャー コントロールのスタイルがPGS_VERT場合は、上ボタンのPGB_TOPORLEFTを指定し、下ボタンにPGB_BOTTOMORRIGHTを指定します。 詳細については、「[ポケットベル コントロール のスタイル](/windows/win32/Controls/pager-control-styles)」を参照してください。|

### <a name="return-value"></a>戻り値

指定されたボタンがホット状態の場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate)メッセージを送信します。 次に、返される状態がPGF_HOTかどうかをテストします。 詳細については[、PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate)メッセージの「戻り値」セクションを参照してください。

## <a name="cpagerctrlisbuttoninvisible"></a><a name="isbuttoninvisible"></a>CPagerCtrl::アイズボタンインビジブル

現在のページャー コントロールの指定されたスクロール ボタンが非表示の状態かどうかを示します。

```
BOOL IsButtonInvisible(int iButton) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Ibutton*|[in]状態を取得するボタンを示します。 ページャー コントロールのスタイルがPGS_HORZ場合は、左側のボタンのPGB_TOPORLEFTを指定し、右ボタンにPGB_BOTTOMORRIGHTします。 ページャー コントロールのスタイルがPGS_VERT場合は、上ボタンのPGB_TOPORLEFTを指定し、下ボタンにPGB_BOTTOMORRIGHTを指定します。 詳細については、「[ポケットベル コントロール のスタイル](/windows/win32/Controls/pager-control-styles)」を参照してください。|

### <a name="return-value"></a>戻り値

指定されたボタンが非表示状態の場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

Windows では、ウィンドウをクリックすると、さらに含まれているウィンドウの多くを表示できないため、ウィンドウが最も遠い範囲にスクロールされると、特定の方向のスクロール ボタンが非表示になります。

このメソッドは、Windows SDK で説明されている[PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate)メッセージを送信します。 次に、返される状態がPGF_INVISIBLEかどうかをテストします。 詳細については[、PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate)メッセージの「戻り値」セクションを参照してください。

### <a name="example"></a>例

次の例では[、CPagerCtrl::IsButtonInvisible](#isbuttoninvisible)メソッドを使用して、ページャー コントロールの左右のスクロール ボタンが表示されているかどうかを確認します。

[!code-cpp[NVC_MFC_CSplitButton_s2#6](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_5.cpp)]

## <a name="cpagerctrlisbuttonnormal"></a><a name="isbuttonnormal"></a>CPagerCtrl::イスタノーマル

現在のページャー コントロールの指定されたスクロール ボタンが通常の状態かどうかを示します。

```
BOOL IsButtonNormal(int iButton) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Ibutton*|[in]状態を取得するボタンを示します。 ページャー コントロールのスタイルがPGS_HORZ場合は、左側のボタンのPGB_TOPORLEFTを指定し、右ボタンにPGB_BOTTOMORRIGHTします。 ページャー コントロールのスタイルがPGS_VERT場合は、上ボタンのPGB_TOPORLEFTを指定し、下ボタンにPGB_BOTTOMORRIGHTを指定します。 詳細については、「[ポケットベル コントロール のスタイル](/windows/win32/Controls/pager-control-styles)」を参照してください。|

### <a name="return-value"></a>戻り値

指定されたボタンが通常の状態の場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate)メッセージを送信します。 次に、返される状態がPGF_NORMALかどうかをテストします。 詳細については[、PGM_GETBUTTONSTATE](/windows/win32/Controls/pgm-getbuttonstate)メッセージの「戻り値」セクションを参照してください。

## <a name="cpagerctrlrecalcsize"></a><a name="recalcsize"></a>CPagerCtrl::レカルクサイズ

現在のページャー コントロールに、含まれているウィンドウのサイズを再計算します。

```cpp
void RecalcSize();
```

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[PGM_RECALCSIZE](/windows/win32/Controls/pgm-recalcsize)メッセージを送信します。 その結果、ページャー コントロールは、PGN_CALCSIZE[通知を](/windows/win32/Controls/pgn-calcsize)送信して、含まれているウィンドウのスクロール可能なサイズを取得します。

### <a name="example"></a>例

次の例では[、CPagerCtrl::RecalcSize](#recalcsize)メソッドを使用して、現在のページャー コントロールにサイズを再計算するよう要求します。

[!code-cpp[NVC_MFC_CSplitButton_s2#3](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_6.cpp)]

### <a name="example"></a>例

次の例では[、メッセージ リフレクション](../../mfc/tn062-message-reflection-for-windows-controls.md)を使用して、コントロールの親ダイアログで計算を実行する代わりに、独自のサイズをページャー コントロールが再計算できるようにします。 この例では`MyPagerCtrl`[、CPagerCtrl クラス](../../mfc/reference/cpagerctrl-class.md)からクラスを派生し、メッセージ マップを使用して[、通知](/windows/win32/Controls/pgn-calcsize)ハンドラーに`OnCalcsize`PGN_CALCSIZE通知を関連付けます。 この例では、通知ハンドラーは、ページャー コントロールの幅と高さを固定値に設定します。

[!code-cpp[NVC_MFC_CSplitButton_s2#8](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_7.cpp)]

## <a name="cpagerctrlsetbkcolor"></a><a name="setbkcolor"></a>CページCtrl::セットBkカラー

現在のページャー コントロールの背景色を設定します。

```
COLORREF SetBkColor(COLORREF clrBk);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*clrBk*|[in]ページャー コントロールの新しい背景色を含む[COLORREF](/windows/win32/gdi/colorref)値。|

### <a name="return-value"></a>戻り値

ページャー コントロールの前の背景色を含む[COLORREF](/windows/win32/gdi/colorref)値。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[PGM_SETBKCOLOR](/windows/win32/Controls/pgm-setbkcolor)メッセージを送信します。

### <a name="example"></a>例

次の例では[、CPagerCtrl::SetBkColor](#setbkcolor)メソッドを使用して、ページャー コントロールの背景色を赤に設定し[、CPagerCtrl::GetBkColor](#getbkcolor)メソッドを使用して変更が行われたことを確認します。

[!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]

## <a name="cpagerctrlsetborder"></a><a name="setborder"></a>CPagerCtrl::セットボーダー

現在のページャー コントロールの境界線のサイズを設定します。

```
int SetBorder(int iBorder);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*アイボーダー*|[in]新しい境界線のサイズ (ピクセル単位)。 *iBorder*パラメーターが負の場合、境界線のサイズはゼロに設定されます。|

### <a name="return-value"></a>戻り値

直前の境界線のサイズをピクセル単位で指定します。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK に記載されている[PGM_SETBORDER](/windows/win32/Controls/pgm-setborder)メッセージを送信します。

### <a name="example"></a>例

次の例では、ページャー コントロールを作成し[、CPagerCtrl::SetChild](#setchild)メソッドを使用して、非常に長いボタン コントロールをページャー コントロールに関連付けます。 次に[、CPagerCtrl::SetButtonSize](#setbuttonsize)メソッドを使用してページャー コントロールの高さを 20 ピクセルに設定し[、CPagerCtrl::SetBorder](#setborder)メソッドを使用して境界線の太さを 1 ピクセルに設定します。

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

## <a name="cpagerctrlsetbuttonsize"></a><a name="setbuttonsize"></a>コントロール::セットボタンサイズ

現在のページャー コントロールのボタン サイズを設定します。

```
int SetButtonSize(int iButtonSize);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*ボタンサイズ*|[in]新しいボタンのサイズ (ピクセル単位)。|

### <a name="return-value"></a>戻り値

前のボタンのサイズ (ピクセル単位)。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[PGM_SETBUTTONSIZE](/windows/win32/Controls/pgm-setpos)メッセージを送信します。

ページャー コントロールにPGS_HORZスタイルがある場合、ボタンのサイズによってページャー ボタンの幅が決まり、ページャー コントロールにPGS_VERTスタイルがある場合は、ボタンのサイズによってページャー ボタンの高さが決まります。 既定のボタン サイズはスクロール バーの幅の 4 分の 3 で、ボタンの最小サイズは 12 ピクセルです。 詳細については、「[ポケットベル コントロール のスタイル](/windows/win32/Controls/pager-control-styles)」を参照してください。

### <a name="example"></a>例

次の例では、ページャー コントロールを作成し[、CPagerCtrl::SetChild](#setchild)メソッドを使用して、非常に長いボタン コントロールをページャー コントロールに関連付けます。 次に[、CPagerCtrl::SetButtonSize](#setbuttonsize)メソッドを使用してページャー コントロールの高さを 20 ピクセルに設定し[、CPagerCtrl::SetBorder](#setborder)メソッドを使用して境界線の太さを 1 ピクセルに設定します。

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

## <a name="cpagerctrlsetchild"></a><a name="setchild"></a>CPagerCtrl::セットチャイルド

現在のページャー コントロールのウィンドウを設定します。

```cpp
void SetChild(HWND hwndChild);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*フルンドチャイルド*|[in]格納するウィンドウへのハンドル。|

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[PGM_SETCHILD](/windows/win32/Controls/pgm-setchild)メッセージを送信します。

このメソッドは、含まれているウィンドウの親を変更しません。スクロール用のページャー コントロールにウィンドウ ハンドルを割り当てるだけです。 ほとんどの場合、含まれているウィンドウは、ページャー コントロールの子ウィンドウになります。

### <a name="example"></a>例

次の例では、ページャー コントロールを作成し[、CPagerCtrl::SetChild](#setchild)メソッドを使用して、非常に長いボタン コントロールをページャー コントロールに関連付けます。 次に[、CPagerCtrl::SetButtonSize](#setbuttonsize)メソッドを使用してページャー コントロールの高さを 20 ピクセルに設定し[、CPagerCtrl::SetBorder](#setborder)メソッドを使用して境界線の太さを 1 ピクセルに設定します。

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

## <a name="cpagerctrlsetscrollpos"></a><a name="setscrollpos"></a>をクリックします。

現在のページャー コントロールのスクロール位置を設定します。

```cpp
void SetScrollPos(int iPos);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Ipo*|[in]新しいスクロール位置 (ピクセル単位)。|

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[PGM_SETPOS](/windows/win32/Controls/pgm-setpos)メッセージを送信します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/cpagerctrl-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[ポケットベル コントロール](/windows/win32/Controls/pager-controls)
