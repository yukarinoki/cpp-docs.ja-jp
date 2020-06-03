---
title: CDWordArray クラス
ms.date: 11/04/2016
f1_keywords:
- CDWordArray
- AFXCOLL/CDWordArray
- AFXCOLL/CDWordArray::CDWordArray
- AFXCOLL/CDWordArray::Add
- AFXCOLL/CDWordArray::Append
- AFXCOLL/CDWordArray::Copy
- AFXCOLL/CDWordArray::ElementAt
- AFXCOLL/CDWordArray::FreeExtra
- AFXCOLL/CDWordArray::GetAt
- AFXCOLL/CDWordArray::GetCount
- AFXCOLL/CDWordArray::GetData
- AFXCOLL/CDWordArray::GetSize
- AFXCOLL/CDWordArray::GetUpperBound
- AFXCOLL/CDWordArray::InsertAt
- AFXCOLL/CDWordArray::IsEmpty
- AFXCOLL/CDWordArray::RemoveAll
- AFXCOLL/CDWordArray::RemoveAt
- AFXCOLL/CDWordArray::SetAt
- AFXCOLL/CDWordArray::SetAtGrow
- AFXCOLL/CDWordArray::SetSize
helpviewer_keywords:
- CDWordArray [MFC], CDWordArray
- CDWordArray [MFC], Add
- CDWordArray [MFC], Append
- CDWordArray [MFC], Copy
- CDWordArray [MFC], ElementAt
- CDWordArray [MFC], FreeExtra
- CDWordArray [MFC], GetAt
- CDWordArray [MFC], GetCount
- CDWordArray [MFC], GetData
- CDWordArray [MFC], GetSize
- CDWordArray [MFC], GetUpperBound
- CDWordArray [MFC], InsertAt
- CDWordArray [MFC], IsEmpty
- CDWordArray [MFC], RemoveAll
- CDWordArray [MFC], RemoveAt
- CDWordArray [MFC], SetAt
- CDWordArray [MFC], SetAtGrow
- CDWordArray [MFC], SetSize
ms.assetid: 581be11e-ced6-47d1-8679-e0b8e7d99494
ms.openlocfilehash: e009ca3e3612d10d9cdf62d4bea32224f7b7522c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373995"
---
# <a name="cdwordarray-class"></a>CDWordArray クラス

32 ビットのダブルワードの配列をサポートします。

## <a name="syntax"></a>構文

```
class CDWordArray : public CObject
```

## <a name="members"></a>メンバー

の`CDWordArray`メンバー関数は、[クラス CObArray](../../mfc/reference/cobarray-class.md)のメンバー関数に似ています。 メンバー関数については `CObArray` クラスの説明を参照してください。 ポインターが`CObject`関数パラメーターまたは戻り値として見える場所はどこでも、`DWORD`を置き換えます。

`CObject* CObArray::GetAt( int <nIndex> ) const;`

たとえば、次のように変換します。

`DWORD CDWordArray::GetAt( int <nIndex> ) const;`

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[次の文字列を使用します。](../../mfc/reference/cobarray-class.md#cobarray)|空の配列を生成します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を追加します。](../../mfc/reference/cobarray-class.md#add)|配列の末尾に要素を追加します。必要に応じて、配列を大きくします。|
|[を追加します。](../../mfc/reference/cobarray-class.md#append)|配列に別の配列を追加します。必要に応じて、配列を大きくします。|
|[コピー](../../mfc/reference/cobarray-class.md#copy)|配列に別の配列をコピーします。必要に応じて、配列を大きくします。|
|[要素配列::要素](../../mfc/reference/cobarray-class.md#elementat)|配列内のバイトへの一時的な参照を返します。|
|[キーフリーアレイ::フリーエクストラ](../../mfc/reference/cobarray-class.md#freeextra)|現在の上限を超えている未使用のメモリをすべて解放します。|
|[をクリックします。](../../mfc/reference/cobarray-class.md#getat)|指定されたインデックス位置にある値を返します。|
|[を見る](../../mfc/reference/cobarray-class.md#getcount)|この配列内の要素の数を取得します。|
|[を取得します。](../../mfc/reference/cobarray-class.md#getdata)|配列内の要素へのアクセスを許可します。 NULL にすることができます。|
|[次の文字列を使用します。](../../mfc/reference/cobarray-class.md#getsize)|この配列内の要素の数を取得します。|
|[を指定します。](../../mfc/reference/cobarray-class.md#getupperbound)|有効な最大のインデックスを返します。|
|[を挿入します。](../../mfc/reference/cobarray-class.md#insertat)|指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。|
|[を指定します。](../../mfc/reference/cobarray-class.md#isempty)|配列が空かどうかを判別します。|
|[すべてを削除します。](../../mfc/reference/cobarray-class.md#removeall)|この配列からすべての要素を削除します。|
|[をクリックします。](../../mfc/reference/cobarray-class.md#removeat)|特定のインデックス位置にある要素を削除します。|
|[セットアレー::セットアット](../../mfc/reference/cobarray-class.md#setat)|指定されたインデックスの値を設定します。配列は大きくできません。|
|[を組み込む](../../mfc/reference/cobarray-class.md#setatgrow)|指定されたインデックスの値を設定します。必要に応じて、配列を大きくします。|
|[を指定します。](../../mfc/reference/cobarray-class.md#setsize)|この配列に含まれる要素の数を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[演算子\[\]](../../mfc/reference/cobarray-class.md#operator_at)|指定されたインデックス位置にある要素を設定または取得します。|

## <a name="remarks"></a>解説

`CDWordArray` には、`IMPLEMENT_SERIAL` マクロが組み込まれており、その要素のシリアル化とダンプがサポートされます。 倍精度浮動小数点数型の配列が、オーバーロードされた挿入 ( **<<**) 演算子または`Serialize`メンバー関数を使用してアーカイブに格納される場合、各要素はシリアル化されます。

> [!NOTE]
> 配列を使用する前に、`SetSize` を使用してそのサイズを設定し、メモリを割り当てます。 `SetSize` を使用しない場合、配列に要素を追加すると、配列の再割り当てとコピーが頻繁に発生します。 頻繁な再割り当てとコピーは非効率であり、メモリが断片化される可能性があります。

配列内の個々の要素からのデバッグ出力が必要な場合は、`CDumpContext`オブジェクトの深さを 1 以上に設定する必要があります。

の使用方法`CDWordArray`の詳細については、[記事の「コレクション](../../mfc/collections.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcoll.h

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CObArray クラス](../../mfc/reference/cobarray-class.md)
