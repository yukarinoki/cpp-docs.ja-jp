---
title: '方法 : ポインターと配列を固定する'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- pointers, pinning
- arrays [C++], pinning
ms.assetid: ee783260-e676-46b8-a38e-11a06f1d57b0
ms.openlocfilehash: 54897253b93c97eb2d1ef94b6922c99fb75fdae9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641860"
---
# <a name="how-to-pin-pointers-and-arrays"></a>方法 : ポインターと配列を固定する

マネージ オブジェクトで定義されている下位のオブジェクトをピン留めすると、オブジェクト全体をピン留めの効果があります。  たとえば、配列の要素が固定されている場合、配列全体もピン留めされます。 固定配列を宣言するための言語拡張機能はありません。 配列をピン留めするには、その要素の型とその要素の 1 つに固定ポインターを宣言します。

## <a name="example"></a>例

### <a name="code"></a>コード

```cpp
// pin_ptr_array.cpp
// compile with: /clr
#include <stdio.h>
using namespace System;

int main() {
   array<Byte>^ arr = gcnew array<Byte>(4);
   arr[0] = 'C';
   arr[1] = '+';
   arr[2] = '+';
   arr[3] = '\0';
   pin_ptr<Byte> p = &arr[1];   // entire array is now pinned
   unsigned char * cp = p;

   printf_s("%s\n", cp); // bytes pointed at by cp
                         // will not move during call
}
```

```Output
++
```

## <a name="see-also"></a>関連項目

[pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)