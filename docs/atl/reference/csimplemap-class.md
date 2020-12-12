---
description: '詳細情報: CSimpleMap クラス'
title: CSimpleMap クラス
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
ms.openlocfilehash: 66640e3fcd325d59b82a10d98188a6fcd74ca79d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140622"
---
# <a name="csimplemap-class"></a>CSimpleMap クラス

このクラスは、単純なマッピング配列をサポートします。

## <a name="syntax"></a>構文

```
template <class TKey, class TVal, class TEqual = CSimpleMapEqualHelper<TKey, TVal>>
class CSimpleMap
```

#### <a name="parameters"></a>パラメーター

*TKey*<br/>
キー要素の型。

*TVal*<br/>
値要素の型。

*TEqual*<br/>
型の要素に対する等値テストを定義する特徴オブジェクト `T` 。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CSimpleMap:: _ArrayElementType](#_arrayelementtype)|値型の Typedef。|
|[CSimpleMap:: _ArrayKeyType](#_arraykeytype)|キーの型の Typedef。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSimpleMap::CSimpleMap](#csimplemap)|コンストラクターです。|
|[CSimpleMap:: ~ CSimpleMap](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSimpleMap:: Add](#add)|マップ配列にキーと関連付けられた値を追加します。|
|[CSimpleMap:: FindKey](#findkey)|特定のキーを検索します。|
|[CSimpleMap:: FindVal](#findval)|特定の値を検索します。|
|[CSimpleMap:: GetKeyAt](#getkeyat)|指定されたキーを取得します。|
|[CSimpleMap:: GetSize](#getsize)|マッピング配列内のエントリの数を返します。|
|[CSimpleMap:: GetValueAt](#getvalueat)|指定された値を取得します。|
|[CSimpleMap:: Lookup](#lookup)|指定されたキーに関連付けられている値を返します。|
|[CSimpleMap:: Remove](#remove)|キーと一致する値を削除します。|
|[CSimpleMap:: RemoveAll](#removeall)|すべてのキーと値を削除します。|
|[CSimpleMap:: RemoveAt](#removeat)|特定のキーと一致する値を削除します。|
|[CSimpleMap::ReverseLookup](#reverselookup)|指定された値に関連付けられているキーを返します。|
|[CSimpleMap:: SetAt](#setat)|指定されたキーに関連付けられている値を設定します。|
|[CSimpleMap::SetAtIndex](#setatindex)|特定のキーと値を設定します。|

## <a name="remarks"></a>解説

`CSimpleMap` 指定された任意の型の単純なマッピング配列をサポートし `T` 、順序付けられていないキー要素の配列および関連する値を管理します。

パラメーターは、 `TEqual` 型の2つの要素に対して等値関数を定義する手段を提供し `T` ます。 [CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md)に類似したクラスを作成することにより、任意の配列の等値テストの動作を変更できます。 たとえば、ポインターの配列を処理するときに、ポインターが参照する値に応じて等価性を定義すると便利な場合があります。 既定の実装では、 **operator = = ()** が利用されます。

`CSimpleMap`と[CSimpleArray](../../atl/reference/csimplearray-class.md)は、以前の ATL リリースとの互換性のために用意されています。また、 [CAtlArray](../../atl/reference/catlarray-class.md)と[CAtlMap](../../atl/reference/catlmap-class.md)によって、より完全かつ効率的なコレクション実装が提供されます。

ATL および MFC の他のマップコレクションとは異なり、このクラスは単純な配列を使用して実装され、検索検索には線形検索が必要です。 `CAtlMap` 配列に多数の要素が含まれている場合は、を使用する必要があります。

## <a name="requirements"></a>要件

**ヘッダー:** atl. h

## <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#91](../../atl/codesnippet/cpp/csimplemap-class_1.cpp)]

## <a name="csimplemapadd"></a><a name="add"></a> CSimpleMap:: Add

マップ配列にキーと関連付けられた値を追加します。

```
BOOL Add(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
キー。

*val*<br/>
関連付けられた値。

### <a name="return-value"></a>戻り値

キーと値が正常に追加された場合は TRUE、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

各キーと値のペアが追加されると、それぞれのデータが常に連続して格納されるように、マッピング配列のメモリが解放されて再割り当てされます。 つまり、2番目の key 要素は常に、メモリ内の最初のキー要素の直後になります。

## <a name="csimplemap_arrayelementtype"></a><a name="_arrayelementtype"></a> CSimpleMap:: _ArrayElementType

キーの型の typedef。

```
typedef TVal _ArrayElementType;
```

## <a name="csimplemap_arraykeytype"></a><a name="_arraykeytype"></a> CSimpleMap:: _ArrayKeyType

値型の typedef。

```
typedef TKey _ArrayKeyType;
```

## <a name="csimplemapcsimplemap"></a><a name="csimplemap"></a> CSimpleMap::CSimpleMap

コンストラクターです。

```
CSimpleMap();
```

### <a name="remarks"></a>解説

データメンバーを初期化します。

## <a name="csimplemapcsimplemap"></a><a name="dtor"></a> CSimpleMap:: ~ CSimpleMap

デストラクターです。

```
~CSimpleMap();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放します。

## <a name="csimplemapfindkey"></a><a name="findkey"></a> CSimpleMap:: FindKey

特定のキーを検索します。

```
int FindKey(const TKey& key) const;
```

### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー。

### <a name="return-value"></a>戻り値

見つかった場合は、キーのインデックスを返します。それ以外の場合は-1 を返します。

## <a name="csimplemapfindval"></a><a name="findval"></a> CSimpleMap:: FindVal

特定の値を検索します。

```
int FindVal(const TVal& val) const;
```

### <a name="parameters"></a>パラメーター

*val*<br/>
検索する値。

### <a name="return-value"></a>戻り値

値が見つかった場合は、そのインデックスを返します。それ以外の場合は-1 を返します。

## <a name="csimplemapgetkeyat"></a><a name="getkeyat"></a> CSimpleMap:: GetKeyAt

指定したインデックス位置にあるキーを取得します。

```
TKey& GetKeyAt(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
返すキーのインデックス。

### <a name="return-value"></a>戻り値

*NIndex* によって参照されているキーを返します。

### <a name="remarks"></a>解説

*NIndex* で渡されるインデックスは、戻り値が意味を持つために有効である必要があります。

## <a name="csimplemapgetsize"></a><a name="getsize"></a> CSimpleMap:: GetSize

マッピング配列内のエントリの数を返します。

```
int GetSize() const;
```

### <a name="return-value"></a>戻り値

マッピング配列内のエントリの数 (キーと値が1つのエントリ) を返します。

## <a name="csimplemapgetvalueat"></a><a name="getvalueat"></a> CSimpleMap:: GetValueAt

特定のインデックスにある値を取得します。

```
TVal& GetValueAt(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
返される値のインデックス。

### <a name="return-value"></a>戻り値

は、 *nIndex* によって参照される値を返します。

### <a name="remarks"></a>解説

*NIndex* で渡されるインデックスは、戻り値が意味を持つために有効である必要があります。

## <a name="csimplemaplookup"></a><a name="lookup"></a> CSimpleMap:: Lookup

指定されたキーに関連付けられている値を返します。

```
TVal Lookup(const TKey& key) const;
```

### <a name="parameters"></a>パラメーター

*key*<br/>
キー。

### <a name="return-value"></a>戻り値

関連付けられた値を返します。 一致するキーが見つからない場合は、NULL が返されます。

## <a name="csimplemapremove"></a><a name="remove"></a> CSimpleMap:: Remove

キーと一致する値を削除します。

```
BOOL Remove(const TKey& key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
キー。

### <a name="return-value"></a>戻り値

キーと一致する値が正常に削除された場合は TRUE、それ以外の場合は FALSE を返します。

## <a name="csimplemapremoveall"></a><a name="removeall"></a> CSimpleMap:: RemoveAll

すべてのキーと値を削除します。

```cpp
void RemoveAll();
```

### <a name="remarks"></a>解説

マッピング配列オブジェクトからすべてのキーと値を削除します。

## <a name="csimplemapremoveat"></a><a name="removeat"></a> CSimpleMap:: RemoveAt

指定したインデックス位置にあるキーと関連付けられた値を削除します。

```
BOOL RemoveAt(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
削除するキーと関連付けられた値のインデックス。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、指定されたインデックスが無効なインデックスの場合は FALSE を返します。

## <a name="csimplemapreverselookup"></a><a name="reverselookup"></a> CSimpleMap::ReverseLookup

指定された値に関連付けられているキーを返します。

```
TKey ReverseLookup(const TVal& val) const;
```

### <a name="parameters"></a>パラメーター

*val*<br/>
値。

### <a name="return-value"></a>戻り値

関連付けられたキーを返します。 一致するキーが見つからない場合は、NULL が返されます。

## <a name="csimplemapsetat"></a><a name="setat"></a> CSimpleMap:: SetAt

指定されたキーに関連付けられている値を設定します。

```
BOOL SetAt(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
キー。

*val*<br/>
割り当てる新しい値。

### <a name="return-value"></a>戻り値

キーが見つかった場合は TRUE を返し、値が正常に変更された場合は FALSE を返します。それ以外の場合は FALSE を返します。

## <a name="csimplemapsetatindex"></a><a name="setatindex"></a> CSimpleMap::SetAtIndex

指定したインデックス位置にあるキーと値を設定します。

```
BOOL SetAtIndex(
    int nIndex,
    const TKey& key,
    const TVal& val);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
変更するキーと値のペアを参照するインデックス。

*key*<br/>
新しいキーです。

*val*<br/>
新しい値。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、インデックスが有効でない場合は FALSE を返します。

### <a name="remarks"></a>解説

は、 *nIndex* が指すキーと値の両方を更新します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
