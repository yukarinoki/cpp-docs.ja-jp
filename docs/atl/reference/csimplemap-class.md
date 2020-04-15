---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayElementType
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayKeyType
- ATLSIMPCOLL/ATL::CSimpleMap::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::Add
- ATLSIMPCOLL/ATL::CSimpleMap::FindKey
- ATLSIMPCOLL/ATL::CSimpleMap::FindVal
- ATLSIMPCOLL/ATL::CSimpleMap::GetKeyAt
- ATLSIMPCOLL/ATL::CSimpleMap::GetSize
- ATLSIMPCOLL/ATL::CSimpleMap::GetValueAt
- ATLSIMPCOLL/ATL::CSimpleMap::Lookup
- ATLSIMPCOLL/ATL::CSimpleMap::Remove
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleMap::ReverseLookup
- ATLSIMPCOLL/ATL::CSimpleMap::SetAt
- ATLSIMPCOLL/ATL::CSimpleMap::SetAtIndex
helpviewer_keywords:
- CSimpleMap class
ms.assetid: 61b06eb4-ae73-44b0-a305-0afb5a33e8b1
ms.openlocfilehash: b8650f36ac3d190207870616754dcd596cb7cc45
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330802"
---
# <a name="csimplemap-class"></a>クラス

このクラスは、単純なマッピング配列をサポートします。

## <a name="syntax"></a>構文

```
template <class TKey, class TVal, class TEqual = CSimpleMapEqualHelper<TKey, TVal>>
class CSimpleMap
```

#### <a name="parameters"></a>パラメーター

*Tkey*<br/>
キー要素の型。

*TVal*<br/>
値要素の型。

*TEqual*<br/>
型の要素の等価性テストを定義する特性オブジェクト`T`。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[シンプルマップ::_ArrayElementType](#_arrayelementtype)|値型の Typedef。|
|[シンプルマップ::_ArrayKeyType](#_arraykeytype)|キーの型の型定義。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[シンプルマップ::Cシンプルマップ](#csimplemap)|コンストラクターです。|
|[シンプルマップ::~シンプルマップ](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[シンプルマップ::追加](#add)|マップ配列にキーと関連する値を追加します。|
|[シンプルマップ::キーを検索](#findkey)|特定のキーを検索します。|
|[シンプルマップ::FindVal](#findval)|特定の値を検索します。|
|[シンプルマップ::ゲットキーアット](#getkeyat)|指定したキーを取得します。|
|[シンプルマップ::ゲットサイズ](#getsize)|マッピング配列のエントリ数を返します。|
|[を使用します。](#getvalueat)|指定した値を取得します。|
|[単一のマップ::ルックアップ](#lookup)|指定されたキーに関連付けられた値を返します。|
|[シンプルマップ::削除](#remove)|キーと一致する値を削除します。|
|[シンプルマップ::すべて削除](#removeall)|すべてのキーと値を削除します。|
|[シンプルマップ::削除アット](#removeat)|特定のキーと一致する値を削除します。|
|[単一のマップ::逆ルックアップ](#reverselookup)|指定された値に関連付けられたキーを返します。|
|[シンプルマップ::セットアット](#setat)|指定したキーに関連付けられた値を設定します。|
|[シンプルマップ::セットアインデックス](#setatindex)|特定のキーと値を設定します。|

## <a name="remarks"></a>解説

`CSimpleMap`は、任意の型`T`の単純なマッピング配列をサポートします。

このパラメーター`TEqual`は、型の 2 つの要素に対して等価関数を`T`定義する手段を提供します。 [CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md)に似たクラスを作成することで、任意の配列の等価性テストの動作を変更できます。 たとえば、ポインターの配列を扱う場合、ポインターが参照する値に応じて等値を定義すると便利です。 デフォルトの実装では **、operator==() を**使用します。

CSimpleArray と`CSimpleMap` [CSimpleArray](../../atl/reference/csimplearray-class.md)の両方が以前の ATL リリースとの互換性のために提供されており、より完全で効率的なコレクションの実装は[、CAtlArray](../../atl/reference/catlarray-class.md)と[CAtlMap](../../atl/reference/catlmap-class.md)によって提供されます。

ATL および MFC の他のマップ コレクションとは異なり、このクラスは単純な配列で実装され、検索検索には線形検索が必要です。 `CAtlMap`配列に多数の要素が含まれている場合に使用する必要があります。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsimpcoll.h

## <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#91](../../atl/codesnippet/cpp/csimplemap-class_1.cpp)]

## <a name="csimplemapadd"></a><a name="add"></a>シンプルマップ::追加

マップ配列にキーと関連する値を追加します。

```
BOOL Add(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
キーです。

*ヴァル*<br/>
関連付けられた値。

### <a name="return-value"></a>戻り値

キーと値が正常に追加された場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

キーと値のペアを追加するたびに、マッピング配列のメモリが解放され、再割り当てされ、それぞれのデータが常に連続して格納されるようにします。 つまり、2 番目のキー要素は常にメモリ内の最初のキー要素に直接従います。

## <a name="csimplemap_arrayelementtype"></a><a name="_arrayelementtype"></a>シンプルマップ::_ArrayElementType

キーの型の型定義。

```
typedef TVal _ArrayElementType;
```

## <a name="csimplemap_arraykeytype"></a><a name="_arraykeytype"></a>シンプルマップ::_ArrayKeyType

値型の型定義。

```
typedef TKey _ArrayKeyType;
```

## <a name="csimplemapcsimplemap"></a><a name="csimplemap"></a>シンプルマップ::Cシンプルマップ

コンストラクターです。

```
CSimpleMap();
```

### <a name="remarks"></a>解説

データ メンバーを初期化します。

## <a name="csimplemapcsimplemap"></a><a name="dtor"></a>シンプルマップ::~シンプルマップ

デストラクターです。

```
~CSimpleMap();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放します。

## <a name="csimplemapfindkey"></a><a name="findkey"></a>シンプルマップ::キーを検索

特定のキーを検索します。

```
int FindKey(const TKey& key) const;
```

### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー。

### <a name="return-value"></a>戻り値

見つかった場合はキーのインデックスを返し、それ以外の場合は -1 を返します。

## <a name="csimplemapfindval"></a><a name="findval"></a>シンプルマップ::FindVal

特定の値を検索します。

```
int FindVal(const TVal& val) const;
```

### <a name="parameters"></a>パラメーター

*ヴァル*<br/>
検索する値。

### <a name="return-value"></a>戻り値

見つかった場合は値のインデックスを返し、それ以外の場合は -1 を返します。

## <a name="csimplemapgetkeyat"></a><a name="getkeyat"></a>シンプルマップ::ゲットキーアット

指定したインデックス位置にあるキーを取得します。

```
TKey& GetKeyAt(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
返すキーのインデックス。

### <a name="return-value"></a>戻り値

*nIndex*によって参照されるキーを返します。

### <a name="remarks"></a>解説

*nIndex*によって渡されるインデックスは、戻り値を意味のあるものにするために有効である必要があります。

## <a name="csimplemapgetsize"></a><a name="getsize"></a>シンプルマップ::ゲットサイズ

マッピング配列のエントリ数を返します。

```
int GetSize() const;
```

### <a name="return-value"></a>戻り値

マッピング配列内のエントリ数 (キーと値は 1 エントリ) を返します。

## <a name="csimplemapgetvalueat"></a><a name="getvalueat"></a>を使用します。

特定のインデックス位置にある値を取得します。

```
TVal& GetValueAt(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
返す値のインデックス。

### <a name="return-value"></a>戻り値

*nIndex*によって参照される値を返します。

### <a name="remarks"></a>解説

*nIndex*によって渡されるインデックスは、戻り値を意味のあるものにするために有効である必要があります。

## <a name="csimplemaplookup"></a><a name="lookup"></a>単一のマップ::ルックアップ

指定されたキーに関連付けられた値を返します。

```
TVal Lookup(const TKey& key) const;
```

### <a name="parameters"></a>パラメーター

*key*<br/>
キーです。

### <a name="return-value"></a>戻り値

関連付けられた値を返します。 一致するキーが見つからない場合は、NULL が返されます。

## <a name="csimplemapremove"></a><a name="remove"></a>シンプルマップ::削除

キーと一致する値を削除します。

```
BOOL Remove(const TKey& key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
キーです。

### <a name="return-value"></a>戻り値

キーと一致する値が正常に削除された場合は TRUE を返し、それ以外の場合は FALSE を返します。

## <a name="csimplemapremoveall"></a><a name="removeall"></a>シンプルマップ::すべて削除

すべてのキーと値を削除します。

```
void RemoveAll();
```

### <a name="remarks"></a>解説

マッピング配列オブジェクトからすべてのキーと値を削除します。

## <a name="csimplemapremoveat"></a><a name="removeat"></a>シンプルマップ::削除アット

指定したインデックス位置にあるキーと関連付けられた値を削除します。

```
BOOL RemoveAt(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
削除するキーと関連付けられた値のインデックス。

### <a name="return-value"></a>戻り値

指定されたインデックスが無効なインデックスの場合は、成功時に TRUE を返します。

## <a name="csimplemapreverselookup"></a><a name="reverselookup"></a>単一のマップ::逆ルックアップ

指定された値に関連付けられたキーを返します。

```
TKey ReverseLookup(const TVal& val) const;
```

### <a name="parameters"></a>パラメーター

*ヴァル*<br/>
値。

### <a name="return-value"></a>戻り値

関連付けられたキーを返します。 一致するキーが見つからない場合は、NULL が返されます。

## <a name="csimplemapsetat"></a><a name="setat"></a>シンプルマップ::セットアット

指定したキーに関連付けられた値を設定します。

```
BOOL SetAt(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
キーです。

*ヴァル*<br/>
割り当てる新しい値。

### <a name="return-value"></a>戻り値

キーが見つかり、値が正常に変更された場合は TRUE を返します。

## <a name="csimplemapsetatindex"></a><a name="setatindex"></a>シンプルマップ::セットアインデックス

指定したインデックス位置にキーと値を設定します。

```
BOOL SetAtIndex(
    int nIndex,
    const TKey& key,
    const TVal& val);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
変更するキーと値の組み合わせを参照するインデックス。

*key*<br/>
新しいキーです。

*ヴァル*<br/>
新しい値です。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、インデックスが有効でない場合は FALSE を返します。

### <a name="remarks"></a>解説

*nIndex*が指すキーと値の両方を更新します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
