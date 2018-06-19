---
title: CAtlArray クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlArray class
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ceeaf5250cc9dc5cb4cb25c47b3fe179c7c5295
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365555"
---
# <a name="catlarray-class"></a>CAtlArray クラス
このクラスは、配列オブジェクトを実装します。  
  
## <a name="syntax"></a>構文  
  
```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlArray
```  
  
#### <a name="parameters"></a>パラメーター  
 *E*  
 配列に格納されるデータの型。  
  
 *ETraits*  
 コピーまたは要素を移動するために使用するコードです。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[[追加]](#add)|配列オブジェクトに要素を追加するには、このメソッドを呼び出します。|  
|[追加します。](#append)|別の end に 1 つの配列の内容を追加するには、このメソッドを呼び出します。|  
|[AssertValid](#assertvalid)|配列オブジェクトが有効であることを確認するには、このメソッドを呼び出します。|  
|[CAtlArray](#catlarray)|コンストラクターです。|  
|[~ CAtlArray](#dtor)|デストラクターです。|  
|[コピー](#copy)|1 つの配列の要素をコピーするには、このメソッドを呼び出します。|  
|[FreeExtra](#freeextra)|配列から空の要素を削除するには、このメソッドを呼び出します。|  
|[GetAt](#getat)|Array オブジェクトから 1 つの要素を取得するには、このメソッドを呼び出します。|  
|[GetCount](#getcount)|このメソッドを呼び出して、配列に格納されている要素の数を返します。|  
|[GetData](#getdata)|このメソッドを呼び出して、配列内の最初の要素へのポインターを返します。|  
|[InsertArrayAt](#insertarrayat)|1 つの配列を別に挿入するには、このメソッドを呼び出します。|  
|[InsertAt](#insertat)|配列オブジェクトに新しい要素 (または要素の複数のコピー) を挿入するには、このメソッドを呼び出します。|  
|[IsEmpty](#isempty)|配列が空の場合にテストするには、このメソッドを呼び出します。|  
|[RemoveAll](#removeall)|Array オブジェクトからすべての要素を削除するには、このメソッドを呼び出します。|  
|[RemoveAt](#removeat)|配列から 1 つまたは複数の要素を削除するには、このメソッドを呼び出します。|  
|[SetAt](#setat)|配列オブジェクト要素の値を設定するには、このメソッドを呼び出します。|  
|[SetAtGrow](#setatgrow)|必要に応じて、配列を展開して、配列オブジェクト要素の値を設定するには、このメソッドを呼び出します。|  
|[SetCount](#setcount)|配列オブジェクトのサイズを設定するには、このメソッドを呼び出します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子&#91;&#93;](#operator_at)|配列の要素への参照を返すには、この演算子を呼び出します。|  

  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[INARGTYPE](#inargtype)|配列に要素を追加するのに使用するデータ型。|  
|[OUTARGTYPE](#outargtype)|配列から要素を取得するのに使用するデータ型。|  
  
## <a name="remarks"></a>コメント  
 **CAtlArray**を作成して、ユーザー定義型の要素の配列を管理するメソッドを提供します。 標準の c 言語の配列に似ていますが、 **CAtlArray**オブジェクトを動的に縮小および必要に応じて拡張します。 配列インデックスが常に位置 0 から開始し、上限の境界を修正、または新しい要素が追加される順に展開できることができます。  
  
 ATL クラスの要素の数が少ない配列に対して[CSimpleArray](../../atl/reference/csimplearray-class.md)使用できます。  
  
 **CAtlArray**を MFC の関連性が高い**CArray**クラスし、は、MFC プロジェクトでは、シリアル化をサポートしていないいても動作します。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="add"></a>  CAtlArray::Add  
 配列オブジェクトに要素を追加するには、このメソッドを呼び出します。  
  
```
size_t Add(INARGTYPE element);
size_t Add();
```  
  
### <a name="parameters"></a>パラメーター  
 `element`  
 配列に追加する要素。  
  
### <a name="return-value"></a>戻り値  
 追加された要素のインデックスを返します。  
  
### <a name="remarks"></a>コメント  
 新しい要素は、配列の末尾に追加されます。 要素が提供されない場合、空の要素を追加します。つまり、実際の要素が追加されても、サイズの配列は増加します。 操作が失敗した場合、 [AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow) E_OUTOFMEMORY 引数で呼び出されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#1](../../atl/codesnippet/cpp/catlarray-class_1.cpp)]  
  
##  <a name="append"></a>  CAtlArray::Append  
 別の end に 1 つの配列の内容を追加するには、このメソッドを呼び出します。  
  
```
size_t Append(const CAtlArray<E, ETraits>& aSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `aSrc`  
 追加先の配列。  
  
### <a name="return-value"></a>戻り値  
 追加の最初の要素のインデックスを返します。  
  
### <a name="remarks"></a>コメント  
 指定した配列内の要素は、既存の配列の末尾に追加されます。 必要な場合は、新しい要素のためにメモリが割り当てられます。  
  
 配列自体に追加することはできませんし、同じ種類の配列があります。  
  
 デバッグ ビルドは atlassert 場合、`CAtlArray`引数が有効な配列ではありませんまたは`aSrc`は同じオブジェクトを参照します。 リリース ビルドでは、無効な引数は、予期しない動作に可能性があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#2](../../atl/codesnippet/cpp/catlarray-class_2.cpp)]  
  
##  <a name="assertvalid"></a>  CAtlArray::AssertValid  
 配列オブジェクトが有効であることを確認するには、このメソッドを呼び出します。  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>コメント  
 配列オブジェクトが有効でない場合`ATLASSERT`はアサーションをスローします。 このメソッドは _DEBUG が定義されている場合にのみ使用できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#3](../../atl/codesnippet/cpp/catlarray-class_3.cpp)]  
  
##  <a name="catlarray"></a>  CAtlArray::CAtlArray  
 コンストラクターです。  
  
```
CAtlArray() throw();
```  
  
### <a name="remarks"></a>コメント  
 配列オブジェクトを初期化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#4](../../atl/codesnippet/cpp/catlarray-class_4.cpp)]  
  
##  <a name="dtor"></a>  CAtlArray:: ~ CAtlArray  
 デストラクターです。  
  
```
~CAtlArray() throw();
```  
  
### <a name="remarks"></a>コメント  
 配列オブジェクトによって使用されているリソースを解放します。  
  
##  <a name="copy"></a>  CAtlArray::Copy  
 1 つの配列の要素をコピーするには、このメソッドを呼び出します。  
  
```
void Copy(const CAtlArray<E, ETraits>& aSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `aSrc`  
 配列にコピーする要素のソース。  
  
### <a name="remarks"></a>コメント  
 別の配列の要素と 1 つの配列の要素を上書きするには、このメソッドを呼び出します。 必要な場合は、新しい要素のためにメモリが割り当てられます。 それ自体に、配列の要素をコピーすることはできません。  
  
 配列の既存の内容を保持する場合を使用して[CAtlArray::Append](#append)代わりにします。  
  
 デバッグ ビルドは atlassert 場合既存`CAtlArray`オブジェクトが有効でない場合、または`aSrc`は同じオブジェクトを参照します。 リリース ビルドでは、無効な引数は、予期しない動作に可能性があります。  
  
> [!NOTE]
> `CAtlArray::Copy` 作成された要素から成る配列をサポートしていません、 [CAutoPtr](../../atl/reference/cautoptr-class.md)クラスです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#5](../../atl/codesnippet/cpp/catlarray-class_5.cpp)]  
  
##  <a name="freeextra"></a>  CAtlArray::FreeExtra  
 配列から空の要素を削除するには、このメソッドを呼び出します。  
  
```
void FreeExtra() throw();
```  
  
### <a name="remarks"></a>コメント  
 空の要素は削除されますが、サイズと配列の上限値は変更されません。  
  
 デバッグ ビルドでは、CAtlArray オブジェクトが有効でない場合、または配列の最大サイズを超えてしまう場合 ATLASSERT が生成されます。  
  
##  <a name="getat"></a>  CAtlArray::GetAt  
 呼び出しをするには、このメソッドは、配列オブジェクトから 1 つの要素を取得します。  
  
```
const E& GetAt(size_t iElement) const throw();
E& GetAt(size_t iElement) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `iElement`  
 返される配列要素のインデックス値。  
  
### <a name="return-value"></a>戻り値  
 要求された配列要素への参照を返します。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドは atlassert 場合`iElement`配列の要素の数を超えています。 リリース ビルドでは、無効な引数は、予期しない動作に可能性があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#6](../../atl/codesnippet/cpp/catlarray-class_6.cpp)]  
  
##  <a name="getcount"></a>  CAtlArray::GetCount  
 このメソッドを呼び出して、配列に格納されている要素の数を返します。  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 配列に格納されている要素の数を返します。  
  
### <a name="remarks"></a>コメント  
 値がによって返される配列の最初の要素は、0 の位置が、`GetCount`が常に 1 より大きいインデックスの最大値。  
  
### <a name="example"></a>例  
 例を参照して[CAtlArray::GetAt](#getat)です。  
  
##  <a name="getdata"></a>  CAtlArray::GetData  
 このメソッドを呼び出して、配列内の最初の要素へのポインターを返します。  
  
```
E* GetData() throw();
const E* GetData() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 配列内の最初の要素を格納するメモリ位置へのポインターを返します。 使用可能な要素が存在しない場合は、NULL が返されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#7](../../atl/codesnippet/cpp/catlarray-class_7.cpp)]  
  
##  <a name="inargtype"></a>  CAtlArray::INARGTYPE  
 配列に要素を追加するのに使用するデータ型。  
  
```
typedef ETraits::INARGTYPE INARGTYPE;
```  
  
##  <a name="insertarrayat"></a>  CAtlArray::InsertArrayAt  
 1 つの配列を別に挿入するには、このメソッドを呼び出します。  
  
```
void InsertArrayAt(size_t iStart, const CAtlArray<E, ETraits>* paNew);
```  
  
### <a name="parameters"></a>パラメーター  
 `iStart`  
 配列が挿入されるインデックスです。  
  
 `paNew`  
 挿入先の配列。  
  
### <a name="remarks"></a>コメント  
 配列から要素`paNew`要素で始まる、配列オブジェクトにコピーされます`iStart`です。 既存の配列要素は、上書きされないようにに移動されます。  
  
 デバッグ ビルドは atlassert 場合、`CAtlArray`オブジェクトが有効でない場合は、`paNew`ポインターが NULL または無効です。  
  
> [!NOTE]
> `CAtlArray::InsertArrayAt` 作成された要素から成る配列をサポートしていません、 [CAutoPtr](../../atl/reference/cautoptr-class.md)クラスです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#8](../../atl/codesnippet/cpp/catlarray-class_8.cpp)]  
  
##  <a name="insertat"></a>  CAtlArray::InsertAt  
 配列オブジェクトに新しい要素 (または要素の複数のコピー) を挿入するには、このメソッドを呼び出します。  
  
```
void InsertAt(size_t iElement, INARGTYPE element, size_t nCount = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `iElement`  
 挿入される要素または要素には、ここでのインデックス。  
  
 `element`  
 要素または挿入される要素の値。  
  
 `nCount`  
 追加する要素の数。  
  
### <a name="remarks"></a>コメント  
 開始インデックス位置として、配列に 1 つまたは複数の要素を挿入`iElement`です。 既存の要素は、上書きされないようにに移動されます。  
  
 デバッグ ビルドは atlassert 場合、`CAtlArray`オブジェクトが無効、追加する要素の数が 0、またはを格納する配列の要素の合計数が大きすぎます。 製品版ビルドでは、無効なパラメーターを渡すことがあります予想外の結果。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#9](../../atl/codesnippet/cpp/catlarray-class_9.cpp)]  
  
##  <a name="isempty"></a>  CAtlArray::IsEmpty  
 配列が空の場合にテストするには、このメソッドを呼び出します。  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 配列が空の場合、false それ以外の場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 配列は要素が含まれていない場合は空にすることはできます。 したがって、配列に空の要素が含まれている場合でも空ではないです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#10](../../atl/codesnippet/cpp/catlarray-class_10.cpp)]  
  
##  <a name="operator_at"></a>  CAtlArray::operator  
 配列の要素への参照を返すには、この演算子を呼び出します。  
  
```
E& operator[](size_t ielement) throw();
const E& operator[](size_t ielement) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `iElement`  
 返される配列要素のインデックス値。  
  
### <a name="return-value"></a>戻り値  
 要求された配列要素への参照を返します。  
  
### <a name="remarks"></a>コメント  
 同様の機能を実行[CAtlArray::GetAt](#getat)です。 MFC クラスとは異なり[CArray](../../mfc/reference/carray-class.md)の代わりにこの演算子は使用できません[CAtlArray::SetAt](#setat)です。  
  
 デバッグ ビルドは atlassert 場合`iElement`配列内の要素の合計数を超えています。 製品版ビルドでは、予期しない結果が無効なパラメーターにあります。  
  
##  <a name="outargtype"></a>  CAtlArray::OUTARGTYPE  
 配列から要素を取得するのに使用するデータ型。  
  
```
typedef ETraits::OUTARGTYPE OUTARGTYPE;
```  
  
##  <a name="removeall"></a>  CAtlArray::RemoveAll  
 Array オブジェクトからすべての要素を削除するには、このメソッドを呼び出します。  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>コメント  
 Array オブジェクトからすべての要素を削除します。  
  
 このメソッドを呼び出す[CAtlArray::SetCount](#setcount)配列のサイズを変更して、後で、割り当てられたメモリを解放します。  
  
### <a name="example"></a>例  
 例を参照して[CAtlArray::IsEmpty](#isempty)です。  
  
##  <a name="removeat"></a>  CAtlArray::RemoveAt  
 配列から 1 つまたは複数の要素を削除するには、このメソッドを呼び出します。  
  
```
void RemoveAt(size_t iElement, size_t nCount = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `iElement`  
 削除する最初の要素のインデックス。  
  
 `nCount`  
 削除する要素の数を指定します。  
  
### <a name="remarks"></a>コメント  
 配列から 1 つまたは複数の要素を削除します。 下の残りの要素に移動します。 上限の値は、デクリメントされたが、メモリを呼び出すまで解放されません[CAtlArray::FreeExtra](#freeextra)が行われます。  
  
 デバッグ ビルドは atlassert 場合、`CAtlArray`オブジェクトが有効でない場合、または総計の`iElement`と`nCount`配列内の要素の合計数を超えています。 製品版ビルドでは、予期しない結果が無効なパラメーターにあります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#11](../../atl/codesnippet/cpp/catlarray-class_11.cpp)]  
  
##  <a name="setat"></a>  CAtlArray::SetAt  
 配列オブジェクト要素の値を設定するには、このメソッドを呼び出します。  
  
```
void SetAt(size_t iElement, INARGTYPE element);
```  
  
### <a name="parameters"></a>パラメーター  
 `iElement`  
 設定する配列要素を指すインデックス。  
  
 `element`  
 指定した要素の新しい値。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドは atlassert 場合`iElement`配列の要素の数を超えています。 製品版ビルドで予期しない結果に無効なパラメーター可能性があります。  
  
### <a name="example"></a>例  
 例を参照して[CAtlArray::GetAt](#getat)です。  
  
##  <a name="setcount"></a>  CAtlArray::SetCount  
 配列オブジェクトのサイズを設定するには、このメソッドを呼び出します。  
  
```
bool SetCount(size_t nNewSize, int nGrowBy = - 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `nNewSize`  
 配列の必要なサイズ。  
  
 `nGrowBy`  
 値を決定するため、バッファーの大きさ。 値-1 の場合、使用する、内部的に計算した値です。  
  
### <a name="return-value"></a>戻り値  
 場合は、配列が正常にサイズ変更後、それ以外の場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 配列の増加またはサイズでは、小さくできます。 増やされた場合、空の要素が配列に追加されます。 低下している場合は、最大のインデックスを持つ要素が削除され、メモリが解放されます。  
  
 このメソッドを使用すると、使用する前に、配列のサイズを設定できます。 場合`SetCount`を使用していない要素を追加するプロセス — 実行される後続のメモリ割り当てと — パフォーマンスが低下して、メモリが断片化されます。  
  
### <a name="example"></a>例  
 例を参照して[CAtlArray::GetData](#getdata)です。  
  
##  <a name="setatgrow"></a>  CAtlArray::SetAtGrow  
 必要に応じて、配列を展開して、配列オブジェクト要素の値を設定するには、このメソッドを呼び出します。  
  
```
void SetAtGrow(size_t iElement, INARGTYPE element);
```  
  
### <a name="parameters"></a>パラメーター  
 `iElement`  
 設定する配列要素を指すインデックス。  
  
 `element`  
 指定した要素の新しい値。  
  
### <a name="remarks"></a>コメント  
 インデックスによって指し示される要素の値を置換します。 場合`iElement`が現在のサイズよりも大きい、配列の配列は自動的に増加する呼び出しを使用して[CAtlArray::SetCount](#setcount)です。 デバッグ ビルドは atlassert 場合、`CAtlArray`オブジェクトが無効です。 製品版ビルドでは、予期しない結果が無効なパラメーターにあります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#12](../../atl/codesnippet/cpp/catlarray-class_12.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MMXSwarm サンプル](../../visual-cpp-samples.md)   
 [DynamicConsumer サンプル](../../visual-cpp-samples.md)   
 [UpdatePV サンプル](../../visual-cpp-samples.md)   
 [マーキーのサンプル](../../visual-cpp-samples.md)   
 [CArray クラス](../../mfc/reference/carray-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
