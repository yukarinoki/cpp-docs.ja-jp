---
title: CAtlList クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlList class
ms.assetid: 09e98053-64b2-4efa-99ab-d0542caaf981
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4bfe961ef3ac02a0ed068b8cc2b74f2a6cce22ae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="catllist-class"></a>CAtlList クラス
このクラスは、作成して、リスト オブジェクトを管理するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
template<typename E, class ETraits = CElementTraits<E>>  
class CAtlList
```  
  
#### <a name="parameters"></a>パラメーター  
 `E`  
 要素型。  
  
 `ETraits`  
 コピーまたは要素を移動するために使用するコードです。 参照してください[CElementTraits クラス](../../atl/reference/celementtraits-class.md)詳細についてはします。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlList::INARGTYPE](#inargtype)||  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlList::CAtlList](#catllist)|コンストラクターです。|  
|[CAtlList:: ~ CAtlList](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlList::AddHead](#addhead)|リストの先頭に要素を追加するには、このメソッドを呼び出します。|  
|[CAtlList::AddHeadList](#addheadlist)|既存のリストをリストの先頭に追加するには、このメソッドを呼び出します。|  
|[CAtlList::AddTail](#addtail)|このリストの末尾に要素を追加するには、このメソッドを呼び出します。|  
|[CAtlList::AddTailList](#addtaillist)|このリストの末尾に既存のリストを追加するには、このメソッドを呼び出します。|  
|[CAtlList::AssertValid](#assertvalid)|このメソッドを呼び出して、一覧が有効であることを確認します。|  
|[CAtlList::Find](#find)|指定した要素の一覧を検索するには、このメソッドを呼び出します。|  
|[CAtlList::FindIndex](#findindex)|特定のインデックス値、要素の位置を取得するには、このメソッドを呼び出します。|  
|[CAtlList::GetAt](#getat)|このメソッドを呼び出して、リスト内の指定位置にある要素を返します。|  
|[CAtlList::GetCount](#getcount)|このメソッドを呼び出して、一覧にオブジェクトの数を返します。|  
|[CAtlList::GetHead](#gethead)|このメソッドを呼び出して、一覧の先頭の要素を返します。|  
|[CAtlList::GetHeadPosition](#getheadposition)|リストの先頭の位置を取得するには、このメソッドを呼び出します。|  
|[CAtlList::GetNext](#getnext)|このメソッドを呼び出して、一覧から次の要素を返します。|  
|[CAtlList::GetPrev](#getprev)|このメソッドを呼び出して、リストから直前の要素を返します。|  
|[CAtlList::GetTail](#gettail)|このメソッドを呼び出して、リストの末尾にある要素を返します。|  
|[CAtlList::GetTailPosition](#gettailposition)|リストの末尾の位置を取得するには、このメソッドを呼び出します。|  
|[CAtlList::InsertAfter](#insertafter)|指定した位置の後に、リストに新しい要素を挿入するには、このメソッドを呼び出します。|  
|[CAtlList::InsertBefore](#insertbefore)|指定した位置の前に、の一覧に新しい要素を挿入するには、このメソッドを呼び出します。|  
|[CAtlList::IsEmpty](#isempty)|リストが空であるかを判断するには、このメソッドを呼び出します。|  
|[CAtlList::MoveToHead](#movetohead)|指定した要素をリストの先頭に移動するには、このメソッドを呼び出します。|  
|[CAtlList::MoveToTail](#movetotail)|指定した要素をリストの末尾に移動するには、このメソッドを呼び出します。|  
|[CAtlList::RemoveAll](#removeall)|一覧からすべての要素を削除するには、このメソッドを呼び出します。|  
|[CAtlList::RemoveAt](#removeat)|一覧から 1 つの要素を削除するには、このメソッドを呼び出します。|  
|[CAtlList::RemoveHead](#removehead)|一覧の先頭の要素を削除するには、このメソッドを呼び出します。|  
|[CAtlList::RemoveHeadNoReturn](#removeheadnoreturn)|値を返さずに、リストの先頭にある要素を削除するには、このメソッドを呼び出します。|  
|[CAtlList::RemoveTail](#removetail)|リストの末尾にある要素を削除するには、このメソッドを呼び出します。|  
|[CAtlList::RemoveTailNoReturn](#removetailnoreturn)|値を返さずに、リストの末尾にある要素を削除するには、このメソッドを呼び出します。|  
|[CAtlList::SetAt](#setat)|リスト内の指定位置に要素の値を設定するには、このメソッドを呼び出します。|  
|[CAtlList::SwapElements](#swapelements)|リスト内の要素をスワップするには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
 `CAtlList`クラス順番、または値によってアクセス可能な一意でないオブジェクトの一覧を順序付けがサポートされます。 `CAtlList` リストは、二重リンク リストのように動作します。 各リストには、先頭と末尾、および新しい要素 (または場合によってはリスト) を一覧の先頭または末尾に追加または特定の要素の前後に挿入します。  
  
 ほとんどの`CAtlList`メソッドを使用する位置の値を使用します。 この値は、ここで、要素が格納されていると計算したりしないで直接予測の実際のメモリ位置を参照するメソッドによって使用されます。 アクセスする必要がある場合、 *n*番目の要素の一覧で、メソッド[CAtlList::FindIndex](#findindex)は指定されたインデックスの対応する位置の値を返します。 メソッド[CAtlList::GetNext](#getnext)と[CAtlList::GetPrev](#getprev)リスト内のオブジェクトを反復処理するために使用できます。  
  
 ATL で利用可能なコレクション クラスの詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="addhead"></a>  CAtlList::AddHead  
 リストの先頭に要素を追加するには、このメソッドを呼び出します。  
  
```
POSITION AddHead();
POSITION AddHead(INARGTYPE element);
```  
  
### <a name="parameters"></a>パラメーター  
 `element`  
 新しい要素。  
  
### <a name="return-value"></a>戻り値  
 新しく追加された要素の位置を返します。  
  
### <a name="remarks"></a>コメント  
 最初のバージョンを使用すると、コピー コンス トラクターではなく、既定のコンス トラクターを使用して、空の要素が作成されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#13](../../atl/codesnippet/cpp/catllist-class_1.cpp)]  
  
##  <a name="addheadlist"></a>  CAtlList::AddHeadList  
 既存のリストをリストの先頭に追加するには、このメソッドを呼び出します。  
  
```
void AddHeadList(const CAtlList<E, ETraits>* plNew);
```  
  
### <a name="parameters"></a>パラメーター  
 `plNew`  
 追加するリスト。  
  
### <a name="remarks"></a>コメント  
 によって示されるリスト`plNew`が既存のリストの先頭に挿入します。 デバッグ ビルドで、アサーション エラーが発生場合`plNew`が NULL です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#14](../../atl/codesnippet/cpp/catllist-class_2.cpp)]  
  
##  <a name="addtail"></a>  CAtlList::AddTail  
 このリストの末尾に要素を追加するには、このメソッドを呼び出します。  
  
```
POSITION AddTail();
POSITION AddTail(INARGTYPE element);
```  
  
### <a name="parameters"></a>パラメーター  
 `element`  
 追加する要素。  
  
### <a name="return-value"></a>戻り値  
 新しく追加された要素の位置を返します。  
  
### <a name="remarks"></a>コメント  
 最初のバージョンを使用すると、コピー コンス トラクターではなく、既定のコンス トラクターを使用して、空の要素が作成されます。 リストの末尾に要素が追加され、そのため、末尾になります。 このメソッドは、空のリストで使用できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#15](../../atl/codesnippet/cpp/catllist-class_3.cpp)]  
  
##  <a name="addtaillist"></a>  CAtlList::AddTailList  
 このリストの末尾に既存のリストを追加するには、このメソッドを呼び出します。  
  
```
void AddTailList(const CAtlList<E, ETraits>* plNew);
```  
  
### <a name="parameters"></a>パラメーター  
 `plNew`  
 追加するリスト。  
  
### <a name="remarks"></a>コメント  
 によって示されるリスト`plNew`が挿入の最後の要素の後 (存在する場合)、リスト オブジェクト。 最後の要素、`plNew`リストが末尾にします。 デバッグ ビルドで、アサーション エラーが発生場合*plNew*が NULL です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#16](../../atl/codesnippet/cpp/catllist-class_4.cpp)]  
  
##  <a name="assertvalid"></a>  CAtlList::AssertValid  
 このメソッドを呼び出して、一覧が有効であることを確認します。  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドでは、リスト オブジェクトが有効でない場合、アサーションの失敗が発生します。 空でないリストは先頭と末尾の有効なアドレスを指している必要があり、先頭と末尾の NULL を指すの両方を有効にするには、空のリストがあります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#17](../../atl/codesnippet/cpp/catllist-class_5.cpp)]  
  
##  <a name="catllist"></a>  CAtlList::CAtlList  
 コンストラクターです。  
  
```
CAtlList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nBlockSize`  
 ブロック サイズ。  
  
### <a name="remarks"></a>コメント  
 コンス トラクター、`CAtlList`オブジェクト。 ブロック サイズは、新しい要素が必要な場合に割り当てられたメモリの量の測定です。 ブロック サイズを大きくはメモリ割り当てルーチンに呼び出しを減らすことより多くのリソースを使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#18](../../atl/codesnippet/cpp/catllist-class_6.cpp)]  
  
##  <a name="dtor"></a>  CAtlList:: ~ CAtlList  
 デストラクターです。  
  
```
~CAtlList() throw();
```  
  
### <a name="remarks"></a>コメント  
 呼び出しを含む、割り当てられているすべてのリソースを解放[CAtlList::RemoveAll](#removeall)をリストからすべての要素を削除します。  
  
 一覧では、呼び出しの後にいくつかの要素もが含まれている場合に、デバッグ ビルドでアサーション エラーが発生`RemoveAll`です。  
  
##  <a name="find"></a>  CAtlList::Find  
 指定した要素の一覧を検索するには、このメソッドを呼び出します。  
  
```
POSITION Find(INARGTYPE element, POSITION posStartAfter = NULL) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `element`  
 一覧で検索する要素。  
  
 `posStartAfter`  
 検索の開始位置。 値が指定されていない場合、検索は、head 要素で始まります。  
  
### <a name="return-value"></a>戻り値  
 場合は、要素の位置の値を返しますが見つかると、それ以外の場合は NULL を返します。  
  
### <a name="remarks"></a>コメント  
 List オブジェクトが有効でない場合、または場合デバッグ ビルドで、アサーション エラーが発生、`posStartAfter`値が範囲外です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#19](../../atl/codesnippet/cpp/catllist-class_7.cpp)]  
  
##  <a name="findindex"></a>  CAtlList::FindIndex  
 特定のインデックス値、要素の位置を取得するには、このメソッドを呼び出します。  
  
```
POSITION FindIndex(size_t iElement) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `iElement`  
 必要なリストの要素の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 場合に、対応する位置の値、または NULL を返します`iElement`が範囲外です。  
  
### <a name="remarks"></a>コメント  
 このメソッドにアクセスできるように、指定されたインデックス値に対応する位置を返します、 *n*リスト内の th 要素。  
  
 デバッグ ビルドでは、リスト オブジェクトが有効でない場合、アサーションの失敗が発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#20](../../atl/codesnippet/cpp/catllist-class_8.cpp)]  
  
##  <a name="getat"></a>  CAtlList::GetAt  
 このメソッドを呼び出して、リスト内の指定位置にある要素を返します。  
  
```
E& GetAt(POSITION pos) throw();
const E& GetAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 特定の要素を指定する位置を表す値です。  
  
### <a name="return-value"></a>戻り値  
 参照または要素のコピー。  
  
### <a name="remarks"></a>コメント  
 リストが場合**const**、`GetAt`要素のコピーを返します。 これにより、メソッドは、代入ステートメントの右側にあるでのみ使用し、変更から一覧を保護できます。  
  
 リストがない場合**const**、`GetAt`要素への参照を返します。 これは、メソッドは、代入ステートメントのいずれかの側で使用できるようし、できるので、一覧のエントリを変更できます。  
  
 デバッグ ビルドで、アサーション エラーが発生場合`pos`が NULL です。  
  
### <a name="example"></a>例  
 例を参照して[CAtlList::FindIndex](#findindex)です。  
  
##  <a name="getcount"></a>  CAtlList::GetCount  
 このメソッドを呼び出して、一覧にオブジェクトの数を返します。  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 リストの要素数を返します。  
  
### <a name="example"></a>例  
 例を参照して[CAtlList::Find](#find)です。  
  
##  <a name="gethead"></a>  CAtlList::GetHead  
 このメソッドを呼び出して、一覧の先頭の要素を返します。  
  
```
E& GetHead() throw();
const E& GetHead() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 参照またはリストの先頭にある要素のコピーを返します。  
  
### <a name="remarks"></a>コメント  
 リストが場合**const**、`GetHead`リストの先頭にある要素のコピーを返します。 これにより、メソッドは、代入ステートメントの右側にあるでのみ使用し、変更から一覧を保護できます。  
  
 リストがない場合**const**、`GetHead`リストの先頭にある要素への参照を返します。 これは、メソッドは、代入ステートメントのいずれかの側で使用できるようし、できるので、一覧のエントリを変更できます。  
  
 デバッグ ビルドでは、NULL をリストの先頭を指す場合、アサーションの失敗が発生します。  
  
### <a name="example"></a>例  
 例を参照して[CAtlList::AddHead](#addhead)です。  
  
##  <a name="getheadposition"></a>  CAtlList::GetHeadPosition  
 リストの先頭の位置を取得するには、このメソッドを呼び出します。  
  
```
POSITION GetHeadPosition() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 一覧の先頭の要素に対応する位置の値を返します。  
  
### <a name="remarks"></a>コメント  
 リストが空の場合は、返される値は NULL です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#21](../../atl/codesnippet/cpp/catllist-class_9.cpp)]  
  
##  <a name="getnext"></a>  CAtlList::GetNext  
 このメソッドを呼び出して、一覧から次の要素を返します。  
  
```
E& GetNext(POSITION& pos) throw();
const E& GetNext(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 位置の値、前回の呼び出しによって返される`GetNext`、 [CAtlList::GetHeadPosition](#getheadposition)、またはその他の`CAtlList`メソッドです。  
  
### <a name="return-value"></a>戻り値  
 リストが場合**const**、`GetNext`一覧の次の要素のコピーを返します。 これにより、メソッドは、代入ステートメントの右側にあるでのみ使用し、変更から一覧を保護できます。  
  
 リストがない場合**const**、`GetNext`一覧の次の要素への参照を返します。 これは、メソッドは、代入ステートメントのいずれかの側で使用できるようし、できるので、一覧のエントリを変更できます。  
  
### <a name="remarks"></a>コメント  
 位置カウンター`pos`一覧で、次の要素をポイントするか、ありません要素がある場合は NULL に更新されます。 デバッグ ビルドで、アサーション エラーが発生場合`pos`が NULL です。  
  
### <a name="example"></a>例  
 例を参照して[CAtlList::GetHeadPosition](#getheadposition)です。  
  
##  <a name="getprev"></a>  CAtlList::GetPrev  
 このメソッドを呼び出して、リストから直前の要素を返します。  
  
```
E& GetPrev(POSITION& pos) throw();
const E& GetPrev(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 位置の値、前回の呼び出しによって返される`GetPrev`、 [CAtlList::GetTailPosition](#gettailposition)、またはその他の`CAtlList`メソッドです。  
  
### <a name="return-value"></a>戻り値  
 リストが場合**const**、`GetPrev`リストの要素のコピーを返します。 これにより、メソッドは、代入ステートメントの右側にあるでのみ使用し、変更から一覧を保護できます。  
  
 リストがない場合**const**、`GetPrev`リストの要素への参照を返します。 これは、メソッドは、代入ステートメントのいずれかの側で使用できるようし、できるので、一覧のエントリを変更できます。  
  
### <a name="remarks"></a>コメント  
 位置カウンター`pos`一覧で、直前の要素をポイントするか、ありません要素がある場合は NULL に更新されます。 デバッグ ビルドで、アサーション エラーが発生場合`pos`が NULL です。  
  
### <a name="example"></a>例  
 例を参照して[CAtlList::GetTailPosition](#gettailposition)です。  
  
##  <a name="gettail"></a>  CAtlList::GetTail  
 このメソッドを呼び出して、リストの末尾にある要素を返します。  
  
```
E& GetTail() throw();
const E& GetTail() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 参照またはリストの末尾にある要素のコピーを返します。  
  
### <a name="remarks"></a>コメント  
 リストが場合**const**、`GetTail`リストの先頭にある要素のコピーを返します。 これにより、メソッドは、代入ステートメントの右側にあるでのみ使用し、変更から一覧を保護できます。  
  
 リストがない場合**const**、`GetTail`リストの先頭にある要素への参照を返します。 これは、メソッドは、代入ステートメントのいずれかの側で使用できるようし、できるので、一覧のエントリを変更できます。  
  
 デバッグ ビルドでは、リストの末尾が NULL を指している場合、アサーションの失敗が発生します。  
  
### <a name="example"></a>例  
 例を参照して[CAtlList::AddTail](#addtail)です。  
  
##  <a name="gettailposition"></a>  CAtlList::GetTailPosition  
 リストの末尾の位置を取得するには、このメソッドを呼び出します。  
  
```
POSITION GetTailPosition() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 リストの末尾にある要素に対応する位置の値を返します。  
  
### <a name="remarks"></a>コメント  
 リストが空の場合は、返される値は NULL です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#22](../../atl/codesnippet/cpp/catllist-class_10.cpp)]  
  
##  <a name="inargtype"></a>  CAtlList::INARGTYPE  
 要素は入力引数として渡されるときに使用される型。  
  
```
typedef ETraits::INARGTYPE INARGTYPE;
```  
  
##  <a name="insertafter"></a>  CAtlList::InsertAfter  
 指定した位置の後に、リストに新しい要素を挿入するには、このメソッドを呼び出します。  
  
```
POSITION InsertAfter(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 その後、新しい要素を挿入する位置を表す値です。  
  
 `element`  
 挿入される要素。  
  
### <a name="return-value"></a>戻り値  
 新しい要素の位置を表す値を返します。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドでは、挿入に失敗した場合、または末尾の後に要素を挿入しようとしましたが、有効なリストがない場合、アサーションの失敗が発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#23](../../atl/codesnippet/cpp/catllist-class_11.cpp)]  
  
##  <a name="insertbefore"></a>  CAtlList::InsertBefore  
 指定した位置の前に、の一覧に新しい要素を挿入するには、このメソッドを呼び出します。  
  
```
POSITION InsertBefore(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 新しい要素は、この位置の値の前に、の一覧に挿入されます。  
  
 `element`  
 挿入される要素。  
  
### <a name="return-value"></a>戻り値  
 新しい要素の位置を表す値を返します。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドでは、挿入に失敗した場合、または先頭の前に要素を挿入しようとしましたが、有効なリストがない場合、アサーションの失敗が発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#24](../../atl/codesnippet/cpp/catllist-class_12.cpp)]  
  
##  <a name="isempty"></a>  CAtlList::IsEmpty  
 リストが空であるかを判断するには、このメソッドを呼び出します。  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 リストにオブジェクト、それ以外の場合は false が含まれていない場合は true を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#25](../../atl/codesnippet/cpp/catllist-class_13.cpp)]  
  
##  <a name="movetohead"></a>  CAtlList::MoveToHead  
 指定した要素をリストの先頭に移動するには、このメソッドを呼び出します。  
  
```
void MoveToHead(POSITION pos) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 移動先の要素の位置の値。  
  
### <a name="remarks"></a>コメント  
 指定した要素は、現在の位置からリストの先頭に移動されます。 デバッグ ビルドで、アサーション エラーが発生場合`pos`が NULL です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#26](../../atl/codesnippet/cpp/catllist-class_14.cpp)]  
  
##  <a name="movetotail"></a>  CAtlList::MoveToTail  
 指定した要素をリストの末尾に移動するには、このメソッドを呼び出します。  
  
```
void MoveToTail(POSITION pos) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 移動先の要素の位置の値。  
  
### <a name="remarks"></a>コメント  
 指定した要素は、現在の位置からリストの末尾に移動されます。 デバッグ ビルドで、アサーション エラーが発生場合`pos`が NULL です。  
  
### <a name="example"></a>例  
 例を参照して[CAtlList::MoveToHead](#movetohead)です。  
  
##  <a name="removeall"></a>  CAtlList::RemoveAll  
 一覧からすべての要素を削除するには、このメソッドを呼び出します。  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、一覧からすべての要素を削除し、割り当てられたメモリを解放します。 デバッグ ビルドでは、すべての要素が削除されない場合、またはリストの構造が破損した場合、ATLASSERT が生成されます。  
  
### <a name="example"></a>例  
 例を参照して[CAtlList::IsEmpty](#isempty)です。  
  
##  <a name="removeat"></a>  CAtlList::RemoveAt  
 一覧から 1 つの要素を削除するには、このメソッドを呼び出します。  
  
```
void RemoveAt(POSITION pos) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 削除する要素の位置の値。  
  
### <a name="remarks"></a>コメント  
 により参照される要素`pos`が削除され、メモリを解放します。 使用してもかまいません。 `RemoveAt` head またはリストの末尾を削除します。  
  
 デバッグ ビルドでは、一覧が有効でない場合、またはメモリにアクセスするリストの構造体のリスト要素を削除すると、アサーション エラーが発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#27](../../atl/codesnippet/cpp/catllist-class_15.cpp)]  
  
##  <a name="removehead"></a>  CAtlList::RemoveHead  
 一覧の先頭の要素を削除するには、このメソッドを呼び出します。  
  
```
E RemoveHead();
```  
  
### <a name="return-value"></a>戻り値  
 一覧の先頭の要素を返します。  
  
### <a name="remarks"></a>コメント  
 Head 要素は、一覧から削除され、メモリが解放されます。 要素のコピーが返されます。 デバッグ ビルドでは、一覧が空の場合、アサーションの失敗が発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#28](../../atl/codesnippet/cpp/catllist-class_16.cpp)]  
  
##  <a name="removeheadnoreturn"></a>  CAtlList::RemoveHeadNoReturn  
 値を返さずに、リストの先頭にある要素を削除するには、このメソッドを呼び出します。  
  
```
void RemoveHeadNoReturn() throw();
```  
  
### <a name="remarks"></a>コメント  
 Head 要素は、一覧から削除され、メモリが解放されます。 デバッグ ビルドでは、一覧が空の場合、アサーションの失敗が発生します。  
  
### <a name="example"></a>例  
 例を参照して[CAtlList::IsEmpty](#isempty)です。  
  
##  <a name="removetail"></a>  CAtlList::RemoveTail  
 リストの末尾にある要素を削除するには、このメソッドを呼び出します。  
  
```
E RemoveTail();
```  
  
### <a name="return-value"></a>戻り値  
 リストの末尾にある要素を返します。  
  
### <a name="remarks"></a>コメント  
 末尾の要素が、一覧から削除され、メモリが解放されます。 要素のコピーが返されます。 デバッグ ビルドでは、一覧が空の場合、アサーションの失敗が発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#29](../../atl/codesnippet/cpp/catllist-class_17.cpp)]  
  
##  <a name="removetailnoreturn"></a>  CAtlList::RemoveTailNoReturn  
 値を返さずに、リストの末尾にある要素を削除するには、このメソッドを呼び出します。  
  
```
void RemoveTailNoReturn() throw();
```  
  
### <a name="remarks"></a>コメント  
 末尾の要素が、一覧から削除され、メモリが解放されます。 デバッグ ビルドでは、一覧が空の場合、アサーションの失敗が発生します。  
  
### <a name="example"></a>例  
 例を参照して[CAtlList::IsEmpty](#isempty)です。  
  
##  <a name="setat"></a>  CAtlList::SetAt  
 リスト内の指定位置に要素の値を設定するには、このメソッドを呼び出します。  
  
```
void SetAt(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 変更する要素に対応する位置を表す値です。  
  
 `element`  
 新しい要素の値。  
  
### <a name="remarks"></a>コメント  
 既存の値と置き換えられます`element`です。 デバッグ ビルドで、アサーション エラーが発生場合`pos`が NULL です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#30](../../atl/codesnippet/cpp/catllist-class_18.cpp)]  
  
##  <a name="swapelements"></a>  CAtlList::SwapElements  
 リスト内の要素をスワップするには、このメソッドを呼び出します。  
  
```
void SwapElements(POSITION pos1, POSITION pos2) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pos1*  
 最初の位置の値。  
  
 *pos2*  
 2 番目の位置の値。  
  
### <a name="remarks"></a>コメント  
 指定された 2 つの位置にある要素を交換します。 デバッグ ビルドでは、位置のいずれかの値が null の場合、アサーションの失敗が発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#31](../../atl/codesnippet/cpp/catllist-class_19.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CList クラス](../../mfc/reference/clist-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
