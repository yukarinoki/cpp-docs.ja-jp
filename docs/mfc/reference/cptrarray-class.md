---
title: CPtrArray クラス
ms.date: 11/04/2016
f1_keywords:
- CPtrArray
- AFXCOLL/CPtrArray
- AFXCOLL/CPtrArray::CPtrArray
- AFXCOLL/CPtrArray::Add
- AFXCOLL/CPtrArray::Append
- AFXCOLL/CPtrArray::Copy
- AFXCOLL/CPtrArray::ElementAt
- AFXCOLL/CPtrArray::FreeExtra
- AFXCOLL/CPtrArray::GetAt
- AFXCOLL/CPtrArray::GetCount
- AFXCOLL/CPtrArray::GetData
- AFXCOLL/CPtrArray::GetSize
- AFXCOLL/CPtrArray::GetUpperBound
- AFXCOLL/CPtrArray::InsertAt
- AFXCOLL/CPtrArray::IsEmpty
- AFXCOLL/CPtrArray::RemoveAll
- AFXCOLL/CPtrArray::RemoveAt
- AFXCOLL/CPtrArray::SetAt
- AFXCOLL/CPtrArray::SetAtGrow
- AFXCOLL/CPtrArray::SetSize
helpviewer_keywords:
- CPtrArray [MFC], CPtrArray
- CPtrArray [MFC], Add
- CPtrArray [MFC], Append
- CPtrArray [MFC], Copy
- CPtrArray [MFC], ElementAt
- CPtrArray [MFC], FreeExtra
- CPtrArray [MFC], GetAt
- CPtrArray [MFC], GetCount
- CPtrArray [MFC], GetData
- CPtrArray [MFC], GetSize
- CPtrArray [MFC], GetUpperBound
- CPtrArray [MFC], InsertAt
- CPtrArray [MFC], IsEmpty
- CPtrArray [MFC], RemoveAll
- CPtrArray [MFC], RemoveAt
- CPtrArray [MFC], SetAt
- CPtrArray [MFC], SetAtGrow
- CPtrArray [MFC], SetSize
ms.assetid: c23b87a3-bf84-49d6-a66b-61e999d0938a
ms.openlocfilehash: 7bab68fcbd2cfa4cfe44b0fcd2a1f78af886533d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363967"
---
# <a name="cptrarray-class"></a>CPtrArray クラス

void ポインターの配列をサポートします。

## <a name="syntax"></a>構文

```
class CPtrArray : public CObject
```

## <a name="members"></a>メンバー

の`CPtrArray`メンバー関数は、[クラス CObArray](../../mfc/reference/cobarray-class.md)のメンバー関数に似ています。 メンバー関数については `CObArray` クラスの説明を参照してください。 関数のパラメーターまたは`CObject`戻り値としてポインターを見る場合は、任意の場所**で void**へのポインターを置き換えます。

`CObject* CObArray::GetAt( int <nIndex> ) const;`

たとえば、次のように変換します。

`void* CPtrArray::GetAt( int <nIndex> ) const;`

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[次の値を指定します。](../../mfc/reference/cobarray-class.md#cobarray)|空の配列を生成します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[次の値を指定します。](../../mfc/reference/cobarray-class.md#add)|配列の末尾に要素を追加します。必要に応じて、配列を大きくします。|
|[次の値を指定します。](../../mfc/reference/cobarray-class.md#append)|配列に別の配列を追加します。必要に応じて、配列を大きくします。|
|[CPtr配列::コピー](../../mfc/reference/cobarray-class.md#copy)|配列に別の配列をコピーします。必要に応じて、配列を大きくします。|
|[要素配列::要素](../../mfc/reference/cobarray-class.md#elementat)|配列内の要素ポインターへの一時的な参照を返します。|
|[CPtrアレイ::フリーエクストラ](../../mfc/reference/cobarray-class.md#freeextra)|現在の上限を超えている未使用のメモリをすべて解放します。|
|[次の値を指定します。](../../mfc/reference/cobarray-class.md#getat)|指定されたインデックス位置にある値を返します。|
|[次の値を指定します。](../../mfc/reference/cobarray-class.md#getcount)|この配列内の要素の数を取得します。|
|[次の値を取得します。](../../mfc/reference/cobarray-class.md#getdata)|配列内の要素へのアクセスを許可します。 `NULL` を指定できます。|
|[次の値を指定します。](../../mfc/reference/cobarray-class.md#getsize)|この配列内の要素の数を取得します。|
|[を指定します。](../../mfc/reference/cobarray-class.md#getupperbound)|有効な最大のインデックスを返します。|
|[次の操作を行います。](../../mfc/reference/cobarray-class.md#insertat)|指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。|
|[次の値を指定します。](../../mfc/reference/cobarray-class.md#isempty)|配列が空かどうかを判別します。|
|[すべてを削除します。](../../mfc/reference/cobarray-class.md#removeall)|この配列からすべての要素を削除します。|
|[::削除アック](../../mfc/reference/cobarray-class.md#removeat)|特定のインデックス位置にある要素を削除します。|
|[CPtrアレイ::セットアット](../../mfc/reference/cobarray-class.md#setat)|指定されたインデックスの値を設定します。配列は大きくできません。|
|[CPtrArray::セットアックグロー](../../mfc/reference/cobarray-class.md#setatgrow)|指定されたインデックスの値を設定します。必要に応じて、配列を大きくします。|
|[次の値を指定します。](../../mfc/reference/cobarray-class.md#setsize)|この配列に含まれる要素の数を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[\[演算子\]](../../mfc/reference/cobarray-class.md#operator_at)|指定されたインデックス位置にある要素を設定または取得します。|

## <a name="remarks"></a>解説

`CPtrArray`は、実行時型へのアクセスとオブジェクトへのダンプをサポートするIMPLEMENT_DYNAMIC マクロを`CDumpContext`組み込んでいます。 ポインター配列の要素を個別にダンプする必要がある場合は、ダンプ コンテキストの深さを 1 以上に設定する必要があります。

> [!NOTE]
> 配列を使用する前に、`SetSize` を使用してそのサイズを設定し、メモリを割り当てます。 `SetSize` を使用しない場合、配列に要素を追加すると、配列の再割り当てとコピーが頻繁に発生します。 頻繁な再割り当てとコピーは非効率であり、メモリが断片化される可能性があります。

ポインター配列をシリアル化できません。

ポインター配列が削除された場合、または要素が削除されると、ポインターだけが削除され、ポインターが参照するエンティティは削除されません。

の使用方法`CPtrArray`の詳細については、[記事の「コレクション](../../mfc/collections.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CPtrArray`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcoll.h

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CObArray クラス](../../mfc/reference/cobarray-class.md)
