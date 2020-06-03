---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CComClassFactory2
- ATLCOM/ATL::CComClassFactory2
- ATLCOM/ATL::CComClassFactory2::CreateInstance
- ATLCOM/ATL::CComClassFactory2::CreateInstanceLic
- ATLCOM/ATL::CComClassFactory2::GetLicInfo
- ATLCOM/ATL::CComClassFactory2::LockServer
- ATLCOM/ATL::CComClassFactory2::RequestLicKey
helpviewer_keywords:
- CComClassFactory2 class
ms.assetid: 19b66fd6-b9ed-47a0-822c-8132184f5a3e
ms.openlocfilehash: 0cb2064cfaea6317c4522ff917f3963fca2219b8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321012"
---
# <a name="ccomclassfactory2-class"></a>クラス

このクラスは[、IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2)インターフェイスを実装します。

## <a name="syntax"></a>構文

```
template <class license>
class CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

#### <a name="parameters"></a>パラメーター

*ライセンス*<br/>
次の静的関数を実装するクラス。

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[2::インスタンスの作成](#createinstance)|指定した CLSID のオブジェクトを作成します。|
|[2::インスタンスリックを作成します。](#createinstancelic)|ライセンス キーを指定すると、指定された CLSID のオブジェクトが作成されます。|
|[クラスファクトリー2::ゲットリックインフォ](#getlicinfo)|クラス ファクトリのライセンス機能を説明する情報を取得します。|
|[2::ロックサーバー](#lockserver)|クラス ファクトリをメモリ内でロックします。|
|[2::リクエストリックキー](#requestlickey)|ライセンス キーを作成して返します。|

## <a name="remarks"></a>解説

`CComClassFactory2`[は、IClassFactory](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2)の拡張機能である[IClassFactory2](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)インターフェイスを実装します。 `IClassFactory2`ライセンスを使用してオブジェクトの作成を制御します。 ライセンスを受けたマシンで実行されるクラス ファクトリは、実行時のライセンス キーを提供できます。 このライセンス キーを使用すると、フル マシン ライセンスが存在しない場合に、アプリケーションでオブジェクトをインスタンス化できます。

ATL オブジェクトは、通常[、CComCoClass](../../atl/reference/ccomcoclass-class.md)から派生することによってクラス ファクトリを取得します。 このクラスには[、CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を既定のクラス ファクトリとして宣言するマクロ[DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)が含まれます。 を使用`CComClassFactory2`するには、オブジェクトのクラス定義で[DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2)マクロを指定します。 次に例を示します。

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]

`CMyLicense`の`CComClassFactory2`テンプレート パラメータは、 、 、`VerifyLicenseKey``GetLicenseKey`および`IsLicenseValid`静的関数を実装する必要があります。 次に、単純なライセンス クラスの例を示します。

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]

`CComClassFactory2`と ライセンス`CComClassFactory2Base`の*license*両方から派生します。 `CComClassFactory2Base`を取得すると、 と`IClassFactory2``CComObjectRootEx< CComGlobalsThreadModel >`から派生します。

## <a name="inheritance-hierarchy"></a>継承階層

`CComObjectRootBase`

`license`

[ココムオブジェクトルート](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory2`

`CComClassFactory2`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ccomclassfactory2createinstance"></a><a name="createinstance"></a>2::インスタンスの作成

指定した CLSID のオブジェクトを作成し、このオブジェクトへのインターフェイス ポインターを取得します。

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```

### <a name="parameters"></a>パラメーター

*プンクアウター*<br/>
[in]オブジェクトが集約の一部として作成される場合 *、pUnkOuter*は外部不明である必要があります。 それ以外の場合は *、pUnkOuter*は NULL である必要があります。

*riid*<br/>
[in]要求されたインターフェイスの IID。 *pUnkOuter*が NULL 以外の場合は *、riid*を指定する必要があります`IID_IUnknown`。

*Ppvobj*<br/>
[アウト]*riid*によって識別されるインターフェイス ポインターへのポインター。 オブジェクトがこのインターフェイスをサポートしていない場合 *、ppvObj*は NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

マシンのライセンスを完全に取得する必要があります。 フル マシン ライセンスが存在しない場合は[、CreateInstanceLic](#createinstancelic)を呼び出します。

## <a name="ccomclassfactory2createinstancelic"></a><a name="createinstancelic"></a>2::インスタンスリックを作成します。

[CreateInstance](#createinstance)と同様ですが、`CreateInstanceLic`ライセンス キーが必要です。

```
STDMETHOD(CreateInstanceLic)(
    IUnknown* pUnkOuter,
    IUnknown* /* pUnkReserved
*/,
    REFIID riid,
    BSTR bstrKey,
    void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*プンクアウター*<br/>
[in]オブジェクトが集約の一部として作成される場合 *、pUnkOuter*は外部不明である必要があります。 それ以外の場合は *、pUnkOuter*は NULL である必要があります。

*pUnk予約済み*<br/>
[in]使用されていません。 NULL にする必要があります

*riid*<br/>
[in]要求されたインターフェイスの IID。 *pUnkOuter*が NULL 以外の場合は *、riid*を指定する必要があります`IID_IUnknown`。

*をクリックします。*<br/>
[in]の呼び出しから以前に取得されたランタイム`RequestLicKey`ライセンス キー。 このキーは、オブジェクトを作成するために必要です。

*オブジェクト*<br/>
[アウト]*riid*で指定されたインターフェイス ポインターへのポインター。 オブジェクトがこのインターフェイスをサポートしていない場合 *、ppvObject*は NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ライセンス キーは[、RequestLicKey](#requestlickey)を使用して取得できます。 ライセンスのないマシン上にオブジェクトを作成するには、 を呼び出す`CreateInstanceLic`必要があります。

## <a name="ccomclassfactory2getlicinfo"></a><a name="getlicinfo"></a>クラスファクトリー2::ゲットリックインフォ

クラス ファクトリのライセンス機能を説明する情報を[LICINFO](/windows/win32/api/ocidl/ns-ocidl-licinfo)構造体に入力します。

```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[アウト]`LICINFO`構造体へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

この`fRuntimeKeyAvail`構造体のメンバーは、ライセンス キーを指定すると、クラス ファクトリがライセンスのないコンピュータでオブジェクトを作成できるかどうかを示します。 *fLicVerified*メンバーは、フル マシン ライセンスが存在するかどうかを示します。

## <a name="ccomclassfactory2lockserver"></a><a name="lockserver"></a>2::ロックサーバー

モジュールのロックカウントをそれぞれ、 と を呼び`_Module::Lock`出`_Module::Unlock`して、インクリメントとデクリメントします。

```
STDMETHOD(LockServer)(BOOL fLock);
```

### <a name="parameters"></a>パラメーター

*群れ*<br/>
[in]TRUE の場合、ロックカウントはインクリメントされます。それ以外の場合、ロックカウントは減少します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

`_Module`[CComModule](../../atl/reference/ccommodule-class.md)のグローバル インスタンス、またはそこから派生したクラスを指します。

呼`LockServer`び出しを使用すると、クライアントはクラス ファクトリを保持できるため、複数のオブジェクトを迅速に作成できます。

## <a name="ccomclassfactory2requestlickey"></a><a name="requestlickey"></a>2::リクエストリックキー

`fRuntimeKeyAvail` [LICINFO](/windows/win32/api/ocidl/ns-ocidl-licinfo)構造体のメンバーが TRUE である場合、ライセンス キーを作成して返します。

```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```

### <a name="parameters"></a>パラメーター

*dw予約済み*<br/>
[in]使用されていません。 ゼロを指定してください。

*pbstrキー*<br/>
[アウト]ライセンス キーへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ライセンス キーは[、CreateInstanceLic](#createinstancelic)を呼び出して、ライセンスのないコンピュータ上にオブジェクトを作成するために必要です。 FALSE`fRuntimeKeyAvail`の場合、オブジェクトは完全にライセンスされたマシン上でのみ作成できます。

の値を取得するために[GetLicInfo](#getlicinfo)を呼び出`fRuntimeKeyAvail`します。

## <a name="see-also"></a>関連項目

[クラスクラス](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[シングルトンクラス](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[クラス](../../atl/reference/ccomobjectrootex-class.md)<br/>
[スレッドモデル](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
