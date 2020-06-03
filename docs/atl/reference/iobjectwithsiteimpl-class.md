---
title: クラスを使用します。
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
ms.openlocfilehash: 034e5dd42f6e10286520bb2a08effc40b0aca71a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329644"
---
# <a name="iobjectwithsiteimpl-class"></a>クラスを使用します。

このクラスは、オブジェクトがサイトと通信できるようにするメソッドを提供します。

## <a name="syntax"></a>構文

```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`IObjectWithSiteImpl`。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IObjectWithサイトインプル::ゲットサイト](#getsite)|サイトにインターフェイス ポインターを照会します。|
|[サイトインプジェル::セットチャイルドサイト](#setchildsite)|サイトのポインターを持つオブジェクトを`IUnknown`提供します。|
|[IObjectWithSiteImpl::セットサイト](#setsite)|サイトのポインターを持つオブジェクトを`IUnknown`提供します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[IObjectWithサイトインプル::m_spUnkSite](#m_spunksite)|サイトの`IUnknown`ポインターを管理します。|

## <a name="remarks"></a>解説

[インターフェイス](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite)を使用すると、オブジェクトがサイトと通信できるようになります。 Class`IObjectWithSiteImpl`は、このインターフェイスの既定の実装を`IUnknown`提供し、デバッグ ビルドでダンプ デバイスに情報を送信することによって実装します。

`IObjectWithSiteImpl`2 つのメソッドを指定します。 クライアントは、まず`SetSite`サイトの`IUnknown`ポインタを渡して 呼び出します。 このポインターはオブジェクト内に格納され、後で の 呼び出し`GetSite`を通じて取得できます。

通常、クラスは、コントロールではない`IObjectWithSiteImpl`オブジェクトを作成するときから派生します。 コントロールの場合は、サイト ポインターも提供する[IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)からクラスを派生させます。 クラスを と と`IObjectWithSiteImpl`の`IOleObjectImpl`両方から派生させないでください。

## <a name="inheritance-hierarchy"></a>継承階層

`IObjectWithSite`

`IObjectWithSiteImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="iobjectwithsiteimplgetsite"></a><a name="getsite"></a>IObjectWithサイトインプル::ゲットサイト

によって識別されるインターフェイスへのポインターをサイトに`riid`照会します。

```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```

### <a name="remarks"></a>解説

サイトがこのインターフェイスをサポートしている場合、ポインターは を`ppvSite`介して返されます。 それ以外`ppvSite`の場合は、NULL に設定されます。

Windows SDK[の「IObjectWithSite::ゲットサイト](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-getsite)」を参照してください。

## <a name="iobjectwithsiteimplm_spunksite"></a><a name="m_spunksite"></a>IObjectWithサイトインプル::m_spUnkSite

サイトの`IUnknown`ポインターを管理します。

```
CComPtr<IUnknown> m_spUnkSite;
```

### <a name="remarks"></a>解説

`m_spUnkSite`最初に[SetSite](#setsite)への呼び出しを通じてこのポインタを受け取ります。

## <a name="iobjectwithsiteimplsetchildsite"></a><a name="setchildsite"></a>サイトインプジェル::セットチャイルドサイト

サイトのポインターを持つオブジェクトを`IUnknown`提供します。

```
HRESULT SetChildSite(IUnknown* pUnkSite);
```

### <a name="parameters"></a>パラメーター

*プンクサイト*<br/>
[in]このオブジェクトを`IUnknown`管理するサイトのインターフェイス ポインターへのポインター。 NULL の場合、オブジェクトは`IUnknown::Release`、そのサイトを認識しなくなった時点で、既存のサイトを呼び出す必要があります。

### <a name="return-value"></a>戻り値

S_OKを返します。

## <a name="iobjectwithsiteimplsetsite"></a><a name="setsite"></a>IObjectWithSiteImpl::セットサイト

サイトのポインターを持つオブジェクトを`IUnknown`提供します。

```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```

### <a name="remarks"></a>解説

Windows SDK[の「IObjectWithSite::セットサイト](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite)」を参照してください。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
