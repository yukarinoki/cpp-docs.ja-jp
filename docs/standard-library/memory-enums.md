---
title: '&lt;memory&gt; 列挙型'
ms.date: 11/04/2016
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
ms.openlocfilehash: b2f5b50dc1344b95e88742d346e32fc55f821336
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68243849"
---
# <a name="ltmemorygt-enums"></a>&lt;memory&gt; 列挙型

## <a name="pointer_safety"></a> pointer_safety 列挙型

`get_pointer_safety` によって返される可能性がある値の列挙型です。

```
class pointer_safety {
   relaxed,
   preferred,
   strict
};
```

### <a name="remarks"></a>Remarks

スコープを持つ**enum**によって返される値を定義します`get_pointer_safety()`:

`relaxed` -- 安全に派生していないポインター (明らかに、宣言されたオブジェクトまたは割り当てられたオブジェクトへのポインター) が、安全に派生したポインターと同じように扱われます。

`preferred` -- 上と同様ですが、安全に派生していないポインターを逆参照することはできません。

`strict` -- 安全に派生していないポインターは、安全に派生したポインターとは異なる方法で扱われる場合があります。
