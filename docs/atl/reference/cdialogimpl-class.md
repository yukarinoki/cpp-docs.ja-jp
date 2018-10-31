---
title: CDialogImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDialogImpl
- ATLWIN/ATL::CDialogImpl
- ATLWIN/ATL::Create
- ATLWIN/ATL::DestroyWindow
- ATLWIN/ATL::DoModal
- ATLWIN/ATL::EndDialog
- ATLWIN/ATL::GetDialogProc
- ATLWIN/ATL::MapDialogRect
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::DialogProc
- ATLWIN/ATL::StartDialogProc
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes, ATL
- CDialogImpl class
ms.assetid: d430bc7b-8a28-4ad3-9507-277bdd2c2c2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 297a54b588cadc3a43e1b08ca89820807edb8ba2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50069842"
---
# <a name="cdialogimpl-class"></a>CDialogImpl クラス

このクラスは、モーダルまたはモードレス ダイアログ ボックスを作成するためのメソッドを提供します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T,
    class TBase = CWindow>
    class ATL_NO_VTABLE CDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
派生したクラス、`CDialogImpl`します。

*TBase*<br/>
新しいクラスの基本クラス。 既定の基本クラスは[CWindow](../../atl/reference/cwindow-class.md)します。

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[作成します。](#create)|モードレス ダイアログ ボックスを作成します。|
|[DestroyWindow](#destroywindow)|モードレス ダイアログ ボックスを破棄します。|
|[DoModal](#domodal)|モーダル ダイアログ ボックスを作成します。|
|[EndDialog](#enddialog)|モーダル ダイアログ ボックスを破棄します。|

### <a name="cdialogimplbaset-methods"></a>CDialogImplBaseT メソッド

|||
|-|-|
|[GetDialogProc](#getdialogproc)|現在のダイアログ ボックス プロシージャを返します。|
|[MapDialogRect](#mapdialogrect)|指定した四角形の単位 ダイアログ ボックスを画面の単位 (ピクセル単位) にマップします。|
|[OnFinalMessage](#onfinalmessage)|最後のメッセージでは、通常への受信後に呼び出されます。|

### <a name="static-functions"></a>静的関数

|||
|-|-|
|[DialogProc](#dialogproc)|ダイアログ ボックスに送信されるメッセージを処理します。|
|[StartDialogProc](#startdialogproc)|ダイアログ ボックスに送信されるメッセージを処理する最初のメッセージが受信したときに呼び出されます。|

## <a name="remarks"></a>Remarks

`CDialogImpl`モーダルまたはモードレス ダイアログ ボックスを作成することができます。 `CDialogImpl` メッセージを適切なハンドラーを送信する既定のメッセージ マップを使用して、ダイアログ ボックス プロシージャを提供します。

基底クラスのデストラクター`~CWindowImplRoot`により、ウィンドウには、オブジェクトを破棄する前になったことです。

`CDialogImpl` は `CDialogImplBaseT` から派生します。また、後者は `CWindowImplRoot` から派生します。

> [!NOTE]
>  クラスを定義する必要があります、`IDD`ダイアログ テンプレート リソースの ID を指定するメンバー たとえば、ATL プロジェクト ウィザードは、クラスに次の行を自動的に追加します。

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/cdialogimpl-class_1.h)]

場所`MyDlg`は、**短い名前**ウィザードの 入力**名**ページ。

|詳細情報:|解決方法については、|
|--------------------------------|---------|
|コントロールの作成|[ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)|
|ATL ダイアログ ボックスを使用|[ATL ウィンドウ クラス](../../atl/atl-window-classes.md)|
|ATL プロジェクト ウィザード|[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)|
|ダイアログ ボックス|[ダイアログ ボックス](https://msdn.microsoft.com/library/windows/desktop/ms632588)と Windows SDK の後続のトピック|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

##  <a name="create"></a>  CDialogImpl::Create

モードレス ダイアログ ボックスを作成します。

```
HWND Create(
    HWND hWndParent,
    LPARAM dwInitParam = NULL );

HWND Create(
    HWND hWndParent,
    RECT&,
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>パラメーター

*hWndParent*<br/>
[in]オーナー ウィンドウのハンドル。

**RECT &** *rect* [in] A [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897)  ダイアログ ボックスのサイズと位置を指定する構造体。

*dwInitParam*<br/>
[in]ダイアログ ボックスに渡す値を指定します、 *lParam* WM_INITDIALOG メッセージのパラメーター。

### <a name="return-value"></a>戻り値

新しく作成されたダイアログ ボックスへのハンドル。

### <a name="remarks"></a>Remarks

このダイアログ ボックスが自動的に接続されている、`CDialogImpl`オブジェクト。 モーダル ダイアログ ボックスを作成するには[DoModal](#domodal)します。 上記の 2 番目のオーバーライドでのみ使用[CComControl](../../atl/reference/ccomcontrol-class.md)します。

##  <a name="destroywindow"></a>  CDialogImpl::DestroyWindow

モードレス ダイアログ ボックスを破棄します。

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスが正常に破棄された場合は TRUE。それ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

ダイアログ ボックスが正常に破棄されたかどうかに TRUE を返しますそれ以外の場合は FALSE です。

##  <a name="dialogproc"></a>  CDialogImpl::DialogProc

この静的関数は、ダイアログ ボックス プロシージャを実装します。

```
static LRESULT CALLBACK DialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
[in]ダイアログ ボックスへのハンドル。

*uMsg*<br/>
[in]ダイアログ ボックスに送信されるメッセージ。

*wParam*<br/>
[in]追加のメッセージに固有の情報。

*lParam*<br/>
[in]追加のメッセージに固有の情報。

### <a name="return-value"></a>戻り値

メッセージが処理された場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

`DialogProc` メッセージを適切なハンドラーを送信するのにには、既定のメッセージ マップを使用します。

オーバーライドできます`DialogProc`メッセージを処理するためのさまざまなメカニズムを提供します。

##  <a name="domodal"></a>  CDialogImpl::DoModal

モーダル ダイアログ ボックスを作成します。

```
INT_PTR DoModal(
    HWND hWndParent = ::GetActiveWindow(),
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>パラメーター

*hWndParent*<br/>
[in]オーナー ウィンドウのハンドル。 既定値はの戻り値、 [GetActiveWindow](https://msdn.microsoft.com/library/windows/desktop/ms646292) Win32 関数。

*dwInitParam*<br/>
[in]ダイアログ ボックスに渡す値を指定します、 *lParam* WM_INITDIALOG メッセージのパラメーター。

### <a name="return-value"></a>戻り値

成功した場合の値、*呼び出した*への呼び出しで指定されたパラメーター [EndDialog](#enddialog)します。 それ以外の場合、-1 を返します。

### <a name="remarks"></a>Remarks

このダイアログ ボックスが自動的に接続されている、`CDialogImpl`オブジェクト。

モードレス ダイアログ ボックスを作成するには[作成](#create)です。

##  <a name="enddialog"></a>  CDialogImpl::EndDialog

モーダル ダイアログ ボックスを破棄します。

```
BOOL EndDialog(int nRetCode);
```

### <a name="parameters"></a>パラメーター

*終了*<br/>
[in]によって返される値[CDialogImpl::DoModal](#domodal)します。

### <a name="return-value"></a>戻り値

ダイアログ ボックスが破棄された場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

`EndDialog` ダイアログ プロシージャを呼び出す必要があります。 Windows での値を使用 ダイアログ ボックスを破棄すると、後に*呼び出した*の戻り値として`DoModal`、ダイアログ ボックスを作成します。

> [!NOTE]
>  呼び出さない`EndDialog`モードレス ダイアログ ボックスを破棄します。 呼び出す[CWindow::DestroyWindow](../../atl/reference/cwindow-class.md#destroywindow)代わりにします。

##  <a name="getdialogproc"></a>  CDialogImpl::GetDialogProc

返します`DialogProc`、現在のダイアログ ボックス プロシージャ。

```
virtual WNDPROC GetDialogProc();
```

### <a name="return-value"></a>戻り値

現在のダイアログ ボックス プロシージャ。

### <a name="remarks"></a>Remarks

独自のダイアログ プロシージャを置換するには、このメソッドをオーバーライドします。

##  <a name="mapdialogrect"></a>  CDialogImpl::MapDialogRect

(Maps) 画面に指定した四角形のダイアログ ボックスのユニット単位 (ピクセル単位) に変換します。

```
BOOL MapDialogRect(LPRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*lpRect*<br/>
指す、`CRect`オブジェクトまたは[RECT](../../mfc/reference/rect-structure.md)更新領域を囲む更新プログラムのクライアント座標を受け取る構造体。

### <a name="return-value"></a>戻り値

更新プログラムが成功した場合、0 以外の場合更新が失敗した場合は 0。 拡張されたエラー情報を取得するには、`GetLastError` を呼び出します。

### <a name="remarks"></a>Remarks

関数は、指定した座標を置き換えます`RECT`座標を変換後の構造体、構造の作成 ダイアログ ボックスまたはダイアログ ボックス内でコントロールを配置するために使用することができます。

##  <a name="onfinalmessage"></a>  CDialogImpl::OnFinalMessage

最後のメッセージの受信後に呼び出されます (通常`WM_NCDESTROY`)。

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
[in]破棄されているウィンドウへのハンドル。

### <a name="remarks"></a>Remarks

ウィンドウの破棄後にオブジェクトを自動的に削除する場合は呼び出すことに注意してください。**削除は、この**ここです。

##  <a name="startdialogproc"></a>  CDialogImpl::StartDialogProc

ダイアログ ボックスに送信されるメッセージを処理する最初のメッセージを受信すると、1 回だけ呼び出されます。

```
static LRESULT CALLBACK StartDialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
[in]ダイアログ ボックスへのハンドル。

*uMsg*<br/>
[in]ダイアログ ボックスに送信されるメッセージ。

*wParam*<br/>
[in]追加のメッセージに固有の情報。

*lParam*<br/>
[in]追加のメッセージに固有の情報。

### <a name="return-value"></a>戻り値

ウィンドウ プロシージャです。

### <a name="remarks"></a>Remarks

最初の呼び出し後`StartDialogProc`、`DialogProc`は設定ダイアログ プロシージャ、および呼び出しではさらに移動します。

## <a name="see-also"></a>関連項目

[送るに](message-map-macros-atl.md#begin_msg_map)<br/>
[クラスの概要](../../atl/atl-class-overview.md)