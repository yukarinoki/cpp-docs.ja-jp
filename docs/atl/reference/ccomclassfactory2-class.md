---
description: '詳細情報: CComClassFactory2 クラス'
title: CComClassFactory2 クラス
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
ms.openlocfilehash: 7aebf09616c7fc4e85f6c44aee4db84886033f8b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146888"
---
# <a name="ccomclassfactory2-class"></a>CComClassFactory2 クラス

このクラスは、 [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) インターフェイスを実装します。

## <a name="syntax"></a>構文

```
template <class license>
class CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

#### <a name="parameters"></a>パラメーター

*使用*<br/>
次の静的関数を実装するクラス。

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComClassFactory2:: CreateInstance](#createinstance)|指定された CLSID のオブジェクトを作成します。|
|[CComClassFactory2::CreateInstanceLic](#createinstancelic)|ライセンスキーを指定すると、指定した CLSID のオブジェクトが作成されます。|
|[CComClassFactory2:: Get Info](#getlicinfo)|クラスファクトリのライセンス機能について説明する情報を取得します。|
|[CComClassFactory2:: LockServer](#lockserver)|メモリ内のクラスファクトリをロックします。|
|[CComClassFactory2:: Requestのキー](#requestlickey)|ライセンスキーを作成して返します。|

## <a name="remarks"></a>解説

`CComClassFactory2`[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)の拡張である[IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2)インターフェイスを実装します。 `IClassFactory2` ライセンスによってオブジェクトの作成を制御します。 ライセンスされたコンピューターで実行されるクラスファクトリは、実行時ライセンスキーを提供できます。 このライセンスキーを使用すると、アプリケーションは、完全なコンピューターライセンスが存在しない場合にオブジェクトをインスタンス化できます。

ATL オブジェクトは通常、 [CComCoClass](../../atl/reference/ccomcoclass-class.md)から派生することによってクラスファクトリを取得します。 このクラスには、 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を既定のクラスファクトリとして宣言するマクロ[DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)が含まれています。 を使用するには `CComClassFactory2` 、オブジェクトのクラス定義で [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) マクロを指定します。 次に例を示します。

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]

`CMyLicense`のテンプレートパラメーターは、 `CComClassFactory2` 静的関数、、およびを実装する必要があり `VerifyLicenseKey` `GetLicenseKey` `IsLicenseValid` ます。 単純なライセンスクラスの例を次に示します。

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]

`CComClassFactory2` との両方 `CComClassFactory2Base` の *ライセンス* から派生します。 `CComClassFactory2Base`さらに、は、およびから派生し `IClassFactory2` `CComObjectRootEx< CComGlobalsThreadModel >` ます。

## <a name="inheritance-hierarchy"></a>継承階層

`CComObjectRootBase`

`license`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory2`

`CComClassFactory2`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="ccomclassfactory2createinstance"></a><a name="createinstance"></a> CComClassFactory2:: CreateInstance

指定した CLSID のオブジェクトを作成し、このオブジェクトへのインターフェイスポインターを取得します。

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```

### <a name="parameters"></a>パラメーター

*pUnkOuter*<br/>
からオブジェクトが集計の一部として作成されている場合、 *pUnkOuter* は外側の unknown である必要があります。 それ以外の場合、 *pUnkOuter* は NULL である必要があります。

*riid*<br/>
から要求されたインターフェイスの IID。 *PUnkOuter* が NULL 以外の場合、 *riid* はである必要があり `IID_IUnknown` ます。

*ppvObj*<br/>
入出力 *Riid* によって識別されるインターフェイスポインターへのポインター。 オブジェクトがこのインターフェイスをサポートしていない場合、 *ppvObj* は NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

コンピューターに完全にライセンスを付与する必要があります。 完全なコンピューターライセンスが存在しない場合は、 [CreateInstanceLic](#createinstancelic)を呼び出します。

## <a name="ccomclassfactory2createinstancelic"></a><a name="createinstancelic"></a> CComClassFactory2::CreateInstanceLic

には、ライセンスキーが必要な点を除いて、 [CreateInstance](#createinstance)と似て `CreateInstanceLic` います。

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
からオブジェクトが集計の一部として作成されている場合、 *pUnkOuter* は外側の unknown である必要があります。 それ以外の場合、 *pUnkOuter* は NULL である必要があります。

*pUnkReserved*<br/>
から使用しません。 NULL にする必要があります

*riid*<br/>
から要求されたインターフェイスの IID。 *PUnkOuter* が NULL 以外の場合、 *riid* はである必要があり `IID_IUnknown` ます。

*bstrKey*<br/>
から以前にを呼び出したときに取得したランタイムライセンスキー `RequestLicKey` 。 このキーは、オブジェクトを作成するために必要です。

*ppvObject*<br/>
入出力 *Riid* によって指定されたインターフェイスポインターへのポインター。 オブジェクトがこのインターフェイスをサポートしていない場合、 *ppvObject* は NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

[Requestのキー](#requestlickey)を使用してライセンスキーを取得できます。 ライセンスされていないコンピューター上にオブジェクトを作成するには、を呼び出す必要があり `CreateInstanceLic` ます。

## <a name="ccomclassfactory2getlicinfo"></a><a name="getlicinfo"></a> CComClassFactory2:: Get Info

は、クラスファクトリのライセンス機能を説明する情報を使用し [て、登録](/windows/win32/api/ocidl/ns-ocidl-licinfo) されている情報を格納します。

```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```

### <a name="parameters"></a>パラメーター

*pLicInfo*<br/>
入出力構造体へのポインター `LICINFO` 。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

`fRuntimeKeyAvail`この構造体のメンバーは、ライセンスキーが指定されているかどうかを示します。これは、クラスファクトリが、ライセンスされていないコンピューター上でオブジェクトを作成できるかどうかを示します。 *FLicVerified* メンバーは、完全なコンピューターライセンスが存在するかどうかを示します。

## <a name="ccomclassfactory2lockserver"></a><a name="lockserver"></a> CComClassFactory2:: LockServer

とをそれぞれ呼び出して、モジュールのロックカウントをインクリメントおよびデクリメントし `_Module::Lock` `_Module::Unlock` ます。

```
STDMETHOD(LockServer)(BOOL fLock);
```

### <a name="parameters"></a>パラメーター

*fLock*<br/>
からTRUE の場合、ロック数がインクリメントされます。それ以外の場合は、ロック数が減少します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

`_Module`[CComModule](../../atl/reference/ccommodule-class.md)のグローバルインスタンス、またはそれから派生したクラスを参照します。

を呼び出すこと `LockServer` で、クライアントは、複数のオブジェクトをすばやく作成できるように、クラスファクトリに保持できます。

## <a name="ccomclassfactory2requestlickey"></a><a name="requestlickey"></a> CComClassFactory2:: Requestのキー

ライセンスキーを作成して返します。このとき、使用している場合は、そのメンバーが TRUE であることを示し `fRuntimeKeyAvail` ます。 [](/windows/win32/api/ocidl/ns-ocidl-licinfo)

```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```

### <a name="parameters"></a>パラメーター

*dwReserved*<br/>
から使用しません。 ゼロを指定してください。

*pbstrKey*<br/>
入出力ライセンスキーへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

[CreateInstanceLic](#createinstancelic)を呼び出して、ライセンスされていないコンピューターにオブジェクトを作成するには、ライセンスキーが必要です。 `fRuntimeKeyAvail`が FALSE の場合、オブジェクトは完全にライセンスされたコンピューター上でのみ作成できます。

[Get/info](#getlicinfo)を呼び出して、の値を取得 `fRuntimeKeyAvail` します。

## <a name="see-also"></a>関連項目

[CComClassFactoryAutoThread クラス](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[CComClassFactorySingleton クラス](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
