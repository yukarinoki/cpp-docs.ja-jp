---
description: '詳細情報: &lt; forward_list &gt; 関数'
title: '&lt;forward_list&gt; 系関数'
ms.date: 11/04/2016
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
ms.openlocfilehash: 3f827b777f2e6fa62dd78c7d737d5da84b50610c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324363"
---
# <a name="ltforward_listgt-functions"></a>&lt;forward_list&gt; 系関数

## <a name="swap"></a><a name="swap"></a> フォト

2 つの前方リストの要素を交換します。

```cpp
void swap(forward_list <Type, Allocator>& left, forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`forward_list` 型のオブジェクト。

*そうです*\
`forward_list` 型のオブジェクト。

### <a name="remarks"></a>解説

このテンプレート関数は、`left.swap(right)` を実行します。
