---
description: '詳細情報: CPtrList クラス'
title: CPtrList クラス
ms.date: 11/04/2016
f1_keywords:
- CPtrList
helpviewer_keywords:
- lists, generic
- CPtrList class [MFC]
- generic lists
ms.assetid: 4139a09c-4338-4f42-9eea-51336120b43c
ms.openlocfilehash: 27849db4687860ab68feb548de1ed8ad209b73a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343252"
---
# <a name="cptrlist-class"></a>CPtrList クラス

void ポインターのリストをサポートします。

## <a name="syntax"></a>構文

```
class CPtrList : public CObject
```

## <a name="members"></a>メンバー

のメンバー関数 `CPtrList` は、 [CObList](../../mfc/reference/coblist-class.md)クラスのメンバー関数に似ています。 メンバー関数については `CObList` クラスの説明を参照してください。 `CObject`関数パラメーターまたは戻り値としてポインターが表示されている場合は、へのポインターを置き換え **`void`** ます。

`CObject*& CObList::GetHead() const;`

たとえば、次のように変換します。

`void*& CPtrList::GetHead() const;`

## <a name="remarks"></a>解説

`CPtrList` には、実行時の型へのアクセスとオブジェクトへのダンプをサポートする IMPLEMENT_DYNAMIC マクロが組み込まれて `CDumpContext` います。 ポインター リストの各要素をダンプする必要があるときは、ダンプ コンテキストの深さを 1 以上に設定する必要があります。

ポインター リストはシリアル化できません。

`CPtrList` オブジェクトが削除されたとき、またはその要素が削除されたときは、ポインターだけが削除されます。ポインターが参照するエンティティは削除されません。

の使用方法の詳細については `CPtrList` 、「 [コレクション](../../mfc/collections.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CPtrList`

## <a name="requirements"></a>要件

**ヘッダー:** afxcoll.h

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CObList クラス](../../mfc/reference/coblist-class.md)
