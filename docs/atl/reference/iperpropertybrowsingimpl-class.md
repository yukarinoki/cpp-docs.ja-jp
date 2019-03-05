---
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
ms.openlocfilehash: 54c475e736425718e954b0e954ea2b327d938556
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299454"
---
# <a name="iperpropertybrowsingimpl-class"></a>IPerPropertyBrowsingImpl クラス

このクラスは実装`IUnknown`し、クライアントは、オブジェクトのプロパティ ページの情報にアクセスできます。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
派生したクラス、`IPerPropertyBrowsingImpl`します。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IPerPropertyBrowsingImpl::GetDisplayString](#getdisplaystring)|特定のプロパティを説明する文字列を取得します。|
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](#getpredefinedstrings)|特定のプロパティで許容される値に対応する文字列の配列を取得します。|
|[IPerPropertyBrowsingImpl::GetPredefinedValue](#getpredefinedvalue)|指定した DISPID で識別されるプロパティの値を含むバリアント型を取得します。 取得した文字列の名前を持つように DISPID が関連付けられている`GetPredefinedStrings`します。 ATL の実装では、E_NOTIMPL を返します。|
|[IPerPropertyBrowsingImpl::MapPropertyToPage](#mappropertytopage)|特定のプロパティに関連付けられたプロパティ ページの CLSID を取得します。|

## <a name="remarks"></a>Remarks

[IPerPropertyBrowsing](/windows/desktop/api/ocidl/nn-ocidl-iperpropertybrowsing)インターフェイスにより、クライアントは、オブジェクトのプロパティ ページの情報にアクセスします。 クラス`IPerPropertyBrowsingImpl`このインターフェイスの既定の実装を提供し、実装`IUnknown`ダンプ情報を送信することによってデバッグでのデバイスをビルドします。

> [!NOTE]
>  コンテナー アプリケーションとして Microsoft Access を使用する場合からクラスを派生する必要があります`IPerPropertyBrowsingImpl`します。 それ以外の場合、アクセスは、コントロールを読み込めません。

**関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IPerPropertyBrowsing`

`IPerPropertyBrowsingImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

##  <a name="getdisplaystring"></a>  IPerPropertyBrowsingImpl::GetDisplayString

特定のプロパティを説明する文字列を取得します。

```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```

### <a name="remarks"></a>Remarks

参照してください[IPerPropertyBrowsing::GetDisplayString](/windows/desktop/api/ocidl/nf-ocidl-iperpropertybrowsing-getdisplaystring) Windows SDK にします。

##  <a name="getpredefinedstrings"></a>  IPerPropertyBrowsingImpl::GetPredefinedStrings

各配列項目数は 0 を格納します。

```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```

### <a name="return-value"></a>戻り値

ATL の実装の[GetPredefinedValue](#getpredefinedvalue) E_NOTIMPL を返します。

### <a name="remarks"></a>Remarks

参照してください[IPerPropertyBrowsing::GetPredefinedStrings](/windows/desktop/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedstrings) Windows SDK にします。

##  <a name="getpredefinedvalue"></a>  IPerPropertyBrowsingImpl::GetPredefinedValue

指定した DISPID で識別されるプロパティの値を含むバリアント型を取得します。 取得した文字列の名前を持つように DISPID が関連付けられている`GetPredefinedStrings`します。

```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>Remarks

ATL の実装の[GetPredefinedStrings](#getpredefinedstrings)対応する文字列が取得されません。

参照してください[IPerPropertyBrowsing::GetPredefinedValue](/windows/desktop/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedvalue) Windows SDK にします。

##  <a name="mappropertytopage"></a>  IPerPropertyBrowsingImpl::MapPropertyToPage

指定したプロパティに関連付けられたプロパティ ページの CLSID を取得します。

```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```

### <a name="remarks"></a>Remarks

ATL では、オブジェクトのプロパティのマップを使用して、この情報を取得します。

参照してください[IPerPropertyBrowsing::MapPropertyToPage](/windows/desktop/api/ocidl/nf-ocidl-iperpropertybrowsing-mappropertytopage) Windows SDK にします。

## <a name="see-also"></a>関連項目

[IPropertyPageImpl クラス](../../atl/reference/ipropertypageimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl クラス](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
