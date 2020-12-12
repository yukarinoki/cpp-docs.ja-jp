---
description: 詳細については、「 &lt; 新しい typedef」を参照してください。 &gt;
title: '&lt;new&gt; typedefs'
ms.date: 11/04/2016
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
ms.openlocfilehash: 0c8e73f10b8429d2c55805c017dded98843af9f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338158"
---
# <a name="ltnewgt-typedefs"></a>&lt;new&gt; typedefs

## <a name="hardware_constructive_interference_size"></a><a name="hardware_constructive_interference_size"></a> hardware_constructive_interference_size

```cpp
inline constexpr size_t hardware_constructive_interference_size = implementation-defined;
```

### <a name="remarks"></a>解説

この数は、同時実行スレッドによって一時的な近傍性を使用してアクセスされる2つのオブジェクトによって占有される連続メモリの最大推奨サイズです。 少なくともである必要があり `alignof(max_align_t)` ます。

### <a name="example"></a>例

```cpp
struct together {
    atomic<int> dog;
    int puppy;
};

struct kennel {
    // Other data members...
    alignas(sizeof(together)) together pack;
    // Other data members...
};

static_assert(sizeof(together) <= hardware_constructive_interference_size);
```

## <a name="hardware_destructive_interference_size"></a><a name="hardware_destructive_interference_size"></a> hardware_destructive_interference_size

```cpp
inline constexpr size_t hardware_destructive_interference_size = implementation-defined;
```

### <a name="remarks"></a>解説

この数値は、同時にアクセスされる2つのオブジェクト間の最小オフセットとして、実装によって発生する競合によるパフォーマンスの低下を回避するために推奨されます。 少なくともである必要があり `alignof(max_align_t)` ます。

### <a name="example"></a>例

```cpp
struct keep_apart {
    alignas(hardware_destructive_interference_size) atomic<int> cat;
    alignas(hardware_destructive_interference_size) atomic<int> dog;
};
```

## <a name="new_handler"></a><a name="new_handler"></a> new_handler

新しいハンドラーとして使用するのに適した関数を指す型。

```cpp
typedef void (*new_handler)();
```

### <a name="remarks"></a>解説

この種類のハンドラー関数は、 **operator new** または `operator new[]` 追加のストレージの要求を満たすことができない場合に呼び出されます。

### <a name="example"></a>例

`new_handler` を戻り値として使用する例については、「[set_new_handler](../standard-library/new-functions.md#set_new_handler)」をご覧ください。
