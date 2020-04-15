---
title: クラスを永続化します。
ms.date: 11/04/2016
f1_keywords:
- IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl::GetClassID
- ATLCOM/ATL::IPersistPropertyBagImpl::InitNew
- ATLCOM/ATL::IPersistPropertyBagImpl::Load
- ATLCOM/ATL::IPersistPropertyBagImpl::Save
helpviewer_keywords:
- IPersistPropertyBagImpl class
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
ms.openlocfilehash: f656ecc76b175eae523059c60bb8a3efc6f0b312
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326479"
---
# <a name="ipersistpropertybagimpl-class"></a>クラスを永続化します。

このクラスは、`IUnknown`オブジェクトがクライアント提供のプロパティ バッグにプロパティを保存することを実装し、許可します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T>
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`IPersistPropertyBagImpl`。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[プロパティバグプル::取得クラスID](#getclassid)|オブジェクトの CLSID を取得します。|
|[IPersist プロパティバグプル::イニトニュー](#initnew)|新しく作成されたオブジェクトを初期化します。 ATL 実装はS_OKを返します。|
|[IPersist プロパティバグプル::読み込み](#load)|クライアントが指定したプロパティ バッグからオブジェクトのプロパティを読み込みます。|
|[IPersist プロパティバグプル::保存](#save)|オブジェクトのプロパティをクライアントが指定したプロパティ バッグに保存します。|

## <a name="remarks"></a>解説

[IPersistPropertyBag](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768205\(v=vs.85\))インターフェイスを使用すると、オブジェクトのプロパティをクライアント提供のプロパティ バッグに保存できます。 Class`IPersistPropertyBagImpl`は、このインターフェイスの既定の実装を`IUnknown`提供し、デバッグ ビルドでダンプ デバイスに情報を送信することによって実装します。

`IPersistPropertyBag`[と](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768196\(v=vs.85\))連携して[動作します。](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768231\(v=vs.85\)) これらの後者の 2 つのインターフェイスは、クライアントによって実装する必要があります。 を`IPropertyBag`使用して、クライアントはオブジェクトの個々のプロパティを保存して読み込みます。 を`IErrorLog`通じて、オブジェクトとクライアントの両方が、発生したエラーを報告できます。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md), [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IPersistPropertyBag`

`IPersistPropertyBagImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ipersistpropertybagimplgetclassid"></a><a name="getclassid"></a>プロパティバグプル::取得クラスID

オブジェクトの CLSID を取得します。

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>解説

「Windows SDK[の IPersist::GetClassID」](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid)を参照してください。

## <a name="ipersistpropertybagimplinitnew"></a><a name="initnew"></a>IPersist プロパティバグプル::イニトニュー

新しく作成されたオブジェクトを初期化します。

```
STDMETHOD(InitNew)();
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

Windows SDK の[「プロパティ バッグ::InitNew」](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768204\(v=vs.85\))を参照してください。

## <a name="ipersistpropertybagimplload"></a><a name="load"></a>IPersist プロパティバグプル::読み込み

クライアントが指定したプロパティ バッグからオブジェクトのプロパティを読み込みます。

```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```

### <a name="remarks"></a>解説

ATL は、オブジェクトのプロパティ マップを使用して、この情報を取得します。

「プロパティ[バッグ::読み込む](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768206\(v=vs.85\))」を参照してください。

## <a name="ipersistpropertybagimplsave"></a><a name="save"></a>IPersist プロパティバグプル::保存

オブジェクトのプロパティをクライアントが指定したプロパティ バッグに保存します。

```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```

### <a name="remarks"></a>解説

ATL は、オブジェクトのプロパティ マップを使用してこの情報を格納します。 既定では、このメソッドは *、fSaveAllProperties*の値に関係なく、すべてのプロパティを保存します。

「プロパティ[バッグ::](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768207\(v=vs.85\))保存」を参照してください。

## <a name="see-also"></a>関連項目

[BEGIN_PROP_MAP](property-map-macros.md#begin_prop_map)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
