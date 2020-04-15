---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CAtlArray
- ATLCOLL/ATL::CAtlArray
- ATLCOLL/ATL::Add
- ATLCOLL/ATL::Append
- ATLCOLL/ATL::AssertValid
- ATLCOLL/ATL::Copy
- ATLCOLL/ATL::FreeExtra
- ATLCOLL/ATL::GetAt
- ATLCOLL/ATL::GetCount
- ATLCOLL/ATL::GetData
- ATLCOLL/ATL::InsertArrayAt
- ATLCOLL/ATL::InsertAt
- ATLCOLL/ATL::IsEmpty
- ATLCOLL/ATL::RemoveAll
- ATLCOLL/ATL::RemoveAt
- ATLCOLL/ATL::SetAt
- ATLCOLL/ATL::SetAtGrow
- ATLCOLL/ATL::SetCount
- ATLCOLL/ATL::INARGTYPE
- ATLCOLL/ATL::OUTARGTYPE
helpviewer_keywords:
- CAtlArray class
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
ms.openlocfilehash: 85168af654d3d63e06559486b464938b7fd90ad3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321576"
---
# <a name="catlarray-class"></a>クラス

このクラスは、配列オブジェクトを実装します。

## <a name="syntax"></a>構文

```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlArray
```

#### <a name="parameters"></a>パラメーター

*E*<br/>
配列に格納されるデータの型。

*海峡*<br/>
要素をコピーまたは移動するために使用するコード。

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[追加](#add)|配列オブジェクトに要素を追加します。|
|[Append](#append)|ある配列の内容を別の配列の末尾に追加します。|
|[Assertvalid](#assertvalid)|配列オブジェクトが有効であることを確認します。|
|[カトルアレイ](#catlarray)|コンストラクターです。|
|[~カトルアレイ](#dtor)|デストラクターです。|
|[コピー](#copy)|配列の要素を別の配列にコピーします。|
|[フリーエクストラ](#freeextra)|配列から空の要素を削除します。|
|[Getat](#getat)|配列オブジェクトから 1 つの要素を取得します。|
|[GetCount](#getcount)|配列に格納されている要素の数を返します。|
|[GetData](#getdata)|配列の最初の要素へのポインターを返します。|
|[アレイアットを挿入する](#insertarrayat)|配列を別の配列に挿入します。|
|[挿入時](#insertat)|配列オブジェクトに新しい要素 (または要素の複数のコピー) を挿入します。|
|[空っぽ](#isempty)|配列が空かどうかをテストします。|
|[Removeall](#removeall)|配列オブジェクトからすべての要素を削除します。|
|[RemoveAt](#removeat)|配列から 1 つ以上の要素を削除します。|
|[Setat](#setat)|配列オブジェクト内の要素の値を設定します。|
|[セタットグロー](#setatgrow)|配列オブジェクト内の要素の値を設定し、必要に応じて配列を展開します。|
|[カウントを設定します。](#setcount)|配列オブジェクトのサイズを設定します。|

### <a name="operators"></a>オペレーター

|||
|-|-|
|[演算子 &#91;&#93;](#operator_at)|配列内の要素への参照を返します。|

### <a name="typedefs"></a>Typedefs

|||
|-|-|
|[イナルグタイプ](#inargtype)|配列に要素を追加するために使用するデータ型。|
|[アウトアーグタイプ](#outargtype)|配列から要素を取得するために使用するデータ型。|

## <a name="remarks"></a>解説

`CAtlArray`には、ユーザー定義型の要素の配列を作成および管理するためのメソッドが用意されています。 標準の C 配列と同様に`CAtlArray`、オブジェクトは必要に応じて動的に縮小および拡張できます。 配列インデックスは常に位置 0 から始まり、上限は固定するか、新しい要素が追加されると拡張できます。

要素数が少ない配列では、ATL クラス[CSimpleArray を](../../atl/reference/csimplearray-class.md)使用できます。

`CAtlArray`MFC の`CArray`クラスと密接に関連しており、MFC プロジェクトでは動作しますが、シリアル化はサポートしません。

詳細については、「 [ATL コレクション クラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="catlarrayadd"></a><a name="add"></a>カトルアレイ::追加

配列オブジェクトに要素を追加します。

```
size_t Add(INARGTYPE element);
size_t Add();
```

### <a name="parameters"></a>パラメーター

*要素*<br/>
配列に追加する要素。

### <a name="return-value"></a>戻り値

追加された要素のインデックスを返します。

### <a name="remarks"></a>解説

新しい要素が配列の末尾に追加されます。 要素が指定されていない場合は、空の要素が追加されます。つまり、実際の要素が追加されたかのように配列のサイズが大きくなります。 操作が失敗した場合[、AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)は引数E_OUTOFMEMORYを付けて呼び出されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#1](../../atl/codesnippet/cpp/catlarray-class_1.cpp)]

## <a name="catlarrayappend"></a><a name="append"></a>追加

ある配列の内容を別の配列の末尾に追加します。

```
size_t Append(const CAtlArray<E, ETraits>& aSrc);
```

### <a name="parameters"></a>パラメーター

*Asrc*<br/>
追加する配列。

### <a name="return-value"></a>戻り値

最初に追加された要素のインデックスを返します。

### <a name="remarks"></a>解説

指定された配列の要素は、既存の配列の末尾に追加されます。 必要に応じて、新しい要素に対応するためにメモリが割り当てられます。

配列は同じ型である必要があり、配列自体に配列を追加することはできません。

デバッグ ビルドでは、`CAtlArray`引数が有効な配列でない場合、または*aSrc*が同じオブジェクトを参照している場合は、ATLASSERT が発生します。 リリース ビルドでは、無効な引数が予期しない動作を引き起こしうる可能性があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#2](../../atl/codesnippet/cpp/catlarray-class_2.cpp)]

## <a name="catlarrayassertvalid"></a><a name="assertvalid"></a>アサート有効

配列オブジェクトが有効であることを確認します。

```
void AssertValid() const;
```

### <a name="remarks"></a>解説

配列オブジェクトが有効でない場合、ATLASSERT はアサーションをスローします。 このメソッドは、_DEBUGが定義されている場合にのみ使用できます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#3](../../atl/codesnippet/cpp/catlarray-class_3.cpp)]

## <a name="catlarraycatlarray"></a><a name="catlarray"></a>カトルアレイ::カトルアレイ

コンストラクターです。

```
CAtlArray() throw();
```

### <a name="remarks"></a>解説

配列オブジェクトを初期化します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#4](../../atl/codesnippet/cpp/catlarray-class_4.cpp)]

## <a name="catlarraycatlarray"></a><a name="dtor"></a>カトルアレイ::~カトルアレイ

デストラクターです。

```
~CAtlArray() throw();
```

### <a name="remarks"></a>解説

配列オブジェクトが使用するリソースを解放します。

## <a name="catlarraycopy"></a><a name="copy"></a>カトルアレイ::コピー

配列の要素を別の配列にコピーします。

```
void Copy(const CAtlArray<E, ETraits>& aSrc);
```

### <a name="parameters"></a>パラメーター

*Asrc*<br/>
配列にコピーする要素のソース。

### <a name="remarks"></a>解説

ある配列の要素を別の配列の要素で上書きします。 必要に応じて、新しい要素に対応するためにメモリが割り当てられます。 配列の要素をそれ自体にコピーすることはできません。

配列の既存の内容を保持する場合は、代わりに[CAtlArray::Append を](#append)使用します。

デバッグ ビルドでは、既存`CAtlArray`のオブジェクトが有効でない場合、または*aSrc*が同じオブジェクトを参照している場合は、ATLASSERT が発生します。 リリース ビルドでは、無効な引数が予期しない動作を引き起こしうる可能性があります。

> [!NOTE]
> `CAtlArray::Copy`[CAutoPtr](../../atl/reference/cautoptr-class.md)クラスで作成された要素で構成される配列はサポートされていません。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#5](../../atl/codesnippet/cpp/catlarray-class_5.cpp)]

## <a name="catlarrayfreeextra"></a><a name="freeextra"></a>カトルアレイ::フリーエクストラ

配列から空の要素を削除します。

```
void FreeExtra() throw();
```

### <a name="remarks"></a>解説

空の要素は削除されますが、配列のサイズと上限は変更されません。

デバッグ ビルドでは、AtLASSERT が発生する場合、CAtlArray オブジェクトが有効でないか、配列が最大サイズを超える場合。

## <a name="catlarraygetat"></a><a name="getat"></a>カトルアレイ::ゲットアット

配列オブジェクトから 1 つの要素を取得します。

```
const E& GetAt(size_t iElement) const throw();
E& GetAt(size_t iElement) throw();
```

### <a name="parameters"></a>パラメーター

*i要素*<br/>
返す配列要素のインデックス値。

### <a name="return-value"></a>戻り値

必要な配列要素への参照を返します。

### <a name="remarks"></a>解説

デバッグ ビルドでは *、iElement*が配列内の要素の数を超えた場合に ATLASSERT が発生します。 リリース ビルドでは、無効な引数が予期しない動作を招く可能性があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#6](../../atl/codesnippet/cpp/catlarray-class_6.cpp)]

## <a name="catlarraygetcount"></a><a name="getcount"></a>カトルアレイ::ゲットカウント

配列に格納されている要素の数を返します。

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>戻り値

配列に格納されている要素の数を返します。

### <a name="remarks"></a>解説

配列の最初の要素が位置 0 にあるため、返される`GetCount`値は常に最大のインデックスより 1 大きくなります。

### <a name="example"></a>例

[CAtlArray::GetAt](#getat)の例を参照してください。

## <a name="catlarraygetdata"></a><a name="getdata"></a>カトルアレイ::ゲットデータ

配列の最初の要素へのポインターを返します。

```
E* GetData() throw();
const E* GetData() const throw();
```

### <a name="return-value"></a>戻り値

配列の最初の要素を格納しているメモリ位置へのポインターを返します。 使用できる要素がない場合は、NULL が返されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#7](../../atl/codesnippet/cpp/catlarray-class_7.cpp)]

## <a name="catlarrayinargtype"></a><a name="inargtype"></a>カトルアレイ::イナルグタイプ

配列に要素を追加するために使用するデータ型。

```
typedef ETraits::INARGTYPE INARGTYPE;
```

## <a name="catlarrayinsertarrayat"></a><a name="insertarrayat"></a>::挿入配列

配列を別の配列に挿入します。

```
void InsertArrayAt(size_t iStart, const CAtlArray<E, ETraits>* paNew);
```

### <a name="parameters"></a>パラメーター

*Istart*<br/>
配列を挿入するインデックス。

*パ新しい*<br/>
挿入する配列。

### <a name="remarks"></a>解説

配列*paNew*の要素は、要素*iStart*から始めて配列オブジェクトにコピーされます。 既存の配列要素は、上書きされないように移動されます。

デバッグ ビルドでは、`CAtlArray`オブジェクトが無効な場合、または*paNew*ポインターが NULL または無効な場合に ATLASSERT が発生します。

> [!NOTE]
> `CAtlArray::InsertArrayAt`[CAutoPtr](../../atl/reference/cautoptr-class.md)クラスで作成された要素で構成される配列はサポートされていません。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#8](../../atl/codesnippet/cpp/catlarray-class_8.cpp)]

## <a name="catlarrayinsertat"></a><a name="insertat"></a>カトルアレイ::挿入

配列オブジェクトに新しい要素 (または要素の複数のコピー) を挿入します。

```
void InsertAt(size_t iElement, INARGTYPE element, size_t nCount = 1);
```

### <a name="parameters"></a>パラメーター

*i要素*<br/>
要素を挿入するインデックス。

*要素*<br/>
挿入する要素の値。

*nカウント*<br/>
追加する要素の数。

### <a name="remarks"></a>解説

*1*つ以上の要素を配列に挿入します。 既存の要素は上書きされないように移動されます。

デバッグ ビルドでは、`CAtlArray`オブジェクトが無効な場合、追加する要素の数が 0 の場合、または要素の組み合わせの数が大きすぎて配列に格納できない場合、ATLASSERT が発生します。 製品版ビルドでは、無効なパラメーターを渡すと、予期しない結果が生じる可能性があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#9](../../atl/codesnippet/cpp/catlarray-class_9.cpp)]

## <a name="catlarrayisempty"></a><a name="isempty"></a>カトルアレイ::IsEmpty

配列が空かどうかをテストします。

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>戻り値

配列が空の場合は true、それ以外の場合は false を返します。

### <a name="remarks"></a>解説

要素が含まれている場合、配列は空と見なされます。 したがって、配列に空の要素が含まれている場合でも、空ではありません。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#10](../../atl/codesnippet/cpp/catlarray-class_10.cpp)]

## <a name="catlarrayoperator-"></a><a name="operator_at"></a>カトルアレイ::演算子 []

配列内の要素への参照を返します。

```
E& operator[](size_t ielement) throw();
const E& operator[](size_t ielement) const throw();
```

### <a name="parameters"></a>パラメーター

*i要素*<br/>
返す配列要素のインデックス値。

### <a name="return-value"></a>戻り値

必要な配列要素への参照を返します。

### <a name="remarks"></a>解説

[CAtlArray::GetAt](#getat)と同様の関数を実行します。 MFC クラス[CArray](../../mfc/reference/carray-class.md)とは異なり、この演算子は[、CAtlArray::SetAt](#setat)の代用として使用することはできません。

デバッグ ビルドでは *、iElement*が配列内の要素の合計数を超えた場合に ATLASSERT が発生します。 製品版ビルドでは、無効なパラメーターが原因で予期しない結果が生じる場合があります。

## <a name="catlarrayoutargtype"></a><a name="outargtype"></a>カトルアレイ::アウトバーグタイプ

配列から要素を取得するために使用するデータ型。

```
typedef ETraits::OUTARGTYPE OUTARGTYPE;
```

## <a name="catlarrayremoveall"></a><a name="removeall"></a>カトルアレイ::すべての削除

配列オブジェクトからすべての要素を削除します。

```
void RemoveAll() throw();
```

### <a name="remarks"></a>解説

配列オブジェクトからすべての要素を削除します。

このメソッドは、配列のサイズを変更し、その後、割り当てられたすべてのメモリを解放するために[CAtlArray::SetCount](#setcount)を呼び出します。

### <a name="example"></a>例

[次](#isempty)の例を参照してください。

## <a name="catlarrayremoveat"></a><a name="removeat"></a>カトルアレイ::削除アット

配列から 1 つ以上の要素を削除します。

```
void RemoveAt(size_t iElement, size_t nCount = 1);
```

### <a name="parameters"></a>パラメーター

*i要素*<br/>
削除する最初の要素のインデックス。

*nカウント*<br/>
削除する要素の数を指定します。

### <a name="remarks"></a>解説

配列から 1 つ以上の要素を削除します。 残りの要素は下方向にシフトされます。 上限は減分されますが[、CAtlArray::FreeExtra](#freeextra)の呼び出しが行われるまでメモリは解放されません。

デバッグ ビルドでは、`CAtlArray`オブジェクトが有効でない場合、または*iElement*と*nCount*の合計が配列内の要素の合計数を超えた場合に ATLASSERT が発生します。 製品版ビルドでは、無効なパラメーターが原因で予期しない結果が生じる場合があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#11](../../atl/codesnippet/cpp/catlarray-class_11.cpp)]

## <a name="catlarraysetat"></a><a name="setat"></a>カトルアレイ::セットアット

配列オブジェクト内の要素の値を設定します。

```
void SetAt(size_t iElement, INARGTYPE element);
```

### <a name="parameters"></a>パラメーター

*i要素*<br/>
設定する配列要素を指すインデックス。

*要素*<br/>
指定された要素の新しい値。

### <a name="remarks"></a>解説

デバッグ ビルドでは *、iElement*が配列内の要素の数を超えた場合に ATLASSERT が発生します。 製品版ビルドでは、無効なパラメーターを使用すると、予期しない結果が生じる可能性があります。

### <a name="example"></a>例

[CAtlArray::GetAt](#getat)の例を参照してください。

## <a name="catlarraysetcount"></a><a name="setcount"></a>を指定します。

配列オブジェクトのサイズを設定します。

```
bool SetCount(size_t nNewSize, int nGrowBy = - 1);
```

### <a name="parameters"></a>パラメーター

*nNewサイズ*<br/>
配列の必要なサイズ。

*nグローバイ*<br/>
バッファを作成する大きさを決定するために使用される値。 値 -1 を指定すると、内部的に計算された値が使用されます。

### <a name="return-value"></a>戻り値

配列のサイズが正常に変更された場合は true を返し、それ以外の場合は false を返します。

### <a name="remarks"></a>解説

配列のサイズは増減できます。 増加した場合は、余分な空の要素が配列に追加されます。 減少した場合、インデックスが最大の要素は削除され、メモリは解放されます。

このメソッドは、配列を使用する前に配列のサイズを設定するために使います。 使用`SetCount`しない場合、要素を追加するプロセスと、その後実行されるメモリ割り当てによって、パフォーマンスが低下し、メモリが断片化されます。

### <a name="example"></a>例

[次](#getdata)の例を参照してください。

## <a name="catlarraysetatgrow"></a><a name="setatgrow"></a>カトルアレイ::セットアックグロー

配列オブジェクト内の要素の値を設定し、必要に応じて配列を展開します。

```
void SetAtGrow(size_t iElement, INARGTYPE element);
```

### <a name="parameters"></a>パラメーター

*i要素*<br/>
設定する配列要素を指すインデックス。

*要素*<br/>
指定された要素の新しい値。

### <a name="remarks"></a>解説

インデックスが指す要素の値を置き換えます。 *iElement*が配列の現在のサイズより大きい場合、配列は[CAtlArray::SetCount](#setcount)の呼び出しを使用して自動的に増やされます。 デバッグ ビルドでは、`CAtlArray`オブジェクトが有効でない場合に ATLASSERT が発生します。 製品版ビルドでは、無効なパラメーターが原因で予期しない結果が生じる場合があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#12](../../atl/codesnippet/cpp/catlarray-class_12.cpp)]

## <a name="see-also"></a>関連項目

[MMXSwarm サンプル](../../overview/visual-cpp-samples.md)<br/>
[動的コンシューマサンプル](../../overview/visual-cpp-samples.md)<br/>
[アップデートPV サンプル](../../overview/visual-cpp-samples.md)<br/>
[マーキーサンプル](../../overview/visual-cpp-samples.md)<br/>
[Cアレイクラス](../../mfc/reference/carray-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
