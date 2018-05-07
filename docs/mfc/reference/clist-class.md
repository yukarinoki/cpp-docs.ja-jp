---
title: CList クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b2a84e73c165efd8f2f17e66af149e33d90395e8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
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
|[CList::CList](#clist)|空の順序付きリストを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CList::AddHead](#addhead)|(新しいヘッドにより) リストの先頭に要素 (または別のリスト内のすべての要素) を追加します。|  
|[CList::AddTail](#addtail)|(新しい末尾になります)、リストの末尾に要素 (または別のリスト内のすべての要素) を追加します。|  
|[CList::Find](#find)|ポインター値で指定された要素の位置を取得します。|  
|[CList::FindIndex](#findindex)|0 から始まるインデックスによって指定された要素の位置を取得します。|  
|[CList::GetAt](#getat)|指定された位置に要素を取得します。|  
|[呼び出す](#getcount)|この一覧にある要素の数を返します。|  
|[CList::GetHead](#gethead)|(空にすることはできません)、リストの先頭の要素を返します。|  
|[CList::GetHeadPosition](#getheadposition)|リストの先頭の要素の位置を返します。|  
|[CList::GetNext](#getnext)|反復処理するためには、次の要素を取得します。|  
|[CList::GetPrev](#getprev)|反復処理するためには、直前の要素を取得します。|  
|[CList::GetSize](#getsize)|この一覧にある要素の数を返します。|  
|[CList::GetTail](#gettail)|(空にすることはできません)、リストの末尾の要素を返します。|  
|[CList::GetTailPosition](#gettailposition)|リストの末尾の要素の位置を返します。|  
|[CList::InsertAfter](#insertafter)|指定した位置の後に新しい要素を挿入します。|  
|[CList::InsertBefore](#insertbefore)|指定した位置の前に新しい要素を挿入します。|  
|[CList::IsEmpty](#isempty)|空のリストの条件 (要素がない) をテストします。|  
|[CList::RemoveAll](#removeall)|このリストからすべての要素を削除します。|  
|[CList::RemoveAt](#removeat)|この一覧から、位置によって指定された要素を削除します。|  
|[CList::RemoveHead](#removehead)|リストの先頭から要素を削除します。|  
|[CList::RemoveTail](#removetail)|リストの末尾から要素を削除します。|  
|[CList::SetAt](#setat)|指定された位置に要素を設定します。|  
  
#### <a name="parameters"></a>パラメーター  
 `TYPE`  
 一覧に格納されているオブジェクトの型。  
  
 `ARG` *_* `TYPE`  
 型リストに格納されているオブジェクトを参照するために使用します。 参照であることができます。  
  
## <a name="remarks"></a>コメント  
 `CList` リストは、二重リンク リストのように動作します。  
  
 型の変数**位置**はリストのキーです。 使用することができます、**位置**順番にリストを走査する反復子および位置を保持するためのブックマークとして変数です。 位置は、インデックスと同じただしです。  
  
 要素の挿入は、非常に高速リストの先頭、末尾、および既知**位置**です。 順次検索は、値またはインデックスで要素を検索する必要があります。 この検索は、一覧が長い場合は低速にすることはできます。  
  
 個々 の要素の一覧にダンプする場合は、1 以上、ダンプ コンテキストの深さを設定する必要があります。  
  
 ほとんどの用途のグローバルのヘルパー関数をこのクラスの呼び出しの一部のメンバー関数をカスタマイズする必要があります、`CList`クラスです。 参照してください[コレクション クラスのヘルパー](../../mfc/reference/collection-class-helpers.md) 「マクロとグローバル変数」セクションでします。  
  
 使用する方法についての`CList`、記事を参照して[コレクション](../../mfc/collections.md)です。  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#35](../../mfc/codesnippet/cpp/clist-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CList`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtempl.h  
  
##  <a name="addhead"></a>  CList::AddHead  
 このリストの先頭に新しい要素または要素の一覧を追加します。  
  
```  
POSITION AddHead(ARG_TYPE newElement);  
void AddHead(CList* pNewList);
```  
  
### <a name="parameters"></a>パラメーター  
 `ARG_TYPE`  
 一覧の要素の型を指定するテンプレート パラメーター (参照を使用できます)。  
  
 `newElement`  
 新しい要素。  
  
 `pNewList`  
 別のポインター `CList`  ボックスの一覧です。 内の要素`pNewList`この一覧に追加されます。  
  
### <a name="return-value"></a>戻り値  
 最初のバージョンを返します、**位置**は新しく挿入される要素の値。  
  
### <a name="remarks"></a>コメント  
 一覧は、操作の前に空にすることができます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#36](../../mfc/codesnippet/cpp/clist-class_2.cpp)]  
  
##  <a name="addtail"></a>  CList::AddTail  
 このリストの末尾に新しい要素または要素の一覧を追加します。  
  
```  
POSITION AddTail(ARG_TYPE newElement);  
void AddTail(CList* pNewList);
```  
  
### <a name="parameters"></a>パラメーター  
 `ARG_TYPE`  
 一覧の要素の型を指定するテンプレート パラメーター (参照を使用できます)。  
  
 `newElement`  
 この一覧に追加する要素。  
  
 `pNewList`  
 別のポインター `CList`  ボックスの一覧です。 内の要素`pNewList`この一覧に追加されます。  
  
### <a name="return-value"></a>戻り値  
 最初のバージョンを返します、**位置**は新しく挿入される要素の値。  
  
### <a name="remarks"></a>コメント  
 一覧は、操作の前に空にすることができます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#37](../../mfc/codesnippet/cpp/clist-class_3.cpp)]  
  
##  <a name="clist"></a>  CList::CList  
 空の順序付きリストを構築します。  
  
```  
CList(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBlockSize`  
 リストを拡張するメモリ割り当ての粒度。  
  
### <a name="remarks"></a>コメント  
 単位でメモリが割り当てられているリストするにつれて、`nBlockSize`エントリです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#38](../../mfc/codesnippet/cpp/clist-class_4.cpp)]  
  
##  <a name="find"></a>  CList::Find  
 指定された一致する最初の要素を検索するには、順番にリストから検索`searchValue`です。  
  
```  
POSITION Find(
    ARG_TYPE searchValue,  
    POSITION startAfter = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `ARG_TYPE`  
 一覧の要素の型を指定するテンプレート パラメーター (参照を使用できます)。  
  
 `searchValue`  
 一覧で検索する値。  
  
 `startAfter`  
 検索の開始位置。 値が指定されていない場合、検索は、head 要素で始まります。  
  
### <a name="return-value"></a>戻り値  
 A**位置**イテレーションまたはオブジェクト ポインターの取得に使用できる値**NULL**オブジェクトが見つからない場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#39](../../mfc/codesnippet/cpp/clist-class_5.cpp)]  
  
##  <a name="findindex"></a>  CList::FindIndex  
 値を使用して`nIndex`一覧のインデックス。  
  
```  
POSITION FindIndex(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 検索するリストの要素の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 A**位置**イテレーションまたはオブジェクト ポインターの取得に使用できる値**NULL**場合`nIndex`が負の値または大きすぎます。  
  
### <a name="remarks"></a>コメント  
 停止する、リストの先頭から順次スキャンを開始、 *n*番目の要素。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#40](../../mfc/codesnippet/cpp/clist-class_6.cpp)]  
  
##  <a name="getat"></a>  CList::GetAt  
 指定した位置にあるリスト要素を取得します。  
  
```  
TYPE& GetAt(POSITION position);  
const TYPE& GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 一覧でオブジェクトの種類を指定するテンプレート パラメーター。  
  
 *位置*  
 取得する要素の一覧で位置。  
  
### <a name="return-value"></a>戻り値  
 戻り値の説明を参照してください`GetHead`です。  
  
### <a name="remarks"></a>コメント  
 `GetAt` 指定した位置に関連付けられている、要素 (または、要素への参照) を返します。 インデックスと同じではなく、操作することはできません、**位置**自分での値します。 型の変数**位置**はリストのキーです。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
### <a name="example"></a>例  
  例を参照して[CList::GetHeadPosition](#getheadposition)です。  
  
##  <a name="getcount"></a>  呼び出す  
 この一覧内の要素の数を取得します。  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 要素の数を含む整数値。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出すのと同じ結果が生成されます、 [CList::GetSize](#getsize)メソッドです。  
  
### <a name="example"></a>例  
  例を参照して[CList::RemoveHead](#removehead)です。  
  
##  <a name="gethead"></a>  CList::GetHead  
 この一覧の先頭の要素 (または、head 要素への参照) を取得します。  
  
```  
const TYPE& GetHead() const;  
  
TYPE& GetHead();
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 一覧でオブジェクトの種類を指定するテンプレート パラメーター。  
  
### <a name="return-value"></a>戻り値  
 リストが場合**const**、`GetHead`リストの先頭にある要素のコピーを返します。 これにより、関数は、代入ステートメントの右側にあるでのみ使用し、変更から一覧を保護できます。  
  
 リストがない場合**const**、`GetHead`リストの先頭にある要素への参照を返します。 これは、関数は、代入ステートメントのどちらにも使用して、できるので、一覧のエントリを変更します。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`GetHead`です。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンをアサートします。 使用して[IsEmpty](#isempty)リストに要素が含まれていることを確認します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#41](../../mfc/codesnippet/cpp/clist-class_7.cpp)]  
  
##  <a name="getheadposition"></a>  CList::GetHeadPosition  
 この一覧の先頭の要素の位置を取得します。  
  
```  
POSITION GetHeadPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**イテレーションまたはオブジェクト ポインターの取得に使用できる値**NULL**リストが空の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#42](../../mfc/codesnippet/cpp/clist-class_8.cpp)]  
  
##  <a name="getnext"></a>  CList::GetNext  
 によって識別される要素を取得`rPosition`を設定し、`rPosition`を**位置**一覧の次のエントリの値。  
  
```  
TYPE& GetNext(POSITION& rPosition);  
const TYPE& GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 リスト内の要素の型を指定するテンプレート パラメーター。  
  
 `rPosition`  
 参照、**位置**によって以前返される値`GetNext`、[順](#getheadposition)、またはその他のメンバー関数の呼び出しです。  
  
### <a name="return-value"></a>戻り値  
 リストが場合**const**、`GetNext`リストの要素のコピーを返します。 これにより、関数は、代入ステートメントの右側にあるでのみ使用し、変更から一覧を保護できます。  
  
 リストがない場合**const**、`GetNext`リストの要素への参照を返します。 これは、関数は、代入ステートメントのどちらにも使用して、できるので、一覧のエントリを変更します。  
  
### <a name="remarks"></a>コメント  
 使用することができます`GetNext`への呼び出しに最初の位置を確立する場合は、順方向の反復ループで`GetHeadPosition`または**検索**です。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 場合は、取得した最後の要素を一覧での新しい値`rPosition`に設定されている**NULL**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#43](../../mfc/codesnippet/cpp/clist-class_9.cpp)]  
  
##  <a name="getprev"></a>  CList::GetPrev  
 要素を取得します ボックスの一覧によって識別される`rPosition`を設定し、`rPosition`を**位置**一覧の前のエントリの値。  
  
```  
TYPE& GetPrev(POSITION& rPosition);  
const TYPE& GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 リスト内の要素の型を指定するテンプレート パラメーター。  
  
 `rPosition`  
 参照、**位置**によって以前返される値`GetPrev`またはその他のメンバー関数の呼び出しです。  
  
### <a name="return-value"></a>戻り値  
 リストが場合**const**、`GetPrev`リストの先頭にある要素のコピーを返します。 これにより、関数は、代入ステートメントの右側にあるでのみ使用し、変更から一覧を保護できます。  
  
 リストがない場合**const**、`GetPrev`リストの要素への参照を返します。 これは、関数は、代入ステートメントのどちらにも使用して、できるので、一覧のエントリを変更します。  
  
### <a name="remarks"></a>コメント  
 使用することができます`GetPrev`への呼び出しに最初の位置を確立する場合は、反転反復ループで`GetTailPosition`または**検索**です。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 取得される要素が一覧で、最初、新しい値の`rPosition`に設定されている**NULL**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#44](../../mfc/codesnippet/cpp/clist-class_10.cpp)]  
  
##  <a name="getsize"></a>  CList::GetSize  
 リストの要素の数を返します。  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リストの項目数。  
  
### <a name="remarks"></a>コメント  
 リスト内の要素の数を取得するには、このメソッドを呼び出します。  このメソッドを呼び出すのと同じ結果が生成されます、[呼び出す](#getcount)メソッドです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#45](../../mfc/codesnippet/cpp/clist-class_11.cpp)]  
  
##  <a name="gettail"></a>  CList::GetTail  
 取得、`CObject`ポインターがこのリストの末尾の要素を表します。  
  
```  
TYPE& GetTail();  
const TYPE& GetTail() const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 リスト内の要素の型を指定するテンプレート パラメーター。  
  
### <a name="return-value"></a>戻り値  
 戻り値の説明を参照してください[gethead 関数](../../mfc/reference/coblist-class.md#gethead)です。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`GetTail`です。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンをアサートします。 使用して[IsEmpty](../../mfc/reference/coblist-class.md#isempty)リストに要素が含まれていることを確認します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#46](../../mfc/codesnippet/cpp/clist-class_12.cpp)]  
  
##  <a name="gettailposition"></a>  CList::GetTailPosition  
 このリストの末尾の要素の位置を取得します。**NULL**リストが空の場合。  
  
```  
POSITION GetTailPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**イテレーションまたはオブジェクト ポインターの取得に使用できる値**NULL**リストが空の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#47](../../mfc/codesnippet/cpp/clist-class_13.cpp)]  
  
##  <a name="insertafter"></a>  CList::InsertAfter  
 指定位置にある要素の後に、このリストに要素を追加します。  
  
```  
POSITION InsertAfter(POSITION position, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 *位置*  
 前の **、** 、または `GetNext`Find `GetPrev`メンバー関数呼び出しにより返される **POSITION** 値。  
  
 `ARG_TYPE`  
 リストの要素の型を指定するテンプレート パラメーター。  
  
 `newElement`  
 この一覧に追加する要素。  
  
### <a name="return-value"></a>戻り値  
 イテレーションまたは一覧の要素の取得に使用できる **POSITION** 値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#48](../../mfc/codesnippet/cpp/clist-class_14.cpp)]  
  
##  <a name="insertbefore"></a>  CList::InsertBefore  
 一覧の指定した位置にある要素の前に要素を追加します。  
  
```  
POSITION InsertBefore(POSITION position, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 *位置*  
 前の **、** 、または `GetNext`Find `GetPrev`メンバー関数呼び出しにより返される **POSITION** 値。  
  
 `ARG_TYPE`  
 一覧の要素の型を指定するテンプレート パラメーター (参照を使用できます)。  
  
 `newElement`  
 この一覧に追加する要素。  
  
### <a name="return-value"></a>戻り値  
 イテレーションまたは一覧の要素の取得に使用できる **POSITION** 値。  
  
### <a name="remarks"></a>コメント  
 *position* が **NULL**である場合、一覧の先頭に要素が挿入されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#49](../../mfc/codesnippet/cpp/clist-class_15.cpp)]  
  
##  <a name="isempty"></a>  CList::IsEmpty  
 このリストに要素が含まれないかどうかを示します。  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>戻り値  
 この場合は 0 以外のリストが空です。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#50](../../mfc/codesnippet/cpp/clist-class_16.cpp)]  
  
##  <a name="removeall"></a>  CList::RemoveAll  
 このリストからすべての要素を削除し、関連付けられているメモリを解放します。  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>コメント  
 リストが空で既に場合、エラーは生成されません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#51](../../mfc/codesnippet/cpp/clist-class_17.cpp)]  
  
##  <a name="removeat"></a>  CList::RemoveAt  
 この一覧から、指定した要素を削除します。  
  
```  
void RemoveAt(POSITION position);
```  
  
### <a name="parameters"></a>パラメーター  
 *位置*  
 一覧から削除する要素の位置。  
  
### <a name="remarks"></a>コメント  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#52](../../mfc/codesnippet/cpp/clist-class_18.cpp)]  
  
##  <a name="removehead"></a>  CList::RemoveHead  
 リストの先頭から要素を削除し、ポインターを返します。  
  
```  
TYPE RemoveHead();
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 リスト内の要素の型を指定するテンプレート パラメーター。  
  
### <a name="return-value"></a>戻り値  
 以前、リストの先頭にある要素。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`RemoveHead`です。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンをアサートします。 使用して[IsEmpty](#isempty)リストに要素が含まれていることを確認します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#53](../../mfc/codesnippet/cpp/clist-class_19.cpp)]  
  
##  <a name="removetail"></a>  CList::RemoveTail  
 リストの末尾から要素を削除し、ポインターを返します。  
  
```  
TYPE RemoveTail();
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 リスト内の要素の型を指定するテンプレート パラメーター。  
  
### <a name="return-value"></a>戻り値  
 リストの末尾にあった要素です。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`RemoveTail`です。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンをアサートします。 使用して[IsEmpty](#isempty)リストに要素が含まれていることを確認します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#54](../../mfc/codesnippet/cpp/clist-class_20.cpp)]  
  
##  <a name="setat"></a>  CList::SetAt  
 型の変数**位置**はリストのキーです。  
  
```  
void SetAt(POSITION pos, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 **位置**を設定する要素のです。  
  
 `ARG_TYPE`  
 一覧の要素の型を指定するテンプレート パラメーター (参照を使用できます)。  
  
 `newElement`  
 一覧に追加する要素。  
  
### <a name="remarks"></a>コメント  
 インデックスと同じではなく、操作することはできません、**位置**自分での値します。 `SetAt` リスト内の指定した位置に要素を書き込みます。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#55](../../mfc/codesnippet/cpp/clist-class_21.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの収集](../../visual-cpp-samples.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMap クラス](../../mfc/reference/cmap-class.md)   
 [CArray クラス](../../mfc/reference/carray-class.md)
