---
title: CRBMap クラス
ms.date: 11/04/2016
f1_keywords:
- CRBMap
- ATLCOLL/ATL::CRBMap
- ATLCOLL/ATL::CRBMap::CRBMap
- ATLCOLL/ATL::CRBMap::Lookup
- ATLCOLL/ATL::CRBMap::RemoveKey
- ATLCOLL/ATL::CRBMap::SetAt
helpviewer_keywords:
- CRBMap class
ms.assetid: 658e94dc-e835-4356-aed1-1513e1f66969
ms.openlocfilehash: 9e367ccc875eedf63e4f47018598662af2dfcf7d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331400"
---
# <a name="crbmap-class"></a>CRBMap クラス

このクラスは、Red-Black バイナリ ツリーを使用してマッピング構造を表します。

## <a name="syntax"></a>構文

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CRBMap : public CRBTree<K, V, KTraits, VTraits>
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
|[CRBマップ::CRBマップ](#crbmap)|コンストラクターです。|
|[CRBマップ::~CRBマップ](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CRBマップ::ルックアップ](#lookup)|`CRBMap`オブジェクト内のキーまたは値を検索します。|
|[キーの削除](#removekey)|キーを指定して、オブジェクトから要素を`CRBMap`削除します。|
|[CRBマップ::セットアット](#setat)|マップに要素ペアを挿入します。|

## <a name="remarks"></a>解説

`CRBMap`は、キー要素とその関連値の順序付けられた配列を管理する、任意の型のマッピング配列をサポートします。 各キーには、1 つの値しか関連付けできません。 要素 (キーと値で構成される) は[、CRBMap::SetAt](#setat)メソッドを使用して、バイナリ ツリー構造に格納されます。 要素は、指定されたキー値を持つ要素を削除する[CRBMap::RemoveKey](#removekey)メソッドを使用して削除できます。

ツリーのトラバースは[、CRBツリー:::GetHeadPosition、CRB](../../atl/reference/crbtree-class.md#getheadposition)[ツリー::次の](../../atl/reference/crbtree-class.md#getnext)メソッド、[および CRBツリー::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue)などのメソッドで可能になります。

*KTraits*パラメーターと*VTraits*パラメーターは、要素のコピーまたは移動に必要な補足コードを含む traits クラスです。

`CRBMap`は、赤黒アルゴリズムを使用してバイナリ ツリーを実装する[CRBTree](../../atl/reference/crbtree-class.md)から派生します。 [CRBMultiMap](../../atl/reference/crbmultimap-class.md)は、各キーに複数の値を許可するバリエーションです。 それも`CRBTree`から派生しているので、多くの機能を`CRBMap`と共有します。

両方`CRBMap`に代わるもの`CRBMultiMap`と[、CAtlMap](../../atl/reference/catlmap-class.md)クラスによって提供されています。 格納する必要がある要素が少数の場合は[、CSimpleMap](../../atl/reference/csimplemap-class.md)クラスを使用することを検討してください。

さまざまなコレクション クラスとその機能とパフォーマンス特性の詳細については、「 [ATL コレクション クラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[Crbtree](../../atl/reference/crbtree-class.md)

`CRBMap`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="crbmapcrbmap"></a><a name="crbmap"></a>CRBマップ::CRBマップ

コンストラクターです。

```
explicit CRBMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>パラメーター

*ブロックサイズ*<br/>
ブロックのサイズです。

### <a name="remarks"></a>解説

*nBlockSize*パラメーターは、新しい要素が必要なときに割り当てられるメモリの量の測定です。 ブロック サイズが大きくなると、メモリ割り当てルーチンの呼び出しは減りますが、使用するリソースは多くなります。 デフォルトでは、一度に 10 個の要素に対して領域が割り当てられます。

使用可能なその他のメソッドについては、基本クラス[CRBTree](../../atl/reference/crbtree-class.md)のドキュメントを参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#81](../../atl/codesnippet/cpp/crbmap-class_1.cpp)]

## <a name="crbmapcrbmap"></a><a name="dtor"></a>CRBマップ::~CRBマップ

デストラクターです。

```
~CRBMap() throw();
```

### <a name="remarks"></a>解説

割り当てられたリソースを解放します。

使用可能なその他のメソッドについては、基本クラス[CRBTree](../../atl/reference/crbtree-class.md)のドキュメントを参照してください。

## <a name="crbmaplookup"></a><a name="lookup"></a>CRBマップ::ルックアップ

`CRBMap`オブジェクト内のキーまたは値を検索します。

```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const throw(...);
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>パラメーター

*key*<br/>
検索する要素を識別するキーを指定します。

*value*<br/>
検索された値を受け取る変数。

### <a name="return-value"></a>戻り値

メソッドの最初の形式は、キーが見つかった場合は true を返し、それ以外の場合は false を返します。 2 番目と 3 番目の形式は[、CPair](crbtree-class.md#cpair_class)へのポインターを返します。

### <a name="remarks"></a>解説

使用可能なその他のメソッドについては、基本クラス[CRBTree](../../atl/reference/crbtree-class.md)のドキュメントを参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#82](../../atl/codesnippet/cpp/crbmap-class_2.cpp)]

## <a name="crbmapremovekey"></a><a name="removekey"></a>キーの削除

キーを指定して、オブジェクトから要素を`CRBMap`削除します。

```
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>パラメーター

*key*<br/>
削除する要素ペアに対応するキー。

### <a name="return-value"></a>戻り値

キーが見つかり、削除された場合は true を返し、失敗した場合は false を返します。

### <a name="remarks"></a>解説

使用可能なその他のメソッドについては、基本クラス[CRBTree](../../atl/reference/crbtree-class.md)のドキュメントを参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#83](../../atl/codesnippet/cpp/crbmap-class_3.cpp)]

## <a name="crbmapsetat"></a><a name="setat"></a>CRBマップ::セットアット

マップに要素ペアを挿入します。

```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
オブジェクトに追加するキー値`CRBMap`。

*value*<br/>
オブジェクトに追加する`CRBMap`値。

### <a name="return-value"></a>戻り値

オブジェクト内のキー/値要素ペアの位置を`CRBMap`返します。

### <a name="remarks"></a>解説

`SetAt`一致するキーが見つかった場合は、既存の要素を置き換えます。 キーが見つからない場合は、新しいキー/値ペアが作成されます。

使用可能なその他のメソッドについては、基本クラス[CRBTree](../../atl/reference/crbtree-class.md)のドキュメントを参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#84](../../atl/codesnippet/cpp/crbmap-class_4.cpp)]

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/crbtree-class.md)<br/>
[カトルマップクラス](../../atl/reference/catlmap-class.md)<br/>
[クラス](../../atl/reference/crbmultimap-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
