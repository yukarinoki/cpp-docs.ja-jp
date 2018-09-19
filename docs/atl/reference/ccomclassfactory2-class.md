---
title: CComClassFactory2 クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComClassFactory2
- ATLCOM/ATL::CComClassFactory2
- ATLCOM/ATL::CComClassFactory2::CreateInstance
- ATLCOM/ATL::CComClassFactory2::CreateInstanceLic
- ATLCOM/ATL::CComClassFactory2::GetLicInfo
- ATLCOM/ATL::CComClassFactory2::LockServer
- ATLCOM/ATL::CComClassFactory2::RequestLicKey
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactory2 class
ms.assetid: 19b66fd6-b9ed-47a0-822c-8132184f5a3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 05fcef5ee1141de8261bc4ecc813cd573fb8f901
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099506"
---
# <a name="ccomclassfactory2-class"></a>CComClassFactory2 クラス

このクラスは、実装、 [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2)インターフェイス。

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
|[CComClassFactory2::CreateInstance](#createinstance)|指定した CLSID のオブジェクトを作成します。|
|[CComClassFactory2::CreateInstanceLic](#createinstancelic)|ライセンス キーを指定した CLSID のオブジェクトを作成します。|
|[CComClassFactory2::GetLicInfo](#getlicinfo)|クラス ファクトリのライセンスの機能を説明する情報を取得します。|
|[CComClassFactory2::LockServer](#lockserver)|メモリ内のクラス ファクトリをロックします。|
|[CComClassFactory2::RequestLicKey](#requestlickey)|作成して、ライセンス キーを返します。|

## <a name="remarks"></a>Remarks

`CComClassFactory2` 実装して、 [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2)インターフェイスで、拡張機能の[IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory)します。 `IClassFactory2` コントロール オブジェクトのライセンスで作成します。 ライセンスされたコンピューターで実行するクラス ファクトリと、実行時のライセンス キーを提供できます。 このライセンス キーにより、完全なマシンのライセンスが存在しない場合は、オブジェクトをインスタンス化するアプリケーションです。

ATL オブジェクトから派生することによって、クラス ファクトリを取得する通常[CComCoClass](../../atl/reference/ccomcoclass-class.md)します。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)、宣言する[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 使用する`CComClassFactory2`、指定、 [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2)オブジェクトのクラス定義でマクロ。 例えば:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]

`CMyLicense`、テンプレート パラメーターを`CComClassFactory2`、静的関数を実装する必要があります`VerifyLicenseKey`、 `GetLicenseKey`、および`IsLicenseValid`します。 単純なライセンス クラスの例を次に示します。

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]

`CComClassFactory2` 両方から派生した`CComClassFactory2Base`と*ライセンス*します。 `CComClassFactory2Base`、から派生、`IClassFactory2`と`CComObjectRootEx< CComGlobalsThreadModel >`します。

## <a name="inheritance-hierarchy"></a>継承階層

`CComObjectRootBase`

`license`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory2`

`CComClassFactory2`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom.h

##  <a name="createinstance"></a>  CComClassFactory2::CreateInstance

指定した CLSID のオブジェクトを作成し、このオブジェクトへのインターフェイス ポインターを取得します。

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```

### <a name="parameters"></a>パラメーター

*pUnkOuter*<br/>
[in]かどうか、オブジェクトがの作成、集計の一部として、 *pUnkOuter*不明な外部にある必要があります。 それ以外の場合、 *pUnkOuter* NULL にする必要があります。

*riid*<br/>
[in]要求されたインターフェイスの IID。 場合*pUnkOuter* NULL 以外の場合は、 *riid*あります`IID_IUnknown`します。

*ppvObj*<br/>
[out]によって識別されるインターフェイス ポインターへのポインター *riid*します。 オブジェクトは、このインターフェイスをサポートしていない場合*ppvObj* NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

完全にライセンスを取得するマシンが必要です。 完全なマシンのライセンスが存在しない場合は、呼び出す[コントロール](#createinstancelic)します。

##  <a name="createinstancelic"></a>  CComClassFactory2::CreateInstanceLic

ような[CreateInstance](#createinstance)ことを除いて、`CreateInstanceLic`ライセンス キーが必要です。

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

*pUnkOuter*<br/>
[in]かどうか、オブジェクトがの作成、集計の一部として、 *pUnkOuter*不明な外部にある必要があります。 それ以外の場合、 *pUnkOuter* NULL にする必要があります。

*pUnkReserved*<br/>
[in]使用されません。 NULL にする必要があります。

*riid*<br/>
[in]要求されたインターフェイスの IID。 場合*pUnkOuter* NULL 以外の場合は、 *riid*あります`IID_IUnknown`します。

*bstrKey*<br/>
[in]ランタイム ライセンス キーが以前の呼び出しから取得した`RequestLicKey`します。 オブジェクトを作成するには、このキーが必要です。

*ppvObject*<br/>
[out]指定されたインターフェイス ポインターへのポインター *riid*します。 オブジェクトは、このインターフェイスをサポートしていない場合*ppvObject* NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ライセンス キーを使用して、取得できます[RequestLicKey](#requestlickey)します。 ライセンスのないマシン上でオブジェクトを作成するために呼び出す必要がある`CreateInstanceLic`します。

##  <a name="getlicinfo"></a>  CComClassFactory2::GetLicInfo

入力、 [LICINFO](/windows/desktop/api/ocidl/ns-ocidl-taglicinfo)クラス ファクトリを記述する情報の構造体の機能のライセンスします。

```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```

### <a name="parameters"></a>パラメーター

*pLicInfo*<br/>
[out]ポインター、`LICINFO`構造体。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

`fRuntimeKeyAvail`この構造体のメンバーができるかどうか、ライセンス キーを指定するには、クラス ファクトリ オブジェクトを許可されていないコンピューターで作成することを示します。 *FLicVerified*メンバーは、完全なマシンのライセンスが存在するかどうかを示します。

##  <a name="lockserver"></a>  CComClassFactory2::LockServer

インクリメントおよびデクリメントはモジュールのロックを呼び出すことによってカウント`_Module::Lock`と`_Module::Unlock`、それぞれします。

```
STDMETHOD(LockServer)(BOOL fLock);
```

### <a name="parameters"></a>パラメーター

*群れ*<br/>
[in]TRUE の場合、ロック数がインクリメントされます。それ以外の場合、ロック数は減少します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

`_Module` グローバル インスタンスを指す[CComModule](../../atl/reference/ccommodule-class.md)またはその派生クラス。

呼び出す`LockServer`により、クライアントは複数のオブジェクトをすばやく作成できるように、クラス ファクトリを保持します。

##  <a name="requestlickey"></a>  CComClassFactory2::RequestLicKey

作成しているライセンス キーを返します、`fRuntimeKeyAvail`のメンバー、 [LICINFO](/windows/desktop/api/ocidl/ns-ocidl-taglicinfo)構造は TRUE になります。

```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```

### <a name="parameters"></a>パラメーター

*dwReserved*<br/>
[in]使用されません。 ゼロを指定してください。

*pbstrKey*<br/>
[out]ライセンス キーへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ライセンス キーが呼び出し元に必要な[コントロール](#createinstancelic)ライセンスのないマシン上でオブジェクトを作成します。 場合`fRuntimeKeyAvail`が FALSE の場合、オブジェクトは、完全にライセンスされたコンピューターでのみ作成できます。

呼び出す[GetLicInfo](#getlicinfo)の値を取得する`fRuntimeKeyAvail`します。

## <a name="see-also"></a>関連項目

[CComClassFactoryAutoThread クラス](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[CComClassFactorySingleton クラス](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
