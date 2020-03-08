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
ms.openlocfilehash: 0d5991dcbf79d1c2415594636a09908586d1dc2f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78864743"
---
# <a name="caxwindow2t-class"></a>CAxWindow2T クラス

このクラスは、ActiveX コントロールをホストするウィンドウを操作するためのメソッドを提供します。また、ライセンスされた ActiveX コントロールのホストもサポートしています。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```

#### <a name="parameters"></a>パラメーター

*TBase*<br/>
`CAxWindowT` の派生元のクラス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|説明|
|----------|-----------------|
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|`CAxWindow2T` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[CAxWindow2T:: Create](#create)|ホストウィンドウを作成します。|
|[CAxWindow2T::CreateControlLic](#createcontrollic)|ライセンスされた ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。|
|[CAxWindow2T::CreateControlLicEx](#createcontrollicex)|ライセンスされた ActiveX コントロールを作成して初期化し、指定したウィンドウでホストし、インターフェイスポインター (またはポインター) をコントロールから取得します。|
|[CAxWindow2T::GetWndClassName](#getwndclassname)|ウィンドウクラスの名前を取得する静的メソッド。|

### <a name="public-operators"></a>パブリック演算子

|Name|説明|
|----------|-----------------|
|[CAxWindow2T:: operator =](#operator_eq)|既存の `CAxWindow2T` オブジェクトに HWND を割り当てます。|

## <a name="remarks"></a>コメント

`CAxWindow2T` には、ActiveX コントロールをホストするウィンドウを操作するためのメソッドが用意されています。 `CAxWindow2T` は、ライセンスされた ActiveX コントロールのホストもサポートしています。 ホスティングは、`CAxWindow2T`によってラップされる " **AtlAxWinLic80**" によって提供されます。

クラス `CAxWindow2` は、`CAxWindow2T` クラスの特殊化として実装されます。 この特殊化は次のように宣言されます。

`typedef CAxWindow2T <CWindow> CAxWindow2;`

> [!NOTE]
> `CAxWindowT` のメンバーについては、 [CAxWindow](../../atl/reference/caxwindow-class.md)に記載されています。

このクラスのメンバーを使用するサンプルについては、「 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/hosting-activex-controls-using-atl-axhost.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`TBase`

`CAxWindowT`

`CAxWindow2T`

## <a name="requirements"></a>要件

**ヘッダー:** atlwin. h

##  <a name="caxwindow2t"></a>CAxWindow2T::CAxWindow2T

`CAxWindow2T` オブジェクトを構築します。

```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
既存のウィンドウのハンドル。

##  <a name="create"></a>CAxWindow2T:: Create

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

### <a name="remarks"></a>コメント

`CAxWindow2T::Create` は、LPCTSTR *lpstrWndClass*パラメーターを、コントロールのホスト (`AtlAxWinLic80`) を提供するウィンドウクラスに設定して[CWindow:: Create](../../atl/reference/cwindow-class.md#create)を呼び出します。

パラメーターと戻り値の説明については、「`CWindow::Create`」を参照してください。

**メモ**0を*Menuorid*パラメーターの値として使用する場合は、コンパイラエラーを回避するために、0u (既定値) として指定する必要があります。

### <a name="example"></a>例

`CAxWindow2T::Create`を使用するサンプルについては、「 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/hosting-activex-controls-using-atl-axhost.md)」を参照してください。

##  <a name="createcontrollic"></a>CAxWindow2T::CreateControlLic

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

### <a name="remarks"></a>コメント

残りのパラメーターと戻り値の説明については、「 [CAxWindow:: CreateControl](../../atl/reference/caxwindow-class.md#createcontrol) 」を参照してください。

### <a name="example"></a>例

`CAxWindow2T::CreateControlLic`を使用するサンプルについては、「 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/hosting-activex-controls-using-atl-axhost.md)」を参照してください。

##  <a name="createcontrollicex"></a>CAxWindow2T::CreateControlLicEx

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

### <a name="remarks"></a>コメント

残りのパラメーターと戻り値の説明については、「 [CAxWindow:: CreateControlEx](../../atl/reference/caxwindow-class.md#createcontrolex) 」を参照してください。

### <a name="example"></a>例

`CAxWindow2T::CreateControlLicEx`を使用するサンプルについては、「 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/hosting-activex-controls-using-atl-axhost.md)」を参照してください。

##  <a name="getwndclassname"></a>CAxWindow2T::GetWndClassName

ウィンドウクラスの名前を取得します。

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>戻り値

ライセンスおよび nonlicensed ActiveX コントロールをホストできるウィンドウクラス (`AtlAxWinLic80`) の名前を格納している文字列へのポインター。

##  <a name="operator_eq"></a>CAxWindow2T:: operator =

既存の `CAxWindow2T` オブジェクトに HWND を割り当てます。

```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
既存のウィンドウのハンドル。

## <a name="see-also"></a>参照

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[コントロールコンテインメントに関する FAQ](../../atl/atl-control-containment-faq.md)
