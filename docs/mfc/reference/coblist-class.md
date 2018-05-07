---
title: CObList クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 35217ee967554332002d8597a00dc21df928306d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="coblist-class"></a>CObList クラス
一意の順序付きリスト fSupports`CObject`アクセス可能なポインター値の順番、またはポインターでします。  
  
## <a name="syntax"></a>構文  
  
```  
class CObList : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[使われて](#coblist)|空のリストを構築`CObject`ポインター。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CObList::AddHead](#addhead)|(新しいヘッドにより) リストの先頭に要素 (または別のリスト内のすべての要素) を追加します。|  
|[CObList::AddTail](#addtail)|(新しい末尾になります)、リストの末尾に要素 (または別のリスト内のすべての要素) を追加します。|  
|[CObList::Find](#find)|ポインター値で指定された要素の位置を取得します。|  
|[CObList::FindIndex](#findindex)|0 から始まるインデックスによって指定された要素の位置を取得します。|  
|[CObList::GetAt](#getat)|指定された位置に要素を取得します。|  
|[CObList::GetCount](#getcount)|この一覧にある要素の数を返します。|  
|[CObList::GetHead](#gethead)|(空にすることはできません)、リストの先頭の要素を返します。|  
|[CObList::GetHeadPosition](#getheadposition)|リストの先頭の要素の位置を返します。|  
|[CObList::GetNext](#getnext)|反復処理するためには、次の要素を取得します。|  
|[CObList::GetPrev](#getprev)|反復処理するためには、直前の要素を取得します。|  
|[CObList::GetSize](#getsize)|この一覧にある要素の数を返します。|  
|[CObList::GetTail](#gettail)|(空にすることはできません)、リストの末尾の要素を返します。|  
|[CObList::GetTailPosition](#gettailposition)|リストの末尾の要素の位置を返します。|  
|[CObList::InsertAfter](#insertafter)|指定した位置の後に新しい要素を挿入します。|  
|[CObList::InsertBefore](#insertbefore)|指定した位置の前に新しい要素を挿入します。|  
|[CObList::IsEmpty](#isempty)|空のリストの条件 (要素がない) をテストします。|  
|[CObList::RemoveAll](#removeall)|このリストからすべての要素を削除します。|  
|[CObList::RemoveAt](#removeat)|この一覧から、位置によって指定された要素を削除します。|  
|[CObList::RemoveHead](#removehead)|リストの先頭から要素を削除します。|  
|[CObList::RemoveTail](#removetail)|リストの末尾から要素を削除します。|  
|[CObList::SetAt](#setat)|指定された位置に要素を設定します。|  
  
## <a name="remarks"></a>コメント  
 `CObList` リストは、二重リンク リストのように動作します。  
  
 型の変数**位置**はリストのキーです。 使用することができます、**位置**順番にリストを走査する反復子、および位置を保持するためのブックマークとして変数です。 位置は、インデックスと同じただしです。  
  
 要素の挿入は、非常に高速リストの先頭、末尾、および既知**位置**です。 順次検索は、値またはインデックスで要素を検索する必要があります。 この検索は、一覧が長い場合は低速にすることはできます。  
  
 `CObList` には、`IMPLEMENT_SERIAL` マクロが組み込まれており、その要素のシリアル化とダンプがサポートされます。 リストの場合`CObject`ポインターが格納されているか、オーバー ロードされた挿入演算子のいずれか、アーカイブ、`Serialize`メンバー関数は、各`CObject`要素はさらにシリアル化します。  
  
 個別にダンプする必要がある場合`CObject`リスト内の要素、1 以上、ダンプ コンテキストの深さを設定する必要があります。  
  
 ときに、`CObList`オブジェクトを削除すると、または、ときにその要素が削除された、のみ、`CObject`ポインターが削除され、参照するオブジェクトではありません。  
  
 独自のクラスを派生できます`CObList`です。 派生したオブジェクトへのポインターを保持するように設計 list クラス新しい`CObject`、新しいデータ メンバーと新しいメンバー関数を追加します。 なお、結果のリストはなく厳密にタイプ セーフである、任意の挿入できるので`CObject`ポインター。  
  
> [!NOTE]
>  使用する必要があります、 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロで一覧をシリアル化する場合は、派生クラスの実装です。  
  
 使用する方法についての`CObList`、記事を参照して[コレクション](../../mfc/collections.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CObList`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcoll.h  
  
##  <a name="addhead"></a>  CObList::AddHead  
 このリストの先頭に新しい要素または要素の一覧を追加します。  
  
```  
POSITION AddHead(CObject* newElement);  
void AddHead(CObList* pNewList);
```  
  
### <a name="parameters"></a>パラメーター  
 `newElement`  
 `CObject`をこの一覧に追加するポインター。  
  
 `pNewList`  
 別のポインター `CObList`  ボックスの一覧です。 内の要素`pNewList`この一覧に追加されます。  
  
### <a name="return-value"></a>戻り値  
 最初のバージョンを返します、**位置**は新しく挿入される要素の値。  
  
 次の表はその他のメンバー関数に似ています`CObList::AddHead`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置 AddHead (void\***  `newElement` **) です。**<br /><br /> **AddHead を無効にする (CPtrList\***  `pNewList` **) です。**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置 AddHead (const CString &** `newElement` **) です。**<br /><br /> **位置 AddHead (LPCTSTR** `newElement` **) です。**<br /><br /> **AddHead を無効にする (CStringList\***  `pNewList` **) です。**|  
  
### <a name="remarks"></a>コメント  
 一覧は、操作の前に空にすることができます。  
  
### <a name="example"></a>例  
  参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections#89](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `AddHead example: A CObList with 2 elements`  
  
 `a CAge at $44A8 40`  
  
 `a CAge at $442A 21`  
  
##  <a name="addtail"></a>  CObList::AddTail  
 このリストの末尾に新しい要素または要素の一覧を追加します。  
  
```  
POSITION AddTail(CObject* newElement);  
void AddTail(CObList* pNewList);
```  
  
### <a name="parameters"></a>パラメーター  
 `newElement`  
 `CObject`をこの一覧に追加するポインター。  
  
 `pNewList`  
 別のポインター `CObList`  ボックスの一覧です。 内の要素`pNewList`この一覧に追加されます。  
  
### <a name="return-value"></a>戻り値  
 最初のバージョンを返します、**位置**は新しく挿入される要素の値。  
  
### <a name="remarks"></a>コメント  
 一覧は、操作の前に空にすることができます。  
  
 次の表はその他のメンバー関数に似ています`CObList::AddTail`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置 AddTail (void\***  `newElement` **) です。**<br /><br /> **AddTail を無効にする (CPtrList\***  `pNewList` **) です。**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置 AddTail (const CString &** `newElement` **) です。**<br /><br /> **位置 AddTail (LPCTSTR** `newElement` **) です。**<br /><br /> **AddTail を無効にする (CStringList\***  `pNewList` **) です。**|  
  
### <a name="example"></a>例  
  参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections#90](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `AddTail example: A CObList with 2 elements`  
  
 `a CAge at $444A 21`  
  
 `a CAge at $4526 40`  
  
##  <a name="coblist"></a>  使われて  
 空の構築`CObject`ポインターのリスト。  
  
```  
CObList(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBlockSize`  
 リストを拡張するメモリ割り当ての粒度。  
  
### <a name="remarks"></a>コメント  
 単位でメモリが割り当てられているリストするにつれて、`nBlockSize`エントリです。 メモリの割り当てに失敗した場合、`CMemoryException`がスローされます。  
  
 次の表はその他のメンバー関数に似ています`CObList::CObList`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**CPtrList (INT_PTR** `nBlockSize` **= 10);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CStringList (INT_PTR** `nBlockSize` **= 10);**|  
  
### <a name="example"></a>例  
  次の一覧を示します、 `CObject`-派生クラス`CAge`のすべてのコレクションの例で使用します。  
  
 [!code-cpp[NVC_MFCCollections#91](../../mfc/codesnippet/cpp/coblist-class_3.h)]  
  
 次の例に示します`CObList`コンス トラクターの使用状況。  
  
 [!code-cpp[NVC_MFCCollections#92](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]  
  
##  <a name="find"></a>  CObList::Find  
 最初に順番にリストから検索`CObject`ポインター、指定した照合`CObject`ポインター。  
  
```  
POSITION Find(
    CObject* searchValue,  
    POSITION startAfter = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `searchValue`  
 この一覧で検索するオブジェクトのポインター。  
  
 `startAfter`  
 検索の開始位置。  
  
### <a name="return-value"></a>戻り値  
 A**位置**イテレーションまたはオブジェクト ポインターの取得に使用できる値**NULL**オブジェクトが見つからない場合。  
  
### <a name="remarks"></a>コメント  
 ポインター値を比較することに注意してください、オブジェクトの内容ではありません。  
  
 次の表はその他のメンバー関数に似ています`CObList::Find`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置の検索 (void\***  `searchValue` **、位置** `startAfter` **= NULL) const です。**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置の検索 (LPCTSTR** `searchValue` **、位置** `startAfter` **= NULL) const です。**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections#93](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]  
  
##  <a name="findindex"></a>  CObList::FindIndex  
 値を使用して`nIndex`一覧のインデックス。  
  
```  
POSITION FindIndex(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 検索するリストの要素の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 A**位置**イテレーションまたはオブジェクト ポインターの取得に使用できる値**NULL**場合`nIndex`が大きすぎます。 (場合に、フレームワークがアサーションを生成`nIndex`が負の値です)。  
  
### <a name="remarks"></a>コメント  
 停止する、リストの先頭から順次スキャンを開始、 *n*番目の要素。  
  
 次の表はその他のメンバー関数に似ています`CObList::FindIndex`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置 FindIndex (INT_PTR** `nIndex` **) const です。**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置 FindIndex (INT_PTR** `nIndex` **) const です。**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections#94](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]  
  
##  <a name="getat"></a>  CObList::GetAt  
 型の変数**位置**はリストのキーです。  
  
```  
CObject*& GetAt(POSITION position);  
const CObject*& GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *位置*  
 A**位置**によって以前返される値`GetHeadPosition`または**検索**メンバー関数の呼び出しです。  
  
### <a name="return-value"></a>戻り値  
 戻り値の説明を参照してください[gethead 関数](#gethead)です。  
  
### <a name="remarks"></a>コメント  
 インデックスと同じではなく、操作することはできません、**位置**自分での値します。 `GetAt` 取得、`CObject`指定した位置に関連付けられたポインター。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 次の表はその他のメンバー関数に似ています`CObList::GetAt`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& GetAt (位置***位置* **) const です。**<br /><br /> **void\*& GetAt (位置***位置* **) です。**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetAt (位置***位置* **) const です。**<br /><br /> **CString & GetAt (位置***位置* **) です。**|  
  
### <a name="example"></a>例  
  例を参照して[FindIndex](#findindex)です。  
  
##  <a name="getcount"></a>  CObList::GetCount  
 この一覧内の要素の数を取得します。  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 要素の数を含む整数値。  
  
 次の表はその他のメンバー関数に似ています`CObList::GetCount`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Const; INT_PTR GetCount)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const; INT_PTR GetCount)**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections#95](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]  
  
##  <a name="gethead"></a>  CObList::GetHead  
 取得、`CObject`ポインターがこの一覧の先頭の要素を表します。  
  
```  
CObject*& GetHead();  
const CObject*& GetHead() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リストへのポインターを介してアクセスする場合、 **const CObList**、し`GetHead`を返します、`CObject`ポインター。 これにより、関数は、代入ステートメントの右側にあるでのみ使用し、したがって変更から一覧を保護できます。  
  
 一覧には直接にも、ポインターを介してアクセスする場合、 `CObList`、し`GetHead`への参照を返します、`CObject`ポインター。 これは、関数は、代入ステートメントのどちらにも使用して、できるので、一覧のエントリを変更します。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`GetHead`です。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンをアサートします。 使用して[IsEmpty](#isempty)リストに要素が含まれていることを確認します。  
  
 次の表はその他のメンバー関数に似ています`CObList::GetHead`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& gethead 関数に関するページ (); const void\*& gethead 関数 ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & gethead 関数に関するページ () const です。CString & gethead 関数に関するページ ();**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 次の例は、の使用を示しています。`GetHead`代入ステートメントの左側にあります。  
  
 [!code-cpp[NVC_MFCCollections#96](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]  
  
##  <a name="getheadposition"></a>  CObList::GetHeadPosition  
 この一覧の先頭の要素の位置を取得します。  
  
```  
POSITION GetHeadPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**イテレーションまたはオブジェクト ポインターの取得に使用できる値**NULL**リストが空の場合。  
  
 次の表はその他のメンバー関数に似ています`CObList::GetHeadPosition`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Const; 位置順)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const; 位置順)**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections#97](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]  
  
##  <a name="getnext"></a>  CObList::GetNext  
 によって識別される要素を取得`rPosition`を設定し、`rPosition`を`POSITION`一覧の次のエントリの値。  
  
```  
CObject*& GetNext(POSITION& rPosition);  
const CObject* GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `rPosition`  
 参照、`POSITION`によって以前返される値`GetNext`、 `GetHeadPosition`、またはその他のメンバー関数の呼び出しです。  
  
### <a name="return-value"></a>戻り値  
 戻り値の説明を参照してください[gethead 関数](#gethead)です。  
  
### <a name="remarks"></a>コメント  
 使用することができます`GetNext`への呼び出しに最初の位置を確立する場合は、順方向の反復ループで`GetHeadPosition`または`Find`です。  
  
 確認する必要があります、`POSITION`値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 場合は、取得した最後の要素を一覧での新しい値`rPosition`に設定されている`NULL`です。  
  
 反復処理中に要素を削除することができます。 例を参照して[RemoveAt](#removeat)です。  
  
> [!NOTE]
>  MFC 8.0 の時点では、このメソッドの const バージョンが返される変更されました`const CObject*`の代わりに`const CObject*&`です。  標準の C++ への適合性をコンパイラをさせるために、この変更が加えられました。  
  
 次の表はその他のメンバー関数に似ています`CObList::GetNext`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|  
  
### <a name="example"></a>例  
  参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections#98](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `a CAge at $479C 40`  
  
 `a CAge at $46C0 21`  
  
##  <a name="getprev"></a>  CObList::GetPrev  
 要素を取得します ボックスの一覧によって識別される`rPosition`を設定し、`rPosition`を`POSITION`一覧の前のエントリの値。  
  
```  
CObject*& GetPrev(POSITION& rPosition);  
const CObject* GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `rPosition`  
 参照、`POSITION`によって以前返される値`GetPrev`またはその他のメンバー関数の呼び出しです。  
  
### <a name="return-value"></a>戻り値  
 戻り値の説明を参照してください[gethead 関数](#gethead)です。  
  
### <a name="remarks"></a>コメント  
 使用することができます`GetPrev`への呼び出しに最初の位置を確立する場合は、反転反復ループで`GetTailPosition`または`Find`です。  
  
 確認する必要があります、`POSITION`値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 取得される要素が一覧で、最初、新しい値の`rPosition`に設定されている`NULL`です。  
  
> [!NOTE]
>  MFC 8.0 の時点では、このメソッドの const バージョンが返される変更されました`const CObject*`の代わりに`const CObject*&`です。  標準の C++ への適合性をコンパイラをさせるために、この変更が加えられました。  
  
 次の表はその他のメンバー関数に似ています`CObList::GetPrev`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|  
  
### <a name="example"></a>例  
  参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections#99](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `a CAge at $421C 21`  
  
 `a CAge at $421C 40`  
  
##  <a name="getsize"></a>  CObList::GetSize  
 リストの要素の数を返します。  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リストの項目数。  
  
### <a name="remarks"></a>コメント  
 リスト内の要素の数を取得するには、このメソッドを呼び出します。  
  
 次の表はその他のメンバー関数に似ています`CObList::GetSize`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Const; INT_PTR GetSize)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const; INT_PTR GetSize)**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections#100](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]  
  
##  <a name="gettail"></a>  CObList::GetTail  
 取得、`CObject`ポインターがこのリストの末尾の要素を表します。  
  
```  
CObject*& GetTail();  
const CObject*& GetTail() const;  
```  
  
### <a name="return-value"></a>戻り値  
 戻り値の説明を参照してください[gethead 関数](#gethead)です。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`GetTail`です。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンをアサートします。 使用して[IsEmpty](#isempty)リストに要素が含まれていることを確認します。  
  
 次の表はその他のメンバー関数に似ています`CObList::GetTail`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& GetTail に関するページ (); const void\*& GetTail ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetTail に関するページ () const です。CString & GetTail ();**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections#101](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]  
  
##  <a name="gettailposition"></a>  CObList::GetTailPosition  
 このリストの末尾の要素の位置を取得します。**NULL**リストが空の場合。  
  
```  
POSITION GetTailPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**イテレーションまたはオブジェクト ポインターの取得に使用できる値**NULL**リストが空の場合。  
  
 次の表はその他のメンバー関数に似ています`CObList::GetTailPosition`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Const; 位置 GetTailPosition)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const; 位置 GetTailPosition)**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections#102](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]  
  
##  <a name="insertafter"></a>  CObList::InsertAfter  
 指定位置にある要素の後に、このリストに要素を追加します。  
  
```  
POSITION InsertAfter(
    POSITION position,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 *位置*  
 前の **、** 、または `GetNext`Find `GetPrev`メンバー関数呼び出しにより返される **POSITION** 値。  
  
 `newElement`  
 この一覧に追加するオブジェクトのポインター。  
  
 次の表はその他のメンバー関数に似ています`CObList::InsertAfter`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置 InsertAfter (位置***位置* **, void\***  `newElement` **) です。**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置 InsertAfter (位置***位置* **、const CString &** `newElement` **) です。**<br /><br /> **位置 InsertAfter (位置***位置* **、LPCTSTR** `newElement` **) です。**|  
  
### <a name="return-value"></a>戻り値  
 A**位置**は同じ値として、*位置*パラメーター。  
  
### <a name="example"></a>例  
  参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections#103](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `InsertAfter example: A CObList with 3 elements`  
  
 `a CAge at $4A44 40`  
  
 `a CAge at $4A64 65`  
  
 `a CAge at $4968 21`  
  
##  <a name="insertbefore"></a>  CObList::InsertBefore  
 一覧の指定した位置にある要素の前に要素を追加します。  
  
```  
POSITION InsertBefore(
    POSITION position,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 *位置*  
 前の **、** 、または `GetNext`Find `GetPrev`メンバー関数呼び出しにより返される **POSITION** 値。  
  
 `newElement`  
 この一覧に追加するオブジェクトのポインター。  
  
### <a name="return-value"></a>戻り値  
 A**位置**イテレーションまたはオブジェクト ポインターの取得に使用できる値**NULL**リストが空の場合。  
  
 次の表はその他のメンバー関数に似ています`CObList::InsertBefore`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置 InsertBefore (位置***位置* **, void\***  `newElement` **) です。**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置 InsertBefore (位置***位置* **、const CString &** `newElement` **) です。**<br /><br /> **位置 InsertBefore (位置***位置* **、LPCTSTR** `newElement` **) です。**|  
  
### <a name="example"></a>例  
  参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections#104](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `InsertBefore example: A CObList with 3 elements`  
  
 `a CAge at $4AE2 40`  
  
 `a CAge at $4B02 65`  
  
 `a CAge at $49E6 21`  
  
##  <a name="isempty"></a>  CObList::IsEmpty  
 このリストに要素が含まれないかどうかを示します。  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>戻り値  
 この場合は 0 以外のリストが空です。それ以外の場合 0 を返します。  
  
 次の表はその他のメンバー関数に似ています`CObList::IsEmpty`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Const; BOOL IsEmpty)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const; BOOL IsEmpty)**|  
  
### <a name="example"></a>例  
  例を参照して[RemoveAll](#removeall)です。  
  
##  <a name="removeall"></a>  CObList::RemoveAll  
 この一覧からすべての要素を削除し、関連付けられている解放`CObList`メモリです。  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>コメント  
 リストが空で既に場合、エラーは生成されません。  
  
 要素を削除すると、 `CObList`、一覧からオブジェクトのポインターを削除します。 ユーザーの責任をオブジェクト自体を削除することをお勧めします。  
  
 次の表はその他のメンバー関数に似ています`CObList::RemoveAll`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAll( );**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAll( );**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections#105](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]  
  
##  <a name="removeat"></a>  CObList::RemoveAt  
 この一覧から、指定した要素を削除します。  
  
```  
void RemoveAt(POSITION position);
```  
  
### <a name="parameters"></a>パラメーター  
 *位置*  
 一覧から削除する要素の位置。  
  
### <a name="remarks"></a>コメント  
 要素を削除すると、 `CObList`、一覧からオブジェクトへのポインターを削除します。 ユーザーの責任をオブジェクト自体を削除することをお勧めします。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 次の表はその他のメンバー関数に似ています`CObList::RemoveAt`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**RemoveAt を無効にする (位置***位置* **) です。**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**RemoveAt を無効にする (位置***位置* **) です。**|  
  
### <a name="example"></a>例  
  リストの反復処理中に要素を削除するときに注意します。 次の例は、有効なことを保証する削除手法**位置**値[GetNext](#getnext)です。  
  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections#106](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `RemoveAt example: A CObList with 2 elements`  
  
 `a CAge at $4C1E 65`  
  
 `a CAge at $4B22 21`  
  
##  <a name="removehead"></a>  CObList::RemoveHead  
 リストの先頭から要素を削除し、ポインターを返します。  
  
```  
CObject* RemoveHead();
```  
  
### <a name="return-value"></a>戻り値  
 `CObject`リストの先頭にあったポインター。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`RemoveHead`です。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンをアサートします。 使用して[IsEmpty](#isempty)リストに要素が含まれていることを確認します。  
  
 次の表はその他のメンバー関数に似ています`CObList::RemoveHead`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* RemoveHead ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveHead ();**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections#107](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]  
  
##  <a name="removetail"></a>  CObList::RemoveTail  
 リストの末尾から要素を削除し、ポインターを返します。  
  
```  
CObject* RemoveTail();
```  
  
### <a name="return-value"></a>戻り値  
 リストの末尾にあったオブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`RemoveTail`です。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンをアサートします。 使用して[IsEmpty](#isempty)リストに要素が含まれていることを確認します。  
  
 次の表はその他のメンバー関数に似ています`CObList::RemoveTail`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* RemoveTail ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveTail ();**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections#108](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]  
  
##  <a name="setat"></a>  CObList::SetAt  
 指定された位置に要素を設定します。  
  
```  
void SetAt(
    POSITION pos,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 **位置**を設定する要素のです。  
  
 `newElement`  
 `CObject`一覧に書き込まれるへのポインター。  
  
### <a name="remarks"></a>コメント  
 型の変数**位置**はリストのキーです。 インデックスと同じではなく、操作することはできません、**位置**自分での値します。 `SetAt` 書き込みます、`CObject`リスト内の指定位置へのポインター。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 次の表はその他のメンバー関数に似ています`CObList::SetAt`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**SetAt を無効にする (位置** `pos` **、const CString &** `newElement` **) です。**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**SetAt を無効にする (位置** `pos` **、LPCTSTR** `newElement` **) です。**|  
  
### <a name="example"></a>例  
  参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections#109](../../mfc/codesnippet/cpp/coblist-class_21.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `SetAt example: A CObList with 2 elements`  
  
 `a CAge at $4D98 40`  
  
 `a CAge at $4DB8 65`  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CStringList クラス](../../mfc/reference/cstringlist-class.md)   
 [CPtrList クラス](../../mfc/reference/cptrlist-class.md)
