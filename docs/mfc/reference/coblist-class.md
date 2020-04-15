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
ms.openlocfilehash: cccd45bf5a97ae7dcc8369015e0a431b3a9e960f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360370"
---
# <a name="coblist-class"></a>CObList クラス

fSupports 連続的にアクセス`CObject`できる、またはポインター値によってアクセスできる一意でないポインターの順序付きリスト。

## <a name="syntax"></a>構文

```
class CObList : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コブリスト::コブリスト](#coblist)|ポインターの空のリストを`CObject`作成します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コブリスト::アドヘッド](#addhead)|リストの先頭に要素 (または別のリストのすべての要素) を追加します (新しいヘッドを作成)。|
|[コブリスト::追加テール](#addtail)|リストの末尾に要素 (または別のリストのすべての要素) を追加します (新しい末尾になります)。|
|[コブリスト::検索](#find)|ポインター値で指定された要素の位置を取得します。|
|[インデックスを検索します。](#findindex)|0 から始まるインデックスで指定された要素の位置を取得します。|
|[コブリスト::ゲットアット](#getat)|指定した位置にある要素を取得します。|
|[コブリスト::取得カウント](#getcount)|このリスト内の要素の数を返します。|
|[コブリスト::ゲットヘッド](#gethead)|リストの head 要素を返します (空にすることはできません)。|
|[コブリスト::ゲットヘッドポジション](#getheadposition)|リストの先頭要素の位置を返します。|
|[次のリストを取得します。](#getnext)|反復処理の次の要素を取得します。|
|[コブリスト::ゲットプレフ](#getprev)|反復処理の前の要素を取得します。|
|[コブリスト::ゲットサイズ](#getsize)|このリスト内の要素の数を返します。|
|[コブリスト::ゲットテール](#gettail)|リストの末尾要素を返します (空にすることはできません)。|
|[コブリスト::ゲットテールポジション](#gettailposition)|リストの末尾要素の位置を返します。|
|[次のリスト::後に挿入](#insertafter)|指定した位置の後に新しい要素を挿入します。|
|[前に挿入します。](#insertbefore)|指定した位置の前に新しい要素を挿入します。|
|[コブリスト::IsEmpty](#isempty)|空のリスト条件 (要素なし) をテストします。|
|[すべての項目を削除します。](#removeall)|このリストからすべての要素を削除します。|
|[コブリスト::削除アット](#removeat)|位置で指定された、このリストから要素を削除します。|
|[コブリスト::削除ヘッド](#removehead)|リストの先頭から要素を削除します。|
|[コブリスト::リムーブテール](#removetail)|リストの末尾から要素を削除します。|
|[コブリスト::セットアット](#setat)|指定した位置に要素を設定します。|

## <a name="remarks"></a>解説

`CObList`リストは、二重にリンクされたリストのように動作します。

POSITION 型の変数は、リストのキーです。 POSITION 変数は、リストを順番に走査する反復器として使用することも、場所を保持するブックマークとしても使用できます。 ただし、位置はインデックスと同じではありません。

要素の挿入は、リストヘッド、末尾、および既知の位置で非常に高速です。 値またはインデックスで要素を検索するには、順次検索が必要です。 この検索は、リストが長い場合に低速になる可能性があります。

`CObList`IMPLEMENT_SERIAL マクロを組み込んで、シリアル化と要素のダンプをサポートします。 ポインターの`CObject`リストが、オーバーロードされた挿入演算子または`Serialize`メンバー関数を使用してアーカイブに格納されている場合、各`CObject`要素は順番にシリアル化されます。

リスト内の個々`CObject`の要素のダンプが必要な場合は、ダンプ コンテキストの深さを 1 以上に設定する必要があります。

オブジェクトが`CObList`削除されたとき、またはその要素が削除されると、`CObject`ポインターだけが削除され、オブジェクトは削除されません。

から独自のクラスを派生させることができます`CObList`。 から派生したオブジェクトへのポインターを保持するように設計された新しいリスト`CObject`クラスは、新しいデータ メンバーと新しいメンバー関数を追加します。 結果のリストは、ポインター`CObject`の挿入が可能であるため、厳密にタイプ セーフではありません。

> [!NOTE]
> リストをシリアル化する場合は、派生クラスの実装で[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロを使用する必要があります。

の使用方法`CObList`の詳細については、[記事の「コレクション](../../mfc/collections.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CObList`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcoll.h

## <a name="coblistaddhead"></a><a name="addhead"></a>コブリスト::アドヘッド

このリストの先頭に新しい要素または要素のリストを追加します。

```
POSITION AddHead(CObject* newElement);
void AddHead(CObList* pNewList);
```

### <a name="parameters"></a>パラメーター

*新しい要素*<br/>
この`CObject`リストに追加するポインター。

*をクリックします。*<br/>
別`CObList`のリストへのポインター。 *pNewList*の要素がこのリストに追加されます。

### <a name="return-value"></a>戻り値

最初のバージョンは、新しく挿入された要素の POSITION 値を返します。

次の表に、 に似たその他`CObList::AddHead`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置追加ヘッド(ボイド**<strong>\*</strong>`newElement`**);**<br /><br /> **ボイド AddHead ( CPtr リスト**<strong>\*</strong>`pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置追加ヘッド(定数 CString** `newElement` **&);**<br /><br /> **位置追加ヘッド (LPCTSTR);** `newElement` **);**<br /><br /> **無効な追加ヘッド(C文字列リスト**<strong>\*</strong>`pNewList`**);**|

### <a name="remarks"></a>解説

リストは、操作の前に空にすることができます。

### <a name="example"></a>例

  クラスの一覧については[、CObList::CObList](#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#89](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]

このプログラムの結果は次のとおりです。

```Output
AddHead example: A CObList with 2 elements
a CAge at $44A8 40
a CAge at $442A 21
```

## <a name="coblistaddtail"></a><a name="addtail"></a>コブリスト::追加テール

このリストの末尾に新しい要素または要素のリストを追加します。

```
POSITION AddTail(CObject* newElement);
void AddTail(CObList* pNewList);
```

### <a name="parameters"></a>パラメーター

*新しい要素*<br/>
この`CObject`リストに追加するポインター。

*をクリックします。*<br/>
別`CObList`のリストへのポインター。 *pNewList*の要素がこのリストに追加されます。

### <a name="return-value"></a>戻り値

最初のバージョンは、新しく挿入された要素の POSITION 値を返します。

### <a name="remarks"></a>解説

リストは、操作の前に空にすることができます。

次の表に、 に似たその他`CObList::AddTail`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置追加テール(ボイド**<strong>\*</strong>`newElement`**);**<br /><br /> **ボイド・アドテール ( CPtr リスト**<strong>\*</strong>`pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置追加テール(コンストCストリング&);** `newElement` **);**<br /><br /> **位置追加テール ( LPCTSTR** `newElement` **);**<br /><br /> **無効な追加のテール( C文字列リスト**<strong>\*</strong>`pNewList` **);**|

### <a name="example"></a>例

  クラスの一覧については[、CObList::CObList](#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#90](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]

このプログラムの結果は次のとおりです。

```Output
AddTail example: A CObList with 2 elements
a CAge at $444A 21
a CAge at $4526 40
```

## <a name="coblistcoblist"></a><a name="coblist"></a>コブリスト::コブリスト

空`CObject`のポインター リストを作成します。

```
CObList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>パラメーター

*ブロックサイズ*<br/>
リストを拡張するためのメモリ割り当ての粒度。

### <a name="remarks"></a>解説

リストが大きくなると、メモリは*nBlockSize*エントリの単位で割り当てられます。 メモリの割り当てに`CMemoryException`失敗すると、 がスローされます。

次の表に、 に似たその他`CObList::CObList`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**CPtrList( INT_PTR** `nBlockSize` **= 10 );**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR =** `nBlockSize` **10)**|

### <a name="example"></a>例

  すべてのコレクションの例で使用`CObject`される -derived クラス`CAge`の一覧を次に示します。

[!code-cpp[NVC_MFCCollections#91](../../mfc/codesnippet/cpp/coblist-class_3.h)]

以下はコンストラクタの`CObList`使用例です。

[!code-cpp[NVC_MFCCollections#92](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]

## <a name="coblistfind"></a><a name="find"></a>コブリスト::検索

リストを順番に検索して、指定した`CObject``CObject`ポインターに一致する最初のポインターを見つけます。

```
POSITION Find(
    CObject* searchValue,
    POSITION startAfter = NULL) const;
```

### <a name="parameters"></a>パラメーター

*検索値*<br/>
このリストで見つかるオブジェクト ポインタ。

*開始後*<br/>
検索の開始位置。

### <a name="return-value"></a>戻り値

反復またはオブジェクト・ポインターの取得に使用できる POSITION 値。オブジェクトが見つからない場合は NULL。

### <a name="remarks"></a>解説

ポインターの値は、オブジェクトの内容ではなく比較されることに注意してください。

次の表に、 に似たその他`CObList::Find`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置検索 ( void** <strong>\*</strong> `searchValue` **, POSITION** `startAfter` **= NULL ) 定数;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置検索( LPCTSTR** `searchValue` **, 位置**`startAfter` **= NULL ) 定数;**|

### <a name="example"></a>例

クラスの一覧については[、CObList::CObList](#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#93](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]

## <a name="coblistfindindex"></a><a name="findindex"></a>インデックスを検索します。

*nIndex*の値をリストのインデックスとして使用します。

```
POSITION FindIndex(INT_PTR nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
検索するリスト要素の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

反復またはオブジェクト・ポインターの取得に使用できる POSITION 値。*nIndex*が大きすぎる場合は NULL です。 *(nIndex*が負の場合、フレームワークはアサーションを生成します)。

### <a name="remarks"></a>解説

リストの先頭から順次スキャンを開始し *、n*番目の要素で停止します。

次の表に、 に似たその他`CObList::FindIndex`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置検索インデックス( INT_PTR** `nIndex` **) 定数;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置検索インデックス( INT_PTR** `nIndex` **) 定数;**|

### <a name="example"></a>例

クラスの一覧については[、CObList::CObList](#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#94](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]

## <a name="coblistgetat"></a><a name="getat"></a>コブリスト::ゲットアット

POSITION 型の変数は、リストのキーです。

```
CObject*& GetAt(POSITION position);
const CObject*& GetAt(POSITION position) const;
```

### <a name="parameters"></a>パラメーター

*位置*<br/>
前`GetHeadPosition`の関数呼び出しまたは`Find`メンバー関数呼び出しによって返される POSITION 値。

### <a name="return-value"></a>戻り値

[GetHead](#gethead)の戻り値の説明を参照してください。

### <a name="remarks"></a>解説

これはインデックスと同じではなく、POSITION 値を自分で操作することはできません。 `GetAt`指定された位置`CObject`に関連付けられたポインターを取得します。

POSITION 値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。

次の表に、 に似たその他`CObList::GetAt`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**定数\*& GetAt ( 位置***位置* **) の定数を無効にします。**<br /><br /> **無効\*& GetAt( ポジションポジション** *position* **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**定数 CString& GetAt (** *位置位置* **) 定数;**<br /><br /> **C文字列&取得(位置***)、* **);**|

### <a name="example"></a>例

  [FindIndex](#findindex)の例を参照してください。

## <a name="coblistgetcount"></a><a name="getcount"></a>コブリスト::取得カウント

このリスト内の要素の数を取得します。

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>戻り値

要素数を含む整数値。

次の表に、 に似たその他`CObList::GetCount`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTRカウント( ) 定数。**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTRカウント( ) 定数。**|

### <a name="example"></a>例

クラスの一覧については[、CObList::CObList](#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#95](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]

## <a name="coblistgethead"></a><a name="gethead"></a>コブリスト::ゲットヘッド

このリスト`CObject`の head 要素を表すポインターを取得します。

```
CObject*& GetHead();
const CObject*& GetHead() const;
```

### <a name="return-value"></a>戻り値

リストにアクセスする場合は、 へのポインター`const CObList`を使用`GetHead`してポインター`CObject`を返します。 これにより、関数は代入ステートメントの右側でのみ使用できるため、リストが変更されないように保護されます。

リストに直接アクセスするか、 へのポインターを`CObList`使用してアクセスした`GetHead`場合は、ポインターへの`CObject`参照を返します。 これにより、代入ステートメントの両側で関数を使用できるため、リストエントリを変更できます。

### <a name="remarks"></a>解説

を呼び出す`GetHead`前に、リストが空でないことを確認する必要があります。 リストが空の場合、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。 [IsEmpty](#isempty)を使用して、リストに要素が含まれていることを確認します。

次の表に、 に似たその他`CObList::GetHead`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**getHead( ) 定数&無効\*です。無効\*&ゲットヘッド( );**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**定数 CString& GetHead( ) 定数です。Cストリング&ゲットヘッド( );**|

### <a name="example"></a>例

クラスの一覧については[、CObList::CObList](#coblist)を`CAge`参照してください。

次の例は、代入ステートメントの`GetHead`左側での使用を示しています。

[!code-cpp[NVC_MFCCollections#96](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]

## <a name="coblistgetheadposition"></a><a name="getheadposition"></a>コブリスト::ゲットヘッドポジション

このリストの head 要素の位置を取得します。

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>戻り値

反復またはオブジェクト・ポインターの取得に使用できる POSITION 値。リストが空の場合は NULL。

次の表に、 に似たその他`CObList::GetHeadPosition`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置取得ヘッドポジション( ) 定数;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置取得ヘッドポジション( ) 定数;**|

### <a name="example"></a>例

クラスの一覧については[、CObList::CObList](#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#97](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]

## <a name="coblistgetnext"></a><a name="getnext"></a>次のリストを取得します。

*rPosition*で識別されるリスト要素を取得し *、rPosition* `POSITION`をリスト内の次のエントリの値に設定します。

```
CObject*& GetNext(POSITION& rPosition);
const CObject* GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>パラメーター

*r位置*<br/>
前`GetNext`の 、 、`GetHeadPosition`または他のメンバー関数呼び出しによって返された POSITION 値への参照。

### <a name="return-value"></a>戻り値

[GetHead](#gethead)の戻り値の説明を参照してください。

### <a name="remarks"></a>解説

または への`GetNext`呼び出し`GetHeadPosition`で初期位置を確立する場合は、順方向反復`Find`ループで使用できます。

POSITION 値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。

取得した要素がリストの最後の要素である場合 *、rPosition*の新しい値は NULL に設定されます。

反復中に要素を削除することができます。 [「RemoveAt」](#removeat)の例を参照してください。

> [!NOTE]
> MFC 8.0 では、このメソッドの const バージョンが`const CObject*` `const CObject*&`、 の代わりに戻るように変更されています。  この変更は、コンパイラを C++ 標準に準拠させるために行われました。

次の表に、 に似たその他`CObList::GetNext`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>例

  クラスの一覧については[、CObList::CObList](#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#98](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]

このプログラムの結果は次のとおりです。

```Output
a CAge at $479C 40
a CAge at $46C0 21
```

## <a name="coblistgetprev"></a><a name="getprev"></a>コブリスト::ゲットプレフ

*rPosition*で識別されるリスト要素を取得し *、rPosition*をリスト内の前のエントリの POSITION 値に設定します。

```
CObject*& GetPrev(POSITION& rPosition);
const CObject* GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>パラメーター

*r位置*<br/>
前`GetPrev`のメンバー関数呼び出しまたは他のメンバー関数呼び出しによって返された POSITION 値への参照。

### <a name="return-value"></a>戻り値

[GetHead](#gethead)の戻り値の説明を参照してください。

### <a name="remarks"></a>解説

または への`GetPrev`呼び出し`GetTailPosition`で初期位置を確立する場合は、逆反復ループ`Find`で使用できます。

POSITION 値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。

取得した要素がリストの最初の要素である場合 *、rPosition*の新しい値は NULL に設定されます。

> [!NOTE]
> MFC 8.0 では、このメソッドの const バージョンが`const CObject*` `const CObject*&`、 の代わりに戻るように変更されています。  この変更は、コンパイラを C++ 標準に準拠させるために行われました。

次の表に、 に似たその他`CObList::GetPrev`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>例

  クラスの一覧については[、CObList::CObList](#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#99](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]

このプログラムの結果は次のとおりです。

```Output
a CAge at $421C 21
a CAge at $421C 40
```

## <a name="coblistgetsize"></a><a name="getsize"></a>コブリスト::ゲットサイズ

リスト要素の数を返します。

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>戻り値

一覧にあるアイテムの数です。

### <a name="remarks"></a>解説

リスト内の要素の数を取得します。

次の表に、 に似たその他`CObList::GetSize`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTRします。**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTRします。**|

### <a name="example"></a>例

クラスの一覧については[、CObList::CObList](#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#100](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]

## <a name="coblistgettail"></a><a name="gettail"></a>コブリスト::ゲットテール

このリスト`CObject`の末尾要素を表すポインターを取得します。

```
CObject*& GetTail();
const CObject*& GetTail() const;
```

### <a name="return-value"></a>戻り値

[GetHead](#gethead)の戻り値の説明を参照してください。

### <a name="remarks"></a>解説

を呼び出す`GetTail`前に、リストが空でないことを確認する必要があります。 リストが空の場合、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。 [IsEmpty](#isempty)を使用して、リストに要素が含まれていることを確認します。

次の表に、 に似たその他`CObList::GetTail`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**getTail( ) 定数&無効\*です。無効\*&ゲットテール( );**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**定数 CString& GetTail( ) 定数。Cストリング&ゲットテール( );**|

### <a name="example"></a>例

クラスの一覧については[、CObList::CObList](#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#101](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]

## <a name="coblistgettailposition"></a><a name="gettailposition"></a>コブリスト::ゲットテールポジション

このリストの末尾要素の位置を取得します。リストが空の場合は**NULL。**

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>戻り値

反復またはオブジェクト・ポインターの取得に使用できる POSITION 値。リストが空の場合は NULL。

次の表に、 に似たその他`CObList::GetTailPosition`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置取得位置( ) 定数;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置取得位置( ) 定数;**|

### <a name="example"></a>例

クラスの一覧については[、CObList::CObList](#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#102](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]

## <a name="coblistinsertafter"></a><a name="insertafter"></a>次のリスト::後に挿入

指定した位置にある要素の後に、このリストに要素を追加します。

```
POSITION InsertAfter(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>パラメーター

*位置*<br/>
前`GetNext`の関数呼び出し`GetPrev`、、`Find`またはメンバー関数呼び出しによって返された POSITION 値。

*新しい要素*<br/>
このリストに追加するオブジェクト ポインター。

次の表に、 に似たその他`CObList::InsertAfter`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置挿入後(位置***位置***、ボイド**<strong>\*</strong>`newElement`**);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置挿入後(位置位置***position***、const CString&);** `newElement` **);**<br /><br /> **位置挿入後(位置***位置***、LPCTSTR);** `newElement` **);**|

### <a name="return-value"></a>戻り値

位置パラメーターと同じ*位置*値。

### <a name="example"></a>例

  クラスの一覧については[、CObList::CObList](#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#103](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]

このプログラムの結果は次のとおりです。

```Output
InsertAfter example: A CObList with 3 elements
a CAge at $4A44 40
a CAge at $4A64 65
a CAge at $4968 21
```

## <a name="coblistinsertbefore"></a><a name="insertbefore"></a>前に挿入します。

一覧の指定した位置にある要素の前に要素を追加します。

```
POSITION InsertBefore(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>パラメーター

*位置*<br/>
前`GetNext`の関数呼び出し`GetPrev`、、`Find`またはメンバー関数呼び出しによって返された POSITION 値。

*新しい要素*<br/>
このリストに追加するオブジェクト ポインター。

### <a name="return-value"></a>戻り値

反復またはオブジェクト・ポインターの取得に使用できる POSITION 値。リストが空の場合は NULL。

次の表に、 に似たその他`CObList::InsertBefore`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置挿入前(位置***位置***、ボイド**<strong>\*</strong>`newElement`**);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置挿入前(位置位置***position***、const CString&);** `newElement` **);**<br /><br /> **位置挿入前(***位置位置* **, LPCTSTR** `newElement` **);**|

### <a name="example"></a>例

  クラスの一覧については[、CObList::CObList](#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#104](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]

このプログラムの結果は次のとおりです。

```Output
InsertBefore example: A CObList with 3 elements
a CAge at $4AE2 40
a CAge at $4B02 65
a CAge at $49E6 21
```

## <a name="coblistisempty"></a><a name="isempty"></a>コブリスト::IsEmpty

このリストに要素が含まれているかどうかを示します。

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>戻り値

このリストが空の場合は 0 以外。それ以外の場合は 0。

次の表に、 に似たその他`CObList::IsEmpty`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**ブールは空です( ) 定数;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**ブールは空です( ) 定数;**|

### <a name="example"></a>例

  [「RemoveAll」](#removeall)の例を参照してください。

## <a name="coblistremoveall"></a><a name="removeall"></a>すべての項目を削除します。

このリストからすべての要素を削除し、関連付けられている`CObList`メモリを解放します。

```
void RemoveAll();
```

### <a name="remarks"></a>解説

リストが既に空の場合は、エラーは生成されません。

から要素を削除すると、`CObList`リストからオブジェクト ポインタが削除されます。 オブジェクト自体を削除するのは、ユーザーの責任です。

次の表に、 に似たその他`CObList::RemoveAll`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**無効すべてを削除します( );**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**無効すべてを削除します( );**|

### <a name="example"></a>例

クラスの一覧については[、CObList::CObList](#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#105](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]

## <a name="coblistremoveat"></a><a name="removeat"></a>コブリスト::削除アット

指定した要素をこのリストから削除します。

```
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>パラメーター

*位置*<br/>
リストから削除する要素の位置。

### <a name="remarks"></a>解説

から`CObList`要素を削除すると、リストからオブジェクト ポインターが削除されます。 オブジェクト自体を削除するのは、ユーザーの責任です。

POSITION 値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。

次の表に、 に似たその他`CObList::RemoveAt`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**ボイド除去(位置***位置***);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**ボイド除去(位置***位置***);**|

### <a name="example"></a>例

  リストの反復中に要素を削除する場合は注意が必要です。 次の例は[、GetNext](#getnext)の有効な**位置**値を保証する削除手法を示しています。

クラスの一覧については[、CObList::CObList](#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#106](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]

このプログラムの結果は次のとおりです。

`RemoveAt example: A CObList with 2 elements`

`a CAge at $4C1E 65`

`a CAge at $4B22 21`

## <a name="coblistremovehead"></a><a name="removehead"></a>コブリスト::削除ヘッド

リストの先頭から要素を削除し、その要素へのポインターを返します。

```
CObject* RemoveHead();
```

### <a name="return-value"></a>戻り値

以前`CObject`のリストの先頭にあるポインター。

### <a name="remarks"></a>解説

を呼び出す`RemoveHead`前に、リストが空でないことを確認する必要があります。 リストが空の場合、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。 [IsEmpty](#isempty)を使用して、リストに要素が含まれていることを確認します。

次の表に、 に似たその他`CObList::RemoveHead`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**ボイド\*除去ヘッド( );**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**C文字列除去ヘッド( );**|

### <a name="example"></a>例

クラスの一覧については[、CObList::CObList](#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#107](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]

## <a name="coblistremovetail"></a><a name="removetail"></a>コブリスト::リムーブテール

リストの末尾から要素を削除し、その要素へのポインターを返します。

```
CObject* RemoveTail();
```

### <a name="return-value"></a>戻り値

リストの末尾にあったオブジェクトへのポインター。

### <a name="remarks"></a>解説

を呼び出す`RemoveTail`前に、リストが空でないことを確認する必要があります。 リストが空の場合、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。 [IsEmpty](#isempty)を使用して、リストに要素が含まれていることを確認します。

次の表に、 に似たその他`CObList::RemoveTail`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**ボイド\*除去テール( );**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**C文字列除去テール( );**|

### <a name="example"></a>例

クラスの一覧については[、CObList::CObList](#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#108](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]

## <a name="coblistsetat"></a><a name="setat"></a>コブリスト::セットアット

指定した位置に要素を設定します。

```
void SetAt(
    POSITION pos,
    CObject* newElement);
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
設定する要素の位置。

*新しい要素*<br/>
リスト`CObject`に書き込まれるポインター。

### <a name="remarks"></a>解説

POSITION 型の変数は、リストのキーです。 これはインデックスと同じではなく、POSITION 値を自分で操作することはできません。 `SetAt`リスト内`CObject`の指定された位置にポインターを書き込みます。

POSITION 値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。

次の表に、 に似たその他`CObList::SetAt`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void SetAt( POSITION** `pos` **, const CString&** `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**ボイドセットアット(ポジション**`pos`**、LPCTSTR);** `newElement` **);**|

### <a name="example"></a>例

  クラスの一覧については[、CObList::CObList](#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#109](../../mfc/codesnippet/cpp/coblist-class_21.cpp)]

このプログラムの結果は次のとおりです。

```Output
SetAt example: A CObList with 2 elements
a CAge at $4D98 40
a CAge at $4DB8 65
```

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/cstringlist-class.md)<br/>
[CPtrList クラス](../../mfc/reference/cptrlist-class.md)
