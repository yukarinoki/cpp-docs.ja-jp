---
title: CPtrList クラス
ms.date: 11/04/2016
f1_keywords:
- CPtrList
helpviewer_keywords:
- lists, generic
- CPtrList class [MFC]
- generic lists
ms.assetid: 4139a09c-4338-4f42-9eea-51336120b43c
ms.openlocfilehash: dfd545e1758ea257a89606655bf735829dbe8840
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586395"
---
# <a name="cptrlist-class"></a>CPtrList クラス

void ポインターのリストをサポートします。

## <a name="syntax"></a>構文

```
class CPtrList : public CObject
```

## <a name="members"></a>メンバー

メンバー関数は、`CPtrList`クラスのメンバー関数のような[CObList](../../mfc/reference/coblist-class.md)します。 メンバー関数については `CObList` クラスの説明を参照してください。 任意の場所が表示、`CObject`関数パラメーターまたは戻り値としてのポインターへのポインターを置き換える**void**します。

`CObject*& CObList::GetHead() const;`

たとえば、次のように変換します。

`void*& CPtrList::GetHead() const;`

## <a name="remarks"></a>Remarks

`CPtrList` 実行時の型へのアクセスとダンプをサポートするために IMPLEMENT_DYNAMIC マクロが組み込まれています、`CDumpContext`オブジェクト。 ポインター リストの各要素をダンプする必要があるときは、ダンプ コンテキストの深さを 1 以上に設定する必要があります。

ポインター リストはシリアル化できません。

`CPtrList` オブジェクトが削除されたとき、またはその要素が削除されたときは、ポインターだけが削除されます。ポインターが参照するエンティティは削除されません。

使用しての詳細については`CPtrList`、記事をご覧ください[コレクション](../../mfc/collections.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CPtrList`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcoll.h

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CObList クラス](../../mfc/reference/coblist-class.md)
