---
description: '詳細情報: IServiceProviderImpl クラス'
title: IServiceProviderImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl::QueryService
helpviewer_keywords:
- IServiceProviderImpl class
- IServiceProvider interface, ATL implementation
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
ms.openlocfilehash: 0cd9fab784fe8bffe420123129aa51c80c187890
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139153"
---
# <a name="iserviceproviderimpl-class"></a>IServiceProviderImpl クラス

このクラスは、インターフェイスの既定の実装を提供 `IServiceProvider` します。

## <a name="syntax"></a>構文

```
template <class T>
class ATL_NO_VTABLE IServiceProviderImpl : public IServiceProvider
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IServiceProviderImpl` 。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IServiceProviderImpl:: QueryService](#queryservice)|指定されたサービスを作成またはアクセスし、指定されたサービスのインターフェイスへのインターフェイスポインターを返します。|

## <a name="remarks"></a>解説

インターフェイスは、 `IServiceProvider` GUID によって指定されたサービスを検索し、サービスで要求されたインターフェイスのインターフェイスポインターを返します。 クラス `IServiceProviderImpl` は、このインターフェイスの既定の実装を提供します。

`IServiceProviderImpl` 1つのメソッドを指定します。 [QueryService](#queryservice)は、指定されたサービスを作成またはアクセスし、サービスの指定されたインターフェイスへのインターフェイスポインターを返します。

`IServiceProviderImpl` では、 [BEGIN_SERVICE_MAP](service-map-macros.md#begin_service_map) で始まり、 [END_SERVICE_MAP](service-map-macros.md#end_service_map)で終了するサービスマップを使用します。

サービスマップには、 [SERVICE_ENTRY](service-map-macros.md#service_entry)という2つのエントリが含まれています。これは、オブジェクトによってサポートされる指定されたサービス ID (SID) を示し、 [SERVICE_ENTRY_CHAIN](service-map-macros.md#service_entry_chain)を呼び出して `QueryService` 別のオブジェクトへのチェーンを呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

`IServiceProvider`

`IServiceProviderImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="iserviceproviderimplqueryservice"></a><a name="queryservice"></a> IServiceProviderImpl:: QueryService

指定されたサービスを作成またはアクセスし、指定されたサービスのインターフェイスへのインターフェイスポインターを返します。

```
STDMETHOD(QueryService)(
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*guidService*<br/>
からサービス識別子 (SID) へのポインター。

*riid*<br/>
から呼び出し元がアクセスを取得するインターフェイスの識別子。

*ppvObj*<br/>
入出力要求されたインターフェイスへの間接ポインター。

### <a name="return-value"></a>戻り値

返される HRESULT 値は、次のいずれかになります。

|戻り値|説明|
|------------------|-------------|
|S_OK|サービスが正常に作成または取得されました。|
|E_INVALIDARG|1 つ以上の引数が無効です。|
|E_OUTOFMEMORY|サービスを作成するにはメモリが不足しています。|
|E_UNEXPECTED|不明なエラーが発生しました。|
|E_NOINTERFACE|要求されたインターフェイスは、このサービスの一部ではないか、サービスが不明です。|

### <a name="remarks"></a>解説

`QueryService` 指定されたサービス内の要求されたインターフェイスへの間接ポインターを返します。 呼び出し元は、不要になったときにこのポインターを解放する必要があります。

を呼び出すと `QueryService` 、サービス識別子 (*guidservice*) とインターフェイス識別子 (*riid*) の両方が渡されます。 *Guidservice* は、アクセスするサービスを指定します。また、 *riid* は、サービスの一部であるインターフェイスを識別します。 返されると、インターフェイスへの間接ポインターを受け取ります。

インターフェイスを実装するオブジェクトは、他のサービスの一部であるインターフェイスも実装する場合があります。 以下、具体例に沿って説明します。

- これらのインターフェイスには、省略可能なものもあります。 サービスの説明で定義されているすべてのインターフェイスは、サービスのすべての実装または返されたすべてのオブジェクトに存在するとは限りません。

- の呼び出しとは異なり `QueryInterface` 、異なるサービス識別子を渡すことは、必ずしも別のコンポーネントオブジェクトモデル (COM) オブジェクトが返されることを意味するわけではありません。

- 返されるオブジェクトには、サービスの定義の一部ではない追加のインターフェイスが含まれている場合があります。

SID_SMyService や SID_SYourService などの2つの異なるサービスでは、どちらも同じインターフェイスの使用を指定できます。ただし、インターフェイスの実装には、2つのサービス間で共通するものがない場合もあります。 これは、 `QueryService` (SID_SMyService、IID_IDispatch) の呼び出しでは、 `QueryService` (SID_SYourService、IID_IDispatch) とは異なるオブジェクトを返す可能性があるためです。 別のサービス識別子を指定した場合、オブジェクト id は想定されません。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
