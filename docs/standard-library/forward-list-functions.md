---
title: '&lt;forward_list&gt; 系関数'
ms.date: 11/04/2016
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
ms.openlocfilehash: b425461f1428470b04a525efdd9a702ae038a283
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159835"
---
# <a name="ltforwardlistgt-functions"></a>&lt;forward_list&gt; 系関数

||
|-|
|[swap](#swap)|

## <a name="swap"></a>  swap

2 つの前方リストの要素を交換します。

```cpp
void swap(
    forward_list <Type, Allocator>& left,
    forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*left*|`forward_list` 型のオブジェクト。|
|*right*|`forward_list` 型のオブジェクト。|

### <a name="remarks"></a>Remarks

このテンプレート関数は、`left.swap(right)` を実行します。

## <a name="see-also"></a>関連項目

[<forward_list>](../standard-library/forward-list.md)<br/>
