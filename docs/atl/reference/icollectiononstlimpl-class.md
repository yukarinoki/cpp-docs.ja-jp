---
title: クラス
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
ms.openlocfilehash: a8ccab08b89da8c1b8ef56c8932e27a6c74e62aa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329903"
---
# <a name="icollectiononstlimpl-class"></a>クラス

このクラスは、コレクション クラスで使用されるメソッドを提供します。

## <a name="syntax"></a>構文

```
template <class T, class CollType, class ItemType, class CopyItem, class EnumType>
class ICollectionOnSTLImpl : public T
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
COM コレクション インターフェイス。

*コルタイプ*<br/>
C++ 標準ライブラリ コンテナー クラス。

*Itemtype*<br/>
コンテナー インターフェイスによって公開される項目の型。

*コピーアイテム*<br/>
[コピー ポリシー クラス](../../atl/atl-copy-policy-classes.md)。

*列挙型*<br/>
[互換性](../../atl/reference/ccomenumonstl-class.md)のある列挙子クラス。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コレクションオンストルプル::get__NewEnum](#newenum)|コレクションの列挙子オブジェクトを返します。|
|[コレクションオンストルプル::ゲットカウント](#get_count)|コレクション内の要素の数を返します。|
|[コレクションオンストルプル::get_Item](#get_item)|コレクションから要求された項目を返します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[コレクションオンストルプル::m_coll](#m_coll)|コレクションです。|

## <a name="remarks"></a>解説

このクラスは、コレクション インターフェイスの 3 つのメソッド[getcount](#get_count)の実装[get__NewEnum](#newenum)を提供します[get_Item。](#get_item)

このクラスを使用するには、次の手順に従います。

- 実装するコレクション インターフェイスを定義 (借用) します。

- このコレクション インターフェイスに`ICollectionOnSTLImpl`基づく特殊化からクラスを派生させます。

- 派生クラスを使用して、 で`ICollectionOnSTLImpl`処理されないコレクション インターフェイスからメソッドを実装します。

> [!NOTE]
> コレクション インターフェイスがデュアル インターフェイスの場合は、ATL がメソッドの実装を`ICollectionOnSTLImpl`提供する場合は、最初のテンプレート パラメーターとして特化を渡す`IDispatch`[IDispatchImpl](../../atl/reference/idispatchimpl-class.md)からクラスを派生します。

- コレクションにデータを追加する[m_coll](#m_coll)メンバーに項目を追加します。

詳細と例については、「 [ATL コレクションと列挙子](../../atl/atl-collections-and-enumerators.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`T`

`ICollectionOnSTLImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="icollectiononstlimplgetcount"></a><a name="get_count"></a>コレクションオンストルプル::ゲットカウント

このメソッドは、コレクション内の項目数を返します。

```
STDMETHOD(getcount)(long* pcount);
```

### <a name="parameters"></a>パラメーター

*pcount*<br/>
[アウト]コレクション内の要素の数。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="icollectiononstlimplget_item"></a><a name="get_item"></a>コレクションオンストルプル::get_Item

このメソッドは、指定された項目をコレクションから返します。

```
STDMETHOD(get_Item)(long Index, ItemType* pvar);
```

### <a name="parameters"></a>パラメーター

*インデックス*<br/>
[in]コレクション内の項目の 1 から始まるインデックス。

*プバー*<br/>
[アウト]*インデックス*に対応する項目。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

項目は、特殊化でテンプレート引数として渡された[コピー・ポリシー・クラスのコピー](../../atl/atl-copy-policy-classes.md) ・メソッドを使用して[、m_coll](#m_coll)内の指定された位置にある`ICollectionOnSTLImpl`データをコピーすることによって取得されます。

## <a name="icollectiononstlimplget__newenum"></a><a name="newenum"></a>コレクションオンストルプル::get__NewEnum

コレクションの列挙子オブジェクトを返します。

```
STDMETHOD(get__NewEnum)(IUnknown** ppUnk);
```

### <a name="parameters"></a>パラメーター

*ppUnk*<br/>
[アウト]新しく作成された列挙子オブジェクトの**IUnknown**ポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

新しく作成された列挙子は、元のコレクションの反復子を`m_coll`保持し (コピーは行われず)、コレクション オブジェクトに対する COM 参照を保持して、未処理の列挙子が存在する間もコレクションが保持されるようにします。

## <a name="icollectiononstlimplm_coll"></a><a name="m_coll"></a>コレクションオンストルプル::m_coll

このメンバーは、コレクションによって表される項目を保持します。

```
CollType m_coll;
```

## <a name="see-also"></a>関連項目

[ATL コレクションのサンプル](../../overview/visual-cpp-samples.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
