---
description: '詳細情報: IPerPropertyBrowsingImpl クラス'
title: IPerPropertyBrowsingImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetDisplayString
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedStrings
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedValue
- ATLCTL/ATL::IPerPropertyBrowsingImpl::MapPropertyToPage
helpviewer_keywords:
- IPerPropertyBrowsingImpl class
- property pages, accessing information
- IPerPropertyBrowsing, ATL implementation
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
ms.openlocfilehash: eba17c0011343f50f586b13086dc76229f08ba3c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139348"
---
# <a name="iperpropertybrowsingimpl-class"></a>IPerPropertyBrowsingImpl クラス

このクラス `IUnknown` はを実装し、クライアントがオブジェクトのプロパティページ内の情報にアクセスできるようにします。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IPerPropertyBrowsingImpl` 。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IPerPropertyBrowsingImpl:: GetDisplayString](#getdisplaystring)|指定されたプロパティを記述する文字列を取得します。|
|[IPerPropertyBrowsingImpl:: Getpre未定義の文字列](#getpredefinedstrings)|指定したプロパティが受け入れることができる値に対応する文字列の配列を取得します。|
|[IPerPropertyBrowsingImpl:: Getpresettings 値](#getpredefinedvalue)|指定した DISPID によって識別されるプロパティの値を格納しているバリアント型を取得します。 DISPID は、から取得した文字列名に関連付けられてい `GetPredefinedStrings` ます。 ATL 実装は E_NOTIMPL を返します。|
|[IPerPropertyBrowsingImpl:: MapPropertyToPage](#mappropertytopage)|指定したプロパティに関連付けられているプロパティページの CLSID を取得します。|

## <a name="remarks"></a>解説

[Iperpropertybrowsing](/windows/win32/api/ocidl/nn-ocidl-iperpropertybrowsing)インターフェイスを使用すると、クライアントは、オブジェクトのプロパティページ内の情報にアクセスできます。 クラス `IPerPropertyBrowsingImpl` は、このインターフェイスの既定の実装を提供し、 `IUnknown` デバッグビルドでダンプデバイスに情報を送信することによってを実装します。

> [!NOTE]
> コンテナーアプリケーションとして Microsoft Access を使用している場合は、からクラスを派生させる必要があり `IPerPropertyBrowsingImpl` ます。 それ以外の場合、アクセスはコントロールを読み込みません。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [atl プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IPerPropertyBrowsing`

`IPerPropertyBrowsingImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlctl. h

## <a name="iperpropertybrowsingimplgetdisplaystring"></a><a name="getdisplaystring"></a> IPerPropertyBrowsingImpl:: GetDisplayString

指定されたプロパティを記述する文字列を取得します。

```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```

### <a name="remarks"></a>解説

Windows SDK の「 [Iperpropertybrowsing:: GetDisplayString](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getdisplaystring) 」を参照してください。

## <a name="iperpropertybrowsingimplgetpredefinedstrings"></a><a name="getpredefinedstrings"></a> IPerPropertyBrowsingImpl:: Getpre未定義の文字列

各配列に項目0を格納します。

```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```

### <a name="return-value"></a>戻り値

ATL の [Getpreの実装値](#getpredefinedvalue) の実装は E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [Iperpropertybrowsing:: Getpreの文字列](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedstrings) 」を参照してください。

## <a name="iperpropertybrowsingimplgetpredefinedvalue"></a><a name="getpredefinedvalue"></a> IPerPropertyBrowsingImpl:: Getpresettings 値

指定した DISPID によって識別されるプロパティの値を格納しているバリアント型を取得します。 DISPID は、から取得した文字列名に関連付けられてい `GetPredefinedStrings` ます。

```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

ATL による [Getprestrings](#getpredefinedstrings) の実装では、対応する文字列は取得されません。

Windows SDK の「 [Iperpropertybrowsing:: Getpreの値](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedvalue) 」を参照してください。

## <a name="iperpropertybrowsingimplmappropertytopage"></a><a name="mappropertytopage"></a> IPerPropertyBrowsingImpl:: MapPropertyToPage

指定したプロパティに関連付けられているプロパティページの CLSID を取得します。

```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```

### <a name="remarks"></a>解説

ATL では、オブジェクトのプロパティマップを使用してこの情報を取得します。

Windows SDK の「 [Iperpropertybrowsing:: MapPropertyToPage](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-mappropertytopage) 」を参照してください。

## <a name="see-also"></a>関連項目

[IPropertyPageImpl クラス](../../atl/reference/ipropertypageimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl クラス](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
