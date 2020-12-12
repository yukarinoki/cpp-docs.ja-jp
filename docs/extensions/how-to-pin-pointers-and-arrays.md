---
description: '詳細については、「方法: ポインターと配列を固定する」を参照してください。'
title: '方法 : ポインターと配列を固定する'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- pointers, pinning
- arrays [C++], pinning
ms.assetid: ee783260-e676-46b8-a38e-11a06f1d57b0
ms.openlocfilehash: ab0e09e94c45cc31862ef8d0b6c0771bfeae115d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119136"
---
# <a name="how-to-pin-pointers-and-arrays"></a>方法 : ポインターと配列を固定する

マネージ オブジェクトに定義されているサブオブジェクトの固定には、オブジェクト全体を固定するという効果があります。  たとえば、配列の要素が固定されている場合、配列全体も固定されます。 固定された配列を宣言するための言語の拡張機能はありません。 配列を固定するには、その要素の型に対して固定ポインターを宣言し、要素の 1 つを固定します。

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

[pin_ptr (C++/CLI)](pin-ptr-cpp-cli.md)
