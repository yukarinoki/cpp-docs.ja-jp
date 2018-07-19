---
title: '&lt;forward_list&gt; 系関数 | Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
ms.openlocfilehash: 097dca5d26014696e218ff6439b81e1d0349b2c5
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966320"
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
