---
description: '詳細情報: `allocator`'
title: allocator
ms.date: 03/21/2019
f1_keywords:
- allocator_cpp
helpviewer_keywords:
- __declspec keyword [C++], allocator
- allocator __declspec keyword
ms.openlocfilehash: 20ca879259c49f01f5283a867b4e562cfddcc058
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288270"
---
# `allocator`

**Microsoft 固有の仕様**

**`allocator`** 宣言指定子は、Windows イベントトレーシング (ETW) を使用して割り当てを表示できるように、カスタムメモリ割り当て関数に適用できます。

## <a name="syntax"></a>構文

> **`__declspec(allocator)`**

## <a name="remarks"></a>解説

Visual Studio のネイティブメモリプロファイラーは、実行時にによって出力された割り当て ETW イベントデータを収集することによって機能します。 CRT および Windows SDK のアロケーターには、割り当てデータをキャプチャできるように、ソース レベルで注釈が付けられています。 独自のアロケーターを作成する場合、新しく割り当てられたヒープメモリへのポインターを返す関数は、次の `__declspec(allocator)` myMalloc の例に示すように、で修飾できます。

```cpp
__declspec(allocator) void* myMalloc(size_t size)
```

詳細については、「 [Visual Studio でのメモリ使用量の測定](/visualstudio/profiling/memory-usage) 」と「 [カスタムネイティブ ETW ヒープイベント](/visualstudio/profiling/custom-native-etw-heap-events)」を参照してください。

**Microsoft 固有の仕様はここまで**
