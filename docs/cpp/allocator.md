---
title: allocator
ms.date: 03/21/2019
f1_keywords:
- allocator_cpp
helpviewer_keywords:
- __declspec keyword [C++], allocator
- allocator __declspec keyword
ms.openlocfilehash: 39708e8cfff7f61c3a3f763f87e1a3da36f0d4b1
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077257"
---
# <a name="allocator"></a>allocator

**Microsoft 固有の仕様**

**アロケーター**宣言指定子は、WINDOWS イベントトレーシング (ETW) を使用して割り当てを表示できるように、カスタムメモリ割り当て関数に適用できます。

## <a name="syntax"></a>構文

```
   __declspec(allocator)
```

## <a name="remarks"></a>解説

Visual Studio のネイティブメモリプロファイラーは、実行時にによって出力された割り当て ETW イベントデータを収集することによって機能します。 CRT および Windows SDK のアロケーターには、割り当てデータをキャプチャできるように、ソース レベルで注釈が付けられています。 独自のアロケーターを作成する場合、新しく割り当てられたヒープメモリへのポインターを返す関数は、次の myMalloc の例に示すように、`__declspec(allocator)`で修飾できます。

```cpp
__declspec(allocator) void* myMalloc(size_t size)
```

詳細については、「 [Visual Studio でのメモリ使用量の測定](/visualstudio/profiling/memory-usage)」と「[カスタムネイティブ ETW ヒープイベント](/visualstudio/profiling/custom-native-etw-heap-events)」を参照してください。

**Microsoft 固有の仕様はここまで**
