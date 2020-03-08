---
title: CAtlArray クラス
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
ms.openlocfilehash: 6a0b83f722d1b616e9c10713646d337f9cb090a4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78864888"
---
# <a name="catlarray-class"></a>CAtlArray クラス

このクラスは、配列オブジェクトを実装します。

## <a name="syntax"></a>構文

```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlArray
```

#### <a name="parameters"></a>パラメーター

*E*<br/>
配列に格納されるデータの型。

*ETraits*<br/>
要素をコピーまたは移動するために使用するコード。

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[追加](#add)|要素を配列オブジェクトに追加するには、このメソッドを呼び出します。|
|[Append](#append)|ある配列の内容を別の配列の末尾に追加するには、このメソッドを呼び出します。|
|[AssertValid](#assertvalid)|配列オブジェクトが有効であることを確認するには、このメソッドを呼び出します。|
|[CAtlArray](#catlarray)|コンストラクターです。|
|[~ CAtlArray](#dtor)|デストラクターです。|
|[Copy](#copy) に設定する必要があります|1つの配列の要素を別の配列にコピーするには、このメソッドを呼び出します。|
|[FreeExtra](#freeextra)|空の要素を配列から削除するには、このメソッドを呼び出します。|
|[GetAt](#getat)|配列オブジェクトから1つの要素を取得するには、このメソッドを呼び出します。|
|[GetCount](#getcount)|配列に格納されている要素の数を返すには、このメソッドを呼び出します。|
|[GetData](#getdata)|配列内の最初の要素へのポインターを返すには、このメソッドを呼び出します。|
|[InsertArrayAt](#insertarrayat)|1つの配列を別の配列に挿入するには、このメソッドを呼び出します。|
|[InsertAt](#insertat)|このメソッドを呼び出して、新しい要素 (または要素の複数のコピー) を配列オブジェクトに挿入します。|
|[IsEmpty](#isempty)|配列が空かどうかをテストするには、このメソッドを呼び出します。|
|[RemoveAll](#removeall)|配列オブジェクトからすべての要素を削除するには、このメソッドを呼び出します。|
|[RemoveAt](#removeat)|配列から1つ以上の要素を削除するには、このメソッドを呼び出します。|
|[SetAt](#setat)|配列オブジェクトの要素の値を設定するには、このメソッドを呼び出します。|
|[SetAtGrow](#setatgrow)|配列オブジェクトの要素の値を設定するには、このメソッドを呼び出し、必要に応じて配列を展開します。|
|[SetCount](#setcount)|配列オブジェクトのサイズを設定するには、このメソッドを呼び出します。|

### <a name="operators"></a>オペレーター

|||
|-|-|
|[operator&#91;&#93;](#operator_at)|配列内の要素への参照を返すには、この演算子を呼び出します。|

### <a name="typedefs"></a>Typedefs

|||
|-|-|
|[INARGTYPE](#inargtype)|配列に要素を追加するために使用するデータ型。|
|[OUTARGTYPE](#outargtype)|配列から要素を取得するために使用するデータ型。|

## <a name="remarks"></a>解説

`CAtlArray` には、ユーザー定義型の要素の配列を作成および管理するためのメソッドが用意されています。 標準 C 配列に似ていますが、`CAtlArray` オブジェクトは必要に応じて動的に縮小および拡張できます。 配列インデックスは、常に位置0から開始し、上限は固定するか、新しい要素が追加されたときに拡張することができます。

要素の数が少ない配列の場合、ATL クラス[CSimpleArray](../../atl/reference/csimplearray-class.md)を使用できます。

`CAtlArray` は MFC の `CArray` クラスに密接に関連しており、シリアル化はサポートされていませんが、MFC プロジェクトでは機能します。

詳細については、「 [ATL コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll. h

##  <a name="add"></a>CAtlArray:: Add

要素を配列オブジェクトに追加するには、このメソッドを呼び出します。

```
size_t Add(INARGTYPE element);
size_t Add();
```

### <a name="parameters"></a>パラメーター

*element*<br/>
配列に追加する要素。

### <a name="return-value"></a>戻り値

追加された要素のインデックスを返します。

### <a name="remarks"></a>解説

新しい要素が配列の末尾に追加されます。 要素が指定されていない場合は、空の要素が追加されます。つまり、実際の要素が追加されているかのように、配列のサイズが大きくなります。 操作が失敗した場合は、引数 E_OUTOFMEMORY を指定して[Atlthrow](debugging-and-error-reporting-global-functions.md#atlthrow)が呼び出されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#1](../../atl/codesnippet/cpp/catlarray-class_1.cpp)]

##  <a name="append"></a>CAtlArray:: Append

ある配列の内容を別の配列の末尾に追加するには、このメソッドを呼び出します。

```
size_t Append(const CAtlArray<E, ETraits>& aSrc);
```

### <a name="parameters"></a>パラメーター

*aSrc*<br/>
追加する配列。

### <a name="return-value"></a>戻り値

追加された最初の要素のインデックスを返します。

### <a name="remarks"></a>解説

指定した配列内の要素が、既存の配列の末尾に追加されます。 必要に応じて、新しい要素を格納するためにメモリが割り当てられます。

配列は同じ型である必要があり、それ自体に配列を追加することはできません。

デバッグビルドでは、`CAtlArray` 引数が有効な配列でない場合、または*Asrc*が同じオブジェクトを参照する場合、ATLASSERT が発生します。 リリースビルドでは、無効な引数が原因で予期しない動作が発生する可能性があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#2](../../atl/codesnippet/cpp/catlarray-class_2.cpp)]

##  <a name="assertvalid"></a>CAtlArray:: AssertValid

配列オブジェクトが有効であることを確認するには、このメソッドを呼び出します。

```
void AssertValid() const;
```

### <a name="remarks"></a>解説

配列オブジェクトが有効でない場合、ATLASSERT はアサーションをスローします。 このメソッドは、_DEBUG が定義されている場合にのみ使用できます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#3](../../atl/codesnippet/cpp/catlarray-class_3.cpp)]

##  <a name="catlarray"></a>CAtlArray::CAtlArray

コンストラクターです。

```
CAtlArray() throw();
```

### <a name="remarks"></a>解説

配列オブジェクトを初期化します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#4](../../atl/codesnippet/cpp/catlarray-class_4.cpp)]

##  <a name="dtor"></a>CAtlArray:: ~ CAtlArray

デストラクターです。

```
~CAtlArray() throw();
```

### <a name="remarks"></a>解説

配列オブジェクトによって使用されているすべてのリソースを解放します。

##  <a name="copy"></a>CAtlArray:: Copy

1つの配列の要素を別の配列にコピーするには、このメソッドを呼び出します。

```
void Copy(const CAtlArray<E, ETraits>& aSrc);
```

### <a name="parameters"></a>パラメーター

*aSrc*<br/>
配列にコピーする要素のソース。

### <a name="remarks"></a>解説

1つの配列の要素を別の配列の要素で上書きするには、このメソッドを呼び出します。 必要に応じて、新しい要素を格納するためにメモリが割り当てられます。 配列の要素をそれ自体にコピーすることはできません。

配列の既存の内容を保持する場合は、代わりに[CAtlArray:: Append](#append)を使用します。

デバッグビルドでは、既存の `CAtlArray` オブジェクトが有効でない場合、または*Asrc*が同じオブジェクトを参照している場合に、ATLASSERT が発生します。 リリースビルドでは、無効な引数が原因で予期しない動作が発生する可能性があります。

> [!NOTE]
> `CAtlArray::Copy` は、 [CAutoPtr](../../atl/reference/cautoptr-class.md)クラスを使用して作成された要素で構成される配列をサポートしていません。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#5](../../atl/codesnippet/cpp/catlarray-class_5.cpp)]

##  <a name="freeextra"></a>CAtlArray:: FreeExtra

空の要素を配列から削除するには、このメソッドを呼び出します。

```
void FreeExtra() throw();
```

### <a name="remarks"></a>解説

空の要素は削除されますが、配列のサイズと上限は変更されません。

デバッグビルドでは、CAtlArray オブジェクトが有効でない場合、または配列の最大サイズを超える場合は、ATLASSERT が発生します。

##  <a name="getat"></a>CAtlArray:: GetAt

配列オブジェクトから1つの要素を取得するには、このメソッドを呼び出します。

```
const E& GetAt(size_t iElement) const throw();
E& GetAt(size_t iElement) throw();
```

### <a name="parameters"></a>パラメーター

*iElement*<br/>
返される配列要素のインデックス値。

### <a name="return-value"></a>戻り値

必須の配列要素への参照を返します。

### <a name="remarks"></a>解説

デバッグビルドでは、 *Ielement*が配列内の要素の数を超えると ATLASSERT が発生します。 リリースビルドでは、無効な引数が原因で予期しない動作が発生する可能性があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#6](../../atl/codesnippet/cpp/catlarray-class_6.cpp)]

##  <a name="getcount"></a>CAtlArray:: GetCount

配列に格納されている要素の数を返すには、このメソッドを呼び出します。

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>戻り値

配列に格納されている要素の数を返します。

### <a name="remarks"></a>解説

配列内の最初の要素は0の位置にあるため、`GetCount` によって返される値は常に、最大のインデックスよりも1大きい値になります。

### <a name="example"></a>例

[CAtlArray:: GetAt](#getat)の例を参照してください。

##  <a name="getdata"></a>CAtlArray:: GetData

配列内の最初の要素へのポインターを返すには、このメソッドを呼び出します。

```
E* GetData() throw();
const E* GetData() const throw();
```

### <a name="return-value"></a>戻り値

配列内の最初の要素を格納しているメモリ位置へのポインターを返します。 使用可能な要素がない場合は、NULL が返されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#7](../../atl/codesnippet/cpp/catlarray-class_7.cpp)]

##  <a name="inargtype"></a>CAtlArray:: INARGTYPE

配列に要素を追加するために使用するデータ型。

```
typedef ETraits::INARGTYPE INARGTYPE;
```

##  <a name="insertarrayat"></a>CAtlArray:: InsertArrayAt

1つの配列を別の配列に挿入するには、このメソッドを呼び出します。

```
void InsertArrayAt(size_t iStart, const CAtlArray<E, ETraits>* paNew);
```

### <a name="parameters"></a>パラメーター

*iStart*<br/>
配列が挿入される位置のインデックス。

*paNew*<br/>
挿入する配列。

### <a name="remarks"></a>解説

配列*panew*の要素は、要素から始まる配列オブジェクトにコピーされます。 既存の配列要素は、上書きされないように移動されます。

デバッグビルドでは、`CAtlArray` オブジェクトが有効でない場合、または*PANEW*ポインターが NULL であるか無効である場合に、が発生します。

> [!NOTE]
> `CAtlArray::InsertArrayAt` は、 [CAutoPtr](../../atl/reference/cautoptr-class.md)クラスを使用して作成された要素で構成される配列をサポートしていません。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#8](../../atl/codesnippet/cpp/catlarray-class_8.cpp)]

##  <a name="insertat"></a>CAtlArray:: InsertAt

このメソッドを呼び出して、新しい要素 (または要素の複数のコピー) を配列オブジェクトに挿入します。

```
void InsertAt(size_t iElement, INARGTYPE element, size_t nCount = 1);
```

### <a name="parameters"></a>パラメーター

*iElement*<br/>
要素または要素が挿入されるインデックス。

*element*<br/>
挿入される要素の値。

*nCount*<br/>
追加する要素の数。

### <a name="remarks"></a>解説

インデックス*Ielement*を開始位置として、配列に1つ以上の要素を挿入します。 既存の要素は、上書きされないように移動されます。

デバッグビルドでは、`CAtlArray` オブジェクトが無効である場合、追加される要素の数が0の場合、または要素の合計数が大きすぎて配列に格納できない場合に、ATLASSERT が発生します。 リテールビルドでは、無効なパラメーターを渡すと、予測できない結果が発生する可能性があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#9](../../atl/codesnippet/cpp/catlarray-class_9.cpp)]

##  <a name="isempty"></a>CAtlArray:: IsEmpty

配列が空かどうかをテストするには、このメソッドを呼び出します。

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>戻り値

配列が空の場合は true、それ以外の場合は false を返します。

### <a name="remarks"></a>解説

配列に要素が含まれていない場合、配列は空であると見なされます。 したがって、配列に空の要素が含まれている場合でも、空ではありません。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#10](../../atl/codesnippet/cpp/catlarray-class_10.cpp)]

##  <a name="operator_at"></a>CAtlArray:: operator []

配列内の要素への参照を返すには、この演算子を呼び出します。

```
E& operator[](size_t ielement) throw();
const E& operator[](size_t ielement) const throw();
```

### <a name="parameters"></a>パラメーター

*iElement*<br/>
返される配列要素のインデックス値。

### <a name="return-value"></a>戻り値

必須の配列要素への参照を返します。

### <a name="remarks"></a>解説

[CAtlArray:: GetAt](#getat)と同様の関数を実行します。 MFC クラス[CArray](../../mfc/reference/carray-class.md)とは異なり、この演算子を[CAtlArray:: SetAt](#setat)の代替として使用することはできません。

デバッグビルドでは、 *Ielement*が配列内の要素の合計数を超えると ATLASSERT が発生します。 リテールビルドでは、無効なパラメーターが原因で予期しない結果が発生する可能性があります。

##  <a name="outargtype"></a>CAtlArray:: OUTARGTYPE

配列から要素を取得するために使用するデータ型。

```
typedef ETraits::OUTARGTYPE OUTARGTYPE;
```

##  <a name="removeall"></a>CAtlArray:: RemoveAll

配列オブジェクトからすべての要素を削除するには、このメソッドを呼び出します。

```
void RemoveAll() throw();
```

### <a name="remarks"></a>解説

配列オブジェクトからすべての要素を削除します。

このメソッドは、 [CAtlArray:: SetCount](#setcount)を呼び出して配列のサイズを変更した後、割り当てられたメモリを解放します。

### <a name="example"></a>例

[CAtlArray:: IsEmpty](#isempty)の例を参照してください。

##  <a name="removeat"></a>CAtlArray:: RemoveAt

配列から1つ以上の要素を削除するには、このメソッドを呼び出します。

```
void RemoveAt(size_t iElement, size_t nCount = 1);
```

### <a name="parameters"></a>パラメーター

*iElement*<br/>
削除する最初の要素のインデックス。

*nCount*<br/>
削除する要素の数を指定します。

### <a name="remarks"></a>解説

配列から1つ以上の要素を削除します。 残りの要素はすべて下に移動されます。 上限はデクリメントされますが、 [CAtlArray:: FreeExtra](#freeextra)の呼び出しが行われるまで、メモリは解放されません。

デバッグビルドでは、`CAtlArray` オブジェクトが有効でない場合、または*Ielement*と*nCount*の合計が配列内の要素の合計数を超えた場合に、ATLASSERT が発生します。 リテールビルドでは、無効なパラメーターが原因で予期しない結果が発生する可能性があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#11](../../atl/codesnippet/cpp/catlarray-class_11.cpp)]

##  <a name="setat"></a>CAtlArray:: SetAt

配列オブジェクトの要素の値を設定するには、このメソッドを呼び出します。

```
void SetAt(size_t iElement, INARGTYPE element);
```

### <a name="parameters"></a>パラメーター

*iElement*<br/>
設定する配列要素を指すインデックス。

*element*<br/>
指定された要素の新しい値。

### <a name="remarks"></a>解説

デバッグビルドでは、 *Ielement*が配列内の要素の数を超えると ATLASSERT が発生します。 リテールビルドでは、無効なパラメーターが原因で予測できない結果になる場合があります。

### <a name="example"></a>例

[CAtlArray:: GetAt](#getat)の例を参照してください。

##  <a name="setcount"></a>CAtlArray:: SetCount

配列オブジェクトのサイズを設定するには、このメソッドを呼び出します。

```
bool SetCount(size_t nNewSize, int nGrowBy = - 1);
```

### <a name="parameters"></a>パラメーター

*nNewSize*<br/>
配列の必要なサイズ。

*nGrowBy*<br/>
バッファーのサイズを決定するために使用される値。 値-1 を指定すると、内部的に計算される値が使用されます。

### <a name="return-value"></a>戻り値

配列のサイズが正常に変更された場合は true、それ以外の場合は false を返します。

### <a name="remarks"></a>解説

配列のサイズを増減することができます。 増加した場合は、余分な空の要素が配列に追加されます。 値が小さくなると、インデックスの最大値を持つ要素が削除され、メモリが解放されます。

使用する前に配列のサイズを設定するには、このメソッドを使用します。 `SetCount` が使用されていない場合、要素を追加するプロセスとその後に実行されるメモリ割り当ては、パフォーマンスとフラグメントメモリを削減します。

### <a name="example"></a>例

[CAtlArray:: GetData](#getdata)の例を参照してください。

##  <a name="setatgrow"></a>CAtlArray::SetAtGrow

配列オブジェクトの要素の値を設定するには、このメソッドを呼び出し、必要に応じて配列を展開します。

```
void SetAtGrow(size_t iElement, INARGTYPE element);
```

### <a name="parameters"></a>パラメーター

*iElement*<br/>
設定する配列要素を指すインデックス。

*element*<br/>
指定された要素の新しい値。

### <a name="remarks"></a>解説

インデックスが指す要素の値を置き換えます。 *Ielement*が配列の現在のサイズより大きい場合、 [CAtlArray:: setcount](#setcount)の呼び出しを使用して配列が自動的に増加します。 デバッグビルドでは、`CAtlArray` オブジェクトが有効でない場合に ATLASSERT が発生します。 リテールビルドでは、無効なパラメーターが原因で予期しない結果が発生する可能性があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#12](../../atl/codesnippet/cpp/catlarray-class_12.cpp)]

## <a name="see-also"></a>参照

[MMXSwarm サンプル](../../overview/visual-cpp-samples.md)<br/>
[DynamicConsumer サンプル](../../overview/visual-cpp-samples.md)<br/>
[UpdatePV サンプル](../../overview/visual-cpp-samples.md)<br/>
[Marquee サンプル](../../overview/visual-cpp-samples.md)<br/>
[CArray クラス](../../mfc/reference/carray-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
