---
title: CWindowImpl クラス
ms.date: 11/04/2016
f1_keywords:
- CWindowImpl
- ATLWIN/ATL::CWindowImpl
- ATLWIN/ATL::CWindowImpl::Create
- ATLWIN/ATL::DefWindowProc
- ATLWIN/ATL::GetCurrentMessage
- ATLWIN/ATL::GetWindowProc
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::SubclassWindow
- ATLWIN/ATL::UnsubclassWindow
- ATLWIN/ATL::GetWndClassInfo
- ATLWIN/ATL::WindowProc
- ATLWIN/ATL::m_pfnSuperWindowProc
helpviewer_keywords:
- CWindowImpl class
- subclassing windows, ATL
ms.assetid: 02eefd45-a0a6-4d1b-99f6-dbf627e2cc2f
ms.openlocfilehash: 96807debc7a3af5eca5d7a0c17a7728431733325
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417932"
---
# <a name="cwindowimpl-class"></a>CWindowImpl クラス

ウィンドウを作成またはサブクラス化するためのメソッドを提供します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T, class TBase = CWindow, class TWinTraits = CControlWinTraits>
class ATL_NO_VTABLE CWindowImpl : public CWindowImplBaseT<TBase, TWinTraits>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>

  `CWindowImpl` から派生した新しいクラス。

*TBase*<br/>
クラスの基底クラス。 基本クラスは、既定では、 [CWindow](../../atl/reference/cwindow-class.md)します。

*TWinTraits*<br/>
A[特性クラス](../../atl/understanding-window-traits.md)ウィンドウのスタイルを定義します。 既定値は `CControlWinTraits` です。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CWindowImpl::Create](#create)|ウィンドウを作成します。|

### <a name="cwindowimplbaset-methods"></a>CWindowImplBaseT メソッド

|||
|-|-|
|[DefWindowProc](#defwindowproc)|既定のメッセージ処理を提供します。|
|[GetCurrentMessage](#getcurrentmessage)|現在のメッセージを返します。|
|[GetWindowProc](#getwindowproc)|現在のウィンドウ プロシージャを返します。|
|[OnFinalMessage](#onfinalmessage)|最後のメッセージを受信した後に呼び出されます (通常はへ)。|
|[SubclassWindow](#subclasswindow)|ウィンドウをサブクラス化します。|
|[UnsubclassWindow](#unsubclasswindow)|前にサブクラス化されたウィンドウを復元します。|

### <a name="static-methods"></a>静的メソッド

|||
|-|-|
|[GetWndClassInfo](#getwndclassinfo)|静的インスタンスを返します[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)、ウィンドウ クラスの情報を管理します。|
|[WindowProc](#windowproc)|ウィンドウに送信されるメッセージを処理します。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|ウィンドウ クラスの元のウィンドウ プロシージャをポイントします。|

## <a name="remarks"></a>Remarks

使用することができます`CWindowImpl`既存のウィンドウのウィンドウまたはサブクラスを作成します。 `CWindowImpl`ウィンドウ プロシージャは、適切なハンドラーにメッセージをメッセージ マップを使用します。

`CWindowImpl::Create` 管理されているウィンドウ クラスの情報に基づいてウィンドウを作成します[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)します。 `CWindowImpl` 含まれています、 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)マクロ、つまり`CWndClassInfo`新しいウィンドウ クラスを登録します。 既存のウィンドウ クラスをスーパークラスしたい場合からクラスを派生`CWindowImpl`を含めると、 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロ。 この場合、`CWndClassInfo` は、既存のクラスに基づくウィンドウ クラスを登録しますが、`CWindowImpl::WindowProc` を使用します。 例:

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]

> [!NOTE]
>  
  `CWndClassInfo` は、1 つのウィンドウ クラスの情報のみを管理するため、`CWindowImpl` のインスタンスによって作成された各ウィンドウは、同じウィンドウ クラスに基づきます。

`CWindowImpl` は、ウィンドウのサブクラス化もサポートします。 
  `SubclassWindow` メソッドは、既存のウィンドウを `CWindowImpl` オブジェクトにアタッチし、ウィンドウ プロシージャを `CWindowImpl::WindowProc` に変更します。 
  `CWindowImpl` の各インスタンスは、別のウィンドウをサブクラス化できます。

> [!NOTE]
>  指定されたいずれかの`CWindowImpl`オブジェクト、いずれかを呼び出す`Create`または`SubclassWindow`します。 同じオブジェクトで両方のメソッドを呼び出さないでください。

加え`CWindowImpl`、atl [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)別のオブジェクトに含まれているウィンドウを作成します。

基底クラスのデストラクター (~ `CWindowImplRoot`) により、オブジェクトが破棄される前にウィンドウが消えます。

`CWindowImpl` 派生した`CWindowImplBaseT`から派生した`CWindowImplRoot`から派生した`TBase`と[CMessageMap](../../atl/reference/cmessagemap-class.md)します。

|詳細情報:|解決方法|
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

##  <a name="create"></a>  CWindowImpl::Create

新しいウィンドウ クラスに基づくウィンドウを作成します。

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
[in]親またはオーナー ウィンドウのハンドル。

*rect*<br/>
[in]A [RECT](/previous-versions/dd162897\(v=vs.85\))ウィンドウの位置を指定する構造体。 `RECT`ポインターまたは参照によって渡すことができます。

*szWindowName*<br/>
[in]ウィンドウの名前を指定します。 既定値は、NULL です。

*dwStyle*<br/>
[in]ウィンドウのスタイル。 この値は、ウィンドウの特性クラスによって提供されるスタイルと組み合わされます。 既定値は、スタイルに対するフル コントロールをクラスに、特徴を示します。 使用可能な値の一覧は、次を参照してください。 [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) Windows SDK に含まれています。

*dwExStyle*<br/>
[in]拡張ウィンドウ スタイル。 この値は、ウィンドウの特性クラスによって提供されるスタイルと組み合わされます。 既定値は、スタイルに対するフル コントロールをクラスに、特徴を示します。 使用可能な値の一覧は、次を参照してください。 [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK に含まれています。

*MenuOrID*<br/>
[in]子ウィンドウの場合、ウィンドウの識別子。 最上位レベルのウィンドウでは、メニューはウィンドウのハンドルします。 既定値は**0 u**します。

*lpCreateParam*<br/>
[in]ウィンドウの作成データへのポインター。 詳細については、最後のパラメーターの説明を参照してください。 [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa)します。

### <a name="return-value"></a>戻り値

成功した場合、新しく作成されたウィンドウを識別するハンドル。 それ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

`Create` 最初にまだ登録されていない場合は、ウィンドウ クラスを登録します。 新しく作成されたウィンドウが自動的にアタッチ、`CWindowImpl`オブジェクト。

> [!NOTE]
>  呼び出さない`Create`既にを呼び出した場合[SubclassWindow](#subclasswindow)します。

既存のウィンドウ クラスに基づくウィンドウ クラスを使用するからクラスを派生`CWindowImpl`を含めると、 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロ。 既存のウィンドウ クラスのウィンドウ プロシージャ[コンテナー内](#m_pfnsuperwindowproc)します。 詳細については、次を参照してください。、 [CWindowImpl](../../atl/reference/cwindowimpl-class.md)の概要。

> [!NOTE]
>  値として 0 が使用する場合、 *MenuOrID*パラメーター 0 u として指定する必要があります (既定値)、コンパイラ エラーを回避するためにします。

##  <a name="defwindowproc"></a>  CWindowImpl::DefWindowProc

によって呼び出される[WindowProc](#windowproc)メッセージ マップで処理されないメッセージを処理します。

```
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);

LRESULT DefWindowProc();
```

### <a name="parameters"></a>パラメーター

*uMsg*<br/>
[in]ウィンドウに送信されるメッセージ。

*wParam*<br/>
[in]追加のメッセージに固有の情報。

*lParam*<br/>
[in]追加のメッセージに固有の情報。

### <a name="return-value"></a>戻り値

メッセージの処理の結果。

### <a name="remarks"></a>Remarks

既定では、`DefWindowProc`呼び出し、 [CallWindowProc](/windows/desktop/api/winuser/nf-winuser-callwindowproca)ウィンドウ プロシージャで指定されたメッセージの情報を送信する Win32 関数[コンテナー内](#m_pfnsuperwindowproc)します。

パラメーターなしの関数は、現在のメッセージから自動的に必要なパラメーターを取得します。

##  <a name="getcurrentmessage"></a>  CWindowImpl::GetCurrentMessage

パッケージ化、現在のメッセージが返されます、`MSG`構造体。

```
const MSG* GetCurrentMessage();
```

### <a name="return-value"></a>戻り値

現在のメッセージ。

##  <a name="getwindowproc"></a>  CWindowImpl::GetWindowProc

返します`WindowProc`、現在のウィンドウ プロシージャ。

```
virtual WNDPROC GetWindowProc();
```

### <a name="return-value"></a>戻り値

現在のウィンドウ プロシージャ。

### <a name="remarks"></a>Remarks

独自のウィンドウ プロシージャを置換するには、このメソッドをオーバーライドします。

##  <a name="getwndclassinfo"></a>  CWindowImpl::GetWndClassInfo

によって呼び出される[作成](#create)ウィンドウ クラスの情報にアクセスします。

```
static CWndClassInfo& GetWndClassInfo();
```

### <a name="return-value"></a>戻り値

静的インスタンス[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)します。

### <a name="remarks"></a>Remarks

既定では、`CWindowImpl`を通じてこのメソッドを取得、 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)マクロで、新しいウィンドウ クラスを指定します。

既存のウィンドウ クラスをスーパークラスからクラスを派生`CWindowImpl`を含めると、 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)をオーバーライドするマクロ`GetWndClassInfo`します。 詳細については、次を参照してください。、 [CWindowImpl](../../atl/reference/cwindowimpl-class.md)の概要。

DECLARE_WND_CLASS と DECLARE_WND_SUPERCLASS マクロだけでなく、オーバーライドすることができます`GetWndClassInfo`で独自の実装。

##  <a name="m_pfnsuperwindowproc"></a>  CWindowImpl::m_pfnSuperWindowProc

に応じて、ウィンドウには、次のウィンドウ プロシージャのいずれかを指します。

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>Remarks

|ウィンドウの種類|ウィンドウ プロシージャ|
|--------------------|----------------------|
|新しいウィンドウ クラスを使用して指定に基づいて、 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)マクロ。|[DefWindowProc](/windows/desktop/api/winuser/nf-winuser-defwindowproca) Win32 関数。|
|指定された、既存のクラスを変更するウィンドウ クラスに基づいて、 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロ。|既存のウィンドウ クラスのウィンドウ プロシージャです。|
|サブクラス化されたウィンドウです。|サブクラス化されたウィンドウの元のウィンドウ プロシージャ。|

[CWindowImpl::DefWindowProc](#defwindowproc)メッセージに保存されているウィンドウ プロシージャに情報を送信します`m_pfnSuperWindowProc`します。

##  <a name="onfinalmessage"></a>  CWindowImpl::OnFinalMessage

最後のメッセージ (通常はへ) を受信した後に呼び出されます。

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
[in]破棄されているウィンドウへのハンドル。

### <a name="remarks"></a>Remarks

既定の実装`OnFinalMessage`、何も行われませんが、ウィンドウを破棄する前にクリーンアップを処理するには、この関数をオーバーライドできます。 ウィンドウの破棄後にオブジェクトを自動的に削除する場合は、呼び出すことが **; 削除**この関数でします。

##  <a name="subclasswindow"></a>  CWindowImpl::SubclassWindow

識別される、ウィンドウをサブクラス*hWnd*にアタッチします、`CWindowImpl`オブジェクト。

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
[in]サブクラス化されているウィンドウのハンドル。

### <a name="return-value"></a>戻り値

ウィンドウが正常にサブクラス化された場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

サブクラス化されたウィンドウは[CWindowImpl::WindowProc](#windowproc)します。 元のウィンドウ プロシージャに保存[コンテナー内](#m_pfnsuperwindowproc)します。

> [!NOTE]
>  呼び出さない`SubclassWindow`既にを呼び出した場合[作成](#create)です。

##  <a name="unsubclasswindow"></a>  CWindowImpl::UnsubclassWindow

サブクラス化されたウィンドウのデタッチ、`CWindowImpl`オブジェクトし、元のウィンドウ プロシージャに保存されている復元[コンテナー内](#m_pfnsuperwindowproc)します。

```
HWND UnsubclassWindow();
```

### <a name="return-value"></a>戻り値

以前にサブクラス化されたウィンドウのハンドル。

##  <a name="windowproc"></a>  CWindowImpl::WindowProc

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
[in]ウィンドウのハンドル。

*uMsg*<br/>
[in]ウィンドウに送信されるメッセージ。

*wParam*<br/>
[in]追加のメッセージに固有の情報。

*lParam*<br/>
[in]追加のメッセージに固有の情報。

### <a name="return-value"></a>戻り値

メッセージの処理の結果。

### <a name="remarks"></a>Remarks

`WindowProc` 既定のメッセージ マップを使用して (を使用して宣言[送るに](message-map-macros-atl.md#begin_msg_map)) メッセージを適切なハンドラーを送信します。 必要に応じて、`WindowProc`呼び出し[DefWindowProc](#defwindowproc)追加メッセージの処理。 最後のメッセージが処理されない場合`WindowProc`は次の処理します。

- ウィンドウをサブクラス化されたなかった場合は、解除処理を実行します。

- 
  `m_hWnd` を消去します。

- 呼び出し[OnFinalMessage](#onfinalmessage)ウィンドウが破棄される前にします。

オーバーライドできます`WindowProc`メッセージを処理するためのさまざまなメカニズムを提供します。

## <a name="see-also"></a>関連項目

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[CComControl クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
