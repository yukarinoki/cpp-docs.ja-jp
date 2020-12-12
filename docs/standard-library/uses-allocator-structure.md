---
description: '詳細情報: uses_allocator 構造'
title: uses_allocator 構造体
ms.date: 11/04/2016
f1_keywords:
- future/std::uses_allocator
ms.assetid: c418f002-62e9-4806-b70c-41c663cae583
ms.openlocfilehash: 3ece99d12443af2ec28b52e2a0dae72d8af4cc91
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153617"
---
# <a name="uses_allocator-structure"></a>uses_allocator 構造体

常に true を保持する特殊化です。

## <a name="syntax"></a>構文

```cpp
template <class Ty, class Alloc>
struct uses_allocator<promise<Ty>, Alloc> : true_type;
template <class Ty, class Alloc>
struct uses_allocator<packaged_task<Ty>, Alloc> : true_type;
```

## <a name="requirements"></a>必要条件

**ヘッダー:**\<future>

**名前空間:** std

## <a name="specializations"></a>特殊化

### <a name="tuple"></a><a name="tuple"></a> \<tuple>

```cpp
template <class... Types, class Alloc>
struct uses_allocator<tuple<Types...>, Alloc>;
```

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[\<future>](../standard-library/future.md)
