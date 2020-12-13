---
description: '詳細情報: &lt; メモリ &gt; 列挙型'
title: '&lt;memory&gt; 列挙型'
ms.date: 11/04/2016
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
ms.openlocfilehash: da9bb22a6095f74b94e1745210fa55061ecf3c71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149098"
---
# <a name="ltmemorygt-enums"></a>&lt;memory&gt; 列挙型

## <a name="pointer_safety-enumeration"></a><a name="pointer_safety"></a> pointer_safety 列挙型

`get_pointer_safety` によって返される可能性がある値の列挙型です。

```cpp
class pointer_safety {
   relaxed,
   preferred,
   strict
};
```

### <a name="remarks"></a>解説

スコープには、 **`enum`** によって返される値が定義されてい `get_pointer_safety()` ます。

`relaxed` -- 安全に派生していないポインター (明らかに、宣言されたオブジェクトまたは割り当てられたオブジェクトへのポインター) が、安全に派生したポインターと同じように扱われます。

`preferred` -- 上と同様ですが、安全に派生していないポインターを逆参照することはできません。

`strict` -- 安全に派生していないポインターは、安全に派生したポインターとは異なる方法で扱われる場合があります。
