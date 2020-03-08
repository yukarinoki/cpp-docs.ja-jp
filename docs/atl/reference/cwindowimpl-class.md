---
title: CWindowImpl クラス
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
ms.openlocfilehash: b8b633dcf4ea14e899ee00552b553476cf697689
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78862973"
---
# <a name="cwindowimpl-class"></a>CWindowImpl クラス

ウィンドウを作成またはサブクラス化するためのメソッドを提供します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T, class TBase = CWindow, class TWinTraits = CControlWinTraits>
class ATL_NO_VTABLE CWindowImpl : public CWindowImplBaseT<TBase, TWinTraits>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
`CWindowImpl` から派生した新しいクラス。

*TBase*<br/>
クラスの基底クラス。 既定では、基本クラスは[CWindow](../../atl/reference/cwindow-class.md)です。

*TWinTraits*<br/>
ウィンドウのスタイルを定義する[特徴クラス](../../atl/understanding-window-traits.md)。 既定では、 `CControlWinTraits`です。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[CWindowImpl:: Create](#create)|ウィンドウを作成します。|

### <a name="cwindowimplbaset-methods"></a>CWindowImplBaseT メソッド

|||
|-|-|
|[DefWindowProc](#defwindowproc)|既定のメッセージ処理を提供します。|
|[GetCurrentMessage](#getcurrentmessage)|現在のメッセージを返します。|
|[GetWindowProc](#getwindowproc)|現在のウィンドウ プロシージャを返します。|
|[OnFinalMessage](#onfinalmessage)|最後のメッセージを受信した後に呼び出されます (通常は WM_NCDESTROY)。|
|[SubclassWindow](#subclasswindow)|ウィンドウをサブクラス化します。|
|[UnsubclassWindow](#unsubclasswindow)|前にサブクラス化されたウィンドウを復元します。|

### <a name="static-methods"></a>静的メソッド

|||
|-|-|
|[GetWndClassInfo](#getwndclassinfo)|ウィンドウクラスの情報を管理する[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)の静的なインスタンスを返します。|
|[WindowProc](#windowproc)|ウィンドウに送信されるメッセージを処理します。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|ウィンドウ クラスの元のウィンドウ プロシージャをポイントします。|

## <a name="remarks"></a>解説

`CWindowImpl` を使用すると、ウィンドウを作成したり、既存のウィンドウをサブクラス化したりできます。 `CWindowImpl` ウィンドウプロシージャはメッセージマップを使用して、メッセージを適切なハンドラーに送信します。

`CWindowImpl::Create` は、 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)によって管理されるウィンドウクラスの情報に基づいてウィンドウを作成します。 `CWindowImpl` には[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)マクロが含まれています。これは `CWndClassInfo` 新しいウィンドウクラスを登録することを意味します。 既存のウィンドウクラスをスーパークラス化する場合は、`CWindowImpl` からクラスを派生させ、 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロを含めます。 この場合、`CWndClassInfo` は、既存のクラスに基づくウィンドウ クラスを登録しますが、`CWindowImpl::WindowProc` を使用します。 次に例を示します。

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]

> [!NOTE]
>  `CWndClassInfo` は、1 つのウィンドウ クラスの情報のみを管理するため、`CWindowImpl` のインスタンスによって作成された各ウィンドウは、同じウィンドウ クラスに基づきます。

`CWindowImpl` は、ウィンドウのサブクラス化もサポートします。 `SubclassWindow` メソッドは、既存のウィンドウを `CWindowImpl` オブジェクトにアタッチし、ウィンドウ プロシージャを `CWindowImpl::WindowProc` に変更します。 `CWindowImpl` の各インスタンスは、別のウィンドウをサブクラス化できます。

> [!NOTE]
>  特定の `CWindowImpl` オブジェクトに対して、`Create` または `SubclassWindow`を呼び出します。 同じオブジェクトで両方のメソッドを呼び出さないでください。

ATL には、`CWindowImpl`に加えて、別のオブジェクトに含まれるウィンドウを作成する[CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)が用意されています。

基底クラスのデストラクター (~ `CWindowImplRoot`) によって、オブジェクトが破棄される前にウィンドウが確実に失われます。

`CWindowImpl` は、`TBase` と[CMessageMap](../../atl/reference/cmessagemap-class.md)から派生した `CWindowImplRoot`から派生する `CWindowImplBaseT`から派生します。

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

**ヘッダー:** atlwin. h

##  <a name="create"></a>CWindowImpl:: Create

新しいウィンドウクラスに基づいてウィンドウを作成します。

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

*hWndParent*<br/>
から親ウィンドウまたはオーナーウィンドウへのハンドル。

*rect*<br/>
からウィンドウの位置を指定する[RECT](/previous-versions/dd162897\(v=vs.85\))構造体。 `RECT` は、ポインターまたは参照渡しで渡すことができます。

*szWindowName*<br/>
からウィンドウの名前を指定します。 既定値は NULL です。

*dwStyle*<br/>
からウィンドウのスタイル。 この値は、ウィンドウの特徴クラスによって提供されるスタイルと組み合わされます。 既定値は、特徴クラスにスタイルに対する完全な制御を与えます。 使用可能な値の一覧については、Windows SDK の「 [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) 」を参照してください。

*dwExStyle*<br/>
から拡張ウィンドウスタイル。 この値は、ウィンドウの特徴クラスによって提供されるスタイルと組み合わされます。 既定値は、特徴クラスにスタイルに対する完全な制御を与えます。 使用可能な値の一覧については、Windows SDK の「 [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) 」を参照してください。

*MenuOrID*<br/>
から子ウィンドウの場合は、ウィンドウ識別子。 トップレベルウィンドウの場合は、ウィンドウのメニューハンドル。 既定値は**0u**です。

*lpCreateParam*<br/>
からウィンドウ作成データへのポインター。 詳細については、 [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)の最後のパラメーターの説明を参照してください。

### <a name="return-value"></a>戻り値

成功した場合は、新しく作成されたウィンドウへのハンドル。 それ以外の場合は NULL。

### <a name="remarks"></a>解説

がまだ登録されていない場合、`Create` は最初にウィンドウクラスを登録します。 新しく作成されたウィンドウは、`CWindowImpl` オブジェクトに自動的にアタッチされます。

> [!NOTE]
>  既に[SubclassWindow](#subclasswindow)を呼び出している場合は、`Create` を呼び出さないでください。

既存のウィンドウクラスに基づくウィンドウクラスを使用するには、`CWindowImpl` からクラスを派生させ、 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロを含めます。 既存のウィンドウクラスのウィンドウプロシージャは[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)に保存されます。 詳細については、「 [CWindowImpl](../../atl/reference/cwindowimpl-class.md)の概要」を参照してください。

> [!NOTE]
>  0を*Menuorid*パラメーターの値として使用する場合は、コンパイラエラーを回避するために、0u (既定値) として指定する必要があります。

##  <a name="defwindowproc"></a>CWindowImpl::D efWindowProc

[WindowProc](#windowproc)によって呼び出され、メッセージマップによって処理されないメッセージを処理します。

```
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);

LRESULT DefWindowProc();
```

### <a name="parameters"></a>パラメーター

*uMsg*<br/>
からウィンドウに送信されたメッセージ。

*wParam*<br/>
からメッセージ固有の追加情報。

*lParam*<br/>
からメッセージ固有の追加情報。

### <a name="return-value"></a>戻り値

メッセージ処理の結果。

### <a name="remarks"></a>解説

既定では、`DefWindowProc` は、 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)で指定されたウィンドウプロシージャにメッセージ情報を送信するために、 [CallWindowProc](/windows/win32/api/winuser/nf-winuser-callwindowprocw) Win32 関数を呼び出します。

パラメーターのない関数は、現在のメッセージから必要なパラメーターを自動的に取得します。

##  <a name="getcurrentmessage"></a>CWindowImpl:: GetCurrentMessage

`MSG` 構造体にパッケージ化された現在のメッセージを返します。

```
const MSG* GetCurrentMessage();
```

### <a name="return-value"></a>戻り値

現在のメッセージ。

##  <a name="getwindowproc"></a>CWindowImpl:: GetWindowProc

現在のウィンドウプロシージャ `WindowProc`を返します。

```
virtual WNDPROC GetWindowProc();
```

### <a name="return-value"></a>戻り値

現在のウィンドウプロシージャ。

### <a name="remarks"></a>解説

ウィンドウプロシージャを独自のに置き換えるには、このメソッドをオーバーライドします。

##  <a name="getwndclassinfo"></a>CWindowImpl:: GetWndClassInfo

ウィンドウクラス情報にアクセスするために、 [Create](#create)によって呼び出されます。

```
static CWndClassInfo& GetWndClassInfo();
```

### <a name="return-value"></a>戻り値

[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)の静的インスタンス。

### <a name="remarks"></a>解説

既定では、`CWindowImpl` は、新しいウィンドウクラスを指定する[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)マクロを使用してこのメソッドを取得します。

既存のウィンドウクラスをスーパークラスにするには、`CWindowImpl` からクラスを派生させ、 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロを含めて `GetWndClassInfo`をオーバーライドします。 詳細については、「 [CWindowImpl](../../atl/reference/cwindowimpl-class.md)の概要」を参照してください。

DECLARE_WND_CLASS マクロと DECLARE_WND_SUPERCLASS マクロを使用するだけでなく、独自の実装で `GetWndClassInfo` をオーバーライドすることもできます。

##  <a name="m_pfnsuperwindowproc"></a>CWindowImpl:: m_pfnSuperWindowProc

ウィンドウに応じて、は次のいずれかのウィンドウプロシージャを指します。

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>解説

|ウィンドウの種類|ウィンドウプロシージャ|
|--------------------|----------------------|
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)マクロで指定された新しいウィンドウクラスに基づくウィンドウ。|[DefWindowProc](/windows/win32/api/winuser/nf-winuser-defwindowprocw) Win32 関数。|
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロを使用して指定された既存のクラスを変更するウィンドウクラスに基づくウィンドウ。|既存のウィンドウクラスのウィンドウプロシージャ。|
|サブクラスウィンドウです。|サブクラスウィンドウの元のウィンドウプロシージャ。|

[CWindowImpl::D efwindowproc](#defwindowproc)は、`m_pfnSuperWindowProc`に保存されたウィンドウプロシージャにメッセージ情報を送信します。

##  <a name="onfinalmessage"></a>CWindowImpl:: OnFinalMessage

最後のメッセージを受信した後に呼び出されます (通常は WM_NCDESTROY)。

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
から破棄されるウィンドウへのハンドル。

### <a name="remarks"></a>解説

`OnFinalMessage` の既定の実装では何も実行されませんが、ウィンドウを破棄する前に、この関数をオーバーライドしてクリーンアップを処理することができます。 ウィンドウの破棄時にオブジェクトを自動的に削除する場合は、この関数で**delete this;** を呼び出すことができます。

##  <a name="subclasswindow"></a>CWindowImpl:: SubclassWindow

*HWnd*によって識別されるウィンドウをサブクラス化し、`CWindowImpl` オブジェクトにアタッチします。

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
からサブクラス化されているウィンドウへのハンドル。

### <a name="return-value"></a>戻り値

ウィンドウが正常にサブクラス化された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

サブクラス化されたウィンドウで、 [CWindowImpl:: WindowProc](#windowproc)が使用されるようになりました。 元のウィンドウプロシージャは[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)に保存されます。

> [!NOTE]
>  既に[Create](#create)を呼び出している場合は、`SubclassWindow` を呼び出さないでください。

##  <a name="unsubclasswindow"></a>CWindowImpl:: UnsubclassWindow

サブクラスウィンドウを `CWindowImpl` オブジェクトからデタッチし、 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)に保存された元のウィンドウプロシージャを復元します。

```
HWND UnsubclassWindow();
```

### <a name="return-value"></a>戻り値

以前にサブクラス化されたウィンドウへのハンドル。

##  <a name="windowproc"></a>CWindowImpl:: WindowProc

この静的関数は、ウィンドウプロシージャを実装します。

```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
からウィンドウへのハンドル。

*uMsg*<br/>
からウィンドウに送信されたメッセージ。

*wParam*<br/>
からメッセージ固有の追加情報。

*lParam*<br/>
からメッセージ固有の追加情報。

### <a name="return-value"></a>戻り値

メッセージ処理の結果。

### <a name="remarks"></a>解説

`WindowProc` は、既定のメッセージマップ ( [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)で宣言) を使用して、メッセージを適切なハンドラーに送信します。 必要に応じて、`WindowProc` は、追加のメッセージ処理のために[DefWindowProc](#defwindowproc)を呼び出します。 最終的なメッセージが処理されない場合、`WindowProc` は次の処理を実行します。

- ウィンドウがサブクラス化されていない場合は、サブクラス解除を実行します。

- `m_hWnd` を消去します。

- ウィンドウが破棄される前に[Onfinalmessage](#onfinalmessage)を呼び出します。

`WindowProc` をオーバーライドして、メッセージを処理するためのさまざまなメカニズムを提供できます。

## <a name="see-also"></a>参照

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[CComControl クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
