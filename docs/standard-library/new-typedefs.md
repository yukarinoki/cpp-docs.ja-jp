---
title: '&lt;new&gt; typedefs'
ms.date: 11/04/2016
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
ms.openlocfilehash: 80123bc35422984ef92bdba6da45052d3461b1d7
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78854941"
---
# <a name="ltnewgt-typedefs"></a>&lt;new&gt; typedefs

## <a name="hardware_constructive_interference_size"></a>hardware_constructive_interference_size

```cpp
inline constexpr size_t hardware_constructive_interference_size = implementation-defined;
```

### <a name="remarks"></a>コメント

この数は、同時実行スレッドによって一時的な近傍性を使用してアクセスされる2つのオブジェクトによって占有される連続メモリの最大推奨サイズです。 少なくとも `alignof(max_align_t)`である必要があります。

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

## <a name="hardware_destructive_interference_size"></a>hardware_destructive_interference_size

```cpp
inline constexpr size_t hardware_destructive_interference_size = implementation-defined;
```

### <a name="remarks"></a>コメント

この数値は、同時にアクセスされる2つのオブジェクト間の最小オフセットとして、実装によって発生する競合によるパフォーマンスの低下を回避するために推奨されます。 少なくとも `alignof(max_align_t)`である必要があります。

### <a name="example"></a>例

```cpp
struct keep_apart {
    alignas(hardware_destructive_interference_size) atomic<int> cat;
    alignas(hardware_destructive_interference_size) atomic<int> dog;
};
```

## <a name="new_handler"></a>new_handler

新しいハンドラーとして使用するのに適した関数を指す型。

```cpp
typedef void (*new_handler)();
```

### <a name="remarks"></a>コメント

この種類のハンドラー関数は、追加のストレージの要求を満たすことができない場合に、 **operator new**または `operator new[]` によって呼び出されます。

### <a name="example"></a>例

[ を戻り値として使用する例については、「](../standard-library/new-functions.md#set_new_handler)set_new_handler`new_handler`」をご覧ください。
