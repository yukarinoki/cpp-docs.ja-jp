---
description: '詳細情報: ICollectionOnSTLImpl クラス'
title: ICollectionOnSTLImpl クラス
ms.date: 11/04/2016
f1_keywords:
- ICollectionOnSTLImpl
- ATLCOM/ATL::ICollectionOnSTLImpl
- ATLCOM/ATL::ICollectionOnSTLImpl::get__NewEnum
- ATLCOM/ATL::ICollectionOnSTLImpl::getcount
- ATLCOM/ATL::ICollectionOnSTLImpl::get_Item
- ATLCOM/ATL::ICollectionOnSTLImpl::m_coll
helpviewer_keywords:
- ICollectionOnSTLImpl class
ms.assetid: 683c88b0-0d97-4779-a762-e493334ba7f9
ms.openlocfilehash: 089fc0fbd8f410d740646e2a653b076d32448647
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139608"
---
# <a name="icollectiononstlimpl-class"></a>ICollectionOnSTLImpl クラス

このクラスは、コレクションクラスによって使用されるメソッドを提供します。

## <a name="syntax"></a>構文

```
template <class T, class CollType, class ItemType, class CopyItem, class EnumType>
class ICollectionOnSTLImpl : public T
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
COM コレクションインターフェイス。

*文字の種類*<br/>
C++ 標準ライブラリコンテナークラス。

*ItemType*<br/>
コンテナーインターフェイスによって公開される項目の型。

*CopyItem*<br/>
[コピーポリシークラス](../../atl/atl-copy-policy-classes.md)。

*EnumType*<br/>
[CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)互換列挙子クラス。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ICollectionOnSTLImpl:: get__NewEnum](#newenum)|コレクションの列挙子オブジェクトを返します。|
|[ICollectionOnSTLImpl:: getcount](#get_count)|コレクション内の要素の数を返します。|
|[ICollectionOnSTLImpl:: get_Item](#get_item)|要求された項目をコレクションから返します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ICollectionOnSTLImpl:: m_coll](#m_coll)|コレクション。|

## <a name="remarks"></a>解説

このクラスは、コレクションインターフェイスの3つのメソッド ( [getcount](#get_count)、 [get_Item](#get_item)、 [get__NewEnum](#newenum)) の実装を提供します。

このクラスを使用するには:

- 実装するコレクションインターフェイスを定義 (または借用) します。

- このコレクションインターフェイスに基づいて、の特殊化からクラスを派生させ `ICollectionOnSTLImpl` ます。

- 派生クラスを使用して、によって処理されないコレクションインターフェイスからメソッドを実装し `ICollectionOnSTLImpl` ます。

> [!NOTE]
> コレクションインターフェイスがデュアルインターフェイスの場合は、 [IDispatchImpl](../../atl/reference/idispatchimpl-class.md)からクラスを派生させ、 `ICollectionOnSTLImpl` ATL でメソッドの実装を提供する場合は、最初のテンプレートパラメーターとして特殊化を渡し `IDispatch` ます。

- コレクションを作成するには、 [m_coll](#m_coll) メンバーに項目を追加します。

詳細と例については、「 [ATL コレクションと列挙子](../../atl/atl-collections-and-enumerators.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`T`

`ICollectionOnSTLImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="icollectiononstlimplgetcount"></a><a name="get_count"></a> ICollectionOnSTLImpl:: getcount

このメソッドは、コレクション内の項目の数を返します。

```
STDMETHOD(getcount)(long* pcount);
```

### <a name="parameters"></a>パラメーター

*pcount*<br/>
入出力コレクション内の要素の数。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="icollectiononstlimplget_item"></a><a name="get_item"></a> ICollectionOnSTLImpl:: get_Item

このメソッドは、指定された項目をコレクションから返します。

```
STDMETHOD(get_Item)(long Index, ItemType* pvar);
```

### <a name="parameters"></a>パラメーター

*Index*<br/>
からコレクション内の項目の1から始まるインデックス。

*pvar*<br/>
入出力 *インデックス* に対応する項目。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

項目は、特殊化でテンプレート引数として渡された[コピーポリシークラス](../../atl/atl-copy-policy-classes.md)の copy メソッドを使用して、 [m_coll](#m_coll)内の指定した位置にあるデータをコピーすることによって取得され `ICollectionOnSTLImpl` ます。

## <a name="icollectiononstlimplget__newenum"></a><a name="newenum"></a> ICollectionOnSTLImpl:: get__NewEnum

コレクションの列挙子オブジェクトを返します。

```
STDMETHOD(get__NewEnum)(IUnknown** ppUnk);
```

### <a name="parameters"></a>パラメーター

*ppUnk*<br/>
入出力新しく作成された列挙子オブジェクトの **IUnknown** ポインターです。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

新しく作成された列挙子は、元のコレクション (つまり `m_coll` 、コピーが作成されません) に対して反復子を保持し、コレクションオブジェクトに COM 参照を保持して、未処理の列挙子がある間もコレクションが生きたままになるようにします。

## <a name="icollectiononstlimplm_coll"></a><a name="m_coll"></a> ICollectionOnSTLImpl:: m_coll

このメンバーは、コレクションによって表される項目を保持します。

```
CollType m_coll;
```

## <a name="see-also"></a>関連項目

[ATLCollections サンプル](../../overview/visual-cpp-samples.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
