---
description: '詳細情報: CRBMap クラス'
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
ms.openlocfilehash: 55d96bfd2c7b043bdbdc4c1ee1f329c9b77b9ca9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141051"
---
# <a name="crbmap-class"></a>CRBMap クラス

このクラスは、Red-Black バイナリツリーを使用するマッピング構造体を表します。

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

*KTraits*<br/>
キー要素をコピーまたは移動するために使用されるコード。 詳細については、「 [Celementtraits クラス](../../atl/reference/celementtraits-class.md) 」を参照してください。

*VTraits*<br/>
値要素をコピーまたは移動するために使用されるコード。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CRBMap::CRBMap](#crbmap)|コンストラクターです。|
|[CRBMap:: ~ CRBMap](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CRBMap:: Lookup](#lookup)|オブジェクト内のキーまたは値を参照するには、このメソッドを呼び出し `CRBMap` ます。|
|[CRBMap:: RemoveKey](#removekey)|キーを指定して、オブジェクトから要素を削除するには、このメソッドを呼び出し `CRBMap` ます。|
|[CRBMap:: SetAt](#setat)|Map に要素ペアを挿入するには、このメソッドを呼び出します。|

## <a name="remarks"></a>解説

`CRBMap` 指定された型のマッピング配列をサポートし、キー要素の順序付けられた配列および関連する値を管理します。 各キーは、関連付けられた値を1つだけ持つことができます。 要素 (キーと値で構成される) は、 [CRBMap:: SetAt](#setat) メソッドを使用してバイナリツリー構造に格納されます。 要素は、 [CRBMap:: removekey](#removekey) メソッドを使用して削除できます。これにより、指定されたキー値を持つ要素が削除されます。

このツリーの走査は、 [crbtree:: GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition)、 [Crbtree:: GetNext](../../atl/reference/crbtree-class.md#getnext)、 [crbtree:: GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue)などのメソッドを使用して行うことができます。

*Ktraits* パラメーターと *vtraits* パラメーターは、要素をコピーまたは移動するために必要な補足コードを含む特徴クラスです。

`CRBMap` は、Red-Black アルゴリズムを使用してバイナリツリーを実装する、 [CRBTree](../../atl/reference/crbtree-class.md)から派生します。 [CRBMultiMap](../../atl/reference/crbmultimap-class.md) は、各キーに対して複数の値を許可するバリエーションです。 また、はから派生しているので `CRBTree` 、多くの機能をと共有し `CRBMap` ます。

との両方の代替手段 `CRBMap` `CRBMultiMap` は、 [CAtlMap](../../atl/reference/catlmap-class.md) クラスによって提供されます。 少数の要素だけを格納する必要がある場合は、代わりに [CSimpleMap](../../atl/reference/csimplemap-class.md) クラスを使用することを検討してください。

さまざまなコレクションクラスとその機能とパフォーマンス特性の詳細については、「 [ATL コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CRBTree](../../atl/reference/crbtree-class.md)

`CRBMap`

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll. h

## <a name="crbmapcrbmap"></a><a name="crbmap"></a> CRBMap::CRBMap

コンストラクターです。

```
explicit CRBMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>パラメーター

*nBlockSize*<br/>
ブロックのサイズです。

### <a name="remarks"></a>解説

*Nblocksize* パラメーターは、新しい要素が必要な場合に割り当てられるメモリの量を測定したものです。 ブロックサイズを大きくすると、メモリ割り当てルーチンの呼び出しが減少しますが、より多くのリソースが使用されます。 既定では、一度に10個の要素に対して領域が割り当てられます。

使用できるその他の方法の詳細については、「」の [基本クラスの](../../atl/reference/crbtree-class.md) ドキュメントを参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#81](../../atl/codesnippet/cpp/crbmap-class_1.cpp)]

## <a name="crbmapcrbmap"></a><a name="dtor"></a> CRBMap:: ~ CRBMap

デストラクターです。

```
~CRBMap() throw();
```

### <a name="remarks"></a>解説

割り当てられたリソースを解放します。

使用できるその他の方法の詳細については、「」の [基本クラスの](../../atl/reference/crbtree-class.md) ドキュメントを参照してください。

## <a name="crbmaplookup"></a><a name="lookup"></a> CRBMap:: Lookup

オブジェクト内のキーまたは値を参照するには、このメソッドを呼び出し `CRBMap` ます。

```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const throw(...);
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>パラメーター

*key*<br/>
検索する要素を識別するキーを指定します。

*value*<br/>
検索対象の値を受け取る変数。

### <a name="return-value"></a>戻り値

メソッドの最初の形式は、キーが見つかった場合は true、それ以外の場合は false を返します。 2番目と3番目のフォームは、 [CPair](crbtree-class.md#cpair_class)へのポインターを返します。

### <a name="remarks"></a>解説

使用できるその他の方法の詳細については、「」の [基本クラスの](../../atl/reference/crbtree-class.md) ドキュメントを参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#82](../../atl/codesnippet/cpp/crbmap-class_2.cpp)]

## <a name="crbmapremovekey"></a><a name="removekey"></a> CRBMap:: RemoveKey

キーを指定して、オブジェクトから要素を削除するには、このメソッドを呼び出し `CRBMap` ます。

```
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>パラメーター

*key*<br/>
削除する要素ペアに対応するキー。

### <a name="return-value"></a>戻り値

キーが見つかって削除された場合は true、失敗した場合は false を返します。

### <a name="remarks"></a>解説

使用できるその他の方法の詳細については、「」の [基本クラスの](../../atl/reference/crbtree-class.md) ドキュメントを参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#83](../../atl/codesnippet/cpp/crbmap-class_3.cpp)]

## <a name="crbmapsetat"></a><a name="setat"></a> CRBMap:: SetAt

Map に要素ペアを挿入するには、このメソッドを呼び出します。

```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
オブジェクトに追加するキー値 `CRBMap` 。

*value*<br/>
オブジェクトに追加する値 `CRBMap` 。

### <a name="return-value"></a>戻り値

オブジェクト内のキーと値の要素のペアの位置を返し `CRBMap` ます。

### <a name="remarks"></a>解説

`SetAt` 一致するキーが見つかった場合は、既存の要素を置き換えます。 キーが見つからない場合は、新しいキーと値のペアが作成されます。

使用できるその他の方法の詳細については、「」の [基本クラスの](../../atl/reference/crbtree-class.md) ドキュメントを参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#84](../../atl/codesnippet/cpp/crbmap-class_4.cpp)]

## <a name="see-also"></a>関連項目

[CRBTree クラス](../../atl/reference/crbtree-class.md)<br/>
[CAtlMap クラス](../../atl/reference/catlmap-class.md)<br/>
[CRBMultiMap クラス](../../atl/reference/crbmultimap-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
