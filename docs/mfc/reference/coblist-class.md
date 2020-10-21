---
title: CObList クラス
ms.date: 11/04/2016
f1_keywords:
- CObList
- AFXCOLL/CObList
- AFXCOLL/CObList::CObList
- AFXCOLL/CObList::AddHead
- AFXCOLL/CObList::AddTail
- AFXCOLL/CObList::Find
- AFXCOLL/CObList::FindIndex
- AFXCOLL/CObList::GetAt
- AFXCOLL/CObList::GetCount
- AFXCOLL/CObList::GetHead
- AFXCOLL/CObList::GetHeadPosition
- AFXCOLL/CObList::GetNext
- AFXCOLL/CObList::GetPrev
- AFXCOLL/CObList::GetSize
- AFXCOLL/CObList::GetTail
- AFXCOLL/CObList::GetTailPosition
- AFXCOLL/CObList::InsertAfter
- AFXCOLL/CObList::InsertBefore
- AFXCOLL/CObList::IsEmpty
- AFXCOLL/CObList::RemoveAll
- AFXCOLL/CObList::RemoveAt
- AFXCOLL/CObList::RemoveHead
- AFXCOLL/CObList::RemoveTail
- AFXCOLL/CObList::SetAt
helpviewer_keywords:
- CObList [MFC], CObList
- CObList [MFC], AddHead
- CObList [MFC], AddTail
- CObList [MFC], Find
- CObList [MFC], FindIndex
- CObList [MFC], GetAt
- CObList [MFC], GetCount
- CObList [MFC], GetHead
- CObList [MFC], GetHeadPosition
- CObList [MFC], GetNext
- CObList [MFC], GetPrev
- CObList [MFC], GetSize
- CObList [MFC], GetTail
- CObList [MFC], GetTailPosition
- CObList [MFC], InsertAfter
- CObList [MFC], InsertBefore
- CObList [MFC], IsEmpty
- CObList [MFC], RemoveAll
- CObList [MFC], RemoveAt
- CObList [MFC], RemoveHead
- CObList [MFC], RemoveTail
- CObList [MFC], SetAt
ms.assetid: 80699c93-33d8-4f8b-b8cf-7b58aeab64ca
ms.openlocfilehash: a13363ef9b200051c26781ab6e9870a10de06d88
ms.sourcegitcommit: 19016630f9d35f365e9ba249e0f3617515d7ca33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "92274589"
---
# <a name="coblist-class"></a>CObList クラス

`CObject`順次またはポインター値によってアクセスできる一意でないポインターの順序付きリストをサポートします。

## <a name="syntax"></a>構文

```
class CObList : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CObList:: CObList](#coblist)|ポインターの空のリストを構築 `CObject` します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CObList:: AddHead](#addhead)|要素 (または別のリスト内のすべての要素) をリストの先頭に追加します (新しい head を作成します)。|
|[CObList:: AddTail](#addtail)|要素 (または別のリスト内のすべての要素) をリストの末尾に追加します (新しい末尾を作成します)。|
|[CObList:: Find](#find)|ポインター値によって指定された要素の位置を取得します。|
|[CObList:: FindIndex](#findindex)|0から始まるインデックスで指定された要素の位置を取得します。|
|[CObList:: GetAt](#getat)|指定した位置にある要素を取得します。|
|[CObList:: GetCount](#getcount)|このリスト内の要素の数を返します。|
|[CObList:: GetHead](#gethead)|リストの head 要素を返します (空にすることはできません)。|
|[CObList:: GetHeadPosition](#getheadposition)|リストの先頭の要素の位置を返します。|
|[CObList:: GetNext](#getnext)|反復処理の対象となる次の要素を取得します。|
|[CObList:: GetPrev](#getprev)|反復処理する前の要素を取得します。|
|[CObList:: GetSize](#getsize)|このリスト内の要素の数を返します。|
|[CObList:: GetTail](#gettail)|リストの末尾の要素を返します (空にすることはできません)。|
|[CObList:: GetTailPosition](#gettailposition)|リストの末尾の要素の位置を返します。|
|[CObList:: InsertAfter](#insertafter)|指定された位置の後に新しい要素を挿入します。|
|[CObList:: InsertBefore](#insertbefore)|指定した位置の前に新しい要素を挿入します。|
|[CObList:: IsEmpty](#isempty)|空のリスト条件 (要素なし) があるかどうかをテストします。|
|[CObList:: RemoveAll](#removeall)|このリストからすべての要素を削除します。|
|[CObList:: RemoveAt](#removeat)|位置によって指定された、このリストから要素を削除します。|
|[CObList:: RemoveHead](#removehead)|リストの先頭から要素を削除します。|
|[CObList:: RemoveTail ます。](#removetail)|リストの末尾から要素を削除します。|
|[CObList:: SetAt](#setat)|指定された位置に要素を設定します。|

## <a name="remarks"></a>解説

`CObList` リストは、二重リンクリストのように動作します。

POSITION 型の変数は、リストのキーです。 位置変数を反復子として使用して、リストを順番に移動したり、場所を保持するブックマークとして使用したりできます。 ただし、位置はインデックスと同じではありません。

要素の挿入は、リストの先頭、末尾、および既知の位置で非常に高速です。 値またはインデックスによって要素を検索するには、順次検索が必要です。 リストが長い場合、この検索は遅くなることがあります。

`CObList` には、要素のシリアル化とダンプをサポートするために IMPLEMENT_SERIAL マクロが組み込まれています。 ポインターのリストが、オーバーロードされた `CObject` 挿入演算子またはメンバー関数を使用してアーカイブに格納されている場合 `Serialize` 、各 `CObject` 要素は順番にシリアル化されます。

リスト内の個々の要素のダンプが必要な場合は、 `CObject` ダンプコンテキストの深さを1以上に設定する必要があります。

オブジェクトが削除されたとき `CObList` 、またはその要素が削除されたときには、 `CObject` ポインターだけが削除されます。参照するオブジェクトは削除されません。

独自のクラスをから派生させることができ `CObList` ます。 から派生したオブジェクトへのポインターを保持するように設計された新しいリストクラス `CObject` は、新しいデータメンバーと新しいメンバー関数を追加します。 結果の一覧は、任意のポインターを挿入できるため、厳密には型セーフではありません `CObject` 。

> [!NOTE]
> リストをシリアル化する場合は、派生クラスの実装で [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) マクロを使用する必要があります。

の使用方法の詳細については `CObList` 、「 [コレクション](../../mfc/collections.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CObList`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcoll.h

## <a name="coblistaddhead"></a><a name="addhead"></a> CObList:: AddHead

このリストの先頭に新しい要素または要素のリストを追加します。

```
POSITION AddHead(CObject* newElement);
void AddHead(CObList* pNewList);
```

### <a name="parameters"></a>パラメーター

*(Newelement*<br/>
`CObject`このリストに追加するポインター。

*pNewList*<br/>
別のリストへのポインター `CObList` 。 *Pnewlist*内の要素が、この一覧に追加されます。

### <a name="return-value"></a>戻り値

最初のバージョンは、新しく挿入された要素の位置の値を返します。

次の表は、に似た他のメンバー関数を示して `CObList::AddHead` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置 AddHead (void** <strong>\*</strong> `newElement`**);**<br /><br /> **Void AddHead (CPtrList** <strong>\*</strong> `pNewList`**);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION AddHead (Const CString&** `newElement` **);**<br /><br /> **POSITION AddHead (LPCTSTR** `newElement` **);**<br /><br /> **Void AddHead (CStringList** <strong>\*</strong> `pNewList`**);**|

### <a name="remarks"></a>解説

操作の前に、リストを空にすることができます。

### <a name="example"></a>例

  クラスの一覧については、「 [coblist:: coblist](#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#89](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]

このプログラムの結果は次のとおりです。

```Output
AddHead example: A CObList with 2 elements
a CAge at $44A8 40
a CAge at $442A 21
```

## <a name="coblistaddtail"></a><a name="addtail"></a> CObList:: AddTail

このリストの末尾に新しい要素または要素のリストを追加します。

```
POSITION AddTail(CObject* newElement);
void AddTail(CObList* pNewList);
```

### <a name="parameters"></a>パラメーター

*(Newelement*<br/>
`CObject`このリストに追加するポインター。

*pNewList*<br/>
別のリストへのポインター `CObList` 。 *Pnewlist*内の要素が、この一覧に追加されます。

### <a name="return-value"></a>戻り値

最初のバージョンは、新しく挿入された要素の位置の値を返します。

### <a name="remarks"></a>解説

操作の前に、リストを空にすることができます。

次の表は、に似た他のメンバー関数を示して `CObList::AddTail` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置の AddTail (void** <strong>\*</strong> `newElement`**);**<br /><br /> **Void AddTail (CPtrList** <strong>\*</strong> `pNewList`**);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION AddTail (Const CString&** `newElement` **);**<br /><br /> **位置の AddTail (LPCTSTR** `newElement` **);**<br /><br /> **Void AddTail (CStringList** <strong>\*</strong> `pNewList`**);**|

### <a name="example"></a>例

  クラスの一覧については、「 [coblist:: coblist](#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#90](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]

このプログラムの結果は次のとおりです。

```Output
AddTail example: A CObList with 2 elements
a CAge at $444A 21
a CAge at $4526 40
```

## <a name="coblistcoblist"></a><a name="coblist"></a> CObList:: CObList

空 `CObject` のポインターリストを構築します。

```
CObList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>パラメーター

*nBlockSize*<br/>
リストを拡張するためのメモリ割り当ての粒度。

### <a name="remarks"></a>解説

リストが大きくなるにつれて、メモリは *Nblocksize* エントリの単位で割り当てられます。 メモリ割り当てが失敗すると、 `CMemoryException` がスローされます。

次の表は、に似た他のメンバー関数を示して `CObList::CObList` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**CPtrList (INT_PTR** `nBlockSize` **= 10);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Cstringlist (INT_PTR** `nBlockSize` **= 10);**|

### <a name="example"></a>例

  次に示すのは、 `CObject` `CAge` すべてのコレクションの例で使用されているから派生したクラスの一覧です。

[!code-cpp[NVC_MFCCollections#91](../../mfc/codesnippet/cpp/coblist-class_3.h)]

コンストラクターの使用例を次に示し `CObList` ます。

[!code-cpp[NVC_MFCCollections#92](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]

## <a name="coblistfind"></a><a name="find"></a> CObList:: Find

リストを順番に検索し、指定したポインターに一致する最初のポインターを検索し `CObject` `CObject` ます。

```
POSITION Find(
    CObject* searchValue,
    POSITION startAfter = NULL) const;
```

### <a name="parameters"></a>パラメーター

*searchValue*<br/>
この一覧に含まれるオブジェクトポインター。

*startAfter*<br/>
検索の開始位置。

### <a name="return-value"></a>戻り値

反復またはオブジェクトポインターの取得に使用できる位置の値。オブジェクトが見つからない場合は NULL です。

### <a name="remarks"></a>解説

ポインターの値は、オブジェクトの内容ではなく比較されることに注意してください。

次の表は、に似た他のメンバー関数を示して `CObList::Find` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置検索 (void)** <strong>\*</strong> `searchValue`**、POSITION** `startAfter`**= NULL) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Position Find (LPCTSTR** `searchValue` **, position** `startAfter` **= NULL) const;**|

### <a name="example"></a>例

クラスの一覧については、「 [coblist:: coblist](#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#93](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]

## <a name="coblistfindindex"></a><a name="findindex"></a> CObList:: FindIndex

リストのインデックスとして、 *nIndex* の値を使用します。

```
POSITION FindIndex(INT_PTR nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
検索するリスト要素の0から始まるインデックス。

### <a name="return-value"></a>戻り値

反復またはオブジェクトポインターの取得に使用できる位置の値。 *NIndex* が大きすぎる場合は NULL です。 ( *NIndex* が負の場合、フレームワークはアサーションを生成します)。

### <a name="remarks"></a>解説

リストの先頭からシーケンシャルスキャンを開始し、 *n*番目の要素に対して停止します。

次の表は、に似た他のメンバー関数を示して `CObList::FindIndex` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSITION findindex (INT_PTR** `nIndex` **) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION findindex (INT_PTR** `nIndex` **) const;**|

### <a name="example"></a>例

クラスの一覧については、「 [coblist:: coblist](#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#94](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]

## <a name="coblistgetat"></a><a name="getat"></a> CObList:: GetAt

POSITION 型の変数は、リストのキーです。

```
CObject*& GetAt(POSITION position);
const CObject*& GetAt(POSITION position) const;
```

### <a name="parameters"></a>パラメーター

*position*<br/>
前の `GetHeadPosition` 関数または `Find` メンバー関数呼び出しによって返される位置の値。

### <a name="return-value"></a>戻り値

[GetHead](#gethead)の戻り値の説明を参照してください。

### <a name="remarks"></a>解説

インデックスとは異なり、位置の値を自分で操作することはできません。 `GetAt` 指定した `CObject` 位置に関連付けられているポインターを取得します。

位置の値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。

次の表は、に似た他のメンバー関数を示して `CObList::GetAt` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void \*& GETAT (位置***位置* **) const;**<br /><br /> **void \*& GETAT (位置**の *位置* **) です。**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const CString& GetAt (位置**の *位置* **) const;**<br /><br /> **CString& GetAt (位置**の *位置* **) です。**|

### <a name="example"></a>例

  [Findindex](#findindex)の例を参照してください。

## <a name="coblistgetcount"></a><a name="getcount"></a> CObList:: GetCount

このリスト内の要素の数を取得します。

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>戻り値

要素の数を表す整数値です。

次の表は、に似た他のメンバー関数を示して `CObList::GetCount` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetCount () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetCount () const;**|

### <a name="example"></a>例

クラスの一覧については、「 [coblist:: coblist](#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#95](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]

## <a name="coblistgethead"></a><a name="gethead"></a> CObList:: GetHead

`CObject`このリストの head 要素を表すポインターを取得します。

```
CObject*& GetHead();
const CObject*& GetHead() const;
```

### <a name="return-value"></a>戻り値

へのポインターを使用してリストにアクセスした場合 `const CObList` 、は `GetHead` ポインターを返し `CObject` ます。 これにより、関数を代入ステートメントの右側でのみ使用できるようになるため、リストが変更されないように保護できます。

リストに直接アクセスした場合、またはへのポインターを介してアクセスした場合 `CObList` 、は `GetHead` ポインターへの参照を返し `CObject` ます。 これにより、関数を代入ステートメントのどちら側でも使用できるようになり、リストエントリを変更できるようになります。

### <a name="remarks"></a>解説

を呼び出す前に、リストが空でないことを確認する必要があり `GetHead` ます。 リストが空の場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。 [IsEmpty](#isempty)を使用して、リストに要素が含まれていることを確認します。

次の表は、に似た他のメンバー関数を示して `CObList::GetHead` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void \*& GetHead () const; void \*& GetHead ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString& GetHead () const;CString& GetHead ();**|

### <a name="example"></a>例

クラスの一覧については、「 [coblist:: coblist](#coblist) 」を参照してください `CAge` 。

次の例は、 `GetHead` 代入ステートメントの左側でを使用する方法を示しています。

[!code-cpp[NVC_MFCCollections#96](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]

## <a name="coblistgetheadposition"></a><a name="getheadposition"></a> CObList:: GetHeadPosition

このリストの先頭の要素の位置を取得します。

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>戻り値

反復またはオブジェクトポインターの取得に使用できる位置の値。リストが空の場合は NULL です。

次の表は、に似た他のメンバー関数を示して `CObList::GetHeadPosition` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSITION GetHeadPosition () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION GetHeadPosition () const;**|

### <a name="example"></a>例

クラスの一覧については、「 [coblist:: coblist](#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#97](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]

## <a name="coblistgetnext"></a><a name="getnext"></a> CObList:: GetNext

*RPosition*によって識別されるリスト要素を取得し、 *rPosition*を `POSITION` リスト内の次のエントリの値に設定します。

```
CObject*& GetNext(POSITION& rPosition);
const CObject* GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>パラメーター

*rPosition*<br/>
前 `GetNext` の、 `GetHeadPosition` 、またはその他のメンバー関数呼び出しによって返される位置値への参照。

### <a name="return-value"></a>戻り値

[GetHead](#gethead)の戻り値の説明を参照してください。

### <a name="remarks"></a>解説

`GetNext`またはへの呼び出しを使用して初期位置を設定した場合は、前方反復ループでを使用でき `GetHeadPosition` `Find` ます。

位置の値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。

取得した要素がリスト内の最後の要素である場合、 *rPosition* の新しい値は NULL に設定されます。

イテレーション中に要素を削除することができます。 [RemoveAt](#removeat)の例を参照してください。

> [!NOTE]
> MFC 8.0 では、このメソッドの const バージョンが、ではなくを返すように変更されてい `const CObject*` `const CObject*&` ます。  この変更は、コンパイラが C++ 標準に準拠するようにするために行われました。

次の表は、に似た他のメンバー関数を示して `CObList::GetNext` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>例

  クラスの一覧については、「 [coblist:: coblist](#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#98](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]

このプログラムの結果は次のとおりです。

```Output
a CAge at $479C 40
a CAge at $46C0 21
```

## <a name="coblistgetprev"></a><a name="getprev"></a> CObList:: GetPrev

*RPosition*によって識別されるリスト要素を取得し、 *rPosition*をリスト内の前のエントリの位置の値に設定します。

```
CObject*& GetPrev(POSITION& rPosition);
const CObject* GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>パラメーター

*rPosition*<br/>
前の `GetPrev` または他のメンバー関数呼び出しによって返される位置値への参照。

### <a name="return-value"></a>戻り値

[GetHead](#gethead)の戻り値の説明を参照してください。

### <a name="remarks"></a>解説

またはの呼び出しを使用し `GetPrev` て初期位置を設定した場合は、逆反復ループでを使用でき `GetTailPosition` `Find` ます。

位置の値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。

取得した要素がリスト内の最初の要素の場合、 *rPosition* の新しい値は NULL に設定されます。

> [!NOTE]
> MFC 8.0 では、このメソッドの const バージョンが、ではなくを返すように変更されてい `const CObject*` `const CObject*&` ます。  この変更は、コンパイラが C++ 標準に準拠するようにするために行われました。

次の表は、に似た他のメンバー関数を示して `CObList::GetPrev` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>例

  クラスの一覧については、「 [coblist:: coblist](#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#99](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]

このプログラムの結果は次のとおりです。

```Output
a CAge at $421C 21
a CAge at $421C 40
```

## <a name="coblistgetsize"></a><a name="getsize"></a> CObList:: GetSize

リスト要素の数を返します。

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>戻り値

一覧にあるアイテムの数です。

### <a name="remarks"></a>解説

リスト内の要素の数を取得するには、このメソッドを呼び出します。

次の表は、に似た他のメンバー関数を示して `CObList::GetSize` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetSize () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetSize () const;**|

### <a name="example"></a>例

クラスの一覧については、「 [coblist:: coblist](#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#100](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]

## <a name="coblistgettail"></a><a name="gettail"></a> CObList:: GetTail

`CObject`このリストの末尾の要素を表すポインターを取得します。

```
CObject*& GetTail();
const CObject*& GetTail() const;
```

### <a name="return-value"></a>戻り値

[GetHead](#gethead)の戻り値の説明を参照してください。

### <a name="remarks"></a>解説

を呼び出す前に、リストが空でないことを確認する必要があり `GetTail` ます。 リストが空の場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。 [IsEmpty](#isempty)を使用して、リストに要素が含まれていることを確認します。

次の表は、に似た他のメンバー関数を示して `CObList::GetTail` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void \*& gettail () const; void \*& gettail ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString& GetTail () const;CString& GetTail ();**|

### <a name="example"></a>例

クラスの一覧については、「 [coblist:: coblist](#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#101](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]

## <a name="coblistgettailposition"></a><a name="gettailposition"></a> CObList:: GetTailPosition

このリストの末尾の要素の位置を取得します。リストが空の場合は **NULL** です。

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>戻り値

反復またはオブジェクトポインターの取得に使用できる位置の値。リストが空の場合は NULL です。

次の表は、に似た他のメンバー関数を示して `CObList::GetTailPosition` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSITION GetTailPosition () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION GetTailPosition () const;**|

### <a name="example"></a>例

クラスの一覧については、「 [coblist:: coblist](#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#102](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]

## <a name="coblistinsertafter"></a><a name="insertafter"></a> CObList:: InsertAfter

指定した位置にある要素の後に、このリストに要素を追加します。

```
POSITION InsertAfter(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>パラメーター

*position*<br/>
前 `GetNext` の、 `GetPrev` 、または `Find` メンバー関数呼び出しによって返される位置の値。

*(Newelement*<br/>
このリストに追加するオブジェクトポインター。

次の表は、に似た他のメンバー関数を示して `CObList::InsertAfter` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Position InsertAfter (** 位置*位置* **、void** <strong>\*</strong> `newElement`**);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Position InsertAfter (位置**の *位置* **、const CString&** `newElement` **);**<br /><br /> **Position InsertAfter (position** *position* **, LPCTSTR** `newElement` **);**|

### <a name="return-value"></a>戻り値

*Position パラメーターと*同じ位置の値。

### <a name="example"></a>例

  クラスの一覧については、「 [coblist:: coblist](#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#103](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]

このプログラムの結果は次のとおりです。

```Output
InsertAfter example: A CObList with 3 elements
a CAge at $4A44 40
a CAge at $4A64 65
a CAge at $4968 21
```

## <a name="coblistinsertbefore"></a><a name="insertbefore"></a> CObList:: InsertBefore

一覧の指定した位置にある要素の前に要素を追加します。

```
POSITION InsertBefore(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>パラメーター

*position*<br/>
前 `GetNext` の、 `GetPrev` 、または `Find` メンバー関数呼び出しによって返される位置の値。

*(Newelement*<br/>
このリストに追加するオブジェクトポインター。

### <a name="return-value"></a>戻り値

反復またはオブジェクトポインターの取得に使用できる位置の値。リストが空の場合は NULL です。

次の表は、に似た他のメンバー関数を示して `CObList::InsertBefore` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**InsertBefore (位置** *position* **の位置、void)** <strong>\*</strong> `newElement`**);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置 InsertBefore (位置** *position* **の位置、const CString&** `newElement` **);**<br /><br /> **InsertBefore (位置** *position* **の位置、LPCTSTR) の**位置に挿入し `newElement` **ます。**|

### <a name="example"></a>例

  クラスの一覧については、「 [coblist:: coblist](#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#104](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]

このプログラムの結果は次のとおりです。

```Output
InsertBefore example: A CObList with 3 elements
a CAge at $4AE2 40
a CAge at $4B02 65
a CAge at $49E6 21
```

## <a name="coblistisempty"></a><a name="isempty"></a> CObList:: IsEmpty

このリストに要素が含まれていないかどうかを示します。

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>戻り値

このリストが空の場合は0以外の。それ以外の場合は0です。

次の表は、に似た他のメンバー関数を示して `CObList::IsEmpty` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**BOOL IsEmpty () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**BOOL IsEmpty () const;**|

### <a name="example"></a>例

  [RemoveAll](#removeall)の例を参照してください。

## <a name="coblistremoveall"></a><a name="removeall"></a> CObList:: RemoveAll

このリストからすべての要素を削除し、関連付けられているメモリを解放し `CObList` ます。

```cpp
void RemoveAll();
```

### <a name="remarks"></a>解説

リストが既に空の場合、エラーは生成されません。

から要素を削除する場合は、 `CObList` 一覧からオブジェクトポインターを削除します。 オブジェクト自体を削除するのはお客様の責任です。

次の表は、に似た他のメンバー関数を示して `CObList::RemoveAll` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAll ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAll ();**|

### <a name="example"></a>例

クラスの一覧については、「 [coblist:: coblist](#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#105](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]

## <a name="coblistremoveat"></a><a name="removeat"></a> CObList:: RemoveAt

指定した要素をこのリストから削除します。

```cpp
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>パラメーター

*position*<br/>
リストから削除する要素の位置。

### <a name="remarks"></a>解説

から要素を削除する場合は、 `CObList` 一覧からオブジェクトポインターを削除します。 オブジェクト自体を削除するのはお客様の責任です。

位置の値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。

次の表は、に似た他のメンバー関数を示して `CObList::RemoveAt` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Void RemoveAt (位置**の *位置* **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Void RemoveAt (位置**の *位置* **);**|

### <a name="example"></a>例

  リストの反復処理中に要素を削除する場合は注意してください。 次の例は、 [GetNext](#getnext)の有効な**位置**の値を保証する削除手法を示しています。

クラスの一覧については、「 [coblist:: coblist](#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#106](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]

このプログラムの結果は次のとおりです。

`RemoveAt example: A CObList with 2 elements`

`a CAge at $4C1E 65`

`a CAge at $4B22 21`

## <a name="coblistremovehead"></a><a name="removehead"></a> CObList:: RemoveHead

リストの先頭から要素を削除し、その要素へのポインターを返します。

```
CObject* RemoveHead();
```

### <a name="return-value"></a>戻り値

`CObject`リストの先頭にあるポインター。

### <a name="remarks"></a>解説

を呼び出す前に、リストが空でないことを確認する必要があり `RemoveHead` ます。 リストが空の場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。 [IsEmpty](#isempty)を使用して、リストに要素が含まれていることを確認します。

次の表は、に似た他のメンバー関数を示して `CObList::RemoveHead` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void \* removehead ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveHead ();**|

### <a name="example"></a>例

クラスの一覧については、「 [coblist:: coblist](#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#107](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]

## <a name="coblistremovetail"></a><a name="removetail"></a> CObList:: RemoveTail ます。

リストの末尾から要素を削除し、その要素へのポインターを返します。

```
CObject* RemoveTail();
```

### <a name="return-value"></a>戻り値

リストの末尾にあるオブジェクトへのポインター。

### <a name="remarks"></a>解説

を呼び出す前に、リストが空でないことを確認する必要があり `RemoveTail` ます。 リストが空の場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。 [IsEmpty](#isempty)を使用して、リストに要素が含まれていることを確認します。

次の表は、に似た他のメンバー関数を示して `CObList::RemoveTail` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void \* removetail ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveTail ();**|

### <a name="example"></a>例

クラスの一覧については、「 [coblist:: coblist](#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#108](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]

## <a name="coblistsetat"></a><a name="setat"></a> CObList:: SetAt

指定された位置に要素を設定します。

```cpp
void SetAt(
    POSITION pos,
    CObject* newElement);
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
設定する要素の位置。

*(Newelement*<br/>
`CObject`リストに書き込むポインター。

### <a name="remarks"></a>解説

POSITION 型の変数は、リストのキーです。 インデックスとは異なり、位置の値を自分で操作することはできません。 `SetAt``CObject`リスト内の指定した位置にポインターを書き込みます。

位置の値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。

次の表は、に似た他のメンバー関数を示して `CObList::SetAt` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void SetAt (POSITION** `pos` **, const CString&** `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void SetAt (POSITION** `pos` **, LPCTSTR** `newElement` **);**|

### <a name="example"></a>例

  クラスの一覧については、「 [coblist:: coblist](#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#109](../../mfc/codesnippet/cpp/coblist-class_21.cpp)]

このプログラムの結果は次のとおりです。

```Output
SetAt example: A CObList with 2 elements
a CAge at $4D98 40
a CAge at $4DB8 65
```

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CStringList クラス](../../mfc/reference/cstringlist-class.md)<br/>
[CPtrList クラス](../../mfc/reference/cptrlist-class.md)
