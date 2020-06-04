---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CWindowImpl
- ATLWIN/ATL::CWindowImpl
- ATLWIN/ATL::CWindowImpl::Create
- ATLWIN/ATL::CWindowImpl::DefWindowProc
- ATLWIN/ATL::CWindowImpl::GetCurrentMessage
- ATLWIN/ATL::CWindowImpl::GetWindowProc
- ATLWIN/ATL::CWindowImpl::OnFinalMessage
- ATLWIN/ATL::CWindowImpl::SubclassWindow
- ATLWIN/ATL::CWindowImpl::UnsubclassWindow
- ATLWIN/ATL::CWindowImpl::GetWndClassInfo
- ATLWIN/ATL::CWindowImpl::WindowProc
- ATLWIN/ATL::CWindowImpl::m_pfnSuperWindowProc
helpviewer_keywords:
- CWindowImpl class
- subclassing windows, ATL
ms.assetid: 02eefd45-a0a6-4d1b-99f6-dbf627e2cc2f
ms.openlocfilehash: ea150195f06d12cd6549b9026714d9e1bbf392df
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745991"
---
# <a name="cwindowimpl-class"></a>クラス

ウィンドウを作成またはサブクラス化するためのメソッドを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T, class TBase = CWindow, class TWinTraits = CControlWinTraits>
class ATL_NO_VTABLE CWindowImpl : public CWindowImplBaseT<TBase, TWinTraits>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
`CWindowImpl` から派生した新しいクラス。

*Tベース*<br/>
クラスの基底クラス。 既定では、基本クラスは[CWindow です](../../atl/reference/cwindow-class.md)。

*Tウィントレイツ*<br/>
ウィンドウのスタイルを定義する[traits クラス](../../atl/understanding-window-traits.md)。 既定では、 `CControlWinTraits`です。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cウィンドウインプル::作成](#create)|ウィンドウを作成します。|

### <a name="cwindowimplbaset-methods"></a>CWindowImplBaseT メソッド

|||
|-|-|
|[DefWindowProc](#defwindowproc)|既定のメッセージ処理を提供します。|
|[GetCurrentMessage](#getcurrentmessage)|現在のメッセージを返します。|
|[GetWindowProc](#getwindowproc)|現在のウィンドウ プロシージャを返します。|
|[OnFinalMessage](#onfinalmessage)|最後のメッセージを受信した後に呼び出されます (通常はWM_NCDESTROY)。|
|[SubclassWindow](#subclasswindow)|ウィンドウをサブクラス化します。|
|[UnsubclassWindow](#unsubclasswindow)|前にサブクラス化されたウィンドウを復元します。|

### <a name="static-methods"></a>静的メソッド

|||
|-|-|
|[GetWndClassInfo](#getwndclassinfo)|ウィンドウ クラス情報を管理する[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)の静的インスタンスを返します。|
|[WindowProc](#windowproc)|ウィンドウに送信されるメッセージを処理します。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|ウィンドウ クラスの元のウィンドウ プロシージャをポイントします。|

## <a name="remarks"></a>解説

を使用`CWindowImpl`して、既存のウィンドウを作成したり、サブクラス化したりできます。 ウィンドウ`CWindowImpl`プロシージャは、メッセージ マップを使用して、適切なハンドラにメッセージを送信します。

`CWindowImpl::Create`によって管理されるウィンドウ クラス情報に基づいてウィンドウが作成[されます](../../atl/reference/cwndclassinfo-class.md)。 `CWindowImpl`には[、DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)マクロが含`CWndClassInfo`まれています。 既存のウィンドウ クラスをスーパークラス化する場合は、クラスを`CWindowImpl`派生し[、DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロをインクルードします。 この場合、`CWndClassInfo` は、既存のクラスに基づくウィンドウ クラスを登録しますが、`CWindowImpl::WindowProc` を使用します。 次に例を示します。

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]

> [!NOTE]
> `CWndClassInfo` は、1 つのウィンドウ クラスの情報のみを管理するため、`CWindowImpl` のインスタンスによって作成された各ウィンドウは、同じウィンドウ クラスに基づきます。

`CWindowImpl` は、ウィンドウのサブクラス化もサポートします。 `SubclassWindow` メソッドは、既存のウィンドウを `CWindowImpl` オブジェクトにアタッチし、ウィンドウ プロシージャを `CWindowImpl::WindowProc` に変更します。 `CWindowImpl` の各インスタンスは、別のウィンドウをサブクラス化できます。

> [!NOTE]
> 任意`CWindowImpl`のオブジェクトに対して、 `Create` `SubclassWindow`または を呼び出します。 同じオブジェクトで両方のメソッドを呼び出さないでください。

ATL`CWindowImpl`には、別のオブジェクトに含まれるウィンドウを作成する[CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)が用意されています。

基本クラスのデストラクター (~)`CWindowImplRoot`は、オブジェクトが破棄される前にウィンドウが消えてしまうことを確認します。

`CWindowImpl``CWindowImplBaseT`から派生`CWindowImplRoot`元、`TBase`および[CMessageMap](../../atl/reference/cmessagemap-class.md)から派生します。

|詳細情報|参照先|
|--------------------------------|---------|
|コントロールの作成|[ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)|
|ATL でのウィンドウの使用|[ATL ウィンドウ クラス](../../atl/atl-window-classes.md)|
|ATL プロジェクト ウィザード|[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)|

## <a name="inheritance-hierarchy"></a>継承階層

[CMessageMap](../../atl/reference/cmessagemap-class.md)

`TBase`

`CWindowImplRoot`

`CWindowImplBaseT`

`CWindowImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="cwindowimplcreate"></a><a name="create"></a>Cウィンドウインプル::作成

新しいウィンドウ クラスに基づいてウィンドウを作成します。

```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```

### <a name="parameters"></a>パラメーター

*スーンドペアレント*<br/>
[in]親ウィンドウまたはオーナー ウィンドウへのハンドル。

*Rect*<br/>
[in]ウィンドウの位置を指定する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体。 は`RECT`、ポインターまたは参照によって渡すことができます。

*ウィンドウ名*<br/>
[in]ウィンドウの名前を指定します。 既定値は NULL です。

*Dwstyle*<br/>
[in]ウィンドウのスタイル。 この値は、ウィンドウの traits クラスによって提供されるスタイルと組み合わされます。 既定値は、traits クラスにスタイルに対するフル コントロールを提供します。 使用可能な値の一覧については、Windows SDK[の「ウィンドウの作成](/windows/win32/api/winuser/nf-winuser-createwindoww)」を参照してください。

*ドウェエクススタイル*<br/>
[in]拡張ウィンドウ スタイル。 この値は、ウィンドウの traits クラスによって提供されるスタイルと組み合わされます。 既定値は、traits クラスにスタイルに対するフル コントロールを提供します。 使用可能な値の一覧については、Windows SDK[の「ウィンドウエクスックスの作成](/windows/win32/api/winuser/nf-winuser-createwindowexw)」を参照してください。

*メニューオイド*<br/>
[in]子ウィンドウの場合は、ウィンドウ識別子。 トップレベル ウィンドウの場合は、ウィンドウのメニュー ハンドル。 デフォルト値は**0U**です。

*を作成します。*<br/>
[in]ウィンドウ作成データへのポインター。 詳細については、 [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)の最終パラメータの説明を参照してください。

### <a name="return-value"></a>戻り値

正常に終了した場合は、新しく作成されたウィンドウへのハンドル。 それ以外の場合は NULL。

### <a name="remarks"></a>解説

`Create`ウィンドウ クラスがまだ登録されていない場合は、まず登録します。 新しく作成されたウィンドウは、オブジェクトに`CWindowImpl`自動的にアタッチされます。

> [!NOTE]
> 既に`Create`[SubclassWindow](#subclasswindow)を呼び出している場合は呼び出しません。

既存のウィンドウ クラスに基づくウィンドウ クラスを使用するには、DECLARE_WND_SUPERCLASS マクロ`CWindowImpl`からクラスを[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)派生し、マクロを含めます。 既存のウィンドウ クラスのウィンドウ プロシージャは[、 m_pfnSuperWindowProc](#m_pfnsuperwindowproc)に保存されます。 詳細については[、「CWindowImpl](../../atl/reference/cwindowimpl-class.md)の概要」を参照してください。

> [!NOTE]
> *MenuOrID*パラメーターの値として 0 を使用する場合は、コンパイラ エラーを回避するために 0U (既定値) を指定する必要があります。

## <a name="cwindowimpldefwindowproc"></a><a name="defwindowproc"></a>ウィンドウインプル::Dウィンドウプロセッサ

メッセージ マップで処理されないメッセージを処理するために[、WindowProc](#windowproc)によって呼び出されます。

```
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);

LRESULT DefWindowProc();
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]ウィンドウに送信されるメッセージ。

*wParam*<br/>
[in]メッセージ固有の追加情報。

*lParam*<br/>
[in]メッセージ固有の追加情報。

### <a name="return-value"></a>戻り値

メッセージ処理の結果。

### <a name="remarks"></a>解説

既定では、`DefWindowProc`呼び出し、 [CallWindowProc](/windows/win32/api/winuser/nf-winuser-callwindowprocw) Win32 関数を呼び出して[、m_pfnSuperWindowProc](#m_pfnsuperwindowproc)で指定されたウィンドウ プロシージャにメッセージ情報を送信します。

パラメーターを持たない関数は、現在のメッセージから必要なパラメーターを自動的に取得します。

## <a name="cwindowimplgetcurrentmessage"></a><a name="getcurrentmessage"></a>ウィンドウインプル::現在のメッセージを取得します

構造体にパッケージ化された現在のメッセージを`MSG`返します。

```
const MSG* GetCurrentMessage();
```

### <a name="return-value"></a>戻り値

現在のメッセージ。

## <a name="cwindowimplgetwindowproc"></a><a name="getwindowproc"></a>ウィンドウインプル::ウィンドウプロセスを取得します。

現在`WindowProc`のウィンドウ プロシージャを返します。

```
virtual WNDPROC GetWindowProc();
```

### <a name="return-value"></a>戻り値

現在のウィンドウ プロシージャ。

### <a name="remarks"></a>解説

ウィンドウ プロシージャを独自のプロシージャに置き換えるには、このメソッドをオーバーライドします。

## <a name="cwindowimplgetwndclassinfo"></a><a name="getwndclassinfo"></a>をクリックします。

ウィンドウ クラス情報にアクセスするために[Create](#create)によって呼び出されます。

```
static CWndClassInfo& GetWndClassInfo();
```

### <a name="return-value"></a>戻り値

[の](../../atl/reference/cwndclassinfo-class.md)静的インスタンス。

### <a name="remarks"></a>解説

既定では、`CWindowImpl`新しいウィンドウ クラスを指定する[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)マクロを使用して、このメソッドを取得します。

既存のウィンドウ クラスをスーパークラス化するには、クラス`CWindowImpl`を派生させ、オーバーライド`GetWndClassInfo`する[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロをインクルードします。 詳細については[、「CWindowImpl](../../atl/reference/cwindowimpl-class.md)の概要」を参照してください。

DECLARE_WND_CLASSとDECLARE_WND_SUPERCLASSマクロを使用する以外に、独自`GetWndClassInfo`の実装でオーバーライドできます。

## <a name="cwindowimplm_pfnsuperwindowproc"></a><a name="m_pfnsuperwindowproc"></a>ウィンドウインプル::m_pfnSuperWindowProc

ウィンドウに応じて、次のいずれかのウィンドウ プロシージャを指します。

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>解説

|ウィンドウの種類|ウィンドウプロシージャ|
|--------------------|----------------------|
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)マクロで指定された新しいウィンドウ クラスに基づくウィンドウ。|[関数を使用](/windows/win32/api/winuser/nf-winuser-defwindowprocw)します。|
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロで指定された既存のクラスを変更するウィンドウ クラスに基づくウィンドウ。|既存のウィンドウ クラスのウィンドウ プロシージャ。|
|サブクラス化されたウィンドウ。|サブクラス化されたウィンドウの元のウィンドウ プロシージャ。|

[:D に](#defwindowproc)保存されているウィンドウ プロシージャにメッセージ情報を送信`m_pfnSuperWindowProc`します。

## <a name="cwindowimplonfinalmessage"></a><a name="onfinalmessage"></a>Cウィンドウインプル::オンファイナルメッセージ

最後のメッセージを受信した後に呼び出されます (通常はWM_NCDESTROY)。

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
[in]破棄されるウィンドウへのハンドル。

### <a name="remarks"></a>解説

の既定の`OnFinalMessage`実装では何も行われませんが、ウィンドウを破棄する前にクリーンアップを処理するには、この関数をオーバーライドできます。 ウィンドウの破棄時にオブジェクトを自動的に削除する場合は、この関数で**delete this を**呼び出すことができます。

## <a name="cwindowimplsubclasswindow"></a><a name="subclasswindow"></a>ウィンドウインプル::サブクラスウィンドウ

*hWnd*で識別されるウィンドウをサブクラス化し、オブジェクト`CWindowImpl`にアタッチします。

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
[in]サブクラス化されるウィンドウへのハンドル。

### <a name="return-value"></a>戻り値

ウィンドウが正常にサブクラス化された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

サブクラス化されたウィンドウで[CWindowImpl::WindowProc が](#windowproc)使用されるようになりました。 元のウィンドウ プロシージャは[、 m_pfnSuperWindowProc](#m_pfnsuperwindowproc)に保存されます。

> [!NOTE]
> 既に`SubclassWindow`[Create](#create)を呼び出している場合は、呼び出しを行いません。

## <a name="cwindowimplunsubclasswindow"></a><a name="unsubclasswindow"></a>Cウィンドウインプル::アンサブクラスウィンドウ

サブクラス化されたウィンドウを`CWindowImpl`オブジェクトから切り離し、元のウィンドウ プロシージャを[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)に保存します。

```
HWND UnsubclassWindow();
```

### <a name="return-value"></a>戻り値

以前にサブクラス化されたウィンドウへのハンドル。

## <a name="cwindowimplwindowproc"></a><a name="windowproc"></a>ウィンドウインプル::ウィンドウプロセッサ

この静的関数は、ウィンドウ プロシージャを実装します。

```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
[in]ウィンドウへのハンドル。

*をクリックします。*<br/>
[in]ウィンドウに送信されるメッセージ。

*wParam*<br/>
[in]メッセージ固有の追加情報。

*lParam*<br/>
[in]メッセージ固有の追加情報。

### <a name="return-value"></a>戻り値

メッセージ処理の結果。

### <a name="remarks"></a>解説

`WindowProc`は、デフォルトのメッセージ マップ ( [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)で宣言 ) を使用して、適切なハンドラにメッセージを送信します。 必要に応`WindowProc`じて、追加のメッセージ処理を行うための[DefWindowProc](#defwindowproc)を呼び出します。 最終メッセージが処理されない場合は、`WindowProc`次の処理を行います。

- ウィンドウがサブクラス化されていない場合は、サブクラス化を解除します。

- `m_hWnd` を消去します。

- ウィンドウが破棄される前[に OnFinalMessage](#onfinalmessage)を呼び出します。

メッセージを処理`WindowProc`するための別のメカニズムを提供するためにオーバーライドできます。

## <a name="see-also"></a>関連項目

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[CCom コントロール クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
