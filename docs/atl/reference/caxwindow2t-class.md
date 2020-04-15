---
title: クラス
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
ms.openlocfilehash: 14080b624132979df533135bc1eef108dc793398
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318699"
---
# <a name="caxwindow2t-class"></a>クラス

このクラスは、ActiveX コントロールをホストするウィンドウを操作するためのメソッドを提供し、ライセンスを取得した ActiveX コントロールのホストもサポートします。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```

#### <a name="parameters"></a>パラメーター

*Tベース*<br/>
派生元の`CAxWindowT`クラス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|`CAxWindow2T` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAxWindow2T::作成](#create)|ホスト ウィンドウを作成します。|
|[CAxWindow2T::コントロールコントロールリックの作成](#createcontrollic)|ライセンスされた ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。|
|[CAxWindow2T::コントロールレックスを作成します。](#createcontrollicex)|ライセンスを取得した ActiveX コントロールを作成し、初期化し、指定されたウィンドウでホストし、コントロールからインターフェイス ポインター (またはポインター) を取得します。|
|[クラス名を取得します。](#getwndclassname)|ウィンドウ クラスの名前を取得する静的メソッド。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CAxWindow2T::演算子 =](#operator_eq)|HWND を既存`CAxWindow2T`のオブジェクトに割り当てます。|

## <a name="remarks"></a>解説

`CAxWindow2T`には、ActiveX コントロールをホストするウィンドウを操作するためのメソッドが用意されています。 `CAxWindow2T`また、ライセンスを取得した ActiveX コントロールのホストもサポートされています。 ホスティングは、 によってラップされる " **AtlAxWinLic80**"`CAxWindow2T`によって提供されます。

クラス`CAxWindow2`はクラスの特殊化として実装されます`CAxWindow2T`。 この特殊化は、次のように宣言されています。

`typedef CAxWindow2T <CWindow> CAxWindow2;`

> [!NOTE]
> `CAxWindowT`メンバーは[CAxWindow](../../atl/reference/caxwindow-class.md)の下に文書化されています。

このクラス[のメンバーを使用するサンプルについては、「ATL AXHost を使用した ActiveX コントロールのホスティング](../../atl/hosting-activex-controls-using-atl-axhost.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`TBase`

`CAxWindowT`

`CAxWindow2T`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="caxwindow2tcaxwindow2t"></a><a name="caxwindow2t"></a>CAxWindow2T::CAxWindow2T

`CAxWindow2T` オブジェクトを構築します。

```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
既存のウィンドウのハンドル。

## <a name="caxwindow2tcreate"></a><a name="create"></a>CAxWindow2T::作成

ホスト ウィンドウを作成します。

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

`CAxWindow2T::Create`呼び出し[CWindow::コントロール](../../atl/reference/cwindow-class.md#create)ホスティングを提供するウィンドウ クラスに設定された LPCTSTR *lpstrWndClass*パラメーターを使用して作成 (`AtlAxWinLic80`) を呼び出します。

パラメーター`CWindow::Create`と戻り値の説明については、「」を参照してください。

**注***MenuOrID*パラメーターの値として 0 を使用する場合は、コンパイラ エラーを回避するために 0U (既定値) を指定する必要があります。

### <a name="example"></a>例

を使用するサンプルについては[、ATL AXHost を使用した ActiveX コントロールのホスティング](../../atl/hosting-activex-controls-using-atl-axhost.md)を参照`CAxWindow2T::Create`してください。

## <a name="caxwindow2tcreatecontrollic"></a><a name="createcontrollic"></a>CAxWindow2T::コントロールコントロールリックの作成

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

*をクリックします。*<br/>
コントロールのライセンス キー。非ライセンス コントロールを作成する場合は NULL。

### <a name="remarks"></a>解説

残りのパラメーターと戻り値の説明については[、CAxWindow::CreateControl](../../atl/reference/caxwindow-class.md#createcontrol)を参照してください。

### <a name="example"></a>例

を使用するサンプルについては[、ATL AXHost を使用した ActiveX コントロールのホスティング](../../atl/hosting-activex-controls-using-atl-axhost.md)を参照`CAxWindow2T::CreateControlLic`してください。

## <a name="caxwindow2tcreatecontrollicex"></a><a name="createcontrollicex"></a>CAxWindow2T::コントロールレックスを作成します。

ライセンスを取得した ActiveX コントロールを作成し、初期化し、指定されたウィンドウでホストし、コントロールからインターフェイス ポインター (またはポインター) を取得します。

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

*をクリックします。*<br/>
コントロールのライセンス キー。非ライセンス コントロールを作成する場合は NULL。

### <a name="remarks"></a>解説

残りのパラメーターと戻り値の説明については[、CAxWindow::CreateControlEx](../../atl/reference/caxwindow-class.md#createcontrolex)を参照してください。

### <a name="example"></a>例

を使用するサンプルについては[、ATL AXHost を使用した ActiveX コントロールのホスティング](../../atl/hosting-activex-controls-using-atl-axhost.md)を参照`CAxWindow2T::CreateControlLicEx`してください。

## <a name="caxwindow2tgetwndclassname"></a><a name="getwndclassname"></a>クラス名を取得します。

ウィンドウ クラスの名前を取得します。

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>戻り値

ライセンスを受けた ActiveX コントロールとライセンスされていない`AtlAxWinLic80`ActiveX コントロールをホストできるウィンドウ クラス ( ) の名前を含む文字列へのポインター。

## <a name="caxwindow2toperator-"></a><a name="operator_eq"></a>CAxWindow2T::演算子 =

HWND を既存`CAxWindow2T`のオブジェクトに割り当てます。

```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
既存のウィンドウのハンドル。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[コントロール コンテインメント : Q &amp; A 集](../../atl/atl-control-containment-faq.md)
