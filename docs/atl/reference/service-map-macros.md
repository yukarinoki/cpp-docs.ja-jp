---
title: サービス マップ マクロ
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_SERVICE_MAP
- atlcom/ATL::END_SERVICE_MAP
- atlcom/ATL::SERVICE_ENTRY
- atlcom/ATL::SERVICE_ENTRY_CHAIN
ms.assetid: ca02a125-454a-4cf6-aac2-1c5585025ed4
ms.openlocfilehash: eb2fe41c79135a7ac2ced9bc3242b070170716b9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325942"
---
# <a name="service-map-macros"></a>サービス マップ マクロ

これらのマクロは、サービス マップとエントリを定義します。

|||
|-|-|
|[BEGIN_SERVICE_MAP](#begin_service_map)|ATL サービス マップの先頭を示します。|
|[END_SERVICE_MAP](#end_service_map)|ATL サービス マップの終わりを示します。|
|[SERVICE_ENTRY](#service_entry)|オブジェクトが特定のサービス ID をサポートすることを示します。|
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|指定したオブジェクトにチェーンするように[IServiceProviderImpl::クエリサービス](#queryservice)に指示します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="begin_service_map"></a><a name="begin_service_map"></a>BEGIN_SERVICE_MAP

サービス マップの先頭を示します。

```
BEGIN_SERVICE_MAP(theClass)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
[in]サービス マップを含むクラスを指定します。

### <a name="remarks"></a>解説

サービス マップを使用して、COM オブジェクトにサービス プロバイダ機能を実装します。 まず、クラスを[IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md)から派生させる必要があります。 エントリには、次の 2 種類があります。

- [SERVICE_ENTRY](#service_entry)  指定されたサービス ID (SID) のサポートを示します。

- [SERVICE_ENTRY_CHAIN](#service_entry_chain)  指定した別のオブジェクトにチェーンするように[IServiceProviderImpl::QueryService](#queryservice)に指示します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#57](../../atl/codesnippet/cpp/service-map-macros_1.h)]

## <a name="end_service_map"></a><a name="end_service_map"></a>END_SERVICE_MAP

サービス マップの終わりを示します。

```
END_SERVICE_MAP()
```

### <a name="example"></a>例

[BEGIN_SERVICE_MAP](#begin_service_map)の例を参照してください。

## <a name="service_entry"></a><a name="service_entry"></a>SERVICE_ENTRY

オブジェクトが*SID*で指定されたサービス ID をサポートすることを示します。

```
SERVICE_ENTRY( SID )
```

### <a name="parameters"></a>パラメーター

*Sid*<br/>
サービス ID。

### <a name="example"></a>例

[BEGIN_SERVICE_MAP](#begin_service_map)の例を参照してください。

## <a name="service_entry_chain"></a><a name="service_entry_chain"></a>SERVICE_ENTRY_CHAIN

*パンク*で指定されたオブジェクトにチェーンするように[IServiceProviderImpl::クエリサービス](#queryservice)に指示します。

```
SERVICE_ENTRY_CHAIN( punk )
```

### <a name="parameters"></a>パラメーター

*パンク*<br/>
チェーンする**IUnknown**インターフェイスへのポインター。

### <a name="example"></a>例

[BEGIN_SERVICE_MAP](#begin_service_map)の例を参照してください。

## <a name="iserviceproviderimplqueryservice"></a><a name="queryservice"></a>サービスプロバイダーインプル::クエリサービス

指定したサービスを作成またはアクセスし、サービスの指定されたインターフェイスへのインターフェイス ポインターを返します。

```
STDMETHOD(QueryService)(
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*サービス*<br/>
[in]サービス識別子 (SID) へのポインター。

*riid*<br/>
[in]呼び出し元がアクセスを取得するインターフェイスの識別子。

*Ppvobj*<br/>
[アウト]要求されたインターフェイスへの間接ポインター。

### <a name="return-value"></a>戻り値

返される HRESULT 値は、次のいずれかです。

|戻り値|意味|
|------------------|-------------|
|S_OK|サービスが正常に作成または取得されました。|
|E_INVALIDARG|1 つ以上の引数が無効です。|
|E_OUTOFMEMORY|メモリ不足のため、サービスを作成できませんでした。|
|E_UNEXPECTED|不明なエラーが発生しました。|
|E_NOINTERFACE|要求されたインターフェイスがこのサービスの一部ではないか、またはサービスが不明です。|

### <a name="remarks"></a>解説

`QueryService`指定されたサービス内の要求されたインターフェイスへの間接ポインターを返します。 呼び出し元は、不要になった場合にこのポインターを解放する必要があります。

を呼び`QueryService`出すときは、サービス識別子 (*guidService*) とインターフェイス識別子 (*riid*) の両方を渡します。 *guidService*は、アクセスするサービスを指定し *、riid*は、サービスの一部であるインターフェイスを識別します。 その代わりに、インターフェイスへの間接ポインターを受け取ります。

インターフェイスを実装するオブジェクトは、他のサービスの一部であるインターフェイスも実装する場合があります。 以下、具体例に沿って説明します。

- これらのインターフェイスの一部は省略可能な場合があります。 サービスの説明で定義されているすべてのインターフェイスが、サービスのすべての実装または返されたすべてのオブジェクトに必ずしも存在するとは限りません。

- の`QueryInterface`呼び出しとは異なり、異なるサービス識別子を渡しても、必ずしも別のコンポーネント オブジェクト モデル (COM) オブジェクトが返されるとは限りません。

- 返されるオブジェクトには、サービスの定義の一部ではない追加のインターフェイスが含まれている場合があります。

SID_SMyServiceとSID_SYourServiceなど、2 つの異なるサービスは、インターフェイスの実装に共通点がない場合でも、同じインターフェイスの使用を指定できます。 これは、(SID_SMyService、IID_IDispatch)`QueryService`の呼び出しが (SID_SYourService、IID_IDispatch) とは`QueryService`異なるオブジェクトを返すことができるため、機能します。 異なるサービス ID を指定する場合、オブジェクト ID は想定されません。

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)
