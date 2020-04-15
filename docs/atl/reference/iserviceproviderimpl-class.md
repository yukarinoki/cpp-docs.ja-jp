---
title: クラスを提供します。
ms.date: 11/04/2016
f1_keywords:
- IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl::QueryService
helpviewer_keywords:
- IServiceProviderImpl class
- IServiceProvider interface, ATL implementation
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
ms.openlocfilehash: ef0ee4f77441cb8d19ea2d6dcada1fed9faf2782
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329426"
---
# <a name="iserviceproviderimpl-class"></a>クラスを提供します。

このクラスは、インターフェイスの既定の`IServiceProvider`実装を提供します。

## <a name="syntax"></a>構文

```
template <class T>
class ATL_NO_VTABLE IServiceProviderImpl : public IServiceProvider
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`IServiceProviderImpl`。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[サービスプロバイダーインプル::クエリサービス](#queryservice)|指定したサービスを作成またはアクセスし、サービスの指定されたインターフェイスへのインターフェイス ポインターを返します。|

## <a name="remarks"></a>解説

インターフェイス`IServiceProvider`は、GUID で指定されたサービスを検索し、サービスで要求されたインターフェイスのインターフェイス ポインターを返します。 クラス`IServiceProviderImpl`は、このインターフェイスの既定の実装を提供します。

`IServiceProviderImpl`1 つのメソッドを指定します: [QueryService](#queryservice)は、指定されたサービスを作成またはアクセスし、サービスの指定されたインターフェイスへのインターフェイス ポインターを返します。

`IServiceProviderImpl`は、サービス マップを使用して[、BEGIN_SERVICE_MAP](service-map-macros.md#begin_service_map)から始まり[、END_SERVICE_MAP](service-map-macros.md#end_service_map)で終わります。

サービス マップには、オブジェクトでサポートされている指定されたサービス ID (SID) を示す[SERVICE_ENTRY](service-map-macros.md#service_entry)と、別`QueryService`のオブジェクトへのチェーンを呼び出す[SERVICE_ENTRY_CHAIN](service-map-macros.md#service_entry_chain)の 2 つのエントリが含まれています。

## <a name="inheritance-hierarchy"></a>継承階層

`IServiceProvider`

`IServiceProviderImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

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

[クラスの概要](../../atl/atl-class-overview.md)
