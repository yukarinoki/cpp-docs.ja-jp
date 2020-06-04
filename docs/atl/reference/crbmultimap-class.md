---
title: クラス
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
ms.openlocfilehash: 1e36bc267b3a539d2d1d4bf370b9cdc33828c760
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331429"
---
# <a name="crbmultimap-class"></a>クラス

このクラスは、Red-Black バイナリ ツリーを使用して、各キーを複数の値に関連付けることができるマッピング構造を表します。

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

*クトレイツ*<br/>
キー要素のコピーまたは移動に使用されるコード。 詳細については[、「CElementTraits クラス](../../atl/reference/celementtraits-class.md)」を参照してください。

*VTraits*<br/>
値要素のコピーまたは移動に使用されるコード。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CRBマルチマップ::CRBマルチマップ](#crbmultimap)|コンストラクターです。|
|[CRBマルチマップ::~CRBマルチマップ](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[最初にキーを検索します。](#findfirstwithkey)|指定したキーを持つ最初の要素の位置を検索します。|
|[キーを使用して次に値を取得します。](#getnextvaluewithkey)|指定したキーに関連付けられている値を取得し、位置の値を更新します。|
|[キーを取得します。](#getnextwithkey)|指定したキーに関連付けられている要素を取得し、位置の値を更新します。|
|[挿入](#insert)|マップに要素ペアを挿入します。|
|[キーの削除](#removekey)|指定したキーのすべてのキー/値要素を削除します。|

## <a name="remarks"></a>解説

`CRBMultiMap`は、キー要素と値の順序付けられた配列を管理する、任意の型のマッピング配列をサポートします。 [CRBMap](../../atl/reference/crbmap-class.md)クラスとは異なり、各キーは複数の値に関連付けることができます。

要素 (キーと値で構成される) は[、CRBMultiMap::Insert](#insert)メソッドを使用して、バイナリ ツリー構造に格納されます。 要素は、指定されたキーに一致するすべての要素を削除する[CRBMultiMap::RemoveKey](#removekey)メソッドを使用して削除できます。

ツリーのトラバースは[、CRBツリー:::GetHeadPosition、CRB](../../atl/reference/crbtree-class.md#getheadposition)[ツリー::次の](../../atl/reference/crbtree-class.md#getnext)メソッド、[および CRBツリー::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue)などのメソッドで可能になります。 キーごとに潜在的に複数の値にアクセスするには[、CRBMultiMap::FindFirstWithKey、CRBMultiMap::GetNextValueWithKey](#findfirstwithkey)、および[CRBMultiMap::GetNextWithKey](#getnextwithkey)メソッドを使用できます。 [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey) 実際にこの図を示す例については[、CRBMultiMap::CRBMultiMap](#crbmultimap)を参照してください。

*KTraits*パラメーターと*VTraits*パラメーターは、要素のコピーまたは移動に必要な補足コードを含む traits クラスです。

`CRBMultiMap`は、赤黒アルゴリズムを使用してバイナリ ツリーを実装する[CRBTree](../../atl/reference/crbtree-class.md)から派生します。 [CAtlMap](../../atl/reference/catlmap-class.md)クラスの代わり`CRBMultiMap`として提供`CRBMap`されます。 格納する必要がある要素が少数の場合は[、CSimpleMap](../../atl/reference/csimplemap-class.md)クラスを使用することを検討してください。

さまざまなコレクション クラスとその機能とパフォーマンス特性の詳細については、「 [ATL コレクション クラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[Crbtree](../../atl/reference/crbtree-class.md)

`CRBMultiMap`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="crbmultimapcrbmultimap"></a><a name="crbmultimap"></a>CRBマルチマップ::CRBマルチマップ

コンストラクターです。

```
explicit CRBMultiMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>パラメーター

*ブロックサイズ*<br/>
ブロックのサイズです。

### <a name="remarks"></a>解説

*nBlockSize*パラメーターは、新しい要素が必要なときに割り当てられるメモリの量の測定です。 ブロック サイズが大きくなると、メモリ割り当てルーチンの呼び出しは減りますが、使用するリソースは多くなります。 デフォルトでは、一度に 10 個の要素に対して領域が割り当てられます。

使用可能なその他のメソッドについては、基本クラス[CRBTree](../../atl/reference/crbtree-class.md)のドキュメントを参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#85](../../atl/codesnippet/cpp/crbmultimap-class_1.cpp)]

## <a name="crbmultimapcrbmultimap"></a><a name="dtor"></a>CRBマルチマップ::~CRBマルチマップ

デストラクターです。

```
~CRBMultiMap() throw();
```

### <a name="remarks"></a>解説

割り当てられたリソースを解放します。

使用可能なその他のメソッドについては、基本クラス[CRBTree](../../atl/reference/crbtree-class.md)のドキュメントを参照してください。

## <a name="crbmultimapfindfirstwithkey"></a><a name="findfirstwithkey"></a>最初にキーを検索します。

指定したキーを持つ最初の要素の位置を検索します。

```
POSITION FindFirstWithKey(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>パラメーター

*key*<br/>
見つかる要素を識別するキーを指定します。

### <a name="return-value"></a>戻り値

キーが見つかった場合は最初のキー/値要素の位置を返し、それ以外の場合は NULL を返します。

### <a name="remarks"></a>解説

のキーには、1 つ以上の`CRBMultiMap`値を関連付けることができます。 このメソッドは、その特定のキーに関連付けられた最初の値 (実際には唯一の値) の位置値を提供します。 返される位置の値は、値を取得し、位置を更新するために[、CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)または[CRBMultiMap::GetNextWithKey](#getnextwithkey)で使用できます。

使用可能なその他のメソッドについては、基本クラス[CRBTree](../../atl/reference/crbtree-class.md)のドキュメントを参照してください。

### <a name="example"></a>例

次の例[を](#crbmultimap)参照してください。

## <a name="crbmultimapgetnextvaluewithkey"></a><a name="getnextvaluewithkey"></a>キーを使用して次に値を取得します。

指定したキーに関連付けられている値を取得し、位置の値を更新します。

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
[CRBMultiMap::FindFirstWithKey](#findfirstwithkey)または[CRBMultiMap::GetNextWithKey](#getnextwithkey)、または 以前の呼び出しを呼び出`GetNextValueWithKey`して取得された位置値。

*key*<br/>
見つかる要素を識別するキーを指定します。

### <a name="return-value"></a>戻り値

指定されたキーに関連付けられている要素ペアを返します。

### <a name="remarks"></a>解説

位置の値は、キーに関連付けられた次の値を指すために更新されます。 これ以上値が存在しない場合、位置値は NULL に設定されます。

使用可能なその他のメソッドについては、基本クラス[CRBTree](../../atl/reference/crbtree-class.md)のドキュメントを参照してください。

### <a name="example"></a>例

次の例[を](#crbmultimap)参照してください。

## <a name="crbmultimapgetnextwithkey"></a><a name="getnextwithkey"></a>キーを取得します。

指定したキーに関連付けられている要素を取得し、位置の値を更新します。

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
[CRBMultiMap::FindFirstWithKey](#findfirstwithkey)または[CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)、または 以前の呼び出しを呼び出`GetNextWithKey`して取得される位置値。

*key*<br/>
見つかる要素を識別するキーを指定します。

### <a name="return-value"></a>戻り値

指定されたキーに関連付けられた次の[CRBTree::CPair クラス](crbtree-class.md#cpair_class)要素を返します。

### <a name="remarks"></a>解説

位置の値は、キーに関連付けられた次の値を指すために更新されます。 これ以上値が存在しない場合、位置値は NULL に設定されます。

使用可能なその他のメソッドについては、基本クラス[CRBTree](../../atl/reference/crbtree-class.md)のドキュメントを参照してください。

## <a name="crbmultimapinsert"></a><a name="insert"></a>挿入

マップに要素ペアを挿入します。

```
POSITION Insert(KINARGTYPE key, VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
オブジェクトに追加するキー値`CRBMultiMap`。

*value*<br/>
オブジェクトに追加する値です`CRBMultiMap`*。*

### <a name="return-value"></a>戻り値

オブジェクト内のキー/値要素ペアの位置を`CRBMultiMap`返します。

### <a name="remarks"></a>解説

使用可能なその他のメソッドについては、基本クラス[CRBTree](../../atl/reference/crbtree-class.md)のドキュメントを参照してください。

### <a name="example"></a>例

次の例[を](#crbmultimap)参照してください。

## <a name="crbmultimapremovekey"></a><a name="removekey"></a>キーの削除

指定したキーのすべてのキー/値要素を削除します。

```
size_t RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>パラメーター

*key*<br/>
削除する要素を識別するキーを指定します。

### <a name="return-value"></a>戻り値

指定されたキーに関連付けられた値の数を返します。

### <a name="remarks"></a>解説

`RemoveKey`キー*と一致*するキーを持つすべてのキー/値要素を削除します。

使用可能なその他のメソッドについては、基本クラス[CRBTree](../../atl/reference/crbtree-class.md)のドキュメントを参照してください。

### <a name="example"></a>例

次の例[を](#crbmultimap)参照してください。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/crbtree-class.md)<br/>
[カトルマップクラス](../../atl/reference/catlmap-class.md)<br/>
[CRBMap クラス](../../atl/reference/crbmap-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
