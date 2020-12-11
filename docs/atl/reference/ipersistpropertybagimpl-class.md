---
description: '詳細情報: IPersistPropertyBagImpl クラス'
title: IPersistPropertyBagImpl クラス
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
ms.openlocfilehash: 1e244c4349bd04a83d257280da3315f2c797003a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158167"
---
# <a name="ipersistpropertybagimpl-class"></a>IPersistPropertyBagImpl クラス

このクラスはを実装 `IUnknown` し、オブジェクトがそのプロパティをクライアントが提供するプロパティバッグに保存できるようにします。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T>
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IPersistPropertyBagImpl` 。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IPersistPropertyBagImpl:: GetClassID](#getclassid)|オブジェクトの CLSID を取得します。|
|[IPersistPropertyBagImpl:: InitNew](#initnew)|新しく作成されたオブジェクトを初期化します。 ATL 実装は S_OK を返します。|
|[IPersistPropertyBagImpl:: Load](#load)|クライアントが提供したプロパティバッグから、オブジェクトのプロパティを読み込みます。|
|[IPersistPropertyBagImpl:: Save](#save)|オブジェクトのプロパティを、クライアントが指定したプロパティバッグに保存します。|

## <a name="remarks"></a>解説

[IPersistPropertyBag](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768205\(v=vs.85\))インターフェイスを使用すると、オブジェクトは、クライアントが指定したプロパティバッグにプロパティを保存できます。 クラス `IPersistPropertyBagImpl` は、このインターフェイスの既定の実装を提供し、 `IUnknown` デバッグビルドでダンプデバイスに情報を送信することによってを実装します。

`IPersistPropertyBag`[IPropertyBag](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768196\(v=vs.85\))および[ierrorlog ログ](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768231\(v=vs.85\))と連携して動作します。 これらの後者の2つのインターフェイスは、クライアントによって実装される必要があります。 クライアントは、を介して、 `IPropertyBag` オブジェクトの個々のプロパティを保存して読み込みます。 では `IErrorLog` 、オブジェクトとクライアントの両方で発生したエラーを報告できます。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [atl プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IPersistPropertyBag`

`IPersistPropertyBagImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="ipersistpropertybagimplgetclassid"></a><a name="getclassid"></a> IPersistPropertyBagImpl:: GetClassID

オブジェクトの CLSID を取得します。

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>解説

Windows SDK の「 [IPersist:: GetClassID](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid) 」を参照してください。

## <a name="ipersistpropertybagimplinitnew"></a><a name="initnew"></a> IPersistPropertyBagImpl:: InitNew

新しく作成されたオブジェクトを初期化します。

```
STDMETHOD(InitNew)();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IPersistPropertyBag:: InitNew](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768204\(v=vs.85\)) 」を参照してください。

## <a name="ipersistpropertybagimplload"></a><a name="load"></a> IPersistPropertyBagImpl:: Load

クライアントが提供したプロパティバッグから、オブジェクトのプロパティを読み込みます。

```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```

### <a name="remarks"></a>解説

ATL では、オブジェクトのプロパティマップを使用してこの情報を取得します。

Windows SDK の「 [IPersistPropertyBag:: Load](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768206\(v=vs.85\)) 」を参照してください。

## <a name="ipersistpropertybagimplsave"></a><a name="save"></a> IPersistPropertyBagImpl:: Save

オブジェクトのプロパティを、クライアントが指定したプロパティバッグに保存します。

```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```

### <a name="remarks"></a>解説

ATL では、オブジェクトのプロパティマップを使用してこの情報を格納します。 既定では、このメソッドは *Fsaveallproperties* の値に関係なく、すべてのプロパティを保存します。

Windows SDK の「 [IPersistPropertyBag:: Save](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768207\(v=vs.85\)) 」を参照してください。

## <a name="see-also"></a>関連項目

[BEGIN_PROP_MAP](property-map-macros.md#begin_prop_map)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
