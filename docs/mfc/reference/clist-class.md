---
description: ': CList クラスの詳細情報'
title: CList クラス
ms.date: 11/04/2016
f1_keywords:
- CList
- AFXTEMPL/CList
- AFXTEMPL/CList::CList
- AFXTEMPL/CList::AddHead
- AFXTEMPL/CList::AddTail
- AFXTEMPL/CList::Find
- AFXTEMPL/CList::FindIndex
- AFXTEMPL/CList::GetAt
- AFXTEMPL/CList::GetCount
- AFXTEMPL/CList::GetHead
- AFXTEMPL/CList::GetHeadPosition
- AFXTEMPL/CList::GetNext
- AFXTEMPL/CList::GetPrev
- AFXTEMPL/CList::GetSize
- AFXTEMPL/CList::GetTail
- AFXTEMPL/CList::GetTailPosition
- AFXTEMPL/CList::InsertAfter
- AFXTEMPL/CList::InsertBefore
- AFXTEMPL/CList::IsEmpty
- AFXTEMPL/CList::RemoveAll
- AFXTEMPL/CList::RemoveAt
- AFXTEMPL/CList::RemoveHead
- AFXTEMPL/CList::RemoveTail
- AFXTEMPL/CList::SetAt
helpviewer_keywords:
- CList [MFC], CList
- CList [MFC], AddHead
- CList [MFC], AddTail
- CList [MFC], Find
- CList [MFC], FindIndex
- CList [MFC], GetAt
- CList [MFC], GetCount
- CList [MFC], GetHead
- CList [MFC], GetHeadPosition
- CList [MFC], GetNext
- CList [MFC], GetPrev
- CList [MFC], GetSize
- CList [MFC], GetTail
- CList [MFC], GetTailPosition
- CList [MFC], InsertAfter
- CList [MFC], InsertBefore
- CList [MFC], IsEmpty
- CList [MFC], RemoveAll
- CList [MFC], RemoveAt
- CList [MFC], RemoveHead
- CList [MFC], RemoveTail
- CList [MFC], SetAt
ms.assetid: 6f6273c3-c8f6-47f5-ac2a-0a950379ae5d
ms.openlocfilehash: e216bda53c37c325ffb8aeb943d4cefb223ac1d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236686"
---
# <a name="clist-class"></a>CList クラス

オブジェクト (重複あり) を順に並べたリストをサポートします。このリストには、シーケンシャル アクセスまたは値指定によるアクセスを行うことができます。

## <a name="syntax"></a>構文

```
template<class TYPE, class ARG_TYPE = const TYPE&>
class CList : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CList:: CList](#clist)|空の順序付きリストを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CList:: AddHead](#addhead)|要素 (または別のリスト内のすべての要素) をリストの先頭に追加します (新しい head を作成します)。|
|[CList:: AddTail](#addtail)|要素 (または別のリスト内のすべての要素) をリストの末尾に追加します (新しい末尾を作成します)。|
|[CList:: Find](#find)|ポインター値によって指定された要素の位置を取得します。|
|[CList:: FindIndex](#findindex)|0から始まるインデックスで指定された要素の位置を取得します。|
|[CList:: GetAt](#getat)|指定した位置にある要素を取得します。|
|[CList:: GetCount](#getcount)|このリスト内の要素の数を返します。|
|[CList:: GetHead](#gethead)|リストの head 要素を返します (空にすることはできません)。|
|[CList:: GetHeadPosition](#getheadposition)|リストの先頭の要素の位置を返します。|
|[CList:: GetNext](#getnext)|反復処理の対象となる次の要素を取得します。|
|[CList:: GetPrev](#getprev)|反復処理する前の要素を取得します。|
|[CList:: GetSize](#getsize)|このリスト内の要素の数を返します。|
|[CList:: GetTail](#gettail)|リストの末尾の要素を返します (空にすることはできません)。|
|[CList:: GetTailPosition](#gettailposition)|リストの末尾の要素の位置を返します。|
|[CList:: InsertAfter](#insertafter)|指定された位置の後に新しい要素を挿入します。|
|[CList::InsertBefore](#insertbefore)|指定した位置の前に新しい要素を挿入します。|
|[CList:: IsEmpty](#isempty)|空のリスト条件 (要素なし) があるかどうかをテストします。|
|[CList:: RemoveAll](#removeall)|このリストからすべての要素を削除します。|
|[CList:: RemoveAt](#removeat)|位置によって指定された、このリストから要素を削除します。|
|[CList:: RemoveHead](#removehead)|リストの先頭から要素を削除します。|
|[CList:: RemoveTail ます](#removetail)|リストの末尾から要素を削除します。|
|[CList:: SetAt](#setat)|指定された位置に要素を設定します。|

#### <a name="parameters"></a>パラメーター

*TYPE*<br/>
リストに格納されているオブジェクトの型。

*ARG_TYPE*<br/>
リストに格納されているオブジェクトを参照するために使用される型。 参照を指定できます。

## <a name="remarks"></a>解説

`CList` リストは、二重リンクリストのように動作します。

POSITION 型の変数は、リストのキーです。 位置変数を反復子として使用して、リストを順番に、または場所を保持するブックマークとして走査できます。 ただし、位置はインデックスと同じではありません。

要素の挿入は、リストの先頭、末尾、および既知の位置で非常に高速です。 値またはインデックスによって要素を検索するには、順次検索が必要です。 リストが長い場合、この検索は遅くなることがあります。

リスト内の個々の要素のダンプが必要な場合は、ダンプコンテキストの深さを1以上に設定する必要があります。

このクラスの特定のメンバー関数は、クラスのほとんどの用途に合わせてカスタマイズする必要があるグローバルヘルパー関数を呼び出し `CList` ます。 「マクロとグローバル」セクションの「 [コレクションクラスヘルパー](../../mfc/reference/collection-class-helpers.md) 」を参照してください。

の使用方法の詳細については `CList` 、「 [コレクション](../../mfc/collections.md)」を参照してください。

## <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#35](../../mfc/codesnippet/cpp/clist-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CList`

## <a name="requirements"></a>要件

**ヘッダー:** afxtempl.h

## <a name="clistaddhead"></a><a name="addhead"></a> CList:: AddHead

このリストの先頭に新しい要素または要素のリストを追加します。

```
POSITION AddHead(ARG_TYPE newElement);
void AddHead(CList* pNewList);
```

### <a name="parameters"></a>パラメーター

*ARG_TYPE*<br/>
一覧の要素の型を指定するテンプレート パラメーター (参照を使用できます)。

*(Newelement*<br/>
新しい要素。

*pNewList*<br/>
別のリストへのポインター `CList` 。 *Pnewlist* 内の要素が、この一覧に追加されます。

### <a name="return-value"></a>戻り値

最初のバージョンは、新しく挿入された要素の位置の値を返します。

### <a name="remarks"></a>解説

操作の前に、リストを空にすることができます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#36](../../mfc/codesnippet/cpp/clist-class_2.cpp)]

## <a name="clistaddtail"></a><a name="addtail"></a> CList:: AddTail

このリストの末尾に新しい要素または要素のリストを追加します。

```
POSITION AddTail(ARG_TYPE newElement);
void AddTail(CList* pNewList);
```

### <a name="parameters"></a>パラメーター

*ARG_TYPE*<br/>
一覧の要素の型を指定するテンプレート パラメーター (参照を使用できます)。

*(Newelement*<br/>
この一覧に追加する要素。

*pNewList*<br/>
別のリストへのポインター `CList` 。 *Pnewlist* 内の要素が、この一覧に追加されます。

### <a name="return-value"></a>戻り値

最初のバージョンは、新しく挿入された要素の位置の値を返します。

### <a name="remarks"></a>解説

操作の前に、リストを空にすることができます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#37](../../mfc/codesnippet/cpp/clist-class_3.cpp)]

## <a name="clistclist"></a><a name="clist"></a> CList:: CList

空の順序付きリストを構築します。

```
CList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>パラメーター

*nBlockSize*<br/>
リストを拡張するためのメモリ割り当ての粒度。

### <a name="remarks"></a>解説

リストが大きくなるにつれて、メモリは *Nblocksize* エントリの単位で割り当てられます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#38](../../mfc/codesnippet/cpp/clist-class_4.cpp)]

## <a name="clistfind"></a><a name="find"></a> CList:: Find

リストを順番に検索し、指定された *Searchvalue* に一致する最初の要素を検索します。

```
POSITION Find(
    ARG_TYPE searchValue,
    POSITION startAfter = NULL) const;
```

### <a name="parameters"></a>パラメーター

*ARG_TYPE*<br/>
一覧の要素の型を指定するテンプレート パラメーター (参照を使用できます)。

*searchValue*<br/>
リスト内で検索する値。

*startAfter*<br/>
検索の開始位置。 値が指定されていない場合は、先頭の要素から検索が開始されます。

### <a name="return-value"></a>戻り値

反復またはオブジェクトポインターの取得に使用できる位置の値。オブジェクトが見つからない場合は NULL です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#39](../../mfc/codesnippet/cpp/clist-class_5.cpp)]

## <a name="clistfindindex"></a><a name="findindex"></a> CList:: FindIndex

リストのインデックスとして、 *nIndex* の値を使用します。

```
POSITION FindIndex(INT_PTR nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
検索するリスト要素の0から始まるインデックス。

### <a name="return-value"></a>戻り値

反復またはオブジェクトポインターの取得に使用できる位置の値。 *NIndex* が負の値または大きすぎる場合は NULL になります。

### <a name="remarks"></a>解説

リストの先頭からシーケンシャルスキャンを開始し、 *n* 番目の要素に対して停止します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#40](../../mfc/codesnippet/cpp/clist-class_6.cpp)]

## <a name="clistgetat"></a><a name="getat"></a> CList:: GetAt

指定された位置にあるリスト要素を取得します。

```
TYPE& GetAt(POSITION position);
const TYPE& GetAt(POSITION position) const;
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
リスト内のオブジェクトの種類を指定するテンプレートパラメーター。

*position*<br/>
取得する要素のリスト内の位置。

### <a name="return-value"></a>戻り値

の戻り値の説明を参照してください `GetHead` 。

### <a name="remarks"></a>解説

`GetAt` 指定した位置に関連付けられている要素 (または要素への参照) を返します。 インデックスとは異なり、位置の値を自分で操作することはできません。 POSITION 型の変数は、リストのキーです。

位置の値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。

### <a name="example"></a>例

  「 [CList:: GetHeadPosition](#getheadposition)」の例を参照してください。

## <a name="clistgetcount"></a><a name="getcount"></a> CList:: GetCount

このリスト内の要素の数を取得します。

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>戻り値

要素の数を表す整数値です。

### <a name="remarks"></a>解説

このメソッドを呼び出すと、 [CList:: GetSize](#getsize) メソッドと同じ結果が生成されます。

### <a name="example"></a>例

  「 [CList:: RemoveHead](#removehead)」の例を参照してください。

## <a name="clistgethead"></a><a name="gethead"></a> CList:: GetHead

このリストの head 要素 (または head 要素への参照) を取得します。

```
const TYPE& GetHead() const;

TYPE& GetHead();
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
リスト内のオブジェクトの種類を指定するテンプレートパラメーター。

### <a name="return-value"></a>戻り値

リストがの場合は **`const`** 、 `GetHead` リストの先頭にある要素のコピーを返します。 これにより、関数を代入ステートメントの右辺でのみ使用し、そのリストを変更から保護することができます。

リストがでない場合は **`const`** 、 `GetHead` リストの先頭にある要素への参照を返します。 これにより、関数を代入ステートメントのどちら側でも使用できるようになり、リストエントリを変更できるようになります。

### <a name="remarks"></a>解説

を呼び出す前に、リストが空でないことを確認する必要があり `GetHead` ます。 リストが空の場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。 [IsEmpty](#isempty)を使用して、リストに要素が含まれていることを確認します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#41](../../mfc/codesnippet/cpp/clist-class_7.cpp)]

## <a name="clistgetheadposition"></a><a name="getheadposition"></a> CList:: GetHeadPosition

このリストの先頭の要素の位置を取得します。

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>戻り値

反復またはオブジェクトポインターの取得に使用できる位置の値。リストが空の場合は NULL です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#42](../../mfc/codesnippet/cpp/clist-class_8.cpp)]

## <a name="clistgetnext"></a><a name="getnext"></a> CList:: GetNext

*RPosition* によって識別されるリスト要素を取得し、 *rPosition* をリスト内の次のエントリの位置の値に設定します。

```
TYPE& GetNext(POSITION& rPosition);
const TYPE& GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
リスト内の要素の型を指定するテンプレートパラメーター。

*rPosition*<br/>
Previous `GetNext` 、 [getheadposition](#getheadposition)、またはその他のメンバー関数呼び出しによって返される位置値への参照。

### <a name="return-value"></a>戻り値

リストがの場合は **`const`** 、 `GetNext` リストの要素のコピーを返します。 これにより、関数を代入ステートメントの右辺でのみ使用し、そのリストを変更から保護することができます。

リストがでない場合は **`const`** 、 `GetNext` リストの要素への参照を返します。 これにより、関数を代入ステートメントのどちら側でも使用できるようになり、リストエントリを変更できるようになります。

### <a name="remarks"></a>解説

`GetNext`またはへの呼び出しを使用して初期位置を設定した場合は、前方反復ループでを使用でき `GetHeadPosition` `Find` ます。

位置の値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。

取得した要素がリスト内の最後の要素である場合、の新しい値 `rPosition` は NULL に設定されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#43](../../mfc/codesnippet/cpp/clist-class_9.cpp)]

## <a name="clistgetprev"></a><a name="getprev"></a> CList:: GetPrev

によって識別されるリスト要素を取得 `rPosition` し、 `rPosition` リスト内の前のエントリの位置の値をに設定します。

```
TYPE& GetPrev(POSITION& rPosition);
const TYPE& GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
リスト内の要素の型を指定するテンプレートパラメーター。

*rPosition*<br/>
前の `GetPrev` または他のメンバー関数呼び出しによって返される位置値への参照。

### <a name="return-value"></a>戻り値

リストがの場合は **`const`** 、 `GetPrev` リストの先頭にある要素のコピーを返します。 これにより、関数を代入ステートメントの右辺でのみ使用し、そのリストを変更から保護することができます。

リストがでない場合は **`const`** 、 `GetPrev` リストの要素への参照を返します。 これにより、関数を代入ステートメントのどちら側でも使用できるようになり、リストエントリを変更できるようになります。

### <a name="remarks"></a>解説

またはの呼び出しを使用し `GetPrev` て初期位置を設定した場合は、逆反復ループでを使用でき `GetTailPosition` `Find` ます。

位置の値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。

取得した要素がリスト内の最初の要素の場合、 *rPosition* の新しい値は NULL に設定されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#44](../../mfc/codesnippet/cpp/clist-class_10.cpp)]

## <a name="clistgetsize"></a><a name="getsize"></a> CList:: GetSize

リスト要素の数を返します。

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>戻り値

一覧にあるアイテムの数です。

### <a name="remarks"></a>解説

リスト内の要素の数を取得するには、このメソッドを呼び出します。  このメソッドを呼び出すと、 [CList:: GetCount](#getcount) メソッドと同じ結果が生成されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#45](../../mfc/codesnippet/cpp/clist-class_11.cpp)]

## <a name="clistgettail"></a><a name="gettail"></a> CList:: GetTail

`CObject`このリストの末尾の要素を表すポインターを取得します。

```
TYPE& GetTail();
const TYPE& GetTail() const;
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
リスト内の要素の型を指定するテンプレートパラメーター。

### <a name="return-value"></a>戻り値

[GetHead](../../mfc/reference/coblist-class.md#gethead)の戻り値の説明を参照してください。

### <a name="remarks"></a>解説

を呼び出す前に、リストが空でないことを確認する必要があり `GetTail` ます。 リストが空の場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。 [IsEmpty](../../mfc/reference/coblist-class.md#isempty)を使用して、リストに要素が含まれていることを確認します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#46](../../mfc/codesnippet/cpp/clist-class_12.cpp)]

## <a name="clistgettailposition"></a><a name="gettailposition"></a> CList:: GetTailPosition

このリストの末尾の要素の位置を取得します。リストが空の場合は NULL です。

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>戻り値

反復またはオブジェクトポインターの取得に使用できる位置の値。リストが空の場合は NULL です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#47](../../mfc/codesnippet/cpp/clist-class_13.cpp)]

## <a name="clistinsertafter"></a><a name="insertafter"></a> CList:: InsertAfter

指定した位置にある要素の後に、このリストに要素を追加します。

```
POSITION InsertAfter(POSITION position, ARG_TYPE newElement);
```

### <a name="parameters"></a>パラメーター

*position*<br/>
前 `GetNext` の、 `GetPrev` 、または `Find` メンバー関数呼び出しによって返される位置の値。

*ARG_TYPE*<br/>
リスト要素の型を指定するテンプレートパラメーター。

*(Newelement*<br/>
この一覧に追加する要素。

### <a name="return-value"></a>戻り値

イテレーションまたは一覧の要素の取得に使用できる POSITION 値。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#48](../../mfc/codesnippet/cpp/clist-class_14.cpp)]

## <a name="clistinsertbefore"></a><a name="insertbefore"></a> CList:: InsertBefore

一覧の指定した位置にある要素の前に要素を追加します。

```
POSITION InsertBefore(POSITION position, ARG_TYPE newElement);
```

### <a name="parameters"></a>パラメーター

*position*<br/>
前 `GetNext` の、 `GetPrev` 、または `Find` メンバー関数呼び出しによって返される位置の値。

*ARG_TYPE*<br/>
一覧の要素の型を指定するテンプレート パラメーター (参照を使用できます)。

*(Newelement*<br/>
この一覧に追加する要素。

### <a name="return-value"></a>戻り値

イテレーションまたは一覧の要素の取得に使用できる POSITION 値。

### <a name="remarks"></a>解説

*Position* が NULL の場合、要素はリストの先頭に挿入されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#49](../../mfc/codesnippet/cpp/clist-class_15.cpp)]

## <a name="clistisempty"></a><a name="isempty"></a> CList:: IsEmpty

このリストに要素が含まれていないかどうかを示します。

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>戻り値

このリストが空の場合は0以外の。それ以外の場合は0です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#50](../../mfc/codesnippet/cpp/clist-class_16.cpp)]

## <a name="clistremoveall"></a><a name="removeall"></a> CList:: RemoveAll

このリストからすべての要素を削除し、関連付けられているメモリを解放します。

```cpp
void RemoveAll();
```

### <a name="remarks"></a>解説

リストが既に空の場合、エラーは生成されません。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#51](../../mfc/codesnippet/cpp/clist-class_17.cpp)]

## <a name="clistremoveat"></a><a name="removeat"></a> CList:: RemoveAt

指定した要素をこのリストから削除します。

```cpp
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>パラメーター

*position*<br/>
リストから削除する要素の位置。

### <a name="remarks"></a>解説

位置の値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#52](../../mfc/codesnippet/cpp/clist-class_18.cpp)]

## <a name="clistremovehead"></a><a name="removehead"></a> CList:: RemoveHead

リストの先頭から要素を削除し、その要素へのポインターを返します。

```
TYPE RemoveHead();
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
リスト内の要素の型を指定するテンプレートパラメーター。

### <a name="return-value"></a>戻り値

リストの先頭にある要素。

### <a name="remarks"></a>解説

を呼び出す前に、リストが空でないことを確認する必要があり `RemoveHead` ます。 リストが空の場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。 [IsEmpty](#isempty)を使用して、リストに要素が含まれていることを確認します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#53](../../mfc/codesnippet/cpp/clist-class_19.cpp)]

## <a name="clistremovetail"></a><a name="removetail"></a> CList:: RemoveTail ます

リストの末尾から要素を削除し、その要素へのポインターを返します。

```
TYPE RemoveTail();
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
リスト内の要素の型を指定するテンプレートパラメーター。

### <a name="return-value"></a>戻り値

リストの末尾にある要素。

### <a name="remarks"></a>解説

を呼び出す前に、リストが空でないことを確認する必要があり `RemoveTail` ます。 リストが空の場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。 [IsEmpty](#isempty)を使用して、リストに要素が含まれていることを確認します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#54](../../mfc/codesnippet/cpp/clist-class_20.cpp)]

## <a name="clistsetat"></a><a name="setat"></a> CList:: SetAt

POSITION 型の変数は、リストのキーです。

```cpp
void SetAt(POSITION pos, ARG_TYPE newElement);
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
設定する要素の位置。

*ARG_TYPE*<br/>
一覧の要素の型を指定するテンプレート パラメーター (参照を使用できます)。

*(Newelement*<br/>
リストに追加する要素。

### <a name="remarks"></a>解説

インデックスとは異なり、位置の値を自分で操作することはできません。 `SetAt` リスト内の指定した位置に要素を書き込みます。

位置の値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#55](../../mfc/codesnippet/cpp/clist-class_21.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル収集](../../overview/visual-cpp-samples.md)<br/>
[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CMap クラス](../../mfc/reference/cmap-class.md)<br/>
[CArray クラス](../../mfc/reference/carray-class.md)
