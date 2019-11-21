---
title: allocator
ms.date: 03/21/2019
f1_keywords:
- allocator_cpp
helpviewer_keywords:
- __declspec keyword [C++], allocator
- allocator __declspec keyword
ms.openlocfilehash: f9c8de7c8686b89a2ab9570a2558e3f649e545b5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155239"
---
# <a name="allocator"></a>allocator

**Microsoft 固有の仕様**

**allocator**宣言指定子は、割り当てを使用して Event Tracing for Windows (ETW) 表示するカスタムのメモリ割り当て関数に適用できます。

## <a name="syntax"></a>構文

```
   __declspec(allocator) 
```

## <a name="remarks"></a>Remarks

Visual Studio でのネイティブ メモリ プロファイラーは、割り当て時に生成された ETW イベント データを収集して機能します。 CRT および Windows SDK のアロケーターには、割り当てデータをキャプチャできるように、ソース レベルで注釈が付けられています。 独自のアロケーターを作成するかどうかは、新しく割り当てられたヒープ メモリへのポインターを返す任意の関数で修飾できます`__declspec(allocator)`myMalloc のこの例で示すように、します。

```cpp
__declspec(allocator) void* myMalloc(size_t size)
```

詳細については、次を参照してください。 [Visual Studio でのメモリ使用量の測定](/visualstudio/profiling/memory-usage)と[カスタム ネイティブ ETW ヒープ イベント](/visualstudio/profiling/custom-native-etw-heap-events)します。