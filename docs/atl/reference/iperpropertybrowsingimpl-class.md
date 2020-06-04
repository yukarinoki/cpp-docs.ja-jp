---
title: クラスを参照しています。
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
ms.openlocfilehash: f8fb80cc38e775b9b26afa033647faac694e968a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326516"
---
# <a name="iperpropertybrowsingimpl-class"></a>クラスを参照しています。

このクラスは、`IUnknown`クライアントがオブジェクトのプロパティ ページの情報を実装し、アクセスできるようにします。

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
から派生したクラス`IPerPropertyBrowsingImpl`。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[プロパティブラウジングインプル::GetDisplay文字列](#getdisplaystring)|指定されたプロパティを記述する文字列を取得します。|
|[インプリスプロパティブラウジングインプル::定義済み文字列を取得します。](#getpredefinedstrings)|指定したプロパティが受け取ることができる値に対応する文字列の配列を取得します。|
|[プロパティブラウジングインプル::取得定義済みの値](#getpredefinedvalue)|指定された DISPID によって識別されるプロパティの値を含む VARIANT を取得します。 DISPID は、 から`GetPredefinedStrings`取得した文字列名に関連付けられます。 ATL の実装はE_NOTIMPL返します。|
|[プロパティの参照インプル:::マッププロパティをページへ移動します。](#mappropertytopage)|指定したプロパティに関連付けられているプロパティ ページの CLSID を取得します。|

## <a name="remarks"></a>解説

[インターフェイス](/windows/win32/api/ocidl/nn-ocidl-iperpropertybrowsing)を使用すると、クライアントはオブジェクトのプロパティ ページの情報にアクセスできます。 Class`IPerPropertyBrowsingImpl`は、このインターフェイスの既定の実装を`IUnknown`提供し、デバッグ ビルドでダンプ デバイスに情報を送信することによって実装します。

> [!NOTE]
> コンテナ アプリケーションとして Access を使用している場合は、 から`IPerPropertyBrowsingImpl`クラスを派生させる必要があります。 そうしないと、コントロールが読み込まれません。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md), [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IPerPropertyBrowsing`

`IPerPropertyBrowsingImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="iperpropertybrowsingimplgetdisplaystring"></a><a name="getdisplaystring"></a>プロパティブラウジングインプル::GetDisplay文字列

指定されたプロパティを記述する文字列を取得します。

```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```

### <a name="remarks"></a>解説

Windows SDK[の「IPerProperty ブラウズ::GetDisplay 文字列](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getdisplaystring)」を参照してください。

## <a name="iperpropertybrowsingimplgetpredefinedstrings"></a><a name="getpredefinedstrings"></a>インプリスプロパティブラウジングインプル::定義済み文字列を取得します。

各配列をゼロの項目で埋めます。

```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```

### <a name="return-value"></a>戻り値

ATL の[実装は、E_NOTIMPL](#getpredefinedvalue)返します。

### <a name="remarks"></a>解説

Windows SDK[の「IPerProperty ブラウズ::定義済み文字列を取得](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedstrings)する」を参照してください。

## <a name="iperpropertybrowsingimplgetpredefinedvalue"></a><a name="getpredefinedvalue"></a>プロパティブラウジングインプル::取得定義済みの値

指定された DISPID によって識別されるプロパティの値を含む VARIANT を取得します。 DISPID は、 から`GetPredefinedStrings`取得した文字列名に関連付けられます。

```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

ATL の実装[は、](#getpredefinedstrings)対応する文字列を取得しません。

Windows SDK[の「IPerProperty ブラウジング::定義済みの値を取得](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedvalue)する」を参照してください。

## <a name="iperpropertybrowsingimplmappropertytopage"></a><a name="mappropertytopage"></a>プロパティの参照インプル:::マッププロパティをページへ移動します。

指定したプロパティに関連付けられているプロパティ ページの CLSID を取得します。

```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```

### <a name="remarks"></a>解説

ATL は、オブジェクトのプロパティ マップを使用してこの情報を取得します。

Windows SDK[の「プロパティの参照::マッププロパティ」を](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-mappropertytopage)参照してください。

## <a name="see-also"></a>関連項目

[クラスをプロパティページインビ](../../atl/reference/ipropertypageimpl-class.md)<br/>
[クラスを指定します。](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
