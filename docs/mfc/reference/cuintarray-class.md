---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CUIntArray
- AFXCOLL/CUIntArray
- AFXCOLL/CUIntArray::CUIntArray
- AFXCOLL/CUIntArray::Add
- AFXCOLL/CUIntArray::Append
- AFXCOLL/CUIntArray::Copy
- AFXCOLL/CUIntArray::ElementAt
- AFXCOLL/CUIntArray::FreeExtra
- AFXCOLL/CUIntArray::GetAt
- AFXCOLL/CUIntArray::GetCount
- AFXCOLL/CUIntArray::GetData
- AFXCOLL/CUIntArray::GetSize
- AFXCOLL/CUIntArray::GetUpperBound
- AFXCOLL/CUIntArray::InsertAt
- AFXCOLL/CUIntArray::IsEmpty
- AFXCOLL/CUIntArray::RemoveAll
- AFXCOLL/CUIntArray::RemoveAt
- AFXCOLL/CUIntArray::SetAt
- AFXCOLL/CUIntArray::SetAtGrow
- AFXCOLL/CUIntArray::SetSize
helpviewer_keywords:
- CUIntArray [MFC], CUIntArray
- CUIntArray [MFC], Add
- CUIntArray [MFC], Append
- CUIntArray [MFC], Copy
- CUIntArray [MFC], ElementAt
- CUIntArray [MFC], FreeExtra
- CUIntArray [MFC], GetAt
- CUIntArray [MFC], GetCount
- CUIntArray [MFC], GetData
- CUIntArray [MFC], GetSize
- CUIntArray [MFC], GetUpperBound
- CUIntArray [MFC], InsertAt
- CUIntArray [MFC], IsEmpty
- CUIntArray [MFC], RemoveAll
- CUIntArray [MFC], RemoveAt
- CUIntArray [MFC], SetAt
- CUIntArray [MFC], SetAtGrow
- CUIntArray [MFC], SetSize
ms.assetid: d71f3d8f-ef9f-4e48-9b69-7782c0e2ddf7
ms.openlocfilehash: 9d620269bbf6695af992feaf0df2ef1161c9ae8f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373239"
---
# <a name="cuintarray-class"></a>クラス

符号なし整数の配列をサポートします。

## <a name="syntax"></a>構文

```
class CUIntArray : public CObject
```

## <a name="members"></a>メンバー

の`CUIntArray`メンバー関数は、[クラス CObArray](../../mfc/reference/cobarray-class.md)のメンバー関数に似ています。 メンバー関数については `CObArray` クラスの説明を参照してください。 ポインターが`CObject`関数パラメーターまたは戻り値として見える場所は、UINT に置き換えてください。

`CObject* CObArray::GetAt( int <nIndex> ) const;`

たとえば、次のように変換します。

`UINT CUIntArray::GetAt( int <nIndex> ) const;`

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[クインタアレイ::クインタアレイ](../../mfc/reference/cobarray-class.md#cobarray)|空の配列を生成します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[クイントアレイ::追加](../../mfc/reference/cobarray-class.md#add)|配列の末尾に要素を追加します。必要に応じて、配列を大きくします。|
|[クイント配列::追加](../../mfc/reference/cobarray-class.md#append)|配列に別の配列を追加します。必要に応じて、配列を大きくします。|
|[クインタアレイ::コピー](../../mfc/reference/cobarray-class.md#copy)|配列に別の配列をコピーします。必要に応じて、配列を大きくします。|
|[クイントアレイ::エレメントアット](../../mfc/reference/cobarray-class.md#elementat)|配列内の要素ポインターへの一時的な参照を返します。|
|[クインタアレイ::フリーエクストラ](../../mfc/reference/cobarray-class.md#freeextra)|現在の上限を超えている未使用のメモリをすべて解放します。|
|[クインタアレイ::ゲットアット](../../mfc/reference/cobarray-class.md#getat)|指定されたインデックス位置にある値を返します。|
|[クイントアレイ::ゲットカウント](../../mfc/reference/cobarray-class.md#getcount)|この配列内の要素の数を取得します。|
|[クイントアレイ::ゲットデータ](../../mfc/reference/cobarray-class.md#getdata)|配列内の要素へのアクセスを許可します。 NULL にすることができます。|
|[クイントアレイ::ゲットサイズ](../../mfc/reference/cobarray-class.md#getsize)|この配列内の要素の数を取得します。|
|[クイントアレイ::ゲットアッパーバウンド](../../mfc/reference/cobarray-class.md#getupperbound)|有効な最大のインデックスを返します。|
|[クインタ配列::挿入](../../mfc/reference/cobarray-class.md#insertat)|指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。|
|[クインタ配列::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|配列が空かどうかを判別します。|
|[クインタアレイ::すべて削除](../../mfc/reference/cobarray-class.md#removeall)|この配列からすべての要素を削除します。|
|[クインタアレイ::削除アット](../../mfc/reference/cobarray-class.md#removeat)|特定のインデックス位置にある要素を削除します。|
|[クインタアレイ::セットアット](../../mfc/reference/cobarray-class.md#setat)|指定されたインデックスの値を設定します。配列は大きくできません。|
|[クインタアレイ::セットアットグロー](../../mfc/reference/cobarray-class.md#setatgrow)|指定されたインデックスの値を設定します。必要に応じて、配列を大きくします。|
|[クイントアレイ::セットサイズ](../../mfc/reference/cobarray-class.md#setsize)|この配列に含まれる要素の数を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[キュイントアレイ::演算子\[\]](../../mfc/reference/cobarray-class.md#operator_at)|指定されたインデックス位置にある要素を設定または取得します。|

## <a name="remarks"></a>解説

符号なし整数(UINT)は、UINT の物理サイズがターゲットの動作環境によって変化する可能性があるという点で、単語やダブルワードとは異なります。 UINT はダブルワードと同じサイズです。

`CUIntArray`は、実行時型へのアクセスと[CDumpContext](../../mfc/reference/cdumpcontext-class.md)オブジェクトへのダンプをサポートする[IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)マクロを組み込んでいます。 符号なし整数要素のダンプが必要な場合は、ダンプ コンテキストの深さを 1 以上に設定する必要があります。 符号なし整数配列はシリアル化できません。

> [!NOTE]
> 配列を使用する前に、`SetSize` を使用してそのサイズを設定し、メモリを割り当てます。 `SetSize` を使用しない場合、配列に要素を追加すると、配列の再割り当てとコピーが頻繁に発生します。 頻繁な再割り当てとコピーは非効率であり、メモリが断片化される可能性があります。

の使用方法`CUIntArray`の詳細については、[記事の「コレクション](../../mfc/collections.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CUIntArray`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcoll.h

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
