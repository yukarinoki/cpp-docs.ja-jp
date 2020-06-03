---
title: CStringList クラス
ms.date: 11/04/2016
f1_keywords:
- CStringList
- AFXCOLL/CStringList
- AFXCOLL/CStringList::CStringList
- AFXCOLL/CStringList::AddHead
- AFXCOLL/CStringList::AddTail
- AFXCOLL/CStringList::Find
- AFXCOLL/CStringList::FindIndex
- AFXCOLL/CStringList::GetAt
- AFXCOLL/CStringList::GetCount
- AFXCOLL/CStringList::GetHead
- AFXCOLL/CStringList::GetHeadPosition
- AFXCOLL/CStringList::GetNext
- AFXCOLL/CStringList::GetPrev
- AFXCOLL/CStringList::GetSize
- AFXCOLL/CStringList::GetTail
- AFXCOLL/CStringList::GetTailPosition
- AFXCOLL/CStringList::InsertAfter
- AFXCOLL/CStringList::InsertBefore
- AFXCOLL/CStringList::IsEmpty
- AFXCOLL/CStringList::RemoveAll
- AFXCOLL/CStringList::RemoveAt
- AFXCOLL/CStringList::RemoveHead
- AFXCOLL/CStringList::RemoveTail
- AFXCOLL/CStringList::SetAt
helpviewer_keywords:
- CStringList [MFC], CStringList
- CStringList [MFC], AddHead
- CStringList [MFC], AddTail
- CStringList [MFC], Find
- CStringList [MFC], FindIndex
- CStringList [MFC], GetAt
- CStringList [MFC], GetCount
- CStringList [MFC], GetHead
- CStringList [MFC], GetHeadPosition
- CStringList [MFC], GetNext
- CStringList [MFC], GetPrev
- CStringList [MFC], GetSize
- CStringList [MFC], GetTail
- CStringList [MFC], GetTailPosition
- CStringList [MFC], InsertAfter
- CStringList [MFC], InsertBefore
- CStringList [MFC], IsEmpty
- CStringList [MFC], RemoveAll
- CStringList [MFC], RemoveAt
- CStringList [MFC], RemoveHead
- CStringList [MFC], RemoveTail
- CStringList [MFC], SetAt
ms.assetid: 310a7edb-263c-4bd2-ac43-0bfbfddc5a33
ms.openlocfilehash: 9eb7a713fc02cd3e51135d1985a41688d4c885d9
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447548"
---
# <a name="cstringlist-class"></a>CStringList クラス

`CString` オブジェクトのリストをサポートします。

## <a name="syntax"></a>構文

```
class CStringList : public CObject
```

## <a name="members"></a>メンバー

`CStringList` のメンバー関数は、 [CObList](../../mfc/reference/coblist-class.md)クラスのメンバー関数に似ています。 メンバー関数については `CObList` クラスの説明を参照してください。 戻り値として `CObject` ポインターが表示されている場合は、`CString` (`CString` ポインターではない) に置き換えます。 関数パラメーターとして `CObject` ポインターが表示されている場合は、`LPCTSTR`を置き換えます。

`CObject*& CObList::GetHead() const;`

たとえば、次のように変換します。

`CString& CStringList::GetHead() const;`

and

`POSITION AddHead( CObject* <newElement> );`

次のように変換します。

`POSITION AddHead( LPCTSTR <newElement> );`

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|説明|
|----------|-----------------|
|[CStringList:: CStringList](../../mfc/reference/coblist-class.md#coblist)|空のリストを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[CStringList:: AddHead](../../mfc/reference/coblist-class.md#addhead)|要素 (または別のリスト内のすべての要素) をリストの先頭に追加します (新しい head を作成します)。|
|[CStringList:: AddTail](../../mfc/reference/coblist-class.md#addtail)|要素 (または別のリスト内のすべての要素) をリストの末尾に追加します (新しい末尾を作成します)。|
|[CStringList:: Find](../../mfc/reference/coblist-class.md#find)|ポインター値によって指定された要素の位置を取得します。|
|[CStringList:: FindIndex](../../mfc/reference/coblist-class.md#findindex)|0から始まるインデックスで指定された要素の位置を取得します。|
|[CStringList:: GetAt](../../mfc/reference/coblist-class.md#getat)|指定した位置にある要素を取得します。|
|[CStringList:: GetCount](../../mfc/reference/coblist-class.md#getcount)|このリスト内の要素の数を返します。|
|[CStringList:: GetHead](../../mfc/reference/coblist-class.md#gethead)|リストの head 要素を返します (空にすることはできません)。|
|[CStringList:: GetHeadPosition](../../mfc/reference/coblist-class.md#getheadposition)|リストの先頭の要素の位置を返します。|
|[CStringList:: GetNext](../../mfc/reference/coblist-class.md#getnext)|反復処理の対象となる次の要素を取得します。|
|[CStringList:: GetPrev](../../mfc/reference/coblist-class.md#getprev)|反復処理する前の要素を取得します。|
|[CStringList:: GetSize](../../mfc/reference/coblist-class.md#getsize)|このリスト内の要素の数を返します。|
|[CStringList:: GetTail](../../mfc/reference/coblist-class.md#gettail)|リストの末尾の要素を返します (空にすることはできません)。|
|[CStringList:: GetTailPosition](../../mfc/reference/coblist-class.md#gettailposition)|リストの末尾の要素の位置を返します。|
|[CStringList:: InsertAfter](../../mfc/reference/coblist-class.md#insertafter)|指定された位置の後に新しい要素を挿入します。|
|[CStringList:: InsertBefore](../../mfc/reference/coblist-class.md#insertbefore)|指定した位置の前に新しい要素を挿入します。|
|[CStringList:: IsEmpty](../../mfc/reference/coblist-class.md#isempty)|空のリスト条件 (要素なし) があるかどうかをテストします。|
|[CStringList:: RemoveAll](../../mfc/reference/coblist-class.md#removeall)|このリストからすべての要素を削除します。|
|[CStringList:: RemoveAt](../../mfc/reference/coblist-class.md#removeat)|位置によって指定された、このリストから要素を削除します。|
|[CStringList:: RemoveHead](../../mfc/reference/coblist-class.md#removehead)|リストの先頭から要素を削除します。|
|[CStringList:: RemoveTail](../../mfc/reference/coblist-class.md#removetail)|リストの末尾から要素を削除します。|
|[CStringList:: SetAt](../../mfc/reference/coblist-class.md#setat)|指定された位置に要素を設定します。|

## <a name="remarks"></a>コメント

すべての比較は値によって行われます。つまり、文字列のアドレスではなく、文字列の文字が比較されます。

`CStringList` には、要素のシリアル化とダンプをサポートするための IMPLEMENT_SERIAL マクロが組み込まれています。 オーバーロードされた挿入演算子または `Serialize` メンバー関数を使用して、`CString` オブジェクトの一覧がアーカイブに格納されている場合、各 `CString` 要素は順番にシリアル化されます。

個々の `CString` 要素のダンプが必要な場合は、ダンプコンテキストの深さを1以上に設定する必要があります。

`CStringList`の使用方法の詳細については、「[コレクション](../../mfc/collections.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CStringList`

## <a name="requirements"></a>要件

**ヘッダー:** afxcoll.h

## <a name="see-also"></a>参照

[MFC サンプル収集](../../overview/visual-cpp-samples.md)<br/>
[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
