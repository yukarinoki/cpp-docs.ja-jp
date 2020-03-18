---
title: Service Map マクロ
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_SERVICE_MAP
- atlcom/ATL::END_SERVICE_MAP
- atlcom/ATL::SERVICE_ENTRY
- atlcom/ATL::SERVICE_ENTRY_CHAIN
ms.assetid: ca02a125-454a-4cf6-aac2-1c5585025ed4
ms.openlocfilehash: ab130b2401dc9885f82fd5668a2d722a96dd289b
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79422932"
---
# <a name="service-map-macros"></a>Service Map マクロ

これらのマクロは、サービスマップとエントリを定義します。

|||
|-|-|
|[BEGIN_SERVICE_MAP](#begin_service_map)|ATL サービスマップの開始をマークします。|
|[END_SERVICE_MAP](#end_service_map)|ATL サービスマップの終了をマークします。|
|[SERVICE_ENTRY](#service_entry)|オブジェクトが特定のサービス ID をサポートしていることを示します。|
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|指定されたオブジェクトにチェーンするよう[Iserviceproviderimpl:: QueryService](#queryservice)に指示します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom. h

##  <a name="begin_service_map"></a>BEGIN_SERVICE_MAP

サービスマップの開始をマークします。

```
BEGIN_SERVICE_MAP(theClass)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
からサービスマップを含むクラスを指定します。

### <a name="remarks"></a>解説

サービスプロバイダーの機能を COM オブジェクトに実装するには、サービスマップを使用します。 まず、 [Iserviceproviderimpl](../../atl/reference/iserviceproviderimpl-class.md)からクラスを派生させる必要があります。 エントリには、次の2種類があります。

- [SERVICE_ENTRY](#service_entry)  指定されたサービス ID (SID) のサポートを示します。

- [SERVICE_ENTRY_CHAIN](#service_entry_chain)  指定された別のオブジェクトにチェーンするよう[Iserviceproviderimpl:: QueryService](#queryservice)に指示します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#57](../../atl/codesnippet/cpp/service-map-macros_1.h)]

##  <a name="end_service_map"></a>END_SERVICE_MAP

サービスマップの終了をマークします。

```
END_SERVICE_MAP()
```

### <a name="example"></a>例

[BEGIN_SERVICE_MAP](#begin_service_map)の例を参照してください。

##  <a name="service_entry"></a>SERVICE_ENTRY

オブジェクトが*SID*によって指定されたサービス id をサポートしていることを示します。

```
SERVICE_ENTRY( SID )
```

### <a name="parameters"></a>パラメーター

*SID*<br/>
サービス ID。

### <a name="example"></a>例

[BEGIN_SERVICE_MAP](#begin_service_map)の例を参照してください。

##  <a name="service_entry_chain"></a>SERVICE_ENTRY_CHAIN

*によって*指定されたオブジェクトにチェーンするよう[Iserviceproviderimpl:: QueryService](#queryservice)に指示します。

```
SERVICE_ENTRY_CHAIN( punk )
```

### <a name="parameters"></a>パラメーター

*パンク*<br/>
チェーンする**IUnknown**インターフェイスへのポインター。

### <a name="example"></a>例

[BEGIN_SERVICE_MAP](#begin_service_map)の例を参照してください。

##  <a name="queryservice"></a>IServiceProviderImpl:: QueryService

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

|戻り値|意味|
|------------------|-------------|
|S_OK|サービスが正常に作成または取得されました。|
|E_INVALIDARG|1 つ以上の引数が無効です。|
|E_OUTOFMEMORY|サービスを作成するにはメモリが不足しています。|
|E_UNEXPECTED|不明なエラーが発生しました。|
|E_NOINTERFACE|要求されたインターフェイスは、このサービスの一部ではないか、サービスが不明です。|

### <a name="remarks"></a>解説

`QueryService` は、指定されたサービス内の要求されたインターフェイスへの間接ポインターを返します。 呼び出し元は、不要になったときにこのポインターを解放する必要があります。

`QueryService`を呼び出すと、サービス識別子 (*guidservice*) とインターフェイス識別子 (*riid*) の両方を渡すことになります。 *Guidservice*は、アクセスするサービスを指定します。また、 *riid*は、サービスの一部であるインターフェイスを識別します。 返されると、インターフェイスへの間接ポインターを受け取ります。

インターフェイスを実装するオブジェクトは、他のサービスの一部であるインターフェイスも実装する場合があります。 以下、具体例に沿って説明します。

- これらのインターフェイスには、省略可能なものもあります。 サービスの説明で定義されているすべてのインターフェイスは、サービスのすべての実装または返されたすべてのオブジェクトに存在するとは限りません。

- `QueryInterface`の呼び出しとは異なり、異なるサービス識別子を渡すことは、必ずしも別のコンポーネントオブジェクトモデル (COM) オブジェクトが返されることを意味するわけではありません。

- 返されるオブジェクトには、サービスの定義の一部ではない追加のインターフェイスが含まれている場合があります。

SID_SMyService や SID_SYourService などの2つの異なるサービスでは、どちらも同じインターフェイスの使用を指定できます。ただし、インターフェイスの実装には、2つのサービス間で共通するものがない場合もあります。 これは、`QueryService` (SID_SMyService、IID_IDispatch) の呼び出しが `QueryService` (SID_SYourService、IID_IDispatch) とは異なるオブジェクトを返す可能性があるためです。 別のサービス識別子を指定した場合、オブジェクト id は想定されません。

## <a name="see-also"></a>参照

[マクロ](../../atl/reference/atl-macros.md)
