---
title: クラスを含む
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
ms.openlocfilehash: 7b89346bbc62cdda808b193a199fdf121f052ebb
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747749"
---
# <a name="ccontainedwindowt-class"></a>クラスを含む

このクラスは、別のオブジェクトに含まれるウィンドウを実装します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class TBase = CWindow, class TWinTraits = CControlWinTraits>
class CContainedWindowT : public TBase
```

#### <a name="parameters"></a>パラメーター

*Tベース*<br/>
新しいクラスの基本クラス。 既定の基本クラスは`CWindow`です。

*Tウィントレイツ*<br/>
ウィンドウのスタイルを定義する特徴クラス。 既定では、 `CControlWinTraits`です。

> [!NOTE]
> [の](ccontainedwindowt-class.md)特化されたウィンドウです`CContainedWindowT`。 基本クラスまたは特性を変更する場合は、直接使用`CContainedWindowT`します。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ウィンドウを含む](#ccontainedwindowt)|コンストラクターです。 データ メンバーを初期化して、含まれているウィンドウのメッセージを処理するメッセージ マップを指定します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ウィンドウ::作成](#create)|ウィンドウを作成します。|
|[をクリック :Dします。](#defwindowproc)|既定のメッセージ処理を提供します。|
|[ウィンドウをクリックします。](#getcurrentmessage)|現在のメッセージを返します。|
|[ウィンドウ::レジスタオーンドスーパークラス](#registerwndsuperclass)|含まれているウィンドウのウィンドウ クラスを登録します。|
|[ウィンドウを含む:サブクラス ウィンドウ](#subclasswindow)|ウィンドウをサブクラス化します。|
|[ウィンドウ::スイッチメッセージマップ](#switchmessagemap)|含まれているウィンドウのメッセージを処理するために使用されるメッセージ マップを変更します。|
|[ウィンドウをクリックします。](#unsubclasswindow)|前にサブクラス化されたウィンドウを復元します。|
|[ウィンドウを開封します。](#windowproc)|(静的)含まれているウィンドウに送信されたメッセージを処理します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ウィンドウト::m_dwMsgMapID](#m_dwmsgmapid)|含まれているウィンドウのメッセージを処理するメッセージ マップを識別します。|
|[ウィンドウ::m_lpszClassName](#m_lpszclassname)|新しいウィンドウ クラスの基になる既存のウィンドウ クラスの名前を指定します。|
|[ウィンドウト:m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|ウィンドウ クラスの元のウィンドウ プロシージャをポイントします。|
|[ウィンドウト::m_pObject](#m_pobject)|格納しているオブジェクトへのポイント。|

## <a name="remarks"></a>解説

`CContainedWindowT`は、別のオブジェクトに含まれるウィンドウを実装します。 `CContainedWindowT`'s のウィンドウ プロシージャは、メッセージを適切なハンドラーに送信するために、含まれているオブジェクト内のメッセージ マップを使用します。 オブジェクトを`CContainedWindowT`構築する際には、使用するメッセージ マップを指定します。

`CContainedWindowT`を使用すると、既存のウィンドウ クラスをスーパークラス化して新しいウィンドウを作成できます。 この`Create`メソッドは、まず既存のクラスに基づいているが、 を使用`CContainedWindowT::WindowProc`するウィンドウ クラスを登録します。 `Create`この新しいウィンドウ クラスに基づいてウィンドウを作成します。 の各インスタンス`CContainedWindowT`は、異なるウィンドウ クラスをスーパークラス化できます。

`CContainedWindowT` は、ウィンドウのサブクラス化もサポートします。 `SubclassWindow` メソッドは、既存のウィンドウを `CContainedWindowT` オブジェクトにアタッチし、ウィンドウ プロシージャを `CContainedWindowT::WindowProc` に変更します。 `CContainedWindowT` の各インスタンスは、別のウィンドウをサブクラス化できます。

> [!NOTE]
> 任意`CContainedWindowT`のオブジェクトに対して、 `Create` `SubclassWindow`または を呼び出します。 同じオブジェクトに対して両方のメソッドを呼び出す必要はありません。

ATL プロジェクト ウィザードで [**コントロールの追加**基準] オプションを使用すると、ウィザードは`CContainedWindowT`コントロールを実装するクラスにデータ メンバを自動的に追加します。 次の例は、包含ウィンドウの宣言方法を示しています。

[!code-cpp[NVC_ATL_Windowing#38](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]

[!code-cpp[NVC_ATL_Windowing#39](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]

[!code-cpp[NVC_ATL_Windowing#40](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]

|詳細情報|参照先|
|--------------------------------|---------|
|コントロールの作成|[ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)|
|ATL でのウィンドウの使用|[ATL ウィンドウ クラス](../../atl/atl-window-classes.md)|
|ATL プロジェクト ウィザード|[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)|
|Windows|[Windows](/windows/win32/winmsg/windows) SDK のウィンドウとその後のトピック|

## <a name="inheritance-hierarchy"></a>継承階層

`TBase`

`CContainedWindowT`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="ccontainedwindowtccontainedwindowt"></a><a name="ccontainedwindowt"></a>ウィンドウを含む

コンストラクターは、データ メンバーを初期化します。

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

*クラス名*<br/>
[in]含まれているウィンドウが基になる既存のウィンドウ クラスの名前。

*pObject*<br/>
[in]メッセージ マップを宣言する、格納しているオブジェクトへのポインター。 このオブジェクトのクラスは[、CMessageMap](../../atl/reference/cmessagemap-class.md)から派生する必要があります。

*を使用します。*<br/>
[in]含まれているウィンドウのメッセージを処理するメッセージ マップを識別します。 既定値の 0 は[、BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)で宣言された既定のメッセージ マップを指定します。 [ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)で宣言された代替メッセージ マップを`msgMapID`使用するには、 を渡します。

### <a name="remarks"></a>解説

[Create](#create)を使用して新しいウィンドウを作成する場合は *、lpszClassName*パラメーターに既存のウィンドウ クラスの名前を渡す必要があります。 例については[、CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)の概要を参照してください。

コンストラクタは3つあります。

- 引数が 3 つあるコンストラクターは、通常呼び出されます。

- 引数が 2 つ付けられたコンストラクターでは`TBase::GetWndClassName`、 のクラス名を使用します。

- 引数を指定しないコンストラクターは、後で引数を指定する場合に使用されます。 後で 呼び出`Create`すときは、ウィンドウ クラス名、メッセージ マップ オブジェクト、およびメッセージ マップ ID を指定する必要があります。

サブクラス ウィンドウを使用して既存のウィンドウをサブ[クラス](#subclasswindow)化する場合*は、lpszClassName*値は使用されません。したがって、このパラメーターに NULL を渡すことができます。

## <a name="ccontainedwindowtcreate"></a><a name="create"></a>ウィンドウ::作成

既存のクラスに基づいているが[、CContainedWindowT::ウィンドウプロセッサ](#windowproc)を使用するウィンドウ クラスを登録するために[RegisterWndSuper クラス](#registerwndsuperclass)を呼び出します。

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

*クラス名*<br/>
[in]含まれているウィンドウが基になる既存のウィンドウ クラスの名前。

*pObject*<br/>
[in]メッセージ マップを宣言する、格納しているオブジェクトへのポインター。 このオブジェクトのクラスは[、CMessageMap](../../atl/reference/cmessagemap-class.md)から派生する必要があります。

*を使用します。*<br/>
[in]含まれているウィンドウのメッセージを処理するメッセージ マップを識別します。 既定値の 0 は[、BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)で宣言された既定のメッセージ マップを指定します。 [ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)で宣言された代替メッセージ マップを`msgMapID`使用するには、 を渡します。

*スーンドペアレント*<br/>
[in]親ウィンドウまたはオーナー ウィンドウへのハンドル。

*Rect*<br/>
[in]ウィンドウの位置を指定する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体。 は`RECT`、ポインターまたは参照によって渡すことができます。

*ウィンドウ名*<br/>
[in]ウィンドウの名前を指定します。 既定値は NULL です。

*Dwstyle*<br/>
[in]ウィンドウのスタイル。 デフォルト値は&#124;WS_VISIBLEWS_CHILD。 使用可能な値の一覧については、Windows SDK[の「ウィンドウの作成](/windows/win32/api/winuser/nf-winuser-createwindoww)」を参照してください。

*ドウェエクススタイル*<br/>
[in]拡張ウィンドウ スタイル。 既定値は 0 で、拡張スタイルがないことを意味します。 使用可能な値の一覧については、Windows SDK[の「ウィンドウエクスックスの作成](/windows/win32/api/winuser/nf-winuser-createwindowexw)」を参照してください。

*メニューオイド*<br/>
[in]子ウィンドウの場合は、ウィンドウ識別子。 トップレベル ウィンドウの場合は、ウィンドウのメニュー ハンドル。 デフォルト値は**0U**です。

*を作成します。*<br/>
[in]ウィンドウ作成データへのポインター。 詳細については、 [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)の最終パラメータの説明を参照してください。

### <a name="return-value"></a>戻り値

正常に終了した場合は、新しく作成されたウィンドウへのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

既存のウィンドウ クラス名は[、 m_lpszClassName](#m_lpszclassname)に保存されます。 `Create`この新しいクラスに基づいてウィンドウを作成します。 新しく作成されたウィンドウは、オブジェクトに`CContainedWindowT`自動的にアタッチされます。

> [!NOTE]
> 既に`Create`[SubclassWindow](#subclasswindow)を呼び出している場合は呼び出しません。

> [!NOTE]
> *MenuOrID*パラメーターの値として 0 を使用する場合は、コンパイラ エラーを回避するために 0U (既定値) を指定する必要があります。

## <a name="ccontainedwindowtdefwindowproc"></a><a name="defwindowproc"></a>をクリック :Dします。

メッセージ マップで処理されないメッセージを処理するために[、WindowProc](#windowproc)によって呼び出されます。

```
LRESULT DefWindowProc()
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
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

## <a name="ccontainedwindowtgetcurrentmessage"></a><a name="getcurrentmessage"></a>ウィンドウをクリックします。

現在のメッセージ (`m_pCurrentMsg`) を返します。

```
const _ATL_MSG* GetCurrentMessage();
```

### <a name="return-value"></a>戻り値

構造体にパッケージ化された現在の`MSG`メッセージ。

## <a name="ccontainedwindowtm_dwmsgmapid"></a><a name="m_dwmsgmapid"></a>ウィンドウト::m_dwMsgMapID

現在、包含ウィンドウで使用されているメッセージ マップの識別子を保持します。

```
DWORD m_dwMsgMapID;
```

### <a name="remarks"></a>解説

このメッセージ マップは、格納するオブジェクトで宣言する必要があります。

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)で宣言されたデフォルトのメッセージ・マップは、常にゼロで識別されます。 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)で宣言された代替メッセージ・マップは、`msgMapID`によって識別されます。

`m_dwMsgMapID`は最初にコンストラクタによって初期化され[、SwitchMessageMap](#switchmessagemap)を呼び出すことによって変更できます。 例については[、「CContainedWindowT の概要](../../atl/reference/ccontainedwindowt-class.md)」を参照してください。

## <a name="ccontainedwindowtm_lpszclassname"></a><a name="m_lpszclassname"></a>ウィンドウ::m_lpszClassName

既存のウィンドウ クラスの名前を指定します。

```
LPTSTR m_lpszClassName;
```

### <a name="remarks"></a>解説

ウィンドウを作成すると[、Create](#create)は、この既存のクラスに基づいているが[、CContainedWindowT::ウィンドウプロを](#windowproc)使用する新しいウィンドウ クラスを登録します。

`m_lpszClassName`は、コンストラクターによって初期化されます。 例については[、CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)の概要を参照してください。

## <a name="ccontainedwindowtm_pfnsuperwindowproc"></a><a name="m_pfnsuperwindowproc"></a>ウィンドウト:m_pfnSuperWindowProc

含まれているウィンドウがサブクラス化されている場合`m_pfnSuperWindowProc`は、ウィンドウ クラスの元のウィンドウ プロシージャを指します。

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>解説

含まれているウィンドウがスーパークラス化されている場合、つまり、既存のクラスを変更するウィンドウ クラスに基づいている`m_pfnSuperWindowProc`場合は、既存のウィンドウ クラスのウィンドウ プロシージャを指します。

[DefWindowProc](#defwindowproc)メソッドは、に保存されているウィンドウ プロシージャに`m_pfnSuperWindowProc`メッセージ情報を送信します。

## <a name="ccontainedwindowtm_pobject"></a><a name="m_pobject"></a>ウィンドウト::m_pObject

オブジェクトを含むオブジェクトへの`CContainedWindowT`ポイント。

```
CMessageMap* m_pObject;
```

### <a name="remarks"></a>解説

このコンテナは、クラスが[CMessageMap](../../atl/reference/cmessagemap-class.md)から派生する必要があります。

`m_pObject`は、コンストラクターによって初期化されます。 例については[、CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)の概要を参照してください。

## <a name="ccontainedwindowtregisterwndsuperclass"></a><a name="registerwndsuperclass"></a>ウィンドウ::レジスタオーンドスーパークラス

格納されているウィンドウのウィンドウ クラスを登録するために[Create](#create)によって呼び出されます。

```
ATOM RegisterWndSuperClass();
```

### <a name="return-value"></a>戻り値

成功した場合は、登録されているウィンドウ クラスを一意に識別するアトム。それ以外の場合は、ゼロ。

### <a name="remarks"></a>解説

このウィンドウ クラスは、既存のクラスに基づいていますが[、CContainedWindowT::ウィンドウプロシージャを](#windowproc)使用します。 既存のウィンドウ クラスの名前とウィンドウ プロシージャは、それぞれ[m_lpszClassName](#m_lpszclassname)と[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)に保存されます。

## <a name="ccontainedwindowtsubclasswindow"></a><a name="subclasswindow"></a>ウィンドウを含む:サブクラス ウィンドウ

*hWnd*で識別されるウィンドウをサブクラス化し、オブジェクト`CContainedWindowT`にアタッチします。

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
[in]サブクラス化されるウィンドウへのハンドル。

### <a name="return-value"></a>戻り値

ウィンドウが正常にサブクラス化された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

サブクラス化されたウィンドウで[、CContainedWindowT::ウィンドウプロシージャが](#windowproc)使用されるようになりました。 元のウィンドウ プロシージャは[、 m_pfnSuperWindowProc](#m_pfnsuperwindowproc)に保存されます。

> [!NOTE]
> 既に`SubclassWindow`[Create](#create)を呼び出している場合は、呼び出しを行いません。

## <a name="ccontainedwindowtswitchmessagemap"></a><a name="switchmessagemap"></a>ウィンドウ::スイッチメッセージマップ

含まれているウィンドウのメッセージを処理するために使用されるメッセージ マップを変更します。

```cpp
void SwitchMessageMap(DWORD dwMsgMapID);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
[in]メッセージ マップ識別子。 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)で宣言された既定のメッセージ マップを使用するには、0 を渡します。 [ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)で宣言された代替メッセージ マップを`msgMapID`使用するには、 を渡します。

### <a name="remarks"></a>解説

メッセージ マップは、含まれるオブジェクトで定義する必要があります。

最初は、メッセージ マップ識別子をコンストラクターで指定します。

## <a name="ccontainedwindowtunsubclasswindow"></a><a name="unsubclasswindow"></a>ウィンドウをクリックします。

サブクラス化されたウィンドウを`CContainedWindowT`オブジェクトから切り離し、元のウィンドウ プロシージャを[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)に保存します。

```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```

### <a name="parameters"></a>パラメーター

*bフォース*<br/>
[in]TRUE に設定すると、この`CContainedWindowT`オブジェクトのウィンドウ プロシージャが現在アクティブでない場合でも、元のウィンドウ プロシージャが強制的に復元されます。 *bForce*が FALSE に設定され、この`CContainedWindowT`オブジェクトのウィンドウプロシージャが現在アクティブでない場合、元のウィンドウプロシージャは復元されません。

### <a name="return-value"></a>戻り値

以前にサブクラス化されたウィンドウへのハンドル。 *bForce*が FALSE に設定され、この`CContainedWindowT`オブジェクトのウィンドウ プロシージャが現在アクティブでない場合は、NULL を返します。

### <a name="remarks"></a>解説

このメソッドは、ウィンドウが破棄される前に元のウィンドウ プロシージャを復元する場合にのみ使用します。 それ以外の場合、ウィンドウが破棄されると[、WindowProc](#windowproc)は自動的にこれを実行します。

## <a name="ccontainedwindowtwindowproc"></a><a name="windowproc"></a>ウィンドウを開封します。

この静的メソッドは、ウィンドウ プロシージャを実装します。

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

`WindowProc`m_dwMsgMapIDで識別されるメッセージ マップにメッセージ[を](#m_dwmsgmapid)送信します。 必要に応`WindowProc`じて、追加のメッセージ処理を行うための[DefWindowProc](#defwindowproc)を呼び出します。

## <a name="see-also"></a>関連項目

[Cウィンドウクラス](../../atl/reference/cwindow-class.md)<br/>
[クラス](../../atl/reference/cwindowimpl-class.md)<br/>
[クラス](../../atl/reference/cmessagemap-class.md)<br/>
[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[ALT_MSG_MAP(メッセージマップID)](message-map-macros-atl.md#alt_msg_map)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
