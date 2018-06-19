---
title: CTypedPtrList クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTypedPtrList
- AFXTEMPL/CTypedPtrList
- AFXTEMPL/CTypedPtrList::AddHead
- AFXTEMPL/CTypedPtrList::AddTail
- AFXTEMPL/CTypedPtrList::GetAt
- AFXTEMPL/CTypedPtrList::GetHead
- AFXTEMPL/CTypedPtrList::GetNext
- AFXTEMPL/CTypedPtrList::GetPrev
- AFXTEMPL/CTypedPtrList::GetTail
- AFXTEMPL/CTypedPtrList::RemoveHead
- AFXTEMPL/CTypedPtrList::RemoveTail
- AFXTEMPL/CTypedPtrList::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CTypedPtrList [MFC], AddHead
- CTypedPtrList [MFC], AddTail
- CTypedPtrList [MFC], GetAt
- CTypedPtrList [MFC], GetHead
- CTypedPtrList [MFC], GetNext
- CTypedPtrList [MFC], GetPrev
- CTypedPtrList [MFC], GetTail
- CTypedPtrList [MFC], RemoveHead
- CTypedPtrList [MFC], RemoveTail
- CTypedPtrList [MFC], SetAt
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: afb32a662c538526c4fe26f6abf46e56a42de728
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374589"
---
# <a name="ctypedptrlist-class"></a>CTypedPtrList クラス
`CPtrList`クラスのオブジェクトに対してタイプ セーフな "ラップ" が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
template<class BASE_CLASS, class TYPE>  
class CTypedPtrList : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>パラメーター  
 `BASE_CLASS`  
 クラスの基本クラス、型付きポインター リストです。ポインター リストのクラスにする必要があります (`CObList`または`CPtrList`)。  
  
 `TYPE`  
 基底クラス リストに格納されている要素の型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTypedPtrList::AddHead](#addhead)|(新しいヘッドにより) リストの先頭に要素 (または別のリスト内のすべての要素) を追加します。|  
|[CTypedPtrList::AddTail](#addtail)|(新しい末尾になります)、リストの末尾に要素 (または別のリスト内のすべての要素) を追加します。|  
|[CTypedPtrList::GetAt](#getat)|指定された位置に要素を取得します。|  
|[CTypedPtrList::GetHead](#gethead)|(空にすることはできません)、リストの先頭の要素を返します。|  
|[CTypedPtrList::GetNext](#getnext)|反復処理するためには、次の要素を取得します。|  
|[CTypedPtrList::GetPrev](#getprev)|反復処理するためには、直前の要素を取得します。|  
|[CTypedPtrList::GetTail](#gettail)|(空にすることはできません)、リストの末尾の要素を返します。|  
|[CTypedPtrList::RemoveHead](#removehead)|リストの先頭から要素を削除します。|  
|[CTypedPtrList::RemoveTail](#removetail)|リストの末尾から要素を削除します。|  
|[CTypedPtrList::SetAt](#setat)|指定された位置に要素を設定します。|  
  
## <a name="remarks"></a>コメント  
 使用すると`CTypedPtrList`なく`CObList`または`CPtrList`C++ の型チェック機能は、一致していないポインター型によって発生したエラーを解消します。  
  
 さらに、`CTypedPtrList`ラッパーを使用した場合に必要になるキャストの多くを実行します`CObList`または`CPtrList`です。  
  
 すべて`CTypedPtrList`関数はインラインでこのテンプレートの使用が大幅には影響しません、コードの速度またはサイズ。  
  
 派生したリスト`CObList`から派生したものですが、シリアル化できる`CPtrList`ことはできません。  
  
 `CTypedPtrList` オブジェクトが削除されたとき、またはその要素が削除されたときは、ポインターだけが削除されます。ポインターが参照するエンティティは削除されません。  
  
 使用する方法についての`CTypedPtrList`、記事を参照して[コレクション](../../mfc/collections.md)と[テンプレート ベースのクラス](../../mfc/template-based-classes.md)です。  
  
## <a name="example"></a>例  
 この例のインスタンスを作成する`CTypedPtrList`、1 つのオブジェクトを追加、ディスクの一覧をシリアル化およびオブジェクトを削除します。  
  
 [!code-cpp[NVC_MFCCollections#110](../../mfc/codesnippet/cpp/ctypedptrlist-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCCollections#111](../../mfc/codesnippet/cpp/ctypedptrlist-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `BASE_CLASS`  
  
 `_CTypedPtrList`  
  
 `CTypedPtrList`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtempl.h  
  
##  <a name="addhead"></a>  CTypedPtrList::AddHead  
 このメンバー関数が呼び出す`BASE_CLASS` **:: AddHead**です。  
  
```  
POSITION AddHead(TYPE newElement);  
void AddHead(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 基底クラス リストに格納されている要素の型。  
  
 `newElement`  
 この一覧に追加するオブジェクトのポインター。 A **NULL**値は許可します。  
  
 `BASE_CLASS`  
 クラスの基本クラス、型付きポインター リストです。ポインター リストのクラスにする必要があります ( [CObList](../../mfc/reference/coblist-class.md)または[CPtrList](../../mfc/reference/cptrlist-class.md))。  
  
 `pNewList`  
 別のポインター [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md)オブジェクト。 内の要素`pNewList`この一覧に追加されます。  
  
### <a name="return-value"></a>戻り値  
 最初のバージョンを返します、**位置**は新しく挿入される要素の値。  
  
### <a name="remarks"></a>コメント  
 最初のバージョンでは、リストの先頭の前に新しい要素を追加します。 2 番目のバージョンでは、先頭の前に要素の別のリストを追加します。  
  
##  <a name="addtail"></a>  CTypedPtrList::AddTail  
 このメンバー関数が呼び出す`BASE_CLASS` **:: AddTail**です。  
  
```  
POSITION AddTail(TYPE newElement);  
void AddTail(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 基底クラス リストに格納されている要素の型。  
  
 `newElement`  
 この一覧に追加するオブジェクトのポインター。 A **NULL**値は許可します。  
  
 `BASE_CLASS`  
 クラスの基本クラス、型付きポインター リストです。ポインター リストのクラスにする必要があります ( [CObList](../../mfc/reference/coblist-class.md)または[CPtrList](../../mfc/reference/cptrlist-class.md))。  
  
 `pNewList`  
 別のポインター [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md)オブジェクト。 内の要素`pNewList`この一覧に追加されます。  
  
### <a name="return-value"></a>戻り値  
 最初のバージョンを返します、**位置**は新しく挿入される要素の値。  
  
### <a name="remarks"></a>コメント  
 最初のバージョンでは、リストの末尾の後に新しい要素を追加します。 2 番目のバージョンでは、リストの末尾の後に要素の別のリストを追加します。  
  
##  <a name="getat"></a>  CTypedPtrList::GetAt  
 型の変数**位置**はリストのキーです。  
  
```  
TYPE& GetAt(POSITION position);  
TYPE GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 一覧に格納されている要素の型を指定するテンプレート パラメーター。  
  
 *位置*  
 A**位置**によって以前返される値`GetHeadPosition`または**検索**メンバー関数の呼び出しです。  
  
### <a name="return-value"></a>戻り値  
 リストへのポインターを介してアクセスする場合、 **const CTypedPtrList**、し`GetAt`テンプレート パラメーターによって指定された型のポインターを返します*型*です。 これにより、関数は、代入ステートメントの右側にあるでのみ使用し、したがって変更から一覧を保護できます。  
  
 一覧には直接にも、ポインターを介してアクセスする場合、 `CTypedPtrList`、し`GetAt`テンプレート パラメーターで指定された型のポインターへの参照を返します*型*です。 これは、関数は、代入ステートメントのどちらにも使用して、できるので、一覧のエントリを変更します。  
  
### <a name="remarks"></a>コメント  
 インデックスと同じではなく、操作することはできません、**位置**自分での値します。 `GetAt` 取得、`CObject`指定した位置に関連付けられたポインター。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 このインライン関数が呼び出す`BASE_CLASS` **:: GetAt**です。  
  
##  <a name="gethead"></a>  CTypedPtrList::GetHead  
 この一覧の先頭の要素を表すポインターを取得します。  
  
```  
TYPE& GetHead();  
TYPE GetHead() const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 一覧に格納されている要素の型を指定するテンプレート パラメーター。  
  
### <a name="return-value"></a>戻り値  
 リストへのポインターを介してアクセスする場合、 **const CTypedPtrList**、し`GetHead`テンプレート パラメーターによって指定された型のポインターを返します*型*です。 これにより、関数は、代入ステートメントの右側にあるでのみ使用し、したがって変更から一覧を保護できます。  
  
 一覧には直接にも、ポインターを介してアクセスする場合、 `CTypedPtrList`、し`GetHead`テンプレート パラメーターで指定された型のポインターへの参照を返します*型*です。 これは、関数は、代入ステートメントのどちらにも使用して、できるので、一覧のエントリを変更します。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`GetHead`です。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンをアサートします。 使用して[IsEmpty](../../mfc/reference/coblist-class.md#isempty)リストに要素が含まれていることを確認します。  
  
##  <a name="getnext"></a>  CTypedPtrList::GetNext  
 によって識別される要素を取得`rPosition`を設定し、`rPosition`を**位置**一覧の次のエントリの値。  
  
```  
TYPE& GetNext(POSITION& rPosition);  
TYPE GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 この一覧に含まれる要素の型を指定するテンプレート パラメーター。  
  
 `rPosition`  
 参照、**位置**によって以前返される値`GetNext`、 `GetHeadPosition`、またはその他のメンバー関数の呼び出しです。  
  
### <a name="return-value"></a>戻り値  
 リストへのポインターを介してアクセスする場合、 **const CTypedPtrList**、し`GetNext`テンプレート パラメーターによって指定された型のポインターを返します*型*です。 これにより、関数は、代入ステートメントの右側にあるでのみ使用し、したがって変更から一覧を保護できます。  
  
 一覧には直接にも、ポインターを介してアクセスする場合、 `CTypedPtrList`、し`GetNext`テンプレート パラメーターで指定された型のポインターへの参照を返します*型*です。 これは、関数は、代入ステートメントのどちらにも使用して、できるので、一覧のエントリを変更します。  
  
### <a name="remarks"></a>コメント  
 使用することができます`GetNext`への呼び出しに最初の位置を確立する場合は、順方向の反復ループで`GetHeadPosition`または[CPtrList::Find](../../mfc/reference/coblist-class.md#find)です。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 場合は、取得した最後の要素を一覧での新しい値`rPosition`に設定されている**NULL**です。  
  
 反復処理中に要素を削除することができます。 例を参照して[CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat)です。  
  
##  <a name="getprev"></a>  CTypedPtrList::GetPrev  
 要素を取得します ボックスの一覧によって識別される`rPosition`を設定し、`rPosition`を**位置**一覧の前のエントリの値。  
  
```  
TYPE& GetPrev(POSITION& rPosition);  
TYPE GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 この一覧に含まれる要素の型を指定するテンプレート パラメーター。  
  
 `rPosition`  
 参照、**位置**によって以前返される値`GetPrev`またはその他のメンバー関数の呼び出しです。  
  
### <a name="return-value"></a>戻り値  
 リストへのポインターを介してアクセスする場合、 **const CTypedPtrList**、し`GetPrev`テンプレート パラメーターによって指定された型のポインターを返します*型*です。 これにより、関数は、代入ステートメントの右側にあるでのみ使用し、したがって変更から一覧を保護できます。  
  
 一覧には直接にも、ポインターを介してアクセスする場合、 `CTypedPtrList`、し`GetPrev`テンプレート パラメーターで指定された型のポインターへの参照を返します*型*です。 これは、関数は、代入ステートメントのどちらにも使用して、できるので、一覧のエントリを変更します。  
  
### <a name="remarks"></a>コメント  
 使用することができます`GetPrev`への呼び出しに最初の位置を確立する場合は、反転反復ループで`GetTailPosition`または**検索**です。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 取得される要素が一覧で、最初、新しい値の`rPosition`に設定されている**NULL**です。  
  
##  <a name="gettail"></a>  CTypedPtrList::GetTail  
 この一覧の先頭の要素を表すポインターを取得します。  
  
```  
TYPE& GetTail();  
TYPE GetTail() const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 一覧に格納されている要素の型を指定するテンプレート パラメーター。  
  
### <a name="return-value"></a>戻り値  
 リストへのポインターを介してアクセスする場合、 **const CTypedPtrList**、し`GetTail`テンプレート パラメーターによって指定された型のポインターを返します*型*です。 これにより、関数は、代入ステートメントの右側にあるでのみ使用し、したがって変更から一覧を保護できます。  
  
 一覧には直接にも、ポインターを介してアクセスする場合、 `CTypedPtrList`、し`GetTail`テンプレート パラメーターで指定された型のポインターへの参照を返します*型*です。 これは、関数は、代入ステートメントのどちらにも使用して、できるので、一覧のエントリを変更します。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`GetTail`です。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンをアサートします。 使用して[IsEmpty](../../mfc/reference/coblist-class.md#isempty)リストに要素が含まれていることを確認します。  
  
##  <a name="removehead"></a>  CTypedPtrList::RemoveHead  
 リストの先頭から要素を削除し、それを取得します。  
  
```  
TYPE RemoveHead();
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 一覧に格納されている要素の型を指定するテンプレート パラメーター。  
  
### <a name="return-value"></a>戻り値  
 リストの先頭にあったのポインター。 このポインターは、テンプレート パラメーターで指定された型*型*です。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`RemoveHead`です。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンをアサートします。 使用して[IsEmpty](../../mfc/reference/coblist-class.md#isempty)リストに要素が含まれていることを確認します。  
  
##  <a name="removetail"></a>  CTypedPtrList::RemoveTail  
 リストの末尾から要素を削除し、それを取得します。  
  
```  
TYPE RemoveTail();
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 一覧に格納されている要素の型を指定するテンプレート パラメーター。  
  
### <a name="return-value"></a>戻り値  
 リストの末尾にあったのポインター。 このポインターは、テンプレート パラメーターで指定された型*型*です。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`RemoveTail`です。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンをアサートします。 使用して[IsEmpty](../../mfc/reference/coblist-class.md#isempty)リストに要素が含まれていることを確認します。  
  
##  <a name="setat"></a>  CTypedPtrList::SetAt  
 このメンバー関数が呼び出す`BASE_CLASS` **:: SetAt**です。  
  
```  
void SetAt(POSITION pos, TYPE newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 **位置**を設定する要素のです。  
  
 *TYPE*  
 基底クラス リストに格納されている要素の型。  
  
 `newElement`  
 一覧に書き込まれるオブジェクトのポインター。  
  
### <a name="remarks"></a>コメント  
 型の変数**位置**はリストのキーです。 インデックスと同じではなく、操作することはできません、**位置**自分での値します。 `SetAt` オブジェクトへのポインターを一覧内の指定位置に書き込みます。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 詳細についてを参照してください。 [CObList::SetAt](../../mfc/reference/coblist-class.md#setat)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの収集](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPtrList クラス](../../mfc/reference/cptrlist-class.md)   
 [CObList クラス](../../mfc/reference/coblist-class.md)
