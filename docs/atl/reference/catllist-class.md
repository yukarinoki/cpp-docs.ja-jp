---
title: CAtlList クラス
ms.date: 11/04/2016
f1_keywords:
- CAtlList
- ATLCOLL/ATL::CAtlList
- ATLCOLL/ATL::CAtlList::INARGTYPE
- ATLCOLL/ATL::CAtlList::CAtlList
- ATLCOLL/ATL::CAtlList::AddHead
- ATLCOLL/ATL::CAtlList::AddHeadList
- ATLCOLL/ATL::CAtlList::AddTail
- ATLCOLL/ATL::CAtlList::AddTailList
- ATLCOLL/ATL::CAtlList::AssertValid
- ATLCOLL/ATL::CAtlList::Find
- ATLCOLL/ATL::CAtlList::FindIndex
- ATLCOLL/ATL::CAtlList::GetAt
- ATLCOLL/ATL::CAtlList::GetCount
- ATLCOLL/ATL::CAtlList::GetHead
- ATLCOLL/ATL::CAtlList::GetHeadPosition
- ATLCOLL/ATL::CAtlList::GetNext
- ATLCOLL/ATL::CAtlList::GetPrev
- ATLCOLL/ATL::CAtlList::GetTail
- ATLCOLL/ATL::CAtlList::GetTailPosition
- ATLCOLL/ATL::CAtlList::InsertAfter
- ATLCOLL/ATL::CAtlList::InsertBefore
- ATLCOLL/ATL::CAtlList::IsEmpty
- ATLCOLL/ATL::CAtlList::MoveToHead
- ATLCOLL/ATL::CAtlList::MoveToTail
- ATLCOLL/ATL::CAtlList::RemoveAll
- ATLCOLL/ATL::CAtlList::RemoveAt
- ATLCOLL/ATL::CAtlList::RemoveHead
- ATLCOLL/ATL::CAtlList::RemoveHeadNoReturn
- ATLCOLL/ATL::CAtlList::RemoveTail
- ATLCOLL/ATL::CAtlList::RemoveTailNoReturn
- ATLCOLL/ATL::CAtlList::SetAt
- ATLCOLL/ATL::CAtlList::SwapElements
helpviewer_keywords:
- CAtlList class
ms.assetid: 09e98053-64b2-4efa-99ab-d0542caaf981
ms.openlocfilehash: 2c16713af11a915772085165ed294cba4ae337f2
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168047"
---
# <a name="catllist-class"></a>CAtlList クラス

このクラスには、リストオブジェクトを作成および管理するためのメソッドが用意されています。

## <a name="syntax"></a>構文

```cpp
template<typename E, class ETraits = CElementTraits<E>>
class CAtlList
```

### <a name="parameters"></a>パラメーター

*つまり*<br/>
要素型。

*ETraits*<br/>
要素をコピーまたは移動するために使用するコード。 詳細については、「 [Celementtraits クラス](../../atl/reference/celementtraits-class.md)」を参照してください。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CAtlList:: INARGTYPE](#inargtype)||

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAtlList::CAtlList](#catllist)|コンストラクターです。|
|[CAtlList:: ~ CAtlList](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAtlList:: AddHead](#addhead)|リストの先頭に要素を追加するには、このメソッドを呼び出します。|
|[CAtlList:: Addヘッドホンリスト](#addheadlist)|既存のリストをリストの先頭に追加するには、このメソッドを呼び出します。|
|[CAtlList:: AddTail](#addtail)|このリストの末尾に要素を追加するには、このメソッドを呼び出します。|
|[CAtlList::AddTailList](#addtaillist)|このリストの末尾に既存のリストを追加するには、このメソッドを呼び出します。|
|[CAtlList:: AssertValid](#assertvalid)|リストが有効であることを確認するには、このメソッドを呼び出します。|
|[CAtlList:: Find](#find)|指定した要素のリストを検索するには、このメソッドを呼び出します。|
|[CAtlList:: FindIndex](#findindex)|インデックス値が指定された要素の位置を取得するには、このメソッドを呼び出します。|
|[CAtlList:: GetAt](#getat)|リスト内の指定した位置にある要素を返すには、このメソッドを呼び出します。|
|[CAtlList:: GetCount](#getcount)|リスト内のオブジェクトの数を返すには、このメソッドを呼び出します。|
|[CAtlList::GetHead](#gethead)|リストの先頭にある要素を返すには、このメソッドを呼び出します。|
|[CAtlList:: GetHeadPosition](#getheadposition)|リストの先頭の位置を取得するには、このメソッドを呼び出します。|
|[CAtlList:: GetNext](#getnext)|リストから次の要素を取得するには、このメソッドを呼び出します。|
|[CAtlList:: GetPrev](#getprev)|リストから前の要素を取得するには、このメソッドを呼び出します。|
|[CAtlList:: GetTail](#gettail)|リストの末尾にある要素を返すには、このメソッドを呼び出します。|
|[CAtlList::GetTailPosition](#gettailposition)|リストの末尾の位置を取得するには、このメソッドを呼び出します。|
|[CAtlList:: InsertAfter](#insertafter)|このメソッドを呼び出して、指定した位置の後に新しい要素をリストに挿入します。|
|[CAtlList:: InsertBefore](#insertbefore)|このメソッドを呼び出して、指定した位置の前に新しい要素をリストに挿入します。|
|[CAtlList:: IsEmpty](#isempty)|リストが空かどうかを判断するには、このメソッドを呼び出します。|
|[CAtlList:: MoveToHead](#movetohead)|指定した要素をリストの先頭に移動するには、このメソッドを呼び出します。|
|[CAtlList:: Moveは、](#movetotail)|指定した要素をリストの末尾に移動するには、このメソッドを呼び出します。|
|[CAtlList:: RemoveAll](#removeall)|リストからすべての要素を削除するには、このメソッドを呼び出します。|
|[CAtlList:: RemoveAt](#removeat)|リストから1つの要素を削除するには、このメソッドを呼び出します。|
|[CAtlList:: RemoveHead](#removehead)|リストの先頭にある要素を削除するには、このメソッドを呼び出します。|
|[CAtlList::RemoveHeadNoReturn](#removeheadnoreturn)|値を返さずに、リストの先頭にある要素を削除するには、このメソッドを呼び出します。|
|[CAtlList:: RemoveTail](#removetail)|リストの末尾にある要素を削除するには、このメソッドを呼び出します。|
|[CAtlList::RemoveTailNoReturn](#removetailnoreturn)|値を返さずに、リストの末尾にある要素を削除するには、このメソッドを呼び出します。|
|[CAtlList:: SetAt](#setat)|リスト内の指定した位置にある要素の値を設定するには、このメソッドを呼び出します。|
|[CAtlList:: SwapElements](#swapelements)|リスト内の要素をスワップするには、このメソッドを呼び出します。|

## <a name="remarks"></a>解説

クラス`CAtlList`は、順次または値によってアクセスできる、一意でないオブジェクトの順序付きリストをサポートします。 `CAtlList`リストは、ダブルリンクリストのように動作します。 各リストには先頭と末尾があり、新しい要素 (場合によってはリスト) をリストの末尾に追加するか、特定の要素の前後に挿入することができます。

ほとんどのメソッド`CAtlList`では、位置の値が使用されます。 この値は、要素が格納されている実際のメモリ位置を参照するためにメソッドによって使用されます。また、直接計算したり、予測したりしないでください。 リスト内の*n*番目の要素にアクセスする必要がある場合、メソッド[CAtlList:: findindex](#findindex)は、指定されたインデックスの対応する位置の値を返します。 メソッド[CAtlList:: GetNext](#getnext)と[CAtlList:: getprev](#getprev)を使用して、リスト内のオブジェクトを反復処理できます。

ATL で使用できるコレクションクラスの詳細については、「 [Atl コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll. h

## <a name="catllistaddhead"></a><a name="addhead"></a>CAtlList:: AddHead

リストの先頭に要素を追加するには、このメソッドを呼び出します。

```cpp
POSITION AddHead();
POSITION AddHead(INARGTYPE element);
```

### <a name="parameters"></a>パラメーター

*element*<br/>
新しい要素。

### <a name="return-value"></a>戻り値

新しく追加された要素の位置を返します。

### <a name="remarks"></a>解説

最初のバージョンが使用されている場合は、そのコピーコンストラクターではなく、既定のコンストラクターを使用して空の要素が作成されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#13](../../atl/codesnippet/cpp/catllist-class_1.cpp)]

## <a name="catllistaddheadlist"></a><a name="addheadlist"></a>CAtlList:: Addヘッドホンリスト

既存のリストをリストの先頭に追加するには、このメソッドを呼び出します。

```cpp
void AddHeadList(const CAtlList<E, ETraits>* plNew);
```

### <a name="parameters"></a>パラメーター

*plNew*<br/>
追加するリスト。

### <a name="remarks"></a>解説

*PlNew*によって示されているリストは、既存のリストの先頭に挿入されます。 デバッグビルドでは、 *plNew*が NULL に等しい場合にアサーションエラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#14](../../atl/codesnippet/cpp/catllist-class_2.cpp)]

## <a name="catllistaddtail"></a><a name="addtail"></a>CAtlList:: AddTail

このリストの末尾に要素を追加するには、このメソッドを呼び出します。

```cpp
POSITION AddTail();
POSITION AddTail(INARGTYPE element);
```

### <a name="parameters"></a>パラメーター

*element*<br/>
追加する要素。

### <a name="return-value"></a>戻り値

新しく追加された要素の位置を返します。

### <a name="remarks"></a>解説

最初のバージョンが使用されている場合は、そのコピーコンストラクターではなく、既定のコンストラクターを使用して空の要素が作成されます。 要素がリストの末尾に追加されるため、これが末尾になります。 このメソッドは、空のリストと共に使用できます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#15](../../atl/codesnippet/cpp/catllist-class_3.cpp)]

## <a name="catllistaddtaillist"></a><a name="addtaillist"></a>CAtlList::AddTailList

このリストの末尾に既存のリストを追加するには、このメソッドを呼び出します。

```cpp
void AddTailList(const CAtlList<E, ETraits>* plNew);
```

### <a name="parameters"></a>パラメーター

*plNew*<br/>
追加するリスト。

### <a name="remarks"></a>解説

*PlNew*が指すリストは、リストオブジェクト内の最後の要素 (存在する場合) の後に挿入されます。 したがって、 *plNew*リストの最後の要素が末尾になります。 デバッグビルドでは、 *plNew*が NULL に等しい場合にアサーションエラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#16](../../atl/codesnippet/cpp/catllist-class_4.cpp)]

## <a name="catllistassertvalid"></a><a name="assertvalid"></a>CAtlList:: AssertValid

リストが有効であることを確認するには、このメソッドを呼び出します。

```cpp
void AssertValid() const;
```

### <a name="remarks"></a>解説

デバッグビルドでは、リストオブジェクトが有効でない場合にアサーションエラーが発生します。 空のリストを有効にするには、先頭と末尾の両方が NULL を指している必要があります。また、空でないリストには、有効なアドレスを指す先頭と末尾の両方が含まれている必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#17](../../atl/codesnippet/cpp/catllist-class_5.cpp)]

## <a name="catllistcatllist"></a><a name="catllist"></a>CAtlList::CAtlList

コンストラクターです。

```cpp
CAtlList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>パラメーター

*nBlockSize*<br/>
ブロックのサイズです。

### <a name="remarks"></a>解説

`CAtlList`オブジェクトのコンストラクター。 ブロックサイズは、新しい要素が必要な場合に割り当てられるメモリの量を測定したものです。 ブロックサイズを大きくすると、メモリ割り当てルーチンの呼び出しが減少しますが、より多くのリソースが使用されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#18](../../atl/codesnippet/cpp/catllist-class_6.cpp)]

## <a name="catllistcatllist"></a><a name="dtor"></a>CAtlList:: ~ CAtlList

デストラクターです。

```cpp
~CAtlList() throw();
```

### <a name="remarks"></a>解説

[CAtlList:: RemoveAll](#removeall)の呼び出しを含め、すべての割り当て済みリソースを解放して、リストからすべての要素を削除します。

デバッグビルドでは、の呼び出しの後に`RemoveAll`リストにいくつかの要素がまだ含まれている場合、アサーションエラーが発生します。

## <a name="catllistfind"></a><a name="find"></a>CAtlList:: Find

指定した要素のリストを検索するには、このメソッドを呼び出します。

```cpp
POSITION Find(INARGTYPE element, POSITION posStartAfter = NULL) const throw();
```

### <a name="parameters"></a>パラメーター

*element*<br/>
リスト内で検索する要素。

*posStartAfter*<br/>
検索の開始位置。 値が指定されていない場合は、先頭の要素から検索が開始されます。

### <a name="return-value"></a>戻り値

要素の位置の値が見つかった場合はその値を返し、それ以外の場合は NULL を返します。

### <a name="remarks"></a>解説

デバッグビルドでは、リストオブジェクトが有効でない場合、または*Posstartafter*値が範囲外の場合、アサーションエラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#19](../../atl/codesnippet/cpp/catllist-class_7.cpp)]

## <a name="catllistfindindex"></a><a name="findindex"></a>CAtlList:: FindIndex

インデックス値が指定された要素の位置を取得するには、このメソッドを呼び出します。

```cpp
POSITION FindIndex(size_t iElement) const throw();
```

### <a name="parameters"></a>パラメーター

*iElement*<br/>
必須のリスト要素の0から始まるインデックス。

### <a name="return-value"></a>戻り値

対応する位置の値を返します。 *Ielement*が範囲外の場合は NULL を返します。

### <a name="remarks"></a>解説

このメソッドは、指定されたインデックス値に対応する位置を返し、リスト内の*n*番目の要素にアクセスできるようにします。

デバッグビルドでは、リストオブジェクトが有効でない場合にアサーションエラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#20](../../atl/codesnippet/cpp/catllist-class_8.cpp)]

## <a name="catllistgetat"></a><a name="getat"></a>CAtlList:: GetAt

リスト内の指定した位置にある要素を返すには、このメソッドを呼び出します。

```cpp
E& GetAt(POSITION pos) throw();
const E& GetAt(POSITION pos) const throw();
```

### <a name="parameters"></a>パラメーター

*po*<br/>
特定の要素を指定する位置の値。

### <a name="return-value"></a>戻り値

要素への参照、または要素のコピー。

### <a name="remarks"></a>解説

リストが**const**の場合は`GetAt` 、要素のコピーを返します。 これにより、メソッドを代入ステートメントの右側でのみ使用し、そのリストを変更から保護することができます。

リストが**const**でない場合は`GetAt` 、要素への参照を返します。 これにより、メソッドを代入ステートメントのどちら側でも使用できるようになり、リストエントリを変更できるようになります。

デバッグビルドでは、 *pos*が NULL と等しい場合にアサーションエラーが発生します。

### <a name="example"></a>例

[CAtlList:: FindIndex](#findindex)の例を参照してください。

## <a name="catllistgetcount"></a><a name="getcount"></a>CAtlList:: GetCount

リスト内のオブジェクトの数を返すには、このメソッドを呼び出します。

```cpp
size_t GetCount() const throw();
```

### <a name="return-value"></a>戻り値

リストの要素数を返します。

### <a name="example"></a>例

[CAtlList:: Find](#find)の例を参照してください。

## <a name="catllistgethead"></a><a name="gethead"></a>CAtlList::GetHead

リストの先頭にある要素を返すには、このメソッドを呼び出します。

```cpp
E& GetHead() throw();
const E& GetHead() const throw();
```

### <a name="return-value"></a>戻り値

リストの先頭にある要素への参照、またはそのコピーを返します。

### <a name="remarks"></a>解説

リストが**const**の場合は`GetHead` 、リストの先頭にある要素のコピーを返します。 これにより、メソッドを代入ステートメントの右側でのみ使用し、そのリストを変更から保護することができます。

リストが**const**でない場合は`GetHead` 、リストの先頭にある要素への参照を返します。 これにより、メソッドを代入ステートメントのどちら側でも使用できるようになり、リストエントリを変更できるようになります。

デバッグビルドでは、リストの先頭が NULL を指している場合、アサーションエラーが発生します。

### <a name="example"></a>例

[CAtlList:: AddHead](#addhead)の例を参照してください。

## <a name="catllistgetheadposition"></a><a name="getheadposition"></a>CAtlList:: GetHeadPosition

リストの先頭の位置を取得するには、このメソッドを呼び出します。

```cpp
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>戻り値

リストの先頭にある要素に対応する位置の値を返します。

### <a name="remarks"></a>解説

リストが空の場合、返される値は NULL です。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#21](../../atl/codesnippet/cpp/catllist-class_9.cpp)]

## <a name="catllistgetnext"></a><a name="getnext"></a>CAtlList:: GetNext

リストから次の要素を取得するには、このメソッドを呼び出します。

```cpp
E& GetNext(POSITION& pos) throw();
const E& GetNext(POSITION& pos) const throw();
```

### <a name="parameters"></a>パラメーター

*po*<br/>
以前の`GetNext`、 [CAtlList:: getheadposition](#getheadposition)、またはその他の`CAtlList`メソッドの呼び出しによって返される位置の値。

### <a name="return-value"></a>戻り値

リストが**const**の場合は`GetNext` 、リストの次の要素のコピーを返します。 これにより、メソッドを代入ステートメントの右側でのみ使用し、そのリストを変更から保護することができます。

リストが**const**でない場合は`GetNext` 、リストの次の要素への参照を返します。 これにより、メソッドを代入ステートメントのどちら側でも使用できるようになり、リストエントリを変更できるようになります。

### <a name="remarks"></a>解説

位置カウンター ( *pos*) は、リスト内の次の要素を指すように更新されます。要素がなくなった場合は、NULL になります。 デバッグビルドでは、 *pos*が NULL と等しい場合にアサーションエラーが発生します。

### <a name="example"></a>例

[CAtlList:: GetHeadPosition](#getheadposition)の例を参照してください。

## <a name="catllistgetprev"></a><a name="getprev"></a>CAtlList:: GetPrev

リストから前の要素を取得するには、このメソッドを呼び出します。

```cpp
E& GetPrev(POSITION& pos) throw();
const E& GetPrev(POSITION& pos) const throw();
```

### <a name="parameters"></a>パラメーター

*po*<br/>
以前の`GetPrev`、 [CAtlList:: GetTailPosition](#gettailposition)、またはその他の`CAtlList`メソッドの呼び出しによって返される位置の値。

### <a name="return-value"></a>戻り値

リストが**const**の場合は`GetPrev` 、リストの要素のコピーを返します。 これにより、メソッドを代入ステートメントの右側でのみ使用し、そのリストを変更から保護することができます。

リストが**const**でない場合は`GetPrev` 、リストの要素への参照を返します。 これにより、メソッドを代入ステートメントのどちら側でも使用できるようになり、リストエントリを変更できるようになります。

### <a name="remarks"></a>解説

位置カウンター *pos*は、リスト内の前の要素を指すように更新されます。要素がなくなった場合は、NULL になります。 デバッグビルドでは、 *pos*が NULL と等しい場合にアサーションエラーが発生します。

### <a name="example"></a>例

[CAtlList:: GetTailPosition](#gettailposition)の例を参照してください。

## <a name="catllistgettail"></a><a name="gettail"></a>CAtlList:: GetTail

リストの末尾にある要素を返すには、このメソッドを呼び出します。

```cpp
E& GetTail() throw();
const E& GetTail() const throw();
```

### <a name="return-value"></a>戻り値

リストの末尾にある要素への参照、またはそのコピーを返します。

### <a name="remarks"></a>解説

リストが**const**の場合は`GetTail` 、リストの先頭にある要素のコピーを返します。 これにより、メソッドを代入ステートメントの右側でのみ使用し、そのリストを変更から保護することができます。

リストが**const**でない場合は`GetTail` 、リストの先頭にある要素への参照を返します。 これにより、メソッドを代入ステートメントのどちら側でも使用できるようになり、リストエントリを変更できるようになります。

デバッグビルドでは、リストの末尾が NULL を指している場合、アサーションエラーが発生します。

### <a name="example"></a>例

[CAtlList:: AddTail](#addtail)の例を参照してください。

## <a name="catllistgettailposition"></a><a name="gettailposition"></a>CAtlList::GetTailPosition

リストの末尾の位置を取得するには、このメソッドを呼び出します。

```cpp
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>戻り値

リストの末尾の要素に対応する位置の値を返します。

### <a name="remarks"></a>解説

リストが空の場合、返される値は NULL です。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#22](../../atl/codesnippet/cpp/catllist-class_10.cpp)]

## <a name="catllistinargtype"></a><a name="inargtype"></a>CAtlList:: INARGTYPE

要素が入力引数として渡されるときに使用される型。

```cpp
typedef ETraits::INARGTYPE INARGTYPE;
```

## <a name="catllistinsertafter"></a><a name="insertafter"></a>CAtlList:: InsertAfter

このメソッドを呼び出して、指定した位置の後に新しい要素をリストに挿入します。

```cpp
POSITION InsertAfter(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>パラメーター

*po*<br/>
新しい要素が挿入される位置の後の位置の値。

*element*<br/>
挿入される要素。

### <a name="return-value"></a>戻り値

新しい要素の位置の値を返します。

### <a name="remarks"></a>解説

デバッグビルドでは、リストが有効でない場合、挿入が失敗した場合、または末尾の後に要素を挿入しようとした場合に、アサーションエラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#23](../../atl/codesnippet/cpp/catllist-class_11.cpp)]

## <a name="catllistinsertbefore"></a><a name="insertbefore"></a>CAtlList:: InsertBefore

このメソッドを呼び出して、指定した位置の前に新しい要素をリストに挿入します。

```cpp
POSITION InsertBefore(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>パラメーター

*po*<br/>
この位置の値の前に、新しい要素がリストに挿入されます。

*element*<br/>
挿入される要素。

### <a name="return-value"></a>戻り値

新しい要素の位置の値を返します。

### <a name="remarks"></a>解説

デバッグビルドでは、リストが有効でない場合、挿入が失敗した場合、または先頭の前に要素を挿入しようとした場合に、アサーションエラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#24](../../atl/codesnippet/cpp/catllist-class_12.cpp)]

## <a name="catllistisempty"></a><a name="isempty"></a>CAtlList:: IsEmpty

リストが空かどうかを判断するには、このメソッドを呼び出します。

```cpp
bool IsEmpty() const throw();
```

### <a name="return-value"></a>戻り値

リストにオブジェクトが含まれていない場合は true、それ以外の場合は false を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#25](../../atl/codesnippet/cpp/catllist-class_13.cpp)]

## <a name="catllistmovetohead"></a><a name="movetohead"></a>CAtlList:: MoveToHead

指定した要素をリストの先頭に移動するには、このメソッドを呼び出します。

```cpp
void MoveToHead(POSITION pos) throw();
```

### <a name="parameters"></a>パラメーター

*po*<br/>
移動する要素の位置の値。

### <a name="remarks"></a>解説

指定された要素は、現在の位置からリストの先頭に移動されます。 デバッグビルドでは、 *pos*が NULL と等しい場合にアサーションエラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#26](../../atl/codesnippet/cpp/catllist-class_14.cpp)]

## <a name="catllistmovetotail"></a><a name="movetotail"></a>CAtlList:: Moveは、

指定した要素をリストの末尾に移動するには、このメソッドを呼び出します。

```cpp
void MoveToTail(POSITION pos) throw();
```

### <a name="parameters"></a>パラメーター

*po*<br/>
移動する要素の位置の値。

### <a name="remarks"></a>解説

指定された要素は、現在の位置からリストの末尾に移動されます。 デバッグビルドでは、 *pos*が NULL と等しい場合にアサーションエラーが発生します。

### <a name="example"></a>例

[CAtlList:: MoveToHead](#movetohead)の例を参照してください。

## <a name="catllistremoveall"></a><a name="removeall"></a>CAtlList:: RemoveAll

リストからすべての要素を削除するには、このメソッドを呼び出します。

```cpp
void RemoveAll() throw();
```

### <a name="remarks"></a>解説

このメソッドは、リストからすべての要素を削除し、割り当てられたメモリを解放します。 デバッグビルドでは、すべての要素が削除されない場合、またはリスト構造が破損した場合に、ATLASSERT が発生します。

### <a name="example"></a>例

[CAtlList:: IsEmpty](#isempty)の例を参照してください。

## <a name="catllistremoveat"></a><a name="removeat"></a>CAtlList:: RemoveAt

リストから1つの要素を削除するには、このメソッドを呼び出します。

```cpp
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>パラメーター

*po*<br/>
削除する要素の位置の値。

### <a name="remarks"></a>解説

*Pos*によって参照される要素が削除され、メモリが解放されます。 を使用`RemoveAt`すると、リストの先頭または末尾を削除できます。

デバッグビルドでは、リストが有効でない場合、または要素を削除するとリスト構造に含まれていないメモリにアクセスする場合に、アサーションエラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#27](../../atl/codesnippet/cpp/catllist-class_15.cpp)]

## <a name="catllistremovehead"></a><a name="removehead"></a>CAtlList:: RemoveHead

リストの先頭にある要素を削除するには、このメソッドを呼び出します。

```cpp
E RemoveHead();
```

### <a name="return-value"></a>戻り値

リストの先頭にある要素を返します。

### <a name="remarks"></a>解説

Head 要素がリストから削除され、メモリが解放されます。 要素のコピーが返されます。 デバッグビルドでは、リストが空の場合、アサーションエラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#28](../../atl/codesnippet/cpp/catllist-class_16.cpp)]

## <a name="catllistremoveheadnoreturn"></a><a name="removeheadnoreturn"></a>CAtlList::RemoveHeadNoReturn

値を返さずに、リストの先頭にある要素を削除するには、このメソッドを呼び出します。

```cpp
void RemoveHeadNoReturn() throw();
```

### <a name="remarks"></a>解説

Head 要素がリストから削除され、メモリが解放されます。 デバッグビルドでは、リストが空の場合、アサーションエラーが発生します。

### <a name="example"></a>例

[CAtlList:: IsEmpty](#isempty)の例を参照してください。

## <a name="catllistremovetail"></a><a name="removetail"></a>CAtlList:: RemoveTail

リストの末尾にある要素を削除するには、このメソッドを呼び出します。

```cpp
E RemoveTail();
```

### <a name="return-value"></a>戻り値

リストの末尾にある要素を返します。

### <a name="remarks"></a>解説

Tail 要素がリストから削除され、メモリが解放されます。 要素のコピーが返されます。 デバッグビルドでは、リストが空の場合、アサーションエラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#29](../../atl/codesnippet/cpp/catllist-class_17.cpp)]

## <a name="catllistremovetailnoreturn"></a><a name="removetailnoreturn"></a>CAtlList::RemoveTailNoReturn

値を返さずに、リストの末尾にある要素を削除するには、このメソッドを呼び出します。

```cpp
void RemoveTailNoReturn() throw();
```

### <a name="remarks"></a>解説

Tail 要素がリストから削除され、メモリが解放されます。 デバッグビルドでは、リストが空の場合、アサーションエラーが発生します。

### <a name="example"></a>例

[CAtlList:: IsEmpty](#isempty)の例を参照してください。

## <a name="catllistsetat"></a><a name="setat"></a>CAtlList:: SetAt

リスト内の指定した位置にある要素の値を設定するには、このメソッドを呼び出します。

```cpp
void SetAt(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>パラメーター

*po*<br/>
変更する要素に対応する位置の値。

*element*<br/>
新しい要素の値。

### <a name="remarks"></a>解説

既存の値を*要素*に置き換えます。 デバッグビルドでは、 *pos*が NULL と等しい場合にアサーションエラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#30](../../atl/codesnippet/cpp/catllist-class_18.cpp)]

## <a name="catllistswapelements"></a><a name="swapelements"></a>CAtlList:: SwapElements

リスト内の要素をスワップするには、このメソッドを呼び出します。

```cpp
void SwapElements(POSITION pos1, POSITION pos2) throw();
```

### <a name="parameters"></a>パラメーター

*pos1*<br/>
最初の位置の値。

*pos2*<br/>
2番目の位置の値。

### <a name="remarks"></a>解説

指定した2つの位置にある要素を交換します。 デバッグビルドでは、いずれかの位置の値が NULL に等しい場合にアサーションエラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#31](../../atl/codesnippet/cpp/catllist-class_19.cpp)]

## <a name="see-also"></a>関連項目

[CList クラス](../../mfc/reference/clist-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
