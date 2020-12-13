---
description: '詳細情報: CRBMultiMap クラス'
title: CRBMultiMap クラス
ms.date: 11/04/2016
f1_keywords:
- CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::FindFirstWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextValueWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextWithKey
- ATLCOLL/ATL::CRBMultiMap::Insert
- ATLCOLL/ATL::CRBMultiMap::RemoveKey
helpviewer_keywords:
- CRBMultiMap class
ms.assetid: 94d3ec0c-3e30-4ab7-a101-d8da4fb8add3
ms.openlocfilehash: 8dfe644521cb7ec4135c5c1f71d36371ac1706ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141025"
---
# <a name="crbmultimap-class"></a>CRBMultiMap クラス

このクラスは、Red-Black バイナリツリーを使用して、各キーを複数の値に関連付けることができるようにするマッピング構造を表します。

## <a name="syntax"></a>構文

```
template<typename K,
         typename V,
         class KTraits = CElementTraits<K>,
         class VTraits = CElementTraits<V>>
class CRBMultiMap : public CRBTree<K, V, KTraits, VTraits>
```

#### <a name="parameters"></a>パラメーター

*K*<br/>
キー要素の型。

*V*<br/>
値要素の型。

*KTraits*<br/>
キー要素をコピーまたは移動するために使用されるコード。 詳細については、「 [Celementtraits クラス](../../atl/reference/celementtraits-class.md) 」を参照してください。

*VTraits*<br/>
値要素をコピーまたは移動するために使用されるコード。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CRBMultiMap::CRBMultiMap](#crbmultimap)|コンストラクターです。|
|[CRBMultiMap:: ~ CRBMultiMap](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CRBMultiMap:: FindFirstWithKey](#findfirstwithkey)|指定したキーを持つ最初の要素の位置を検索するには、このメソッドを呼び出します。|
|[CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)|特定のキーに関連付けられている値を取得し、位置の値を更新するには、このメソッドを呼び出します。|
|[CRBMultiMap::GetNextWithKey](#getnextwithkey)|指定したキーに関連付けられている要素を取得し、位置の値を更新するには、このメソッドを呼び出します。|
|[CRBMultiMap:: Insert](#insert)|Map に要素ペアを挿入するには、このメソッドを呼び出します。|
|[CRBMultiMap:: RemoveKey](#removekey)|指定したキーのすべてのキー/値要素を削除するには、このメソッドを呼び出します。|

## <a name="remarks"></a>解説

`CRBMultiMap` 指定された型のマッピング配列をサポートし、キー要素と値の順序付けられた配列を管理します。 [CRBMap](../../atl/reference/crbmap-class.md)クラスとは異なり、各キーは複数の値に関連付けることができます。

要素 (キーと値で構成される) は、 [CRBMultiMap:: Insert](#insert) メソッドを使用してバイナリツリー構造で格納されます。 要素は、 [CRBMultiMap:: removekey](#removekey) メソッドを使用して削除できます。これにより、指定されたキーに一致するすべての要素が削除されます。

このツリーの走査は、 [crbtree:: GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition)、 [Crbtree:: GetNext](../../atl/reference/crbtree-class.md#getnext)、 [crbtree:: GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue)などのメソッドを使用して行うことができます。 [CRBMultiMap:: FindFirstWithKey](#findfirstwithkey)、 [CRBMultiMap:: GetNextValueWithKey](#getnextvaluewithkey)、 [CRBMultiMap:: GetNextWithKey](#getnextwithkey)の各メソッドを使用して、キーごとに複数の値にアクセスできます。 実際の例については、 [CRBMultiMap:: CRBMultiMap](#crbmultimap) の例を参照してください。

*Ktraits* パラメーターと *vtraits* パラメーターは、要素をコピーまたは移動するために必要な補足コードを含む特徴クラスです。

`CRBMultiMap` は、Red-Black アルゴリズムを使用してバイナリツリーを実装する、 [CRBTree](../../atl/reference/crbtree-class.md)から派生します。 およびの代替 `CRBMultiMap` 手段 `CRBMap` は、 [CAtlMap](../../atl/reference/catlmap-class.md) クラスによって提供されます。 少数の要素だけを格納する必要がある場合は、代わりに [CSimpleMap](../../atl/reference/csimplemap-class.md) クラスを使用することを検討してください。

さまざまなコレクションクラスとその機能とパフォーマンス特性の詳細については、「 [ATL コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CRBTree](../../atl/reference/crbtree-class.md)

`CRBMultiMap`

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll. h

## <a name="crbmultimapcrbmultimap"></a><a name="crbmultimap"></a> CRBMultiMap::CRBMultiMap

コンストラクターです。

```
explicit CRBMultiMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>パラメーター

*nBlockSize*<br/>
ブロックのサイズです。

### <a name="remarks"></a>解説

*Nblocksize* パラメーターは、新しい要素が必要な場合に割り当てられるメモリの量を測定したものです。 ブロックサイズを大きくすると、メモリ割り当てルーチンの呼び出しが減少しますが、より多くのリソースが使用されます。 既定では、一度に10個の要素に対して領域が割り当てられます。

使用できるその他の方法の詳細については、「」の [基本クラスの](../../atl/reference/crbtree-class.md) ドキュメントを参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#85](../../atl/codesnippet/cpp/crbmultimap-class_1.cpp)]

## <a name="crbmultimapcrbmultimap"></a><a name="dtor"></a> CRBMultiMap:: ~ CRBMultiMap

デストラクターです。

```
~CRBMultiMap() throw();
```

### <a name="remarks"></a>解説

割り当てられたリソースを解放します。

使用できるその他の方法の詳細については、「」の [基本クラスの](../../atl/reference/crbtree-class.md) ドキュメントを参照してください。

## <a name="crbmultimapfindfirstwithkey"></a><a name="findfirstwithkey"></a> CRBMultiMap:: FindFirstWithKey

指定したキーを持つ最初の要素の位置を検索するには、このメソッドを呼び出します。

```
POSITION FindFirstWithKey(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>パラメーター

*key*<br/>
検索する要素を識別するキーを指定します。

### <a name="return-value"></a>戻り値

キーが見つかった場合は、最初のキー/値要素の位置を返します。それ以外の場合は NULL を返します。

### <a name="remarks"></a>解説

内のキーに `CRBMultiMap` は、1つまたは複数の値を関連付けることができます。 このメソッドは、その特定のキーに関連付けられている最初の値 (実際には唯一の値) の位置の値を提供します。 返された位置の値を [CRBMultiMap:: GetNextValueWithKey](#getnextvaluewithkey) または [CRBMultiMap:: GetNextWithKey](#getnextwithkey) と共に使用して値を取得し、位置を更新することができます。

使用できるその他の方法の詳細については、「」の [基本クラスの](../../atl/reference/crbtree-class.md) ドキュメントを参照してください。

### <a name="example"></a>例

[CRBMultiMap:: CRBMultiMap](#crbmultimap)の例を参照してください。

## <a name="crbmultimapgetnextvaluewithkey"></a><a name="getnextvaluewithkey"></a> CRBMultiMap::GetNextValueWithKey

特定のキーに関連付けられている値を取得し、位置の値を更新するには、このメソッドを呼び出します。

```
const V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
[CRBMultiMap:: FindFirstWithKey](#findfirstwithkey)または[CRBMultiMap:: GetNextWithKey](#getnextwithkey)を呼び出すか、以前にを呼び出したときに取得される位置の値 `GetNextValueWithKey` 。

*key*<br/>
検索する要素を識別するキーを指定します。

### <a name="return-value"></a>戻り値

指定されたキーに関連付けられている要素ペアを返します。

### <a name="remarks"></a>解説

位置の値は、キーに関連付けられている次の値を指すように更新されます。 それ以上値が存在しない場合は、position 値が NULL に設定されます。

使用できるその他の方法の詳細については、「」の [基本クラスの](../../atl/reference/crbtree-class.md) ドキュメントを参照してください。

### <a name="example"></a>例

[CRBMultiMap:: CRBMultiMap](#crbmultimap)の例を参照してください。

## <a name="crbmultimapgetnextwithkey"></a><a name="getnextwithkey"></a> CRBMultiMap::GetNextWithKey

特定のキーに関連付けられた要素を取得し、位置の値を更新するには、このメソッドを呼び出します。

```
const CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
[CRBMultiMap:: FindFirstWithKey](#findfirstwithkey)または[CRBMultiMap:: GetNextValueWithKey](#getnextvaluewithkey)を呼び出すか、以前にを呼び出したときに取得される位置の値 `GetNextWithKey` 。

*key*<br/>
検索する要素を識別するキーを指定します。

### <a name="return-value"></a>戻り値

指定されたキーに関連付けられている、次の [CRBTree:: CPair Class](crbtree-class.md#cpair_class) 要素を返します。

### <a name="remarks"></a>解説

位置の値は、キーに関連付けられている次の値を指すように更新されます。 それ以上値が存在しない場合は、position 値が NULL に設定されます。

使用できるその他の方法の詳細については、「」の [基本クラスの](../../atl/reference/crbtree-class.md) ドキュメントを参照してください。

## <a name="crbmultimapinsert"></a><a name="insert"></a> CRBMultiMap:: Insert

Map に要素ペアを挿入するには、このメソッドを呼び出します。

```
POSITION Insert(KINARGTYPE key, VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
オブジェクトに追加するキー値 `CRBMultiMap` 。

*value*<br/>
`CRBMultiMap`*キー* に関連付けられた、オブジェクトに追加する値。

### <a name="return-value"></a>戻り値

オブジェクト内のキーと値の要素のペアの位置を返し `CRBMultiMap` ます。

### <a name="remarks"></a>解説

使用できるその他の方法の詳細については、「」の [基本クラスの](../../atl/reference/crbtree-class.md) ドキュメントを参照してください。

### <a name="example"></a>例

[CRBMultiMap:: CRBMultiMap](#crbmultimap)の例を参照してください。

## <a name="crbmultimapremovekey"></a><a name="removekey"></a> CRBMultiMap:: RemoveKey

指定したキーのすべてのキー/値要素を削除するには、このメソッドを呼び出します。

```
size_t RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>パラメーター

*key*<br/>
削除する要素を識別するキーを指定します。

### <a name="return-value"></a>戻り値

指定されたキーに関連付けられている値の数を返します。

### <a name="remarks"></a>解説

`RemoveKey`*キーと一致する* キーを持つキー/値要素をすべて削除します。

使用できるその他の方法の詳細については、「」の [基本クラスの](../../atl/reference/crbtree-class.md) ドキュメントを参照してください。

### <a name="example"></a>例

[CRBMultiMap:: CRBMultiMap](#crbmultimap)の例を参照してください。

## <a name="see-also"></a>関連項目

[CRBTree クラス](../../atl/reference/crbtree-class.md)<br/>
[CAtlMap クラス](../../atl/reference/catlmap-class.md)<br/>
[CRBMap クラス](../../atl/reference/crbmap-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
