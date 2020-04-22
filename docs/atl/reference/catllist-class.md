---
title: クラスを表します。
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
ms.openlocfilehash: 0e4ea8eef51431c100f5d3119d7f75e9673e276e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748739"
---
# <a name="catllist-class"></a>クラスを表します。

このクラスには、リスト オブジェクトを作成および管理するためのメソッドが用意されています。

## <a name="syntax"></a>構文

```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlList
```

#### <a name="parameters"></a>パラメーター

*E*<br/>
要素型。

*海峡*<br/>
要素をコピーまたは移動するために使用するコード。 詳細については[、「CElementTraits クラス](../../atl/reference/celementtraits-class.md)」を参照してください。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[カトルリスト::イナルグタイプ](#inargtype)||

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[カトルリスト::カトルリスト](#catllist)|コンストラクターです。|
|[カトルリスト::~カトルリスト](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[カトルリスト::アドヘッド](#addhead)|リストの先頭に要素を追加します。|
|[カトルリスト::追加ヘッドリスト](#addheadlist)|リストの先頭に既存のリストを追加します。|
|[カトルリスト::追加テール](#addtail)|このリストの末尾に要素を追加します。|
|[カトルリスト::追加テールリスト](#addtaillist)|このリストの末尾に既存のリストを追加します。|
|[カトルリスト::アサートValid](#assertvalid)|リストが有効であることを確認します。|
|[カトルリスト::検索](#find)|指定した要素のリストを検索します。|
|[インデックスを検索します。](#findindex)|インデックス値を指定して要素の位置を取得します。|
|[カトルリスト::ゲットアット](#getat)|リスト内の指定した位置にある要素を返します。|
|[カトルリスト::取得カウント](#getcount)|リスト内のオブジェクトの数を返します。|
|[カトルリスト::ゲットヘッド](#gethead)|リストの先頭にある要素を返します。|
|[カトルリスト::ゲットヘッドポジション](#getheadposition)|リストの先頭の位置を取得します。|
|[カトルリスト::次に取得](#getnext)|リストから次の要素を返します。|
|[カトルリスト::ゲットプレフ](#getprev)|リストから前の要素を返します。|
|[カトルリスト::ゲットテール](#gettail)|リストの末尾にある要素を返します。|
|[カトルリスト::ゲットテールポジション](#gettailposition)|リストの末尾の位置を取得します。|
|[CAtlList::後に挿入](#insertafter)|指定した位置の後に新しい要素をリストに挿入します。|
|[CAtlList::前に挿入](#insertbefore)|指定した位置の前に新しい要素をリストに挿入します。|
|[カトルリスト::IsEmpty](#isempty)|リストが空かどうかを調べます。|
|[カトルリスト::移動ヘッド](#movetohead)|指定した要素をリストの先頭に移動します。|
|[カトルリスト:::ムーブトテール](#movetotail)|指定した要素をリストの末尾に移動します。|
|[一覧::すべて削除](#removeall)|リストからすべての要素を削除します。|
|[カトルリスト::削除アット](#removeat)|リストから 1 つの要素を削除します。|
|[キャップルリスト::削除ヘッド](#removehead)|リストの先頭にある要素を削除します。|
|[CAtlリスト::リムートヘッドノーリターン](#removeheadnoreturn)|値を返さずに、リストの先頭にある要素を削除します。|
|[カトルリスト::リムートテール](#removetail)|リストの末尾にある要素を削除します。|
|[カトルリスト::リムープテールノーリターン](#removetailnoreturn)|値を返さずに、リストの末尾にある要素を削除します。|
|[カトルリスト::セットアット](#setat)|リスト内の指定した位置にある要素の値を設定します。|
|[要素を指定します。](#swapelements)|リスト内の要素を交換します。|

## <a name="remarks"></a>解説

この`CAtlList`クラスは、一意でないオブジェクトの順序付きリストを順次または値でアクセス可能にサポートします。 `CAtlList`リストは、二重にリンクされたリストのように動作します。 各リストには頭と尾があり、新しい要素 (または場合によってはリスト) をリストの最後に追加したり、特定の要素の前後に挿入したりできます。

ほとんどの方法では`CAtlList`、位置値を使用します。 この値は、要素が格納されている実際のメモリ位置を参照するためにメソッドによって使用され、計算または直接予測すべきではありません。 リストの*n*番目の要素にアクセスする必要がある場合、メソッド[CAtlList::FindIndex](#findindex)は、指定されたインデックスの対応する位置の値を返します。 メソッド[CAtlList::GetNext](#getnext)と[CAtlList::GetPrev](#getprev)は、リスト内のオブジェクトを反復処理するために使用できます。

ATL で使用できるコレクション クラスの詳細については、「 [ATL コレクション クラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="catllistaddhead"></a><a name="addhead"></a>カトルリスト::アドヘッド

リストの先頭に要素を追加します。

```
POSITION AddHead();
POSITION AddHead(INARGTYPE element);
```

### <a name="parameters"></a>パラメーター

*要素*<br/>
新しい要素。

### <a name="return-value"></a>戻り値

新しく追加された要素の位置を返します。

### <a name="remarks"></a>解説

最初のバージョンを使用する場合、コピー コンストラクターではなく、既定のコンストラクターを使用して空の要素が作成されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#13](../../atl/codesnippet/cpp/catllist-class_1.cpp)]

## <a name="catllistaddheadlist"></a><a name="addheadlist"></a>カトルリスト::追加ヘッドリスト

リストの先頭に既存のリストを追加します。

```cpp
void AddHeadList(const CAtlList<E, ETraits>* plNew);
```

### <a name="parameters"></a>パラメーター

*plNew*<br/>
追加するリスト。

### <a name="remarks"></a>解説

*plNew*が指すリストは、既存のリストの先頭に挿入されます。 デバッグ ビルドでは *、plNew*が NULL に等しい場合にアサーション エラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#14](../../atl/codesnippet/cpp/catllist-class_2.cpp)]

## <a name="catllistaddtail"></a><a name="addtail"></a>カトルリスト::追加テール

このリストの末尾に要素を追加します。

```
POSITION AddTail();
POSITION AddTail(INARGTYPE element);
```

### <a name="parameters"></a>パラメーター

*要素*<br/>
追加する要素。

### <a name="return-value"></a>戻り値

新しく追加された要素の位置を返します。

### <a name="remarks"></a>解説

最初のバージョンを使用する場合、コピー コンストラクターではなく、既定のコンストラクターを使用して空の要素が作成されます。 要素がリストの末尾に追加され、末尾になります。 このメソッドは、空のリストと共に使用できます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#15](../../atl/codesnippet/cpp/catllist-class_3.cpp)]

## <a name="catllistaddtaillist"></a><a name="addtaillist"></a>カトルリスト::追加テールリスト

このリストの末尾に既存のリストを追加します。

```cpp
void AddTailList(const CAtlList<E, ETraits>* plNew);
```

### <a name="parameters"></a>パラメーター

*plNew*<br/>
追加するリスト。

### <a name="remarks"></a>解説

*plNew*が指すリストは、リストオブジェクトの最後の要素 (存在する場合) の後に挿入されます。 したがって *、plNew*リストの最後の要素は末尾になります。 デバッグ ビルドでは *、plNew*が NULL に等しい場合にアサーション エラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#16](../../atl/codesnippet/cpp/catllist-class_4.cpp)]

## <a name="catllistassertvalid"></a><a name="assertvalid"></a>カトルリスト::アサートValid

リストが有効であることを確認します。

```cpp
void AssertValid() const;
```

### <a name="remarks"></a>解説

デバッグ ビルドでは、リスト オブジェクトが有効でない場合にアサーション エラーが発生します。 有効にするには、空のリストに、NULL を指す頭と尾の両方が必要です。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#17](../../atl/codesnippet/cpp/catllist-class_5.cpp)]

## <a name="catllistcatllist"></a><a name="catllist"></a>カトルリスト::カトルリスト

コンストラクターです。

```
CAtlList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>パラメーター

*ブロックサイズ*<br/>
ブロックのサイズです。

### <a name="remarks"></a>解説

オブジェクトの`CAtlList`コンストラクター。 ブロック サイズは、新しい要素が必要なときに割り当てられるメモリの量を測定します。 ブロック サイズが大きくなると、メモリ割り当てルーチンの呼び出しは減りますが、使用するリソースは多くなります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#18](../../atl/codesnippet/cpp/catllist-class_6.cpp)]

## <a name="catllistcatllist"></a><a name="dtor"></a>カトルリスト::~カトルリスト

デストラクターです。

```
~CAtlList() throw();
```

### <a name="remarks"></a>解説

[CAtlList::RemoveAll](#removeall)の呼び出しを含むすべての割り当て済みリソースを解放し、リストからすべての要素を削除します。

デバッグ ビルドでは、リストに呼び出し後に要素が含まれている場合にアサーション`RemoveAll`エラーが発生します。

## <a name="catllistfind"></a><a name="find"></a>カトルリスト::検索

指定した要素のリストを検索します。

```
POSITION Find(INARGTYPE element, POSITION posStartAfter = NULL) const throw();
```

### <a name="parameters"></a>パラメーター

*要素*<br/>
リスト内で見つかる要素。

*後に開始する*<br/>
検索の開始位置。 値を指定しない場合、検索は head 要素から開始されます。

### <a name="return-value"></a>戻り値

見つかった場合は要素の POSITION 値を返し、それ以外の場合は NULL を返します。

### <a name="remarks"></a>解説

デバッグ ビルドでは、リスト オブジェクトが有効でない場合、または*posStartAfter*値が範囲外の場合にアサーション エラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#19](../../atl/codesnippet/cpp/catllist-class_7.cpp)]

## <a name="catllistfindindex"></a><a name="findindex"></a>インデックスを検索します。

インデックス値を指定して要素の位置を取得します。

```
POSITION FindIndex(size_t iElement) const throw();
```

### <a name="parameters"></a>パラメーター

*i要素*<br/>
必要なリスト要素の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

対応する POSITION 値を返します*iElement*。

### <a name="remarks"></a>解説

このメソッドは、指定されたインデックス値に対応する POSITION を返し、リスト内の*n*番目の要素にアクセスできるようにします。

デバッグ ビルドでは、リスト オブジェクトが有効でない場合にアサーション エラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#20](../../atl/codesnippet/cpp/catllist-class_8.cpp)]

## <a name="catllistgetat"></a><a name="getat"></a>カトルリスト::ゲットアット

リスト内の指定した位置にある要素を返します。

```
E& GetAt(POSITION pos) throw();
const E& GetAt(POSITION pos) const throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
特定の要素を指定する POSITION 値。

### <a name="return-value"></a>戻り値

要素への参照または要素のコピー。

### <a name="remarks"></a>解説

リストが**const**の`GetAt`場合は、要素のコピーを返します。 これにより、メソッドは代入ステートメントの右側でのみ使用でき、リストが変更されないように保護されます。

リストが**const**でない場合`GetAt`は、要素への参照を返します。 これにより、メソッドは代入ステートメントの両側で使用され、リストエントリを変更することができます。

デバッグ ビルドでは *、pos*が NULL に等しい場合、アサーション エラーが発生します。

### <a name="example"></a>例

[次](#findindex)の例を参照してください。

## <a name="catllistgetcount"></a><a name="getcount"></a>カトルリスト::取得カウント

リスト内のオブジェクトの数を返します。

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>戻り値

リストの要素数を返します。

### <a name="example"></a>例

[「CAtlList::Find」](#find)の例を参照してください。

## <a name="catllistgethead"></a><a name="gethead"></a>カトルリスト::ゲットヘッド

リストの先頭にある要素を返します。

```
E& GetHead() throw();
const E& GetHead() const throw();
```

### <a name="return-value"></a>戻り値

リストの先頭にある要素への参照または要素のコピーを返します。

### <a name="remarks"></a>解説

リストが**const**の`GetHead`場合は、リストの先頭にある要素のコピーを返します。 これにより、メソッドは代入ステートメントの右側でのみ使用でき、リストが変更されないように保護されます。

リストが**const**でない場合`GetHead`は、リストの先頭にある要素への参照を返します。 これにより、メソッドは代入ステートメントの両側で使用され、リストエントリを変更することができます。

デバッグ ビルドでは、リストの先頭が NULL を指すとアサーション エラーが発生します。

### <a name="example"></a>例

[次](#addhead)の例を参照してください。

## <a name="catllistgetheadposition"></a><a name="getheadposition"></a>カトルリスト::ゲットヘッドポジション

リストの先頭の位置を取得します。

```
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>戻り値

リストの先頭にある要素に対応する POSITION 値を返します。

### <a name="remarks"></a>解説

リストが空の場合、返される値は NULL です。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#21](../../atl/codesnippet/cpp/catllist-class_9.cpp)]

## <a name="catllistgetnext"></a><a name="getnext"></a>カトルリスト::次に取得

リストから次の要素を返します。

```
E& GetNext(POSITION& pos) throw();
const E& GetNext(POSITION& pos) const throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
以前の呼び出し`GetNext`によって返される POSITION 値 、 [CAtlList::GetHeadPosition](#getheadposition)、またはその他の`CAtlList`メソッド。

### <a name="return-value"></a>戻り値

リストが**const**の`GetNext`場合は、リストの次の要素のコピーを返します。 これにより、メソッドは代入ステートメントの右側でのみ使用でき、リストが変更されないように保護されます。

リストが**const**でない場合`GetNext`は、リストの次の要素への参照を返します。 これにより、メソッドは代入ステートメントの両側で使用され、リストエントリを変更することができます。

### <a name="remarks"></a>解説

POSITION カウンタ*pos*は、リスト内の次の要素を指すために更新され、要素がなくなった場合は NULL になります。 デバッグ ビルドでは *、pos*が NULL に等しい場合、アサーション エラーが発生します。

### <a name="example"></a>例

[の](#getheadposition)例を参照してください。

## <a name="catllistgetprev"></a><a name="getprev"></a>カトルリスト::ゲットプレフ

リストから前の要素を返します。

```
E& GetPrev(POSITION& pos) throw();
const E& GetPrev(POSITION& pos) const throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
以前の呼び出し`GetPrev`によって返される POSITION 値 、 [CAtlList::GetTailPosition](#gettailposition)、またはその他の`CAtlList`メソッド。

### <a name="return-value"></a>戻り値

リストが**const**の`GetPrev`場合は、リストの要素のコピーを返します。 これにより、メソッドは代入ステートメントの右側でのみ使用でき、リストが変更されないように保護されます。

リストが**const**でない場合`GetPrev`は、リストの要素への参照を返します。 これにより、メソッドは代入ステートメントの両側で使用され、リストエントリを変更することができます。

### <a name="remarks"></a>解説

POSITION カウンタ*pos*は、リスト内の前の要素を指すために更新され、要素がなくなった場合は NULL になります。 デバッグ ビルドでは *、pos*が NULL に等しい場合、アサーション エラーが発生します。

### <a name="example"></a>例

[の](#gettailposition)例を参照してください。

## <a name="catllistgettail"></a><a name="gettail"></a>カトルリスト::ゲットテール

リストの末尾にある要素を返します。

```
E& GetTail() throw();
const E& GetTail() const throw();
```

### <a name="return-value"></a>戻り値

リストの末尾にある要素への参照または要素のコピーを返します。

### <a name="remarks"></a>解説

リストが**const**の`GetTail`場合は、リストの先頭にある要素のコピーを返します。 これにより、メソッドは代入ステートメントの右側でのみ使用でき、リストが変更されないように保護されます。

リストが**const**でない場合`GetTail`は、リストの先頭にある要素への参照を返します。 これにより、メソッドは代入ステートメントの両側で使用され、リストエントリを変更することができます。

デバッグ ビルドでは、リストの末尾が NULL を指している場合、アサーション エラーが発生します。

### <a name="example"></a>例

[次](#addtail)の例を参照してください。

## <a name="catllistgettailposition"></a><a name="gettailposition"></a>カトルリスト::ゲットテールポジション

リストの末尾の位置を取得します。

```
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>戻り値

リストの末尾にある要素に対応する POSITION 値を返します。

### <a name="remarks"></a>解説

リストが空の場合、返される値は NULL です。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#22](../../atl/codesnippet/cpp/catllist-class_10.cpp)]

## <a name="catllistinargtype"></a><a name="inargtype"></a>カトルリスト::イナルグタイプ

要素が入力引数として渡されるときに使用される型。

```
typedef ETraits::INARGTYPE INARGTYPE;
```

## <a name="catllistinsertafter"></a><a name="insertafter"></a>CAtlList::後に挿入

指定した位置の後に新しい要素をリストに挿入します。

```
POSITION InsertAfter(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
新しい要素が挿入される位置の値。

*要素*<br/>
挿入する要素。

### <a name="return-value"></a>戻り値

新しい要素の位置値を返します。

### <a name="remarks"></a>解説

デバッグ ビルドでは、リストが有効でない場合、挿入に失敗した場合、または末尾の後に要素を挿入しようとした場合、アサーション エラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#23](../../atl/codesnippet/cpp/catllist-class_11.cpp)]

## <a name="catllistinsertbefore"></a><a name="insertbefore"></a>CAtlList::前に挿入

指定した位置の前に新しい要素をリストに挿入します。

```
POSITION InsertBefore(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
新しい要素は、この POSITION 値の前にリストに挿入されます。

*要素*<br/>
挿入する要素。

### <a name="return-value"></a>戻り値

新しい要素の位置値を返します。

### <a name="remarks"></a>解説

デバッグ ビルドでは、リストが有効でない場合、挿入に失敗した場合、または要素を先頭の前に挿入しようとした場合、アサーション エラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#24](../../atl/codesnippet/cpp/catllist-class_12.cpp)]

## <a name="catllistisempty"></a><a name="isempty"></a>カトルリスト::IsEmpty

リストが空かどうかを調べます。

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>戻り値

リストにオブジェクトが含まれている場合は true を返し、それ以外の場合は false を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#25](../../atl/codesnippet/cpp/catllist-class_13.cpp)]

## <a name="catllistmovetohead"></a><a name="movetohead"></a>カトルリスト::移動ヘッド

指定した要素をリストの先頭に移動します。

```cpp
void MoveToHead(POSITION pos) throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
移動する要素の POSITION 値。

### <a name="remarks"></a>解説

指定した要素は、現在の位置からリストの先頭に移動します。 デバッグ ビルドでは *、pos*が NULL に等しい場合、アサーション エラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#26](../../atl/codesnippet/cpp/catllist-class_14.cpp)]

## <a name="catllistmovetotail"></a><a name="movetotail"></a>カトルリスト:::ムーブトテール

指定した要素をリストの末尾に移動します。

```cpp
void MoveToTail(POSITION pos) throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
移動する要素の POSITION 値。

### <a name="remarks"></a>解説

指定した要素は、現在の位置からリストの末尾に移動されます。 デバッグ ビルドでは *、pos*が NULL に等しい場合、アサーション エラーが発生します。

### <a name="example"></a>例

[次](#movetohead)の例を参照してください。

## <a name="catllistremoveall"></a><a name="removeall"></a>一覧::すべて削除

リストからすべての要素を削除します。

```cpp
void RemoveAll() throw();
```

### <a name="remarks"></a>解説

このメソッドは、リストからすべての要素を削除し、割り当てられたメモリを解放します。 デバッグ ビルドでは、すべての要素が削除されていない場合、またはリスト構造が破損した場合に ATLASSERT が発生します。

### <a name="example"></a>例

[次](#isempty)の例を参照してください。

## <a name="catllistremoveat"></a><a name="removeat"></a>カトルリスト::削除アット

リストから 1 つの要素を削除します。

```cpp
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
削除する要素の POSITION 値。

### <a name="remarks"></a>解説

*pos*によって参照される要素が削除され、メモリが解放されます。 リストの頭または尾`RemoveAt`部を取り除くために使用しても構いません。

デバッグ ビルドでは、リストが有効でない場合、または要素を削除すると、リスト構造の一部ではないメモリにアクセスするアサーション エラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#27](../../atl/codesnippet/cpp/catllist-class_15.cpp)]

## <a name="catllistremovehead"></a><a name="removehead"></a>キャップルリスト::削除ヘッド

リストの先頭にある要素を削除します。

```
E RemoveHead();
```

### <a name="return-value"></a>戻り値

リストの先頭にある要素を返します。

### <a name="remarks"></a>解説

head 要素がリストから削除され、メモリが解放されます。 要素のコピーが返されます。 デバッグ ビルドでは、リストが空の場合にアサーション エラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#28](../../atl/codesnippet/cpp/catllist-class_16.cpp)]

## <a name="catllistremoveheadnoreturn"></a><a name="removeheadnoreturn"></a>CAtlリスト::リムートヘッドノーリターン

値を返さずに、リストの先頭にある要素を削除します。

```cpp
void RemoveHeadNoReturn() throw();
```

### <a name="remarks"></a>解説

head 要素がリストから削除され、メモリが解放されます。 デバッグ ビルドでは、リストが空の場合にアサーション エラーが発生します。

### <a name="example"></a>例

[次](#isempty)の例を参照してください。

## <a name="catllistremovetail"></a><a name="removetail"></a>カトルリスト::リムートテール

リストの末尾にある要素を削除します。

```
E RemoveTail();
```

### <a name="return-value"></a>戻り値

リストの末尾にある要素を返します。

### <a name="remarks"></a>解説

tail 要素がリストから削除され、メモリが解放されます。 要素のコピーが返されます。 デバッグ ビルドでは、リストが空の場合にアサーション エラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#29](../../atl/codesnippet/cpp/catllist-class_17.cpp)]

## <a name="catllistremovetailnoreturn"></a><a name="removetailnoreturn"></a>カトルリスト::リムープテールノーリターン

値を返さずに、リストの末尾にある要素を削除します。

```cpp
void RemoveTailNoReturn() throw();
```

### <a name="remarks"></a>解説

tail 要素がリストから削除され、メモリが解放されます。 デバッグ ビルドでは、リストが空の場合にアサーション エラーが発生します。

### <a name="example"></a>例

[次](#isempty)の例を参照してください。

## <a name="catllistsetat"></a><a name="setat"></a>カトルリスト::セットアット

リスト内の指定した位置にある要素の値を設定します。

```cpp
void SetAt(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
変更する要素に対応する POSITION 値。

*要素*<br/>
新しい要素の値。

### <a name="remarks"></a>解説

既存の値を*要素*で置き換えます。 デバッグ ビルドでは *、pos*が NULL に等しい場合、アサーション エラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#30](../../atl/codesnippet/cpp/catllist-class_18.cpp)]

## <a name="catllistswapelements"></a><a name="swapelements"></a>要素を指定します。

リスト内の要素を交換します。

```cpp
void SwapElements(POSITION pos1, POSITION pos2) throw();
```

### <a name="parameters"></a>パラメーター

*pos1*<br/>
最初の POSITION 値。

*pos2*<br/>
2 番目の位置値。

### <a name="remarks"></a>解説

指定した 2 つの位置で要素を入れ替えます。 デバッグ ビルドでは、いずれかの位置値が NULL に等しい場合にアサーション エラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#31](../../atl/codesnippet/cpp/catllist-class_19.cpp)]

## <a name="see-also"></a>関連項目

[CList クラス](../../mfc/reference/clist-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
