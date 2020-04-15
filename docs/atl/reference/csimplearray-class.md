---
title: クラス
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
ms.openlocfilehash: e45c9b3fd778aacd3a3e2d5d3696661afa0c6fb0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330906"
---
# <a name="csimplearray-class"></a>クラス

このクラスは、単純な配列を管理するためのメソッドを提供します。

## <a name="syntax"></a>構文

```
template <class T, class TEqual = CSimpleArrayEqualHelper<T>>
class CSimpleArray
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
配列に格納するデータの型。

*TEqual*<br/>
*T*型の要素の等価性テストを定義する特性オブジェクト。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[::CSimpleアレイ](#csimplearray)|単純な配列のコンストラクター。|
|[::~シンプルアレイ](#dtor)|単純な配列のデストラクター。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を追加します。](#add)|新しい要素を配列に追加します。|
|[を見る](#find)|配列内の要素を検索します。|
|[を取得します。](#getdata)|配列に格納されているデータへのポインターを返します。|
|[次の値を指定します。](#getsize)|配列に格納されている要素の数を返します。|
|[をクリックします。](#remove)|配列から指定された要素を削除します。|
|[すべてを削除します。](#removeall)|配列からすべての要素を削除します。|
|[::削除](#removeat)|指定した要素を配列から削除します。|
|[::セットアインデックス](#setatindex)|配列内の指定した要素を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CSimpleArray::operator\[\]](#operator_at)|配列から要素を取得します。|
|[次の操作を行います。](#operator_eq)|代入演算子。|

## <a name="remarks"></a>解説

`CSimpleArray`には、任意の型の単純な配列を作成および管理するための`T`メソッドが用意されています。

このパラメーター`TEqual`は、型の 2 つの要素に対して等価関数を`T`定義する手段を提供します。 [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)に似たクラスを作成することで、任意の配列の等価性テストの動作を変更できます。 たとえば、ポインターの配列を扱う場合、ポインターが参照する値に応じて等値を定義すると便利です。 デフォルトの実装では **、operator=()** が使用されます。

CSimpleMap と`CSimpleArray`[の](../../atl/reference/csimplemap-class.md)両方が少数の要素用に設計されています。 配列に多数の要素が含まれている場合は[、CAtlArray](../../atl/reference/catlarray-class.md)と[CAtlMap](../../atl/reference/catlmap-class.md)を使用する必要があります。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsimpcoll.h

## <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#86](../../atl/codesnippet/cpp/csimplearray-class_1.cpp)]

## <a name="csimplearrayadd"></a><a name="add"></a>を追加します。

新しい要素を配列に追加します。

```
BOOL Add(const T& t);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
配列に追加する要素。

### <a name="return-value"></a>戻り値

要素が配列に正常に追加された場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#87](../../atl/codesnippet/cpp/csimplearray-class_2.cpp)]

## <a name="csimplearraycsimplearray"></a><a name="csimplearray"></a>::CSimpleアレイ

配列オブジェクトのコンストラクター。

```
CSimpleArray(const CSimpleArray<T, TEqual>& src);
CSimpleArray();
```

### <a name="parameters"></a>パラメーター

*src*<br/>
既存の `CSimpleArray` オブジェクトです。

### <a name="remarks"></a>解説

データ メンバーを初期化し、新しい空`CSimpleArray`のオブジェクトまたは既存`CSimpleArray`のオブジェクトのコピーを作成します。

## <a name="csimplearraycsimplearray"></a><a name="dtor"></a>::~シンプルアレイ

デストラクターです。

```
~CSimpleArray();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放します。

## <a name="csimplearrayfind"></a><a name="find"></a>を見る

配列内の要素を検索します。

```
int Find(const T& t) const;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
検索対象の要素。

### <a name="return-value"></a>戻り値

見つかった要素のインデックスを返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#88](../../atl/codesnippet/cpp/csimplearray-class_3.cpp)]

## <a name="csimplearraygetdata"></a><a name="getdata"></a>を取得します。

配列に格納されているデータへのポインターを返します。

```
T* GetData() const;
```

### <a name="return-value"></a>戻り値

配列内のデータへのポインターを返します。

## <a name="csimplearraygetsize"></a><a name="getsize"></a>次の値を指定します。

配列に格納されている要素の数を返します。

```
int GetSize() const;
```

### <a name="return-value"></a>戻り値

配列に格納されている要素の数を返します。

## <a name="csimplearrayoperator-"></a><a name="operator_at"></a>次の操作を行います。\[\]

配列から要素を取得します。

```
T& operator[](int nindex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
要素のインデックス。

### <a name="return-value"></a>戻り値

*nIndex*によって参照される配列の要素を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#89](../../atl/codesnippet/cpp/csimplearray-class_4.cpp)]

## <a name="csimplearrayoperator-"></a><a name="operator_eq"></a>次の操作を行います。

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

更新された`CSimpleArray`オブジェクトへのポインターを返します。

### <a name="remarks"></a>解説

`CSimpleArray` *src*が参照するオブジェクトのすべての要素を現在の配列オブジェクトにコピーし、既存のすべてのデータを置き換えます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#90](../../atl/codesnippet/cpp/csimplearray-class_5.cpp)]

## <a name="csimplearrayremove"></a><a name="remove"></a>をクリックします。

配列から指定された要素を削除します。

```
BOOL Remove(const T& t);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
配列から削除する要素。

### <a name="return-value"></a>戻り値

要素が見つかり削除された場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

要素が削除されると、配列内の残りの要素の番号が再設定され、空の領域が埋められます。

## <a name="csimplearrayremoveall"></a><a name="removeall"></a>すべてを削除します。

配列からすべての要素を削除します。

```
void RemoveAll();
```

### <a name="remarks"></a>解説

現在配列に格納されているすべての要素を削除します。

## <a name="csimplearrayremoveat"></a><a name="removeat"></a>::削除

指定した要素を配列から削除します。

```
BOOL RemoveAtint nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
削除する要素を指すインデックス。

### <a name="return-value"></a>戻り値

要素が削除された場合は TRUE を返し、インデックスが無効な場合は FALSE を返します。

### <a name="remarks"></a>解説

要素が削除されると、配列内の残りの要素の番号が再設定され、空の領域が埋められます。

## <a name="csimplearraysetatindex"></a><a name="setatindex"></a>::セットアインデックス

配列内の指定された要素を設定します。

```
BOOL SetAtIndex(
    int nIndex,
    const T& t);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
変更する要素のインデックス。

*T*<br/>
指定された要素に代入する値。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、インデックスが有効でない場合は FALSE を返します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
