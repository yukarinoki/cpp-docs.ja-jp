---
title: CStringArray クラス
ms.date: 11/04/2016
f1_keywords:
- CStringArray
- AFXCOLL/CStringArray
- AFXCOLL/CStringArray::CStringArray
- AFXCOLL/CStringArray::Add
- AFXCOLL/CStringArray::Append
- AFXCOLL/CStringArray::Copy
- AFXCOLL/CStringArray::ElementAt
- AFXCOLL/CStringArray::FreeExtra
- AFXCOLL/CStringArray::GetAt
- AFXCOLL/CStringArray::GetCount
- AFXCOLL/CStringArray::GetData
- AFXCOLL/CStringArray::GetSize
- AFXCOLL/CStringArray::GetUpperBound
- AFXCOLL/CStringArray::InsertAt
- AFXCOLL/CStringArray::IsEmpty
- AFXCOLL/CStringArray::RemoveAll
- AFXCOLL/CStringArray::RemoveAt
- AFXCOLL/CStringArray::SetAt
- AFXCOLL/CStringArray::SetAtGrow
- AFXCOLL/CStringArray::SetSize
helpviewer_keywords:
- CStringArray [MFC], CStringArray
- CStringArray [MFC], Add
- CStringArray [MFC], Append
- CStringArray [MFC], Copy
- CStringArray [MFC], ElementAt
- CStringArray [MFC], FreeExtra
- CStringArray [MFC], GetAt
- CStringArray [MFC], GetCount
- CStringArray [MFC], GetData
- CStringArray [MFC], GetSize
- CStringArray [MFC], GetUpperBound
- CStringArray [MFC], InsertAt
- CStringArray [MFC], IsEmpty
- CStringArray [MFC], RemoveAll
- CStringArray [MFC], RemoveAt
- CStringArray [MFC], SetAt
- CStringArray [MFC], SetAtGrow
- CStringArray [MFC], SetSize
ms.assetid: 6c637e06-bba8-4c08-b0fc-cf8cb067ce34
ms.openlocfilehash: 96a272cbbb76b399ed7a3db6848ab3f74a615a38
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365988"
---
# <a name="cstringarray-class"></a>CStringArray クラス

[CString](../../atl-mfc-shared/using-cstring.md)オブジェクトの配列をサポートします。

## <a name="syntax"></a>構文

```
class CStringArray : public CObject
```

## <a name="members"></a>メンバー

の`CStringArray`メンバー関数は、[クラス CObArray](../../mfc/reference/cobarray-class.md)のメンバー関数に似ています。 メンバー関数については `CObArray` クラスの説明を参照してください。 ポインターが`CObject`戻り値として見える場所は[、CString オブジェクト (CString](../../atl-mfc-shared/using-cstring.md)ポインターではなく) に置き換えます。 [CString](../../atl-mfc-shared/using-cstring.md) 関数パラメーターとして `CObject` ポインターが使われている場合は、`LPCTSTR` に置き換えます。

`CObject* CObArray::GetAt( int <nIndex> ) const;`

たとえば、次のように変換します。

`CString CStringArray::GetAt( int <nIndex> ) const;`

and

`void SetAt( int <nIndex>, CObject* <newElement> )`

次のように変換します。

`void SetAt( int <nIndex>, LPCTSTR <newElement> )`

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[次の文字列配列を返します。](../../mfc/reference/cobarray-class.md#cobarray)|空の配列を生成します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[次の文字列配列::追加](../../mfc/reference/cobarray-class.md#add)|配列の末尾に要素を追加します。必要に応じて、配列を大きくします。|
|[次の文字列配列::追加](../../mfc/reference/cobarray-class.md#append)|配列に別の配列を追加します。必要に応じて、配列を大きくします。|
|[次の文字列配列::コピー](../../mfc/reference/cobarray-class.md#copy)|配列に別の配列をコピーします。必要に応じて、配列を大きくします。|
|[要素配列::要素](../../mfc/reference/cobarray-class.md#elementat)|配列内の要素ポインターへの一時的な参照を返します。|
|[Cストリングアレイ::フリーエクストラ](../../mfc/reference/cobarray-class.md#freeextra)|現在の上限を超えている未使用のメモリをすべて解放します。|
|[次の文字列配列::ゲットアット](../../mfc/reference/cobarray-class.md#getat)|指定されたインデックス位置にある値を返します。|
|[次の文字列を返します。](../../mfc/reference/cobarray-class.md#getcount)|この配列内の要素の数を取得します。|
|[次の文字列を取得します。](../../mfc/reference/cobarray-class.md#getdata)|配列内の要素へのアクセスを許可します。 **NULL**を指定できます。|
|[次の文字列を配列します。](../../mfc/reference/cobarray-class.md#getsize)|この配列内の要素の数を取得します。|
|[を返す配列::取得します。](../../mfc/reference/cobarray-class.md#getupperbound)|有効な最大のインデックスを返します。|
|[次の文字列配列::挿入](../../mfc/reference/cobarray-class.md#insertat)|指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。|
|[次の文字列を配列します。](../../mfc/reference/cobarray-class.md#isempty)|配列が空かどうかを判別します。|
|[すべてを削除します。](../../mfc/reference/cobarray-class.md#removeall)|この配列からすべての要素を削除します。|
|[次の文字列を返します。](../../mfc/reference/cobarray-class.md#removeat)|特定のインデックス位置にある要素を削除します。|
|[文字列配列::セットアット](../../mfc/reference/cobarray-class.md#setat)|指定されたインデックスの値を設定します。配列は大きくできません。|
|[次の文字列配列::セットアックグロー](../../mfc/reference/cobarray-class.md#setatgrow)|指定されたインデックスの値を設定します。必要に応じて、配列を大きくします。|
|[次の文字列配列::セットサイズ](../../mfc/reference/cobarray-class.md#setsize)|この配列に含まれる要素の数を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[次の操作を行います\[。\]](../../mfc/reference/cobarray-class.md#operator_at)|指定されたインデックス位置にある要素を設定または取得します。|

## <a name="remarks"></a>解説

`CStringArray`IMPLEMENT_SERIAL マクロを組み込んで、シリアル化と要素のダンプをサポートします。 `CString` オブジェクトの配列がアーカイブに格納される場合、オーバーロードされた挿入演算子または `Serialize` メンバー関数によって、各要素は順にシリアル化されます。

> [!NOTE]
> 配列を使用する前に、`SetSize` を使用してそのサイズを設定し、メモリを割り当てます。 `SetSize` を使用しない場合、配列に要素を追加すると、配列の再割り当てとコピーが頻繁に発生します。 頻繁な再割り当てとコピーは非効率であり、メモリが断片化される可能性があります。

配列内の個別の文字列要素をダンプする必要があるときは、ダンプ コンテキストの深さを 1 以上に設定する必要があります。

`CString` 配列が削除されたとき、またはその要素が削除されたときは、文字列メモリは状況に応じて解放されます。

の使用方法`CStringArray`の詳細については、[記事の「コレクション](../../mfc/collections.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CStringArray`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcoll.h

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
