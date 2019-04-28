---
title: IConnectionPointImpl クラス
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
ms.openlocfilehash: 54231a4229db9a9afeecad878d695814565d776b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275543"
---
# <a name="iconnectionpointimpl-class"></a>IConnectionPointImpl クラス

このクラスは、接続ポイントを実装します。

## <a name="syntax"></a>構文

```
template<class T, const IID* piid, class CDV = CComDynamicUnkArray>
class ATL_NO_VTABLE IConnectionPointImpl : public _ICPLocator<piid>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
派生したクラス、`IConnectionPointImpl`します。

*piid*<br/>
コネクション ポイント オブジェクトによって表されるインターフェイスの IID へのポインター。

*CDV*<br/>
接続を管理するクラスです。 既定値は[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)接続を制限しないことができます。 使用することも[CComUnkArray](../../atl/reference/ccomunkarray-class.md)、固定接続数を指定します。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IConnectionPointImpl::Advise](#advise)|接続ポイントとシンクの間の接続を確立します。|
|[IConnectionPointImpl::EnumConnections](#enumconnections)|コネクション ポイントの接続を反復処理する列挙子を作成します。|
|[IConnectionPointImpl::GetConnectionInterface](#getconnectioninterface)|接続ポイントによって表されるインターフェイスの IID を取得します。|
|[IConnectionPointImpl::GetConnectionPointContainer](#getconnectionpointcontainer)|接続可能オブジェクトへのインターフェイス ポインターを取得します。|
|[IConnectionPointImpl::Unadvise](#unadvise)|以前に確立した接続が終了した`Advise`します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[IConnectionPointImpl::m_vec](#m_vec)|コネクション ポイントの接続を管理します。|

## <a name="remarks"></a>Remarks

`IConnectionPointImpl` クライアントへの送信インターフェイスを公開するオブジェクトを使用する接続ポイントを実装します。 クライアントは、シンクと呼ばれるオブジェクトのこのインターフェイスを実装します。

ATL を使用して[IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)接続可能オブジェクトを実装します。 接続可能オブジェクト内の各接続ポイントで識別される、アウトゴーイング インターフェイスを表す*piid*します。 クラス*CDV*接続ポイントとシンクの間の接続を管理します。 各接続は、「クッキー」によって一意に識別します。

ATL でのコネクション ポイントの使用に関する詳細については、記事を参照してください。[コネクション ポイント](../../atl/atl-connection-points.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`_ICPLocator`

`IConnectionPointImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

##  <a name="advise"></a>  IConnectionPointImpl::Advise

接続ポイントとシンクの間の接続を確立します。

```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```

### <a name="remarks"></a>Remarks

使用[Unadvise](#unadvise)接続呼び出しを終了します。

参照してください[iconnectionpoint::advise](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-advise) Windows SDK にします。

##  <a name="enumconnections"></a>  IConnectionPointImpl::EnumConnections

コネクション ポイントの接続を反復処理する列挙子を作成します。

```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```

### <a name="remarks"></a>Remarks

参照してください[IConnectionPoint::EnumConnections](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-enumconnections) Windows SDK にします。

##  <a name="getconnectioninterface"></a>  IConnectionPointImpl::GetConnectionInterface

接続ポイントによって表されるインターフェイスの IID を取得します。

```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```

### <a name="remarks"></a>Remarks

参照してください[IConnectionPoint::GetConnectionInterface](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-getconnectioninterface) Windows SDK にします。

##  <a name="getconnectionpointcontainer"></a>  IConnectionPointImpl::GetConnectionPointContainer

接続可能オブジェクトへのインターフェイス ポインターを取得します。

```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```

### <a name="remarks"></a>Remarks

参照してください[IConnectionPoint::GetConnectionPointContainer](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-getconnectionpointcontainer) Windows SDK にします。

##  <a name="m_vec"></a>  IConnectionPointImpl::m_vec

コネクション ポイント オブジェクトとシンクの間の接続を管理します。

```
CDV m_vec;
```

### <a name="remarks"></a>Remarks

既定では、`m_vec`の種類は[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)します。

##  <a name="unadvise"></a>  IConnectionPointImpl::Unadvise

以前に確立した接続が終了した[Advise](#advise)します。

```
STDMETHOD(Unadvise)(DWORD dwCookie);
```

### <a name="remarks"></a>Remarks

参照してください[:unadvise](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-unadvise) Windows SDK にします。

## <a name="see-also"></a>関連項目

[IConnectionPoint](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
