---
description: '詳細情報: CContainedWindowT クラス'
title: CContainedWindowT クラス
ms.date: 11/04/2016
f1_keywords:
- CContainedWindowT
- ATLWIN/ATL::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::Create
- ATLWIN/ATL::CContainedWindowT::DefWindowProc
- ATLWIN/ATL::CContainedWindowT::GetCurrentMessage
- ATLWIN/ATL::CContainedWindowT::RegisterWndSuperclass
- ATLWIN/ATL::CContainedWindowT::SubclassWindow
- ATLWIN/ATL::CContainedWindowT::SwitchMessageMap
- ATLWIN/ATL::CContainedWindowT::UnsubclassWindow
- ATLWIN/ATL::CContainedWindowT::WindowProc
- ATLWIN/ATL::CContainedWindowT::m_dwMsgMapID
- ATLWIN/ATL::CContainedWindowT::m_lpszClassName
- ATLWIN/ATL::CContainedWindowT::m_pfnSuperWindowProc
- ATLWIN/ATL::CContainedWindowT::m_pObject
helpviewer_keywords:
- CContainedWindow class
- contained windows
- CContainedWindowT class
ms.assetid: cde0ca36-9347-4068-995a-d294dae57ca9
ms.openlocfilehash: 68135ec6d8dc43623ec2a827bbe075e24eef8d42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142078"
---
# <a name="ccontainedwindowt-class"></a>CContainedWindowT クラス

このクラスは、別のオブジェクト内に含まれるウィンドウを実装します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class TBase = CWindow, class TWinTraits = CControlWinTraits>
class CContainedWindowT : public TBase
```

#### <a name="parameters"></a>パラメーター

*TBase*<br/>
新しいクラスの基本クラス。 既定の基底クラスは `CWindow` です。

*TWinTraits*<br/>
ウィンドウのスタイルを定義する特徴クラス。 既定値は、`CControlWinTraits` です。

> [!NOTE]
> [CContainedWindow](ccontainedwindowt-class.md) は、の特殊化です `CContainedWindowT` 。 基底クラスまたは特徴を変更する場合は、を `CContainedWindowT` 直接使用します。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CContainedWindowT::CContainedWindowT](#ccontainedwindowt)|コンストラクターです。 格納されているウィンドウのメッセージを処理するメッセージマップを指定するために、データメンバーを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CContainedWindowT:: Create](#create)|ウィンドウを作成します。|
|[CContainedWindowT::D efWindowProc](#defwindowproc)|既定のメッセージ処理を提供します。|
|[CContainedWindowT:: GetCurrentMessage](#getcurrentmessage)|現在のメッセージを返します。|
|[CContainedWindowT::RegisterWndSuperclass](#registerwndsuperclass)|格納されているウィンドウのウィンドウクラスを登録します。|
|[CContainedWindowT::SubclassWindow](#subclasswindow)|ウィンドウをサブクラス化します。|
|[CContainedWindowT::SwitchMessageMap](#switchmessagemap)|格納されているウィンドウのメッセージを処理するために使用するメッセージマップを変更します。|
|[CContainedWindowT::UnsubclassWindow](#unsubclasswindow)|前にサブクラス化されたウィンドウを復元します。|
|[CContainedWindowT:: WindowProc](#windowproc)|雑音格納されているウィンドウに送信されたメッセージを処理します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CContainedWindowT:: m_dwMsgMapID](#m_dwmsgmapid)|含まれているウィンドウのメッセージを処理するメッセージマップを識別します。|
|[CContainedWindowT:: m_lpszClassName](#m_lpszclassname)|新しいウィンドウクラスの基になる既存のウィンドウクラスの名前を指定します。|
|[CContainedWindowT:: m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|ウィンドウ クラスの元のウィンドウ プロシージャをポイントします。|
|[CContainedWindowT:: m_pObject](#m_pobject)|格納しているオブジェクトを指します。|

## <a name="remarks"></a>解説

`CContainedWindowT` 別のオブジェクト内に含まれるウィンドウを実装します。 `CContainedWindowT`のウィンドウプロシージャは、コンテナーオブジェクトのメッセージマップを使用して、メッセージを適切なハンドラーに送信します。 オブジェクトを構築するときは `CContainedWindowT` 、使用するメッセージマップを指定します。

`CContainedWindowT` 既存のウィンドウクラスを superclassing して、新しいウィンドウを作成できます。 メソッドは、 `Create` まず、既存のクラスに基づくウィンドウクラスを登録しますが、を使用 `CContainedWindowT::WindowProc` します。 `Create` 次に、この新しいウィンドウクラスに基づいてウィンドウを作成します。 の各インスタンス `CContainedWindowT` は、別のウィンドウクラスをスーパークラスにすることができます。

`CContainedWindowT` は、ウィンドウのサブクラス化もサポートします。 `SubclassWindow` メソッドは、既存のウィンドウを `CContainedWindowT` オブジェクトにアタッチし、ウィンドウ プロシージャを `CContainedWindowT::WindowProc` に変更します。 `CContainedWindowT` の各インスタンスは、別のウィンドウをサブクラス化できます。

> [!NOTE]
> 特定のオブジェクトに対して `CContainedWindowT` 、 `Create` またはを呼び出し `SubclassWindow` ます。 同じオブジェクトで両方のメソッドを呼び出すことはできません。

ATL プロジェクトウィザードの **[に基づいてコントロールを追加** ] オプションを使用すると、ウィザードによって、 `CContainedWindowT` コントロールを実装するクラスにデータメンバーが自動的に追加されます。 次の例では、含まれているウィンドウがどのように宣言されているかを示します。

[!code-cpp[NVC_ATL_Windowing#38](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]

[!code-cpp[NVC_ATL_Windowing#39](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]

[!code-cpp[NVC_ATL_Windowing#40](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]

|詳細情報|解決方法については、|
|--------------------------------|---------|
|コントロールの作成|[ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)|
|ATL でのウィンドウの使用|[ATL ウィンドウクラス](../../atl/atl-window-classes.md)|
|ATL プロジェクト ウィザード|[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)|
|Windows|Windows SDK の[Windows](/windows/win32/winmsg/windows)とそれ以降のトピック|

## <a name="inheritance-hierarchy"></a>継承階層

`TBase`

`CContainedWindowT`

## <a name="requirements"></a>要件

**ヘッダー:** atlwin. h

## <a name="ccontainedwindowtccontainedwindowt"></a><a name="ccontainedwindowt"></a> CContainedWindowT::CContainedWindowT

コンストラクターは、データメンバーを初期化します。

```
CContainedWindowT(
    LPTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);

CContainedWindowT(
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0)
    CContainedWindowT();
```

### <a name="parameters"></a>パラメーター

*lpszClassName*<br/>
から格納されているウィンドウの基になる既存のウィンドウクラスの名前。

*pObject*<br/>
からメッセージマップを宣言するコンテナーオブジェクトへのポインター。 このオブジェクトのクラスは、 [CMessageMap](../../atl/reference/cmessagemap-class.md)から派生しなければなりません。

*dwMsgMapID*<br/>
から格納されているウィンドウのメッセージを処理するメッセージマップを識別します。 既定値は0で、 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)で宣言された既定のメッセージマップを指定します。 [ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)で宣言された代替メッセージマップを使用するには、を渡し `msgMapID` ます。

### <a name="remarks"></a>解説

[Create](#create)で新しいウィンドウを作成する場合は、 *lpszclassname* パラメーターの既存のウィンドウクラスの名前を渡す必要があります。 例については、「 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) の概要」を参照してください。

コンストラクターには次の3つがあります。

- 3つの引数を持つコンストラクターは、通常、と呼ばれます。

- 2つの引数を持つコンストラクターは、のクラス名を使用し `TBase::GetWndClassName` ます。

- 引数を持たないコンストラクターは、後で引数を指定する場合に使用します。 後でを呼び出すときに、ウィンドウクラス名、メッセージマップオブジェクト、およびメッセージマップ ID を指定する必要があり `Create` ます。

[SubclassWindow](#subclasswindow)を使用して既存のウィンドウをサブクラス化する場合、 *lpszclassname* 値は使用されません。したがって、このパラメーターには NULL を渡すことができます。

## <a name="ccontainedwindowtcreate"></a><a name="create"></a> CContainedWindowT:: Create

[RegisterWndSuperclass](#registerwndsuperclass)を呼び出して、既存のクラスに基づくウィンドウクラスを登録しますが、 [CContainedWindowT:: WindowProc](#windowproc)を使用します。

```
HWND Create(
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    LPCTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszClassName*<br/>
から格納されているウィンドウの基になる既存のウィンドウクラスの名前。

*pObject*<br/>
からメッセージマップを宣言するコンテナーオブジェクトへのポインター。 このオブジェクトのクラスは、 [CMessageMap](../../atl/reference/cmessagemap-class.md)から派生しなければなりません。

*dwMsgMapID*<br/>
から格納されているウィンドウのメッセージを処理するメッセージマップを識別します。 既定値は0で、 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)で宣言された既定のメッセージマップを指定します。 [ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)で宣言された代替メッセージマップを使用するには、を渡し `msgMapID` ます。

*hWndParent*<br/>
から親ウィンドウまたはオーナーウィンドウへのハンドル。

*rect*<br/>
からウィンドウの位置を指定する [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体。 は、 `RECT` ポインターによって、または参照渡しで渡すことができます。

*szWindowName*<br/>
からウィンドウの名前を指定します。 既定値は NULL です。

*dwStyle*<br/>
からウィンドウのスタイル。 既定値は WS_VISIBLE &#124; WS_CHILD です。 使用可能な値の一覧については、Windows SDK の「 [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) 」を参照してください。

*dwExStyle*<br/>
から拡張ウィンドウスタイル。 既定値は0で、拡張スタイルはありません。 使用可能な値の一覧については、Windows SDK の「 [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) 」を参照してください。

*MenuOrID*<br/>
から子ウィンドウの場合は、ウィンドウ識別子。 トップレベルウィンドウの場合は、ウィンドウのメニューハンドル。 既定値は **0u** です。

*lpCreateParam*<br/>
からウィンドウ作成データへのポインター。 詳細については、 [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)の最後のパラメーターの説明を参照してください。

### <a name="return-value"></a>戻り値

成功した場合は、新しく作成されたウィンドウへのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

既存のウィンドウクラス名は [m_lpszClassName](#m_lpszclassname)に保存されます。 `Create` 次に、この新しいクラスに基づいてウィンドウを作成します。 新しく作成されたウィンドウは、自動的にオブジェクトにアタッチされ `CContainedWindowT` ます。

> [!NOTE]
> `Create`既に[SubclassWindow](#subclasswindow)を呼び出している場合は、を呼び出さないでください。

> [!NOTE]
> 0を *Menuorid* パラメーターの値として使用する場合は、コンパイラエラーを回避するために、0u (既定値) として指定する必要があります。

## <a name="ccontainedwindowtdefwindowproc"></a><a name="defwindowproc"></a> CContainedWindowT::D efWindowProc

[WindowProc](#windowproc)によって呼び出され、メッセージマップによって処理されないメッセージを処理します。

```
LRESULT DefWindowProc()
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
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

既定では、は `DefWindowProc` [CallWindowProc](/windows/win32/api/winuser/nf-winuser-callwindowprocw) Win32 関数を呼び出して、メッセージ情報を [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)で指定されたウィンドウプロシージャに送信します。

## <a name="ccontainedwindowtgetcurrentmessage"></a><a name="getcurrentmessage"></a> CContainedWindowT:: GetCurrentMessage

現在のメッセージ () を返し `m_pCurrentMsg` ます。

```
const _ATL_MSG* GetCurrentMessage();
```

### <a name="return-value"></a>戻り値

構造体にパッケージ化されている現在のメッセージ `MSG` 。

## <a name="ccontainedwindowtm_dwmsgmapid"></a><a name="m_dwmsgmapid"></a> CContainedWindowT:: m_dwMsgMapID

含まれているウィンドウに現在使用されているメッセージマップの識別子を保持します。

```
DWORD m_dwMsgMapID;
```

### <a name="remarks"></a>解説

このメッセージマップは、含んでいるオブジェクトで宣言されている必要があります。

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)で宣言された既定のメッセージマップは、常に0によって識別されます。 [ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)で宣言された代替メッセージマップは、によって識別され `msgMapID` ます。

`m_dwMsgMapID` はコンストラクターによって最初に初期化され、 [SwitchMessageMap](#switchmessagemap)を呼び出すことによって変更できます。 例については、「 [CContainedWindowT の概要](../../atl/reference/ccontainedwindowt-class.md)」を参照してください。

## <a name="ccontainedwindowtm_lpszclassname"></a><a name="m_lpszclassname"></a> CContainedWindowT:: m_lpszClassName

既存のウィンドウクラスの名前を指定します。

```
LPTSTR m_lpszClassName;
```

### <a name="remarks"></a>解説

ウィンドウを作成すると、この既存のクラスに基づく新しいウィンドウクラス [が登録さ](#create) れますが、 [CContainedWindowT:: WindowProc](#windowproc)が使用されます。

`m_lpszClassName` は、コンストラクターによって初期化されます。 例については、「 [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) の概要」を参照してください。

## <a name="ccontainedwindowtm_pfnsuperwindowproc"></a><a name="m_pfnsuperwindowproc"></a> CContainedWindowT:: m_pfnSuperWindowProc

含まれているウィンドウがサブクラス化されている場合、は `m_pfnSuperWindowProc` ウィンドウクラスの元のウィンドウプロシージャを指します。

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>解説

格納されているウィンドウがスーパークラスである場合は、既存のクラスを変更するウィンドウクラスに基づいていることを意味します。これは、 `m_pfnSuperWindowProc` 既存のウィンドウクラスのウィンドウプロシージャを指します。

[DefWindowProc](#defwindowproc)メソッドは、に保存されているウィンドウプロシージャにメッセージ情報を送信し `m_pfnSuperWindowProc` ます。

## <a name="ccontainedwindowtm_pobject"></a><a name="m_pobject"></a> CContainedWindowT:: m_pObject

オブジェクトを格納しているオブジェクトを指し `CContainedWindowT` ます。

```
CMessageMap* m_pObject;
```

### <a name="remarks"></a>解説

このコンテナーは、クラスが [CMessageMap](../../atl/reference/cmessagemap-class.md)から派生する必要があり、包含ウィンドウによって使用されるメッセージマップを宣言します。

`m_pObject` は、コンストラクターによって初期化されます。 例については、「 [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) の概要」を参照してください。

## <a name="ccontainedwindowtregisterwndsuperclass"></a><a name="registerwndsuperclass"></a> CContainedWindowT::RegisterWndSuperclass

格納されているウィンドウのウィンドウクラスを登録するために、 [Create](#create) によって呼び出されます。

```
ATOM RegisterWndSuperClass();
```

### <a name="return-value"></a>戻り値

成功した場合は、登録されているウィンドウクラスを一意に識別する atom。それ以外の場合は0。

### <a name="remarks"></a>解説

このウィンドウクラスは、既存のクラスに基づいていますが、 [CContainedWindowT:: WindowProc](#windowproc)を使用します。 既存のウィンドウクラスの名前とウィンドウプロシージャは、それぞれ [m_lpszClassName](#m_lpszclassname) と [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)に保存されます。

## <a name="ccontainedwindowtsubclasswindow"></a><a name="subclasswindow"></a> CContainedWindowT::SubclassWindow

*HWnd* によって識別されるウィンドウをサブクラス化し、オブジェクトにアタッチし `CContainedWindowT` ます。

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
からサブクラス化されているウィンドウへのハンドル。

### <a name="return-value"></a>戻り値

ウィンドウが正常にサブクラス化された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

サブクラス化されたウィンドウで [CContainedWindowT:: WindowProc](#windowproc)が使用されるようになりました。 元のウィンドウプロシージャは [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)に保存されます。

> [!NOTE]
> `SubclassWindow`既に[Create](#create)を呼び出している場合は、を呼び出さないでください。

## <a name="ccontainedwindowtswitchmessagemap"></a><a name="switchmessagemap"></a> CContainedWindowT::SwitchMessageMap

格納されているウィンドウのメッセージを処理するために使用されるメッセージマップを変更します。

```cpp
void SwitchMessageMap(DWORD dwMsgMapID);
```

### <a name="parameters"></a>パラメーター

*dwMsgMapID*<br/>
からメッセージマップの識別子。 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)で宣言された既定のメッセージマップを使用するには、0を渡します。 [ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)で宣言された代替メッセージマップを使用するには、を渡し `msgMapID` ます。

### <a name="remarks"></a>解説

メッセージマップは、含んでいるオブジェクトで定義されている必要があります。

最初に、コンストラクターでメッセージマップの識別子を指定します。

## <a name="ccontainedwindowtunsubclasswindow"></a><a name="unsubclasswindow"></a> CContainedWindowT::UnsubclassWindow

サブクラスウィンドウをオブジェクトからデタッチ `CContainedWindowT` し、 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)に保存された元のウィンドウプロシージャを復元します。

```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```

### <a name="parameters"></a>パラメーター

*bForce*<br/>
からこのオブジェクトのウィンドウプロシージャが現在アクティブでない場合でも、元のウィンドウプロシージャを強制的に復元するには、TRUE に設定し `CContainedWindowT` ます。 *Bforce* が FALSE に設定されていて、このオブジェクトのウィンドウプロシージャ `CContainedWindowT` が現在アクティブになっていない場合、元のウィンドウプロシージャは復元されません。

### <a name="return-value"></a>戻り値

以前にサブクラス化されたウィンドウへのハンドル。 *Bforce* が FALSE に設定され、このオブジェクトのウィンドウプロシージャ `CContainedWindowT` が現在アクティブでない場合、は NULL を返します。

### <a name="remarks"></a>解説

このメソッドは、ウィンドウが破棄される前に元のウィンドウプロシージャを復元する場合にのみ使用します。 それ以外の場合、 [WindowProc](#windowproc) はウィンドウが破棄されると自動的にこれを実行します。

## <a name="ccontainedwindowtwindowproc"></a><a name="windowproc"></a> CContainedWindowT:: WindowProc

この静的メソッドは、ウィンドウプロシージャを実装します。

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

`WindowProc`[m_dwMsgMapID](#m_dwmsgmapid)によって識別されるメッセージマップにメッセージを送信します。 必要に応じ `WindowProc` て、 [DefWindowProc](#defwindowproc) を呼び出して、追加のメッセージ処理を行います。

## <a name="see-also"></a>関連項目

[CWindow クラス](../../atl/reference/cwindow-class.md)<br/>
[CWindowImpl クラス](../../atl/reference/cwindowimpl-class.md)<br/>
[CMessageMap クラス](../../atl/reference/cmessagemap-class.md)<br/>
[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
