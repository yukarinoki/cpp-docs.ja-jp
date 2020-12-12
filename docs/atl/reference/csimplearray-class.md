---
description: '詳細情報: CSimpleArray クラス'
title: CSimpleArray クラス
ms.date: 11/04/2016
f1_keywords:
- CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::Add
- ATLSIMPCOLL/ATL::CSimpleArray::Find
- ATLSIMPCOLL/ATL::CSimpleArray::GetData
- ATLSIMPCOLL/ATL::CSimpleArray::GetSize
- ATLSIMPCOLL/ATL::CSimpleArray::Remove
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleArray::SetAtIndex
helpviewer_keywords:
- CSimpleArray class
ms.assetid: ee0c9f39-b61c-4c18-bc43-4eada21dca3a
ms.openlocfilehash: 95750662587c7ab47500a338c3ecd7e74a92eb34
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140791"
---
# <a name="csimplearray-class"></a>CSimpleArray クラス

このクラスには、単純な配列を管理するためのメソッドが用意されています。

## <a name="syntax"></a>構文

```
template <class T, class TEqual = CSimpleArrayEqualHelper<T>>
class CSimpleArray
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
配列に格納するデータの型。

*TEqual*<br/>
型 *T* の要素に対する等値テストを定義する特徴オブジェクト。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSimpleArray::CSimpleArray](#csimplearray)|単純な配列のコンストラクター。|
|[CSimpleArray:: ~ CSimpleArray](#dtor)|単純な配列のデストラクター。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSimpleArray:: Add](#add)|配列に新しい要素を追加します。|
|[CSimpleArray:: Find](#find)|配列内の要素を検索します。|
|[CSimpleArray:: GetData](#getdata)|配列に格納されているデータへのポインターを返します。|
|[CSimpleArray:: GetSize](#getsize)|配列に格納されている要素の数を返します。|
|[CSimpleArray:: Remove](#remove)|指定された要素を配列から削除します。|
|[CSimpleArray:: RemoveAll](#removeall)|配列からすべての要素を削除します。|
|[CSimpleArray:: RemoveAt](#removeat)|指定した要素を配列から削除します。|
|[CSimpleArray::SetAtIndex](#setatindex)|配列内の指定した要素を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CSimpleArray::operator\[\]](#operator_at)|配列から要素を取得します。|
|[CSimpleArray:: operator =](#operator_eq)|代入演算子。|

## <a name="remarks"></a>解説

`CSimpleArray` 任意の型の単純な配列を作成および管理するためのメソッドを提供し `T` ます。

パラメーターは、 `TEqual` 型の2つの要素に対して等値関数を定義する手段を提供し `T` ます。 [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)に類似したクラスを作成することにより、任意の配列の等値テストの動作を変更できます。 たとえば、ポインターの配列を処理するときに、ポインターが参照する値に応じて等価性を定義すると便利な場合があります。 既定の実装では、 **operator = ()** が利用されます。

`CSimpleArray`と[CSimpleMap](../../atl/reference/csimplemap-class.md)の両方が、少数の要素に対して設計されています。 配列に多数の要素が含まれている場合は、 [CAtlArray](../../atl/reference/catlarray-class.md)と[CAtlMap](../../atl/reference/catlmap-class.md)を使用する必要があります。

## <a name="requirements"></a>要件

**ヘッダー:** atl. h

## <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#86](../../atl/codesnippet/cpp/csimplearray-class_1.cpp)]

## <a name="csimplearrayadd"></a><a name="add"></a> CSimpleArray:: Add

配列に新しい要素を追加します。

```
BOOL Add(const T& t);
```

### <a name="parameters"></a>パラメーター

*t*<br/>
配列に追加する要素。

### <a name="return-value"></a>戻り値

要素が配列に正常に追加された場合は TRUE、それ以外の場合は FALSE を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#87](../../atl/codesnippet/cpp/csimplearray-class_2.cpp)]

## <a name="csimplearraycsimplearray"></a><a name="csimplearray"></a> CSimpleArray::CSimpleArray

配列オブジェクトのコンストラクター。

```
CSimpleArray(const CSimpleArray<T, TEqual>& src);
CSimpleArray();
```

### <a name="parameters"></a>パラメーター

*src*<br/>
既存の `CSimpleArray` オブジェクトです。

### <a name="remarks"></a>解説

データメンバーを初期化し、新しい空のオブジェクトを作成する `CSimpleArray` か、既存のオブジェクトのコピーを作成 `CSimpleArray` します。

## <a name="csimplearraycsimplearray"></a><a name="dtor"></a> CSimpleArray:: ~ CSimpleArray

デストラクターです。

```
~CSimpleArray();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放します。

## <a name="csimplearrayfind"></a><a name="find"></a> CSimpleArray:: Find

配列内の要素を検索します。

```
int Find(const T& t) const;
```

### <a name="parameters"></a>パラメーター

*t*<br/>
検索対象の要素。

### <a name="return-value"></a>戻り値

見つかった要素のインデックスを返します。要素が見つからない場合は-1 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#88](../../atl/codesnippet/cpp/csimplearray-class_3.cpp)]

## <a name="csimplearraygetdata"></a><a name="getdata"></a> CSimpleArray:: GetData

配列に格納されているデータへのポインターを返します。

```
T* GetData() const;
```

### <a name="return-value"></a>戻り値

配列内のデータへのポインターを返します。

## <a name="csimplearraygetsize"></a><a name="getsize"></a> CSimpleArray:: GetSize

配列に格納されている要素の数を返します。

```
int GetSize() const;
```

### <a name="return-value"></a>戻り値

配列に格納されている要素の数を返します。

## <a name="csimplearrayoperator-"></a><a name="operator_at"></a> CSimpleArray:: operator \[\]

配列から要素を取得します。

```
T& operator[](int nindex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
要素のインデックス。

### <a name="return-value"></a>戻り値

*NIndex* によって参照される配列の要素を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#89](../../atl/codesnippet/cpp/csimplearray-class_4.cpp)]

## <a name="csimplearrayoperator-"></a><a name="operator_eq"></a> CSimpleArray:: operator =

代入演算子。

```
CSimpleArray<T, TEqual>
& operator=(
    const CSimpleArray<T, TEqual>& src);
```

### <a name="parameters"></a>パラメーター

*src*<br/>
コピーする配列。

### <a name="return-value"></a>戻り値

更新されたオブジェクトへのポインターを返し `CSimpleArray` ます。

### <a name="remarks"></a>解説

`CSimpleArray` *Src* によって参照されるオブジェクトのすべての要素を現在の配列オブジェクトにコピーし、既存のすべてのデータを置き換えます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#90](../../atl/codesnippet/cpp/csimplearray-class_5.cpp)]

## <a name="csimplearrayremove"></a><a name="remove"></a> CSimpleArray:: Remove

指定された要素を配列から削除します。

```
BOOL Remove(const T& t);
```

### <a name="parameters"></a>パラメーター

*t*<br/>
配列から削除する要素。

### <a name="return-value"></a>戻り値

要素が見つかって削除された場合は TRUE、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

要素が削除されると、配列内の残りの要素は、空の領域を埋めるために番号が付けられます。

## <a name="csimplearrayremoveall"></a><a name="removeall"></a> CSimpleArray:: RemoveAll

配列からすべての要素を削除します。

```cpp
void RemoveAll();
```

### <a name="remarks"></a>解説

配列に現在格納されているすべての要素を削除します。

## <a name="csimplearrayremoveat"></a><a name="removeat"></a> CSimpleArray:: RemoveAt

指定した要素を配列から削除します。

```
BOOL RemoveAtint nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
削除する要素を指すインデックス。

### <a name="return-value"></a>戻り値

要素が削除された場合は TRUE、インデックスが無効な場合は FALSE を返します。

### <a name="remarks"></a>解説

要素が削除されると、配列内の残りの要素は、空の領域を埋めるために番号が付けられます。

## <a name="csimplearraysetatindex"></a><a name="setatindex"></a> CSimpleArray::SetAtIndex

配列内の指定された要素を設定します。

```
BOOL SetAtIndex(
    int nIndex,
    const T& t);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
変更する要素のインデックス。

*t*<br/>
指定された要素に代入する値。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、インデックスが有効でない場合は FALSE を返します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
