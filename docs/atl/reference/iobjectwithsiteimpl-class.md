---
description: '詳細情報: IObjectWithSiteImpl クラス'
title: IObjectWithSiteImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl::GetSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetChildSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetSite
- ATLCOM/ATL::IObjectWithSiteImpl::m_spUnkSite
helpviewer_keywords:
- IObjectWithSiteImpl class
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
ms.openlocfilehash: 100a4d16bea63d573fe4fb00bc37e656a7c2c483
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158297"
---
# <a name="iobjectwithsiteimpl-class"></a>IObjectWithSiteImpl クラス

このクラスは、オブジェクトがそのサイトと通信できるようにするメソッドを提供します。

## <a name="syntax"></a>構文

```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IObjectWithSiteImpl` 。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IObjectWithSiteImpl:: GetSite](#getsite)|サイトにインターフェイスポインターを照会します。|
|[IObjectWithSiteImpl:: SetChildSite](#setchildsite)|サイトのポインターをオブジェクトに提供し `IUnknown` ます。|
|[IObjectWithSiteImpl:: SetSite](#setsite)|サイトのポインターをオブジェクトに提供し `IUnknown` ます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[IObjectWithSiteImpl:: m_spUnkSite](#m_spunksite)|サイトのポインターを管理 `IUnknown` します。|

## <a name="remarks"></a>解説

[IObjectWithSite](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite)インターフェイスを使用すると、オブジェクトはそのサイトと通信できます。 クラス `IObjectWithSiteImpl` は、このインターフェイスの既定の実装を提供し、 `IUnknown` デバッグビルドでダンプデバイスに情報を送信することによってを実装します。

`IObjectWithSiteImpl` 2つのメソッドを指定します。 クライアントは、まず `SetSite` を呼び出し、サイトの `IUnknown` ポインターを渡します。 このポインターはオブジェクト内に格納され、後での呼び出しによって取得でき `GetSite` ます。

通常は、 `IObjectWithSiteImpl` コントロールではないオブジェクトを作成するときに、からクラスを派生させます。 コントロールの場合は、サイトポインターも提供する [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)からクラスを派生させます。 との両方からクラスを派生させないで `IObjectWithSiteImpl` `IOleObjectImpl` ください。

## <a name="inheritance-hierarchy"></a>継承階層

`IObjectWithSite`

`IObjectWithSiteImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="iobjectwithsiteimplgetsite"></a><a name="getsite"></a> IObjectWithSiteImpl:: GetSite

によって識別されるインターフェイスへのポインターをサイトに照会 `riid` します。

```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```

### <a name="remarks"></a>解説

サイトでこのインターフェイスがサポートされている場合は、によってポインターが返され `ppvSite` ます。 それ以外の場合、 `ppvSite` は NULL に設定されます。

Windows SDK の「 [IObjectWithSite:: GetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-getsite) 」を参照してください。

## <a name="iobjectwithsiteimplm_spunksite"></a><a name="m_spunksite"></a> IObjectWithSiteImpl:: m_spUnkSite

サイトのポインターを管理 `IUnknown` します。

```
CComPtr<IUnknown> m_spUnkSite;
```

### <a name="remarks"></a>解説

`m_spUnkSite` は、 [SetSite](#setsite)を呼び出すことによって、最初にこのポインターを受け取ります。

## <a name="iobjectwithsiteimplsetchildsite"></a><a name="setchildsite"></a> IObjectWithSiteImpl:: SetChildSite

サイトのポインターをオブジェクトに提供し `IUnknown` ます。

```
HRESULT SetChildSite(IUnknown* pUnkSite);
```

### <a name="parameters"></a>パラメーター

*pUnkSite*<br/>
から `IUnknown` このオブジェクトを管理しているサイトのインターフェイスポインターへのポインター。 NULL の場合は、オブジェクトが `IUnknown::Release` そのサイトを認識しなくなった時点の既存のサイトでを呼び出す必要があります。

### <a name="return-value"></a>戻り値

S_OK を返します。

## <a name="iobjectwithsiteimplsetsite"></a><a name="setsite"></a> IObjectWithSiteImpl:: SetSite

サイトのポインターをオブジェクトに提供し `IUnknown` ます。

```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```

### <a name="remarks"></a>解説

Windows SDK の「 [IObjectWithSite:: SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite) 」を参照してください。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
