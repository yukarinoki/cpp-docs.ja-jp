---
title: __ptr32、__ptr64
ms.date: 10/09/2018
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
- __ptr32
- __ptr64
- _ptr32
- _ptr64
helpviewer_keywords:
- __ptr64 keyword [C++]
- _ptr32 keyword [C++]
- ptr32 keyword [C++]
- ptr64 keyword [C++]
- _ptr64 keyword [C++]
- __ptr32 keyword [C++]
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
ms.openlocfilehash: 5ff2fa22c8a466252cfaf8b80dc8d56774aff58e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227154"
---
# <a name="__ptr32-__ptr64"></a>__ptr32、__ptr64

**Microsoft 固有の仕様**

**`__ptr32`** は、32ビットシステムのネイティブポインターを表しますが、は **`__ptr64`** 64 ビットシステムのネイティブポインターを表します。

次の例は、これらのポインター型のそれぞれを宣言する方法を示します。

```cpp
int * __ptr32 p32;
int * __ptr64 p64;
```

32ビットシステムでは、で宣言 **`__ptr64`** されたポインターは32ビットポインターに切り詰められます。 64ビットシステムでは、を使用して宣言 **`__ptr32`** されたポインターは、64ビットポインターに強制的に変換されます。

> [!NOTE]
> **`__ptr32`** **`__ptr64`** **/Clr: pure**を使用してコンパイルする場合、またはを使用することはできません。 それ以外の場合は、コンパイラエラー C2472 が生成されます。 **/Clr: pure**および **/clr: safe**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

以前のバージョンとの互換性を保つために、 **_ptr32**と **_ptr64**はのシノニムであり、 **`__ptr32`** コンパイラオプションである [ **`__ptr64`** [ \( 言語拡張機能を無効にする](../build/reference/za-ze-disable-language-extensions.md)] が指定されている場合を除きます。

## <a name="example"></a>例

次の例では、キーワードとキーワードを使用してポインターを宣言し、割り当てる方法を示し **`__ptr32`** **`__ptr64`** ます。

```cpp
#include <cstdlib>
#include <iostream>

int main()
{
    using namespace std;

    int * __ptr32 p32;
    int * __ptr64 p64;

    p32 = (int * __ptr32)malloc(4);
    *p32 = 32;
    cout << *p32 << endl;

    p64 = (int * __ptr64)malloc(4);
    *p64 = 64;
    cout << *p64 << endl;
}
```

```Output
32
64
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[組み込み型](../cpp/fundamental-types-cpp.md)
