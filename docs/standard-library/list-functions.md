---
description: '詳細情報: &lt; list &gt; 関数'
title: '&lt;list &gt; 関数 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- list/std::swap
ms.openlocfilehash: 6a94fcc916db08a510a968b66b0a0dc0cfa9b8e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284708"
---
# <a name="ltlistgt-functions"></a>&lt;関数の一覧表示 &gt;

## <a name="swap"></a><a name="swap"></a> フォト

2 つのリストの要素を交換します。

```cpp
template <class T, class Allocator>
    void swap(list<T, Allocator>& left, list<T, Allocator>& right)
```

### <a name="parameters"></a>パラメーター

*左側*\
`list` 型のオブジェクト。

*そうです*\
`list` 型のオブジェクト。

### <a name="remarks"></a>解説

このテンプレート関数は、`left.swap(right)` を実行します。
