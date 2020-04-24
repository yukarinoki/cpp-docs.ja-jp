---
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
ms.openlocfilehash: adc065687f0c2c40b7e66326ff9d1e6210a6962c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754134"
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
|[Cリスト::Cリスト](#clist)|空の順序付きリストを作成します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[リスト::アドヘッド](#addhead)|リストの先頭に要素 (または別のリストのすべての要素) を追加します (新しいヘッドを作成)。|
|[リスト::追加テール](#addtail)|リストの末尾に要素 (または別のリストのすべての要素) を追加します (新しい末尾になります)。|
|[Cリスト::検索](#find)|ポインター値で指定された要素の位置を取得します。|
|[一覧::インデックスを検索します。](#findindex)|0 から始まるインデックスで指定された要素の位置を取得します。|
|[リスト::ゲットアット](#getat)|指定した位置にある要素を取得します。|
|[一覧::カウントを取得します。](#getcount)|このリスト内の要素の数を返します。|
|[リスト::ゲットヘッド](#gethead)|リストの head 要素を返します (空にすることはできません)。|
|[リスト::ゲットヘッドポジション](#getheadposition)|リストの先頭要素の位置を返します。|
|[次のリストを取得します。](#getnext)|反復処理の次の要素を取得します。|
|[リスト::ゲットプレフ](#getprev)|反復処理の前の要素を取得します。|
|[箇条のリスト::ゲットサイズ](#getsize)|このリスト内の要素の数を返します。|
|[リスト::ゲットテール](#gettail)|リストの末尾要素を返します (空にすることはできません)。|
|[リスト::ゲットテールポジション](#gettailposition)|リストの末尾要素の位置を返します。|
|[箇条のリスト::後に挿入](#insertafter)|指定した位置の後に新しい要素を挿入します。|
|[CList::InsertBefore](#insertbefore)|指定した位置の前に新しい要素を挿入します。|
|[リスト::空です](#isempty)|空のリスト条件 (要素なし) をテストします。|
|[リスト::すべて削除](#removeall)|このリストからすべての要素を削除します。|
|[リスト::削除アット](#removeat)|位置で指定された、このリストから要素を削除します。|
|[リスト::ヘッドの削除](#removehead)|リストの先頭から要素を削除します。|
|[Cリスト::リムープテール](#removetail)|リストの末尾から要素を削除します。|
|[箇条座::セットアット](#setat)|指定した位置に要素を設定します。|

#### <a name="parameters"></a>パラメーター

*種類*<br/>
リストに格納されているオブジェクトの型。

*ARG_TYPE*<br/>
リストに格納されているオブジェクトを参照するために使用する型です。 参照することができます。

## <a name="remarks"></a>解説

`CList`リストは、二重にリンクされたリストのように動作します。

POSITION 型の変数は、リストのキーです。 POSITION 変数を反復器として使用して、リストを順番に走査したり、場所を保持するブックマークとして使用したりできます。 ただし、位置はインデックスと同じではありません。

要素の挿入は、リストヘッド、末尾、および既知の位置で非常に高速です。 値またはインデックスで要素を検索するには、順次検索が必要です。 この検索は、リストが長い場合に低速になる可能性があります。

リスト内の個々の要素のダンプが必要な場合は、ダンプ コンテキストの深さを 1 以上に設定する必要があります。

このクラスの特定のメンバー関数は、クラスのほとんどの使用に合わせてカスタマイズする必要があるグローバル`CList`ヘルパ関数を呼び出します。 「マクロとグローバル」セクションの[コレクション クラス ヘルパー](../../mfc/reference/collection-class-helpers.md)を参照してください。

の使用方法`CList`の詳細については、[記事の「コレクション](../../mfc/collections.md)」を参照してください。

## <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#35](../../mfc/codesnippet/cpp/clist-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CList`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxtempl.h

## <a name="clistaddhead"></a><a name="addhead"></a>リスト::アドヘッド

このリストの先頭に新しい要素または要素のリストを追加します。

```
POSITION AddHead(ARG_TYPE newElement);
void AddHead(CList* pNewList);
```

### <a name="parameters"></a>パラメーター

*ARG_TYPE*<br/>
一覧の要素の型を指定するテンプレート パラメーター (参照を使用できます)。

*新しい要素*<br/>
新しい要素。

*をクリックします。*<br/>
別`CList`のリストへのポインター。 *pNewList*の要素がこのリストに追加されます。

### <a name="return-value"></a>戻り値

最初のバージョンは、新しく挿入された要素の POSITION 値を返します。

### <a name="remarks"></a>解説

リストは、操作の前に空にすることができます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#36](../../mfc/codesnippet/cpp/clist-class_2.cpp)]

## <a name="clistaddtail"></a><a name="addtail"></a>リスト::追加テール

このリストの末尾に新しい要素または要素のリストを追加します。

```
POSITION AddTail(ARG_TYPE newElement);
void AddTail(CList* pNewList);
```

### <a name="parameters"></a>パラメーター

*ARG_TYPE*<br/>
一覧の要素の型を指定するテンプレート パラメーター (参照を使用できます)。

*新しい要素*<br/>
この一覧に追加する要素。

*をクリックします。*<br/>
別`CList`のリストへのポインター。 *pNewList*の要素がこのリストに追加されます。

### <a name="return-value"></a>戻り値

最初のバージョンは、新しく挿入された要素の POSITION 値を返します。

### <a name="remarks"></a>解説

リストは、操作の前に空にすることができます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#37](../../mfc/codesnippet/cpp/clist-class_3.cpp)]

## <a name="clistclist"></a><a name="clist"></a>Cリスト::Cリスト

空の順序付きリストを作成します。

```
CList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>パラメーター

*ブロックサイズ*<br/>
リストを拡張するためのメモリ割り当ての粒度。

### <a name="remarks"></a>解説

リストが大きくなると、メモリは*nBlockSize*エントリの単位で割り当てられます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#38](../../mfc/codesnippet/cpp/clist-class_4.cpp)]

## <a name="clistfind"></a><a name="find"></a>Cリスト::検索

リストを順番に検索して、指定した*検索値*に一致する最初の要素を検索します。

```
POSITION Find(
    ARG_TYPE searchValue,
    POSITION startAfter = NULL) const;
```

### <a name="parameters"></a>パラメーター

*ARG_TYPE*<br/>
一覧の要素の型を指定するテンプレート パラメーター (参照を使用できます)。

*検索値*<br/>
リスト内で見つかる値。

*開始後*<br/>
検索の開始位置。 値を指定しない場合、検索は head 要素から開始されます。

### <a name="return-value"></a>戻り値

反復またはオブジェクト・ポインターの取得に使用できる POSITION 値。オブジェクトが見つからない場合は NULL。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#39](../../mfc/codesnippet/cpp/clist-class_5.cpp)]

## <a name="clistfindindex"></a><a name="findindex"></a>一覧::インデックスを検索します。

*nIndex*の値をリストのインデックスとして使用します。

```
POSITION FindIndex(INT_PTR nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
検索するリスト要素の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

反復またはオブジェクト・ポインターの取得に使用できる POSITION 値。*nIndex が*負の値または大きすぎる場合は NULL です。

### <a name="remarks"></a>解説

リストの先頭から順次スキャンを開始し *、n*番目の要素で停止します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#40](../../mfc/codesnippet/cpp/clist-class_6.cpp)]

## <a name="clistgetat"></a><a name="getat"></a>リスト::ゲットアット

指定した位置にあるリスト要素を取得します。

```
TYPE& GetAt(POSITION position);
const TYPE& GetAt(POSITION position) const;
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
リスト内のオブジェクトのタイプを指定するテンプレートパラメータ。

*位置*<br/>
取得する要素のリスト内の位置。

### <a name="return-value"></a>戻り値

の戻り値の説明`GetHead`を参照してください。

### <a name="remarks"></a>解説

`GetAt`指定された位置に関連付けられた要素 (または要素への参照) を返します。 これはインデックスと同じではなく、POSITION 値を自分で操作することはできません。 POSITION 型の変数は、リストのキーです。

POSITION 値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。

### <a name="example"></a>例

  [次](#getheadposition)の例を参照してください。

## <a name="clistgetcount"></a><a name="getcount"></a>一覧::カウントを取得します。

このリスト内の要素の数を取得します。

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>戻り値

要素数を含む整数値。

### <a name="remarks"></a>解説

このメソッドを呼び出すと[、CList::GetSize](#getsize)メソッドと同じ結果が生成されます。

### <a name="example"></a>例

  [CList::RemoveHead](#removehead)の例を参照してください。

## <a name="clistgethead"></a><a name="gethead"></a>リスト::ゲットヘッド

このリストの head 要素 (または head 要素への参照) を取得します。

```
const TYPE& GetHead() const;

TYPE& GetHead();
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
リスト内のオブジェクトのタイプを指定するテンプレートパラメータ。

### <a name="return-value"></a>戻り値

リストが**const**の`GetHead`場合は、リストの先頭にある要素のコピーを返します。 これにより、関数は代入ステートメントの右側でのみ使用でき、リストが変更されないように保護されます。

リストが**const**でない場合`GetHead`は、リストの先頭にある要素への参照を返します。 これにより、代入ステートメントの両側で関数を使用できるため、リストエントリを変更できます。

### <a name="remarks"></a>解説

を呼び出す`GetHead`前に、リストが空でないことを確認する必要があります。 リストが空の場合、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。 [IsEmpty](#isempty)を使用して、リストに要素が含まれていることを確認します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#41](../../mfc/codesnippet/cpp/clist-class_7.cpp)]

## <a name="clistgetheadposition"></a><a name="getheadposition"></a>リスト::ゲットヘッドポジション

このリストの head 要素の位置を取得します。

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>戻り値

反復またはオブジェクト・ポインターの取得に使用できる POSITION 値。リストが空の場合は NULL。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#42](../../mfc/codesnippet/cpp/clist-class_8.cpp)]

## <a name="clistgetnext"></a><a name="getnext"></a>次のリストを取得します。

*rPosition*で識別されるリスト要素を取得し *、rPosition*をリスト内の次のエントリの POSITION 値に設定します。

```
TYPE& GetNext(POSITION& rPosition);
const TYPE& GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
リスト内の要素の型を指定するテンプレート パラメーター。

*r位置*<br/>
前`GetNext`の関数呼び出し[、GetHeadPosition、](#getheadposition)またはその他のメンバー関数呼び出しによって返された POSITION 値への参照。

### <a name="return-value"></a>戻り値

リストが**const**の`GetNext`場合は、リストの要素のコピーを返します。 これにより、関数は代入ステートメントの右側でのみ使用でき、リストが変更されないように保護されます。

リストが**const**でない場合`GetNext`は、リストの要素への参照を返します。 これにより、代入ステートメントの両側で関数を使用できるため、リストエントリを変更できます。

### <a name="remarks"></a>解説

または への`GetNext`呼び出し`GetHeadPosition`で初期位置を確立する場合は、順方向反復`Find`ループで使用できます。

POSITION 値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。

取得した要素がリストの最後の要素である場合、新しい値`rPosition`は NULL に設定されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#43](../../mfc/codesnippet/cpp/clist-class_9.cpp)]

## <a name="clistgetprev"></a><a name="getprev"></a>リスト::ゲットプレフ

で`rPosition`識別されるリスト要素を取得し、`rPosition`リスト内の前のエントリの POSITION 値を設定します。

```
TYPE& GetPrev(POSITION& rPosition);
const TYPE& GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
リスト内の要素の型を指定するテンプレート パラメーター。

*r位置*<br/>
前`GetPrev`のメンバー関数呼び出しまたは他のメンバー関数呼び出しによって返された POSITION 値への参照。

### <a name="return-value"></a>戻り値

リストが**const**の`GetPrev`場合は、リストの先頭にある要素のコピーを返します。 これにより、関数は代入ステートメントの右側でのみ使用でき、リストが変更されないように保護されます。

リストが**const**でない場合`GetPrev`は、リストの要素への参照を返します。 これにより、代入ステートメントの両側で関数を使用できるため、リストエントリを変更できます。

### <a name="remarks"></a>解説

または への`GetPrev`呼び出し`GetTailPosition`で初期位置を確立する場合は、逆反復ループ`Find`で使用できます。

POSITION 値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。

取得した要素がリストの最初の要素である場合 *、rPosition*の新しい値は NULL に設定されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#44](../../mfc/codesnippet/cpp/clist-class_10.cpp)]

## <a name="clistgetsize"></a><a name="getsize"></a>箇条のリスト::ゲットサイズ

リスト要素の数を返します。

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>戻り値

一覧にあるアイテムの数です。

### <a name="remarks"></a>解説

リスト内の要素の数を取得します。  このメソッドを呼び出すと[、CList::GetCount](#getcount)メソッドと同じ結果が生成されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#45](../../mfc/codesnippet/cpp/clist-class_11.cpp)]

## <a name="clistgettail"></a><a name="gettail"></a>リスト::ゲットテール

このリスト`CObject`の末尾要素を表すポインターを取得します。

```
TYPE& GetTail();
const TYPE& GetTail() const;
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
リスト内の要素の型を指定するテンプレート パラメーター。

### <a name="return-value"></a>戻り値

[GetHead](../../mfc/reference/coblist-class.md#gethead)の戻り値の説明を参照してください。

### <a name="remarks"></a>解説

を呼び出す`GetTail`前に、リストが空でないことを確認する必要があります。 リストが空の場合、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。 [IsEmpty](../../mfc/reference/coblist-class.md#isempty)を使用して、リストに要素が含まれていることを確認します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#46](../../mfc/codesnippet/cpp/clist-class_12.cpp)]

## <a name="clistgettailposition"></a><a name="gettailposition"></a>リスト::ゲットテールポジション

このリストの末尾要素の位置を取得します。リストが空の場合は NULL。

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>戻り値

反復またはオブジェクト・ポインターの取得に使用できる POSITION 値。リストが空の場合は NULL。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#47](../../mfc/codesnippet/cpp/clist-class_13.cpp)]

## <a name="clistinsertafter"></a><a name="insertafter"></a>箇条のリスト::後に挿入

指定した位置にある要素の後に、このリストに要素を追加します。

```
POSITION InsertAfter(POSITION position, ARG_TYPE newElement);
```

### <a name="parameters"></a>パラメーター

*位置*<br/>
前`GetNext`の関数呼び出し`GetPrev`、、`Find`またはメンバー関数呼び出しによって返された POSITION 値。

*ARG_TYPE*<br/>
リスト要素の型を指定するテンプレート パラメーター。

*新しい要素*<br/>
この一覧に追加する要素。

### <a name="return-value"></a>戻り値

イテレーションまたは一覧の要素の取得に使用できる POSITION 値。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#48](../../mfc/codesnippet/cpp/clist-class_14.cpp)]

## <a name="clistinsertbefore"></a><a name="insertbefore"></a>箇条のリスト::前に挿入

一覧の指定した位置にある要素の前に要素を追加します。

```
POSITION InsertBefore(POSITION position, ARG_TYPE newElement);
```

### <a name="parameters"></a>パラメーター

*位置*<br/>
前`GetNext`の関数呼び出し`GetPrev`、、`Find`またはメンバー関数呼び出しによって返された POSITION 値。

*ARG_TYPE*<br/>
一覧の要素の型を指定するテンプレート パラメーター (参照を使用できます)。

*新しい要素*<br/>
この一覧に追加する要素。

### <a name="return-value"></a>戻り値

イテレーションまたは一覧の要素の取得に使用できる POSITION 値。

### <a name="remarks"></a>解説

*位置*が NULL の場合、要素はリストの先頭に挿入されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#49](../../mfc/codesnippet/cpp/clist-class_15.cpp)]

## <a name="clistisempty"></a><a name="isempty"></a>リスト::空です

このリストに要素が含まれているかどうかを示します。

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>戻り値

このリストが空の場合は 0 以外。それ以外の場合は 0。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#50](../../mfc/codesnippet/cpp/clist-class_16.cpp)]

## <a name="clistremoveall"></a><a name="removeall"></a>リスト::すべて削除

このリストからすべての要素を削除し、関連付けられているメモリを解放します。

```cpp
void RemoveAll();
```

### <a name="remarks"></a>解説

リストが既に空の場合は、エラーは生成されません。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#51](../../mfc/codesnippet/cpp/clist-class_17.cpp)]

## <a name="clistremoveat"></a><a name="removeat"></a>リスト::削除アット

指定した要素をこのリストから削除します。

```cpp
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>パラメーター

*位置*<br/>
リストから削除する要素の位置。

### <a name="remarks"></a>解説

POSITION 値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#52](../../mfc/codesnippet/cpp/clist-class_18.cpp)]

## <a name="clistremovehead"></a><a name="removehead"></a>リスト::ヘッドの削除

リストの先頭から要素を削除し、その要素へのポインターを返します。

```
TYPE RemoveHead();
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
リスト内の要素の型を指定するテンプレート パラメーター。

### <a name="return-value"></a>戻り値

以前にリストの先頭に位置する要素。

### <a name="remarks"></a>解説

を呼び出す`RemoveHead`前に、リストが空でないことを確認する必要があります。 リストが空の場合、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。 [IsEmpty](#isempty)を使用して、リストに要素が含まれていることを確認します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#53](../../mfc/codesnippet/cpp/clist-class_19.cpp)]

## <a name="clistremovetail"></a><a name="removetail"></a>Cリスト::リムープテール

リストの末尾から要素を削除し、その要素へのポインターを返します。

```
TYPE RemoveTail();
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
リスト内の要素の型を指定するテンプレート パラメーター。

### <a name="return-value"></a>戻り値

リストの末尾にあった要素。

### <a name="remarks"></a>解説

を呼び出す`RemoveTail`前に、リストが空でないことを確認する必要があります。 リストが空の場合、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。 [IsEmpty](#isempty)を使用して、リストに要素が含まれていることを確認します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#54](../../mfc/codesnippet/cpp/clist-class_20.cpp)]

## <a name="clistsetat"></a><a name="setat"></a>箇条座::セットアット

POSITION 型の変数は、リストのキーです。

```cpp
void SetAt(POSITION pos, ARG_TYPE newElement);
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
設定する要素の位置。

*ARG_TYPE*<br/>
一覧の要素の型を指定するテンプレート パラメーター (参照を使用できます)。

*新しい要素*<br/>
リストに追加する要素。

### <a name="remarks"></a>解説

これはインデックスと同じではなく、POSITION 値を自分で操作することはできません。 `SetAt`リスト内の指定した位置に要素を書き込みます。

POSITION 値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#55](../../mfc/codesnippet/cpp/clist-class_21.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル コレクト](../../overview/visual-cpp-samples.md)<br/>
[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CMap クラス](../../mfc/reference/cmap-class.md)<br/>
[Cアレイクラス](../../mfc/reference/carray-class.md)
