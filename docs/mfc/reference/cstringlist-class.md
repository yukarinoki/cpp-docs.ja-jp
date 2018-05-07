---
title: CStringList クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStringList
- AFXCOLL/CStringList
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
ms.assetid: 310a7edb-263c-4bd2-ac43-0bfbfddc5a33
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 91a88fc73b27323327bce477fa2cdaca747ed21c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cstringlist-class"></a>CStringList クラス
`CString` オブジェクトのリストをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CStringList : public CObject  
```  
  
## <a name="members"></a>メンバー  
 メンバー関数は、`CStringList`クラスのメンバー関数に似ています[CObList](../../mfc/reference/coblist-class.md)です。 メンバー関数については `CObList` クラスの説明を参照してください。 任意の場所が表示、`CObject`ポインターとして戻り値に置き換える、 `CString` (されません、`CString`ポインター)。 任意の場所が表示、`CObject`ポインター、関数パラメーターとして代わり、`LPCTSTR`です。  
  
 `CObject*& CObList::GetHead() const;`  
  
 たとえば、次のように変換します。  
  
 `CString& CStringList::GetHead() const;`  
  
 および  
  
 `POSITION AddHead( CObject* <newElement> );`  
  
 次のように変換します。  
  
 `POSITION AddHead( LPCTSTR <newElement> );`  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[使われて](../../mfc/reference/coblist-class.md#coblist)|空のリストを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CObList::AddHead](../../mfc/reference/coblist-class.md#addhead)|(新しいヘッドにより) リストの先頭に要素 (または別のリスト内のすべての要素) を追加します。|  
|[CObList::AddTail](../../mfc/reference/coblist-class.md#addtail)|(新しい末尾になります)、リストの末尾に要素 (または別のリスト内のすべての要素) を追加します。|  
|[CObList::Find](../../mfc/reference/coblist-class.md#find)|ポインター値で指定された要素の位置を取得します。|  
|[CObList::FindIndex](../../mfc/reference/coblist-class.md#findindex)|0 から始まるインデックスによって指定された要素の位置を取得します。|  
|[CObList::GetAt](../../mfc/reference/coblist-class.md#getat)|指定された位置に要素を取得します。|  
|[CObList::GetCount](../../mfc/reference/coblist-class.md#getcount)|この一覧にある要素の数を返します。|  
|[CObList::GetHead](../../mfc/reference/coblist-class.md#gethead)|(空にすることはできません)、リストの先頭の要素を返します。|  
|[CObList::GetHeadPosition](../../mfc/reference/coblist-class.md#getheadposition)|リストの先頭の要素の位置を返します。|  
|[CObList::GetNext](../../mfc/reference/coblist-class.md#getnext)|反復処理するためには、次の要素を取得します。|  
|[CObList::GetPrev](../../mfc/reference/coblist-class.md#getprev)|反復処理するためには、直前の要素を取得します。|  
|[CObList::GetSize](../../mfc/reference/coblist-class.md#getsize)|この一覧にある要素の数を返します。|  
|[CObList::GetTail](../../mfc/reference/coblist-class.md#gettail)|(空にすることはできません)、リストの末尾の要素を返します。|  
|[CObList::GetTailPosition](../../mfc/reference/coblist-class.md#gettailposition)|リストの末尾の要素の位置を返します。|  
|[CObList::InsertAfter](../../mfc/reference/coblist-class.md#insertafter)|指定した位置の後に新しい要素を挿入します。|  
|[CObList::InsertBefore](../../mfc/reference/coblist-class.md#insertbefore)|指定した位置の前に新しい要素を挿入します。|  
|[CObList::IsEmpty](../../mfc/reference/coblist-class.md#isempty)|空のリストの条件 (要素がない) をテストします。|  
|[CObList::RemoveAll](../../mfc/reference/coblist-class.md#removeall)|このリストからすべての要素を削除します。|  
|[CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat)|この一覧から、位置によって指定された要素を削除します。|  
|[CObList::RemoveHead](../../mfc/reference/coblist-class.md#removehead)|リストの先頭から要素を削除します。|  
|[CObList::RemoveTail](../../mfc/reference/coblist-class.md#removetail)|リストの末尾から要素を削除します。|  
|[CObList::SetAt](../../mfc/reference/coblist-class.md#setat)|指定された位置に要素を設定します。|  
  
## <a name="remarks"></a>コメント  
 すべての比較は、値、つまり、文字列のアドレスではなく、文字列内の文字を比較することによって実行されます。  
  
 `CStringList` には、`IMPLEMENT_SERIAL` マクロが組み込まれており、その要素のシリアル化とダンプがサポートされます。 リストの場合`CString`オブジェクトが格納されているか、オーバー ロードされた挿入演算子のいずれか、アーカイブ、`Serialize`メンバー関数は、各`CString`要素はさらにシリアル化します。  
  
 個別にダンプする必要がある場合`CString`要素、1 以上、ダンプ コンテキストの深さを設定する必要があります。  
  
 使用する方法についての`CStringList`、記事を参照して[コレクション](../../mfc/collections.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CStringList`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcoll.h  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの収集](../../visual-cpp-samples.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



