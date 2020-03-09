---
title: '&lt;list&gt; functions |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- list/std::swap
ms.openlocfilehash: 04f00a9274018432cd03917ae5485f2d395649e4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78874433"
---
# <a name="ltlistgt-functions"></a>&lt;list&gt; 関数

## <a name="swap"></a>フォト

2 つのリストの要素を交換します。

```cpp
template <class T, class Allocator>
    void swap(list<T, Allocator>& left, list<T, Allocator>& right)
```

### <a name="parameters"></a>パラメーター

*左*\
`list` 型オブジェクト。

*右*\
`list` 型オブジェクト。

### <a name="remarks"></a>コメント

このテンプレート関数は、`left.swap(right)` を実行します。
