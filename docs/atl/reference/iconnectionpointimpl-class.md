---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl::Advise
- ATLCOM/ATL::IConnectionPointImpl::EnumConnections
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionInterface
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionPointContainer
- ATLCOM/ATL::IConnectionPointImpl::Unadvise
- ATLCOM/ATL::IConnectionPointImpl::m_vec
helpviewer_keywords:
- connection points [C++], implementing
- IConnectionPointImpl class
ms.assetid: 27992115-3b86-45dd-bc9e-54f32876c557
ms.openlocfilehash: c62ac3310a579379674674a7a9a517e3f2fd60e5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329852"
---
# <a name="iconnectionpointimpl-class"></a>クラス

このクラスはコネクション ポイントを実装します。

## <a name="syntax"></a>構文

```
template<class T, const IID* piid, class CDV = CComDynamicUnkArray>
class ATL_NO_VTABLE IConnectionPointImpl : public _ICPLocator<piid>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`IConnectionPointImpl`。

*ピッド*<br/>
コネクション ポイント オブジェクトによって表されるインターフェイスの IID へのポインター。

*CDV*<br/>
接続を管理するクラス。 デフォルト値は、無制限の接続を許可する[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)です。 また、固定数の接続を指定する[CComUnkArray](../../atl/reference/ccomunkarray-class.md)を使用することもできます。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[I接続ポイントインプル::アドバイス](#advise)|接続ポイントとシンクの間に接続を確立します。|
|[I接続ポイントインプル::列挙接続](#enumconnections)|コネクション ポイントの接続を反復処理する列挙子を作成します。|
|[インターフェイスを使用します。](#getconnectioninterface)|コネクション ポイントによって表されるインターフェイスの IID を取得します。|
|[を指定します。](#getconnectionpointcontainer)|接続可能オブジェクトへのインターフェイス ポインターを取得します。|
|[I接続ポイントインプル::アアドバイスなし](#unadvise)|を使用して以前に確立された`Advise`接続を終了します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[I接続ポイントインプラプル::m_vec](#m_vec)|接続ポイントの接続を管理します。|

## <a name="remarks"></a>解説

`IConnectionPointImpl`はコネクション ポイントを実装し、オブジェクトがクライアントに発信インターフェイスを公開できるようにします。 クライアントは、シンクと呼ばれるオブジェクトにこのインターフェイスを実装します。

ATL は、接続可能オブジェクトを実装するために[IConnectionPoint コンテナのインプレルクト](../../atl/reference/iconnectionpointcontainerimpl-class.md)を使用します。 接続可能オブジェクト内の各接続ポイントは *、piid*で識別される発信インターフェイスを表します。 クラス*CDV*は、接続ポイントとシンク間の接続を管理します。 各接続は、"cookie" によって一意に識別されます。

ATL でのコネクション ポイントの使用の詳細については、[記事「接続ポイント](../../atl/atl-connection-points.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`_ICPLocator`

`IConnectionPointImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="iconnectionpointimpladvise"></a><a name="advise"></a>I接続ポイントインプル::アドバイス

接続ポイントとシンクの間に接続を確立します。

```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```

### <a name="remarks"></a>解説

接続呼び出しを終了するには[Unadvise](#unadvise)を使用します。

「Windows SDK[の IConnectionPoint::アドバイス](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-advise)」を参照してください。

## <a name="iconnectionpointimplenumconnections"></a><a name="enumconnections"></a>I接続ポイントインプル::列挙接続

コネクション ポイントの接続を反復処理する列挙子を作成します。

```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```

### <a name="remarks"></a>解説

「Windows SDK[の IConnectionPoint::列挙接続](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-enumconnections)」を参照してください。

## <a name="iconnectionpointimplgetconnectioninterface"></a><a name="getconnectioninterface"></a>インターフェイスを使用します。

コネクション ポイントによって表されるインターフェイスの IID を取得します。

```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```

### <a name="remarks"></a>解説

「Windows SDK の[I 接続ポイント::GetConnection インターフェイス](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-getconnectioninterface)」を参照してください。

## <a name="iconnectionpointimplgetconnectionpointcontainer"></a><a name="getconnectionpointcontainer"></a>を指定します。

接続可能オブジェクトへのインターフェイス ポインターを取得します。

```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```

### <a name="remarks"></a>解説

次[を](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-getconnectionpointcontainer)参照してください。

## <a name="iconnectionpointimplm_vec"></a><a name="m_vec"></a>I接続ポイントインプラプル::m_vec

接続ポイント オブジェクトとシンク間の接続を管理します。

```
CDV m_vec;
```

### <a name="remarks"></a>解説

既定では、`m_vec`型は[CCom 動的アンクアレイです](../../atl/reference/ccomdynamicunkarray-class.md)。

## <a name="iconnectionpointimplunadvise"></a><a name="unadvise"></a>I接続ポイントインプル::アアドバイスなし

[Advise](#advise)を使用して以前に確立された接続を終了します。

```
STDMETHOD(Unadvise)(DWORD dwCookie);
```

### <a name="remarks"></a>解説

「Windows SDK で[IConnectionPoint::アアドバイスを解除](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-unadvise)する」を参照してください。

## <a name="see-also"></a>関連項目

[IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
