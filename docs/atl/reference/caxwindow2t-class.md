---
title: CAxWindow2T クラス
ms.date: 11/04/2016
f1_keywords:
- CAxWindow2T
- ATLWIN/ATL::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::Create
- ATLWIN/ATL::CAxWindow2T::CreateControlLic
- ATLWIN/ATL::CAxWindow2T::CreateControlLicEx
- ATLWIN/ATL::CAxWindow2T::GetWndClassName
helpviewer_keywords:
- CAxWindow2 class
ms.assetid: b87bc943-7991-4537-b902-2138d7f4d837
ms.openlocfilehash: e29c30e95116ad68d3498f3f8d3231a63c92c0a7
ms.sourcegitcommit: d9c94dcabd94537e304be0261b3263c2071b437b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2020
ms.locfileid: "91353065"
---
# <a name="caxwindow2t-class"></a>CAxWindow2T クラス

このクラスは、ActiveX コントロールをホストするウィンドウを操作するためのメソッドを提供します。また、ライセンスされた ActiveX コントロールのホストもサポートしています。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```

#### <a name="parameters"></a>パラメーター

*TBase*<br/>
の派生元のクラス `CAxWindowT` 。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|`CAxWindow2T` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAxWindow2T:: Create](#create)|ホストウィンドウを作成します。|
|[CAxWindow2T::CreateControlLic](#createcontrollic)|ライセンスされた ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。|
|[CAxWindow2T::CreateControlLicEx](#createcontrollicex)|ライセンスされた ActiveX コントロールを作成して初期化し、指定したウィンドウでホストし、インターフェイスポインター (またはポインター) をコントロールから取得します。|
|[CAxWindow2T::GetWndClassName](#getwndclassname)|ウィンドウクラスの名前を取得する静的メソッド。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CAxWindow2T:: operator =](#operator_eq)|HWND を既存のオブジェクトに割り当て `CAxWindow2T` ます。|

## <a name="remarks"></a>解説

`CAxWindow2T` ActiveX コントロールをホストするウィンドウを操作するためのメソッドを提供します。 `CAxWindow2T` では、ライセンスされた ActiveX コントロールのホストもサポートされています。 ホスティングは、によってラップされる " **AtlAxWinLic80**" によって提供され `CAxWindow2T` ます。

クラス `CAxWindow2` は、クラスの特殊化として実装され `CAxWindow2T` ます。 この特殊化は次のように宣言されます。

`typedef CAxWindow2T <CWindow> CAxWindow2;`

> [!NOTE]
> `CAxWindowT` メンバーは、 [CAxWindow](../../atl/reference/caxwindow-class.md)の下に記載されています。

このクラスのメンバーを使用するサンプルについては、「 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) 」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`TBase`

`CAxWindowT`

`CAxWindow2T`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin. h

## <a name="caxwindow2tcaxwindow2t"></a><a name="caxwindow2t"></a> CAxWindow2T::CAxWindow2T

`CAxWindow2T` オブジェクトを構築します。

```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
既存のウィンドウのハンドル。

## <a name="caxwindow2tcreate"></a><a name="create"></a> CAxWindow2T:: Create

ホストウィンドウを作成します。

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

### <a name="remarks"></a>解説

`CAxWindow2T::Create`コントロールをホストする () を提供するウィンドウクラスに設定された LPCTSTR *lpstrWndClass*パラメーターを使用して[CWindow:: Create](../../atl/reference/cwindow-class.md#create)を呼び出し `AtlAxWinLic80` ます。

`CWindow::Create`パラメーターと戻り値の説明については、「」を参照してください。

**メモ** 0を *Menuorid* パラメーターの値として使用する場合は、コンパイラエラーを回避するために、0u (既定値) として指定する必要があります。

### <a name="example"></a>例

を使用するサンプルについては、「 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) 」を参照してください `CAxWindow2T::Create` 。

## <a name="caxwindow2tcreatecontrollic"></a><a name="createcontrollic"></a> CAxWindow2T::CreateControlLic

ライセンスされた ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。

```
HRESULT CreateControlLic(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);

HRESULT CreateControlLic(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);
```

### <a name="parameters"></a>パラメーター

*Bstrのキー*<br/>
コントロールのライセンスキー。Nonlicensed コントロールを作成する場合は NULL です。

### <a name="remarks"></a>解説

残りのパラメーターと戻り値の説明については、「 [CAxWindow:: CreateControl](../../atl/reference/caxwindow-class.md#createcontrol) 」を参照してください。

### <a name="example"></a>例

を使用するサンプルについては、「 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) 」を参照してください `CAxWindow2T::CreateControlLic` 。

## <a name="caxwindow2tcreatecontrollicex"></a><a name="createcontrollicex"></a> CAxWindow2T::CreateControlLicEx

ライセンスされた ActiveX コントロールを作成して初期化し、指定したウィンドウでホストし、インターフェイスポインター (またはポインター) をコントロールから取得します。

```
HRESULT CreateControlLicEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLicKey = NULL);

    HRESULT CreateControlLicEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLickey = NULL);
```

### <a name="parameters"></a>パラメーター

*Bstrのキー*<br/>
コントロールのライセンスキー。Nonlicensed コントロールを作成する場合は NULL です。

### <a name="remarks"></a>解説

残りのパラメーターと戻り値の説明については、「 [CAxWindow:: CreateControlEx](../../atl/reference/caxwindow-class.md#createcontrolex) 」を参照してください。

### <a name="example"></a>例

を使用するサンプルについては、「 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) 」を参照してください `CAxWindow2T::CreateControlLicEx` 。

## <a name="caxwindow2tgetwndclassname"></a><a name="getwndclassname"></a> CAxWindow2T::GetWndClassName

ウィンドウクラスの名前を取得します。

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>戻り値

`AtlAxWinLic80`ライセンスおよび Nonlicensed ActiveX コントロールをホストできるウィンドウクラス () の名前を格納している文字列へのポインター。

## <a name="caxwindow2toperator-"></a><a name="operator_eq"></a> CAxWindow2T:: operator =

HWND を既存のオブジェクトに割り当て `CAxWindow2T` ます。

```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
既存のウィンドウのハンドル。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[コントロール コンテインメント : Q &amp; A 集](../../atl/atl-control-containment-faq.md)
