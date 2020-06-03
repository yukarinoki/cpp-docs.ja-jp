---
title: クラス
ms.date: 09/07/2019
f1_keywords:
- CWordArray
- AFXCOLL/CWordArray
- AFXCOLL/CWordArray::CWordArray
- AFXCOLL/CWordArray::Add
- AFXCOLL/CWordArray::Append
- AFXCOLL/CWordArray::Copy
- AFXCOLL/CWordArray::ElementAt
- AFXCOLL/CWordArray::FreeExtra
- AFXCOLL/CWordArray::GetAt
- AFXCOLL/CWordArray::GetCount
- AFXCOLL/CWordArray::GetData
- AFXCOLL/CWordArray::GetSize
- AFXCOLL/CWordArray::GetUpperBound
- AFXCOLL/CWordArray::InsertAt
- AFXCOLL/CWordArray::IsEmpty
- AFXCOLL/CWordArray::RemoveAll
- AFXCOLL/CWordArray::RemoveAt
- AFXCOLL/CWordArray::SetAt
- AFXCOLL/CWordArray::SetAtGrow
- AFXCOLL/CWordArray::SetSize
helpviewer_keywords:
- CWordArray [MFC], CWordArray
- CWordArray [MFC], Add
- CWordArray [MFC], Append
- CWordArray [MFC], Copy
- CWordArray [MFC], ElementAt
- CWordArray [MFC], FreeExtra
- CWordArray [MFC], GetAt
- CWordArray [MFC], GetCount
- CWordArray [MFC], GetData
- CWordArray [MFC], GetSize
- CWordArray [MFC], GetUpperBound
- CWordArray [MFC], InsertAt
- CWordArray [MFC], IsEmpty
- CWordArray [MFC], RemoveAll
- CWordArray [MFC], RemoveAt
- CWordArray [MFC], SetAt
- CWordArray [MFC], SetAtGrow
- CWordArray [MFC], SetSize
ms.assetid: 2ba2c194-2c6c-40ff-9db4-e9dbe57e1f57
ms.openlocfilehash: 9dfb0b674d52b288ebd05bf7574f1ae05e4ed1f3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365908"
---
# <a name="cwordarray-class"></a>クラス

16 ビットのワードの配列をサポートします。

## <a name="syntax"></a>構文

```
class CWordArray : public CObject
```

## <a name="members"></a>メンバー

の`CWordArray`メンバー関数は、[クラス CObArray](../../mfc/reference/cobarray-class.md)のメンバー関数に似ています。 メンバー関数については `CObArray` クラスの説明を参照してください。 関数のパラメーターまたは戻り値として[CObject](../../mfc/reference/cobject-class.md)ポインターが表示される場所は、WORD を置き換えます。

`CObject* CObArray::GetAt( int <nIndex> ) const;`

たとえば、次のように変換します。

`WORD CWordArray::GetAt( int <nIndex> ) const;`

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[::Cワードアレイ](../../mfc/reference/cobarray-class.md#cobarray)|空の配列を生成します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を追加します。](../../mfc/reference/cobarray-class.md#add)|配列の末尾に要素を追加します。必要に応じて、配列を大きくします。|
|[を追加します。](../../mfc/reference/cobarray-class.md#append)|配列に別の配列を追加します。必要に応じて、配列を大きくします。|
|[::コピー](../../mfc/reference/cobarray-class.md#copy)|配列に別の配列をコピーします。必要に応じて、配列を大きくします。|
|[::要素](../../mfc/reference/cobarray-class.md#elementat)|配列内の要素ポインターへの一時的な参照を返します。|
|[::フリーエクストラ](../../mfc/reference/cobarray-class.md#freeextra)|現在の上限を超えている未使用のメモリをすべて解放します。|
|[::ゲットアット](../../mfc/reference/cobarray-class.md#getat)|指定されたインデックス位置にある値を返します。|
|[::カウントを取得します。](../../mfc/reference/cobarray-class.md#getcount)|この配列内の要素の数を取得します。|
|[::データを取得します。](../../mfc/reference/cobarray-class.md#getdata)|配列内の要素へのアクセスを許可します。 NULL にすることができます。|
|[::ゲットサイズ](../../mfc/reference/cobarray-class.md#getsize)|この配列内の要素の数を取得します。|
|[::ゲットアッパーバウンド](../../mfc/reference/cobarray-class.md#getupperbound)|有効な最大のインデックスを返します。|
|[::挿入](../../mfc/reference/cobarray-class.md#insertat)|指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。|
|[::空っぽ](../../mfc/reference/cobarray-class.md#isempty)|配列が空かどうかを判別します。|
|[::すべて削除](../../mfc/reference/cobarray-class.md#removeall)|この配列からすべての要素を削除します。|
|[::削除](../../mfc/reference/cobarray-class.md#removeat)|特定のインデックス位置にある要素を削除します。|
|[::セットアット](../../mfc/reference/cobarray-class.md#setat)|指定されたインデックスの値を設定します。配列は大きくできません。|
|[::セットアックグロー](../../mfc/reference/cobarray-class.md#setatgrow)|指定されたインデックスの値を設定します。必要に応じて、配列を大きくします。|
|[::セットサイズ](../../mfc/reference/cobarray-class.md#setsize)|この配列に含まれる要素の数を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[ &#91;&#93;演算子](../../mfc/reference/cobarray-class.md#operator_at)|指定されたインデックス位置にある要素を設定または取得します。|

## <a name="remarks"></a>解説

`CWordArray`IMPLEMENT_SERIAL[マクロを](run-time-object-model-services.md#implement_serial)組み込んで、シリアル化と要素のダンプをサポートします。 単語の配列が、オーバーロードされた挿入演算子または[CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)メンバー関数を使用してアーカイブに格納されている場合、各要素はシリアル化されます。

> [!NOTE]
> 配列を使用する前に、`SetSize` を使用してそのサイズを設定し、メモリを割り当てます。 `SetSize` を使用しない場合、配列に要素を追加すると、配列の再割り当てとコピーが頻繁に発生します。 頻繁な再割り当てとコピーは非効率であり、メモリが断片化される可能性があります。

配列内の個々の要素のダンプが必要な場合は、ダンプ コンテキストの深さを 1 以上に設定する必要があります。

の使用方法`CWordArray`の詳細については、[記事の「コレクション](../../mfc/collections.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CWordArray`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcoll.h

## <a name="see-also"></a>関連項目

[MFC サンプル コレクト](../../overview/visual-cpp-samples.md)<br/>
[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
