---
title: __sptr、__uptr
ms.date: 10/10/2018
f1_keywords:
- __uptr_cpp
- __sptr_cpp
- __uptr
- __sptr
- _uptr
- _sptr
helpviewer_keywords:
- __sptr modifier
- __uptr modifier
ms.assetid: c7f5f3b2-9106-4a0b-a6de-d1588ab153ed
ms.openlocfilehash: 5aac130073a635d0bc5f537aff75c526a9f086c2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225840"
---
# <a name="__sptr-__uptr"></a>__sptr、__uptr

**Microsoft 固有の仕様**

**`__sptr`** 32 ビットポインター宣言では、または修飾子を使用して、 **`__uptr`** コンパイラが32ビットポインターを64ビットポインターに変換する方法を指定します。 たとえば、32 ビット ポインターが 64 ビット ポインター変数に割り当てられたときや、64 ビット プラットフォーム上で 32 ビット ポインターが逆参照される場合などに変換が必要になります。

64 ビット プラットフォームをサポートする Microsoft のドキュメントでは、32 ビット ポインターの最上位ビットを符号ビットと呼んでいる場合があります。 既定では、コンパイラは符号拡張を使用して 32 ビット ポインターを 64 ビット ポインターに変換します。 つまり、64 ビット ポインターの下位 32 ビットに 32 ビット ポインターの値が設定され、上位 32 ビットに 32 ビット ポインターの符号ビットの値が設定されます。 符号ビットが 0 の場合はこの変換で正しい結果が得られますが、符号ビットが 1 の場合は正しい結果が得られません。 たとえば、32 ビット アドレス 0x7FFFFFFF はこれと同等の 64 ビットアドレス 0x000000007FFFFFFF になりますが、32 ビット アドレス 0x80000000 は誤って 0xFFFFFFFF80000000 に変換されます。

、 **`__sptr`** 、または符号付きポインターの修飾子は、ポインター変換によって64ビットポインターの最上位ビットが32ビットポインターの符号ビットに設定されることを指定します。 **`__uptr`**、、または符号なしポインターは、変換によって最上位ビットがゼロに設定されることを指定します。 次の宣言は、 **`__sptr`** **`__uptr`** 2 つの非修飾ポインター、 [__ptr32](../cpp/ptr32-ptr64.md)型で修飾された2つのポインター、および関数パラメーターで使用されると修飾子を示しています。

```cpp
int * __sptr psp;
int * __uptr pup;
int * __ptr32 __sptr psp32;
int * __ptr32 __uptr pup32;
void MyFunction(char * __uptr __ptr32 myValue);
```

**`__sptr`** ポインター宣言では、および修飾子を使用し **`__uptr`** ます。 [ポインター型修飾子](../c-language/pointer-declarations.md)の位置で修飾子を使用します。これは、修飾子がアスタリスクの後に続く必要があることを意味します。 修飾子を[メンバーへのポインター](../cpp/pointers-to-members.md)と共に使用することはできません。 これらの修飾子は、ポインター以外の宣言には影響を与えません。

以前のバージョンとの互換性を保つために、 **_sptr**と **_uptr**はのシノニムであり、 **`__sptr`** コンパイラオプションである [ **`__uptr`** [ \( 言語拡張機能を無効にする](../build/reference/za-ze-disable-language-extensions.md)] が指定されている場合を除きます。

## <a name="example"></a>例

次の例では、および修飾子を使用する32ビットポインターを宣言し **`__sptr`** **`__uptr`** 、各32ビットポインターを64ビットポインター変数に割り当てて、各64ビットポインターの16進数の値を表示します。 この例はネイティブの 64 ビット コンパイラでコンパイルされ、64 ビット プラットフォームで実行されます。

```cpp
// sptr_uptr.cpp
// processor: x64
#include "stdio.h"

int main()
{
    void *        __ptr64 p64;
    void *        __ptr32 p32d; //default signed pointer
    void * __sptr __ptr32 p32s; //explicit signed pointer
    void * __uptr __ptr32 p32u; //explicit unsigned pointer

// Set the 32-bit pointers to a value whose sign bit is 1.
    p32d = reinterpret_cast<void *>(0x87654321);
    p32s = p32d;
    p32u = p32d;

// The printf() function automatically displays leading zeroes with each 32-bit pointer. These are unrelated
// to the __sptr and __uptr modifiers.
    printf("Display each 32-bit pointer (as an unsigned 64-bit pointer):\n");
    printf("p32d:       %p\n", p32d);
    printf("p32s:       %p\n", p32s);
    printf("p32u:       %p\n", p32u);

    printf("\nDisplay the 64-bit pointer created from each 32-bit pointer:\n");
    p64 = p32d;
    printf("p32d: p64 = %p\n", p64);
    p64 = p32s;
    printf("p32s: p64 = %p\n", p64);
    p64 = p32u;
    printf("p32u: p64 = %p\n", p64);
    return 0;
}
```

```Output
Display each 32-bit pointer (as an unsigned 64-bit pointer):
p32d:       0000000087654321
p32s:       0000000087654321
p32u:       0000000087654321

Display the 64-bit pointer created from each 32-bit pointer:
p32d: p64 = FFFFFFFF87654321
p32s: p64 = FFFFFFFF87654321
p32u: p64 = 0000000087654321
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[Microsoft 固有の修飾子](../cpp/microsoft-specific-modifiers.md)
