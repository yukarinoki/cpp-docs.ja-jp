---
title: クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- dialog boxes, ATL
- CDialogImpl class
ms.assetid: d430bc7b-8a28-4ad3-9507-277bdd2c2c2e
ms.openlocfilehash: d5ab7293f73429a93c3fcab243c2e34d3c78f28a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747708"
---
# <a name="cdialogimpl-class"></a>クラス

このクラスには、モーダル ダイアログ ボックスまたはモードレス ダイアログ ボックスを作成するためのメソッドが用意されています。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T,
    class TBase = CWindow>
    class ATL_NO_VTABLE CDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`CDialogImpl`。

*Tベース*<br/>
新しいクラスの基本クラス。 既定の基本クラスは[CWindow です](../../atl/reference/cwindow-class.md)。

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[作成](#create)|モードレス ダイアログ ボックスを作成します。|
|[ウィンドウを破壊する](#destroywindow)|モードレス ダイアログ ボックスを破棄します。|
|[Domodal](#domodal)|モーダル ダイアログ ボックスを作成します。|
|[Enddialog](#enddialog)|モーダル ダイアログ ボックスを破棄します。|

### <a name="cdialogimplbaset-methods"></a>メソッド

|||
|-|-|
|[ダイアログ を取得します。](#getdialogproc)|現在のダイアログ ボックス プロシージャを返します。|
|[マップダイアログレック](#mapdialogrect)|指定された四角形のダイアログ ボックスの単位をスクリーン単位 (ピクセル) に割り当てします。|
|[OnFinalMessage](#onfinalmessage)|通常、WM_NCDESTROY最後のメッセージを受信した後に呼び出されます。|

### <a name="static-functions"></a>静的関数

|||
|-|-|
|[DialogProc](#dialogproc)|ダイアログ ボックスに送信されたメッセージを処理します。|
|[ダイアログ プロスを開始します。](#startdialogproc)|ダイアログ ボックスに送信されたメッセージを処理するために最初のメッセージを受信したときに呼び出されます。|

## <a name="remarks"></a>解説

を`CDialogImpl`使用すると、モーダルまたはモードレスダイアログボックスを作成できます。 `CDialogImpl`には、既定のメッセージ マップを使用してメッセージを適切なハンドラーに送信するダイアログ ボックス プロシージャが用意されています。

基本クラスのデストラクター`~CWindowImplRoot`は、オブジェクトを破棄する前にウィンドウが消え去ったことを確認します。

`CDialogImpl` は `CDialogImplBaseT` から派生します。また、後者は `CWindowImplRoot` から派生します。

> [!NOTE]
> クラスは、ダイアログ`IDD`テンプレート リソース ID を指定するメンバーを定義する必要があります。 たとえば、ATL プロジェクト ウィザードは、次の行を自動的にクラスに追加します。

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/cdialogimpl-class_1.h)]

は`MyDlg`、ウィザードの **[名前]** ページに入力された**短い名前**です。

|詳細情報|参照先|
|--------------------------------|---------|
|コントロールの作成|[ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)|
|ATL でのダイアログ ボックスの使用|[ATL ウィンドウ クラス](../../atl/atl-window-classes.md)|
|ATL プロジェクト ウィザード|[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)|
|ダイアログ ボックス|[ダイアログ ボックス](/windows/win32/dlgbox/dialog-boxes)と Windows SDK の後続のトピック|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="cdialogimplcreate"></a><a name="create"></a>クリッピング::作成

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

*スーンドペアレント*<br/>
[in]所有者ウィンドウへのハンドル。

**RECT&** ダイアログのサイズと位置を指定する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体を*rect* .in.

*ドウィニトパラム*<br/>
[in]WM_INITDIALOG メッセージの*lParam*パラメータでダイアログ ボックスに渡す値を指定します。

### <a name="return-value"></a>戻り値

新しく作成されたダイアログ ボックスへのハンドル。

### <a name="remarks"></a>解説

このダイアログ ボックスは、オブジェクトに`CDialogImpl`自動的にアタッチされます。 モーダル ダイアログ ボックスを作成するには[、DoModal](#domodal)を呼び出します。 上の 2 番目のオーバーライドは[CComControl](../../atl/reference/ccomcontrol-class.md)でのみ使用されます。

## <a name="cdialogimpldestroywindow"></a><a name="destroywindow"></a>:Dエストロイウィンドウ

モードレス ダイアログ ボックスを破棄します。

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスが正常に破棄された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ダイアログ ボックスが正常に破棄された場合は TRUE を返します。それ以外の場合は FALSE。

## <a name="cdialogimpldialogproc"></a><a name="dialogproc"></a>:Dアログ・プロセス

この静的関数は、ダイアログ ボックスプロシージャを実装します。

```
static LRESULT CALLBACK DialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
[in]ダイアログ ボックスのハンドル。

*をクリックします。*<br/>
[in]ダイアログ ボックスに送信されるメッセージ。

*wParam*<br/>
[in]メッセージ固有の追加情報。

*lParam*<br/>
[in]メッセージ固有の追加情報。

### <a name="return-value"></a>戻り値

メッセージが処理される場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

`DialogProc`は、デフォルトのメッセージ・マップを使用して、適切なハンドラーにメッセージを送信します。

メッセージを処理`DialogProc`するための別のメカニズムを提供するためにオーバーライドできます。

## <a name="cdialogimpldomodal"></a><a name="domodal"></a>ダイアログインプル::Doモーダル

モーダル ダイアログ ボックスを作成します。

```
INT_PTR DoModal(
    HWND hWndParent = ::GetActiveWindow(),
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>パラメーター

*スーンドペアレント*<br/>
[in]所有者ウィンドウへのハンドル。 既定値は、[関数](/windows/win32/api/winuser/nf-winuser-getactivewindow)の戻り値です。

*ドウィニトパラム*<br/>
[in]WM_INITDIALOG メッセージの*lParam*パラメータでダイアログ ボックスに渡す値を指定します。

### <a name="return-value"></a>戻り値

成功した場合は[、EndDialog](#enddialog)の呼び出しで指定された*nRetCode*パラメーターの値。 それ以外の場合は、-1。

### <a name="remarks"></a>解説

このダイアログ ボックスは、オブジェクトに`CDialogImpl`自動的にアタッチされます。

モードレス ダイアログ ボックスを作成するには、 [Create](#create)を呼び出します。

## <a name="cdialogimplenddialog"></a><a name="enddialog"></a>ダイアログボックスインプル::エンドダイアログ

モーダル ダイアログ ボックスを破棄します。

```
BOOL EndDialog(int nRetCode);
```

### <a name="parameters"></a>パラメーター

*nレットコード*<br/>
[in]によって返される値[::DoModal.](#domodal)

### <a name="return-value"></a>戻り値

ダイアログ ボックスが破棄された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

`EndDialog`ダイアログ プロシージャを通して呼び出す必要があります。 ダイアログ ボックスが破棄されると、ダイアログ ボックスを作成した`DoModal`戻り値として*nRetCode*の値が使用されます。

> [!NOTE]
> モードレス`EndDialog`ダイアログ ボックスを破棄するために呼び出しません。 代わりに[CWindow::Dエストロイウィンドウを](../../atl/reference/cwindow-class.md#destroywindow)呼び出します。

## <a name="cdialogimplgetdialogproc"></a><a name="getdialogproc"></a>をクリックします。

現在`DialogProc`のダイアログ ボックス プロシージャを返します。

```
virtual WNDPROC GetDialogProc();
```

### <a name="return-value"></a>戻り値

現在のダイアログ ボックスプロシージャ。

### <a name="remarks"></a>解説

ダイアログ プロシージャを独自のプロシージャに置き換えるには、このメソッドをオーバーライドします。

## <a name="cdialogimplmapdialogrect"></a><a name="mapdialogrect"></a>ダイアログレクト::マップダイアログレック

指定された四角形のダイアログ ボックスの単位を画面単位 (ピクセル) に変換 (マップ) します。

```
BOOL MapDialogRect(LPRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*Lprect*<br/>
更新領域を`CRect`囲む更新のクライアント座標を受け取るオブジェクトまたは[RECT](/windows/win32/api/windef/ns-windef-rect)構造体へのポインター。

### <a name="return-value"></a>戻り値

更新が成功した場合は 0 以外。更新が失敗した場合は 0。 拡張されたエラー情報を取得するには、`GetLastError` を呼び出します。

### <a name="remarks"></a>解説

この関数は、指定した`RECT`構造体の座標を変換された座標に置き換えます。

## <a name="cdialogimplonfinalmessage"></a><a name="onfinalmessage"></a>終値::オンファイナルメッセージ

最後のメッセージを受信した後に`WM_NCDESTROY`呼び出されます (通常)。

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
[in]破棄されるウィンドウへのハンドル。

### <a name="remarks"></a>解説

ウィンドウの破棄時にオブジェクトを自動的に削除する場合は、**これを削除**します。

## <a name="cdialogimplstartdialogproc"></a><a name="startdialogproc"></a>を開始します。

ダイアログ ボックスに送信されたメッセージを処理するために、最初のメッセージを受信したときに 1 回だけ呼び出されます。

```
static LRESULT CALLBACK StartDialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
[in]ダイアログ ボックスのハンドル。

*をクリックします。*<br/>
[in]ダイアログ ボックスに送信されるメッセージ。

*wParam*<br/>
[in]メッセージ固有の追加情報。

*lParam*<br/>
[in]メッセージ固有の追加情報。

### <a name="return-value"></a>戻り値

ウィンドウ プロシージャ。

### <a name="remarks"></a>解説

の`StartDialogProc`最初の呼び出`DialogProc`しの後、ダイアログ プロシージャとして設定され、さらに呼び出しが行われます。

## <a name="see-also"></a>関連項目

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
