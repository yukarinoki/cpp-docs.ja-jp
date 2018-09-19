---
title: IPersistPropertyBagImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl::GetClassID
- ATLCOM/ATL::IPersistPropertyBagImpl::InitNew
- ATLCOM/ATL::IPersistPropertyBagImpl::Load
- ATLCOM/ATL::IPersistPropertyBagImpl::Save
dev_langs:
- C++
helpviewer_keywords:
- IPersistPropertyBagImpl class
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e104b5d471302b614852d98b379f941b2d9b7ead
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024951"
---
# <a name="ipersistpropertybagimpl-class"></a>IPersistPropertyBagImpl クラス

このクラスは実装`IUnknown`でき、そのプロパティをクライアントが指定したプロパティ バッグに保存するオブジェクト。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T>
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
派生したクラス、`IPersistPropertyBagImpl`します。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IPersistPropertyBagImpl::GetClassID](#getclassid)|オブジェクトの CLSID を取得します。|
|[IPersistPropertyBagImpl::InitNew](#initnew)|新しく作成されたオブジェクトを初期化します。 ATL の実装では、S_OK を返します。|
|[IPersistPropertyBagImpl::Load](#load)|クライアントが指定したプロパティ バッグからオブジェクトのプロパティを読み込みます。|
|[IPersistPropertyBagImpl::Save](#save)|オブジェクトのプロパティは、クライアントが指定したプロパティ バッグに保存します。|

## <a name="remarks"></a>Remarks

[IPersistPropertyBag](https://msdn.microsoft.com/library/aa768205.aspx)インターフェイスにより、クライアントが指定したプロパティ バッグのプロパティを保存するオブジェクト。 クラス`IPersistPropertyBagImpl`このインターフェイスの既定の実装を提供し、実装`IUnknown`ダンプ情報を送信することによってデバッグでのデバイスをビルドします。

`IPersistPropertyBag` 連携して[IPropertyBag](https://msdn.microsoft.com/library/aa768196.aspx)と[IErrorLog](https://msdn.microsoft.com/library/aa768231.aspx)します。 クライアントによってこれら後者の 2 つのインターフェイスを実装する必要があります。 を通じて`IPropertyBag`クライアントが保存され、オブジェクトの個々 のプロパティを読み込みます。 を通じて`IErrorLog`オブジェクトとクライアントの両方が発生したエラーを報告できます。

**関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IPersistPropertyBag`

`IPersistPropertyBagImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom.h

##  <a name="getclassid"></a>  IPersistPropertyBagImpl::GetClassID

オブジェクトの CLSID を取得します。

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Remarks

参照してください[IPersist::GetClassID](/windows/desktop/api/objidl/nf-objidl-ipersist-getclassid) Windows SDK にします。

##  <a name="initnew"></a>  IPersistPropertyBagImpl::InitNew

新しく作成されたオブジェクトを初期化します。

```
STDMETHOD(InitNew)();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>Remarks

参照してください[IPersistPropertyBag::InitNew](https://msdn.microsoft.com/library/aa768204.aspx) Windows SDK にします。

##  <a name="load"></a>  IPersistPropertyBagImpl::Load

クライアントが指定したプロパティ バッグからオブジェクトのプロパティを読み込みます。

```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```

### <a name="remarks"></a>Remarks

ATL では、オブジェクトのプロパティのマップを使用して、この情報を取得します。

参照してください[IPersistPropertyBag::Load](https://msdn.microsoft.com/library/aa768206.aspx) Windows SDK にします。

##  <a name="save"></a>  IPersistPropertyBagImpl::Save

オブジェクトのプロパティは、クライアントが指定したプロパティ バッグに保存します。

```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```

### <a name="remarks"></a>Remarks

ATL では、オブジェクトのプロパティ マップを使用して、この情報を格納します。 既定では、このメソッドの値に関係なく、すべてのプロパティを保存します。 *fSaveAllProperties*します。

参照してください[IPersistPropertyBag::Save](https://msdn.microsoft.com/library/aa768207.aspx) Windows SDK にします。

## <a name="see-also"></a>関連項目

[あり、その場合](property-map-macros.md#begin_prop_map)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
