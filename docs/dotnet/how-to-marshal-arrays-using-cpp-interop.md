---
title: '方法: C++ Interop を使用して配列をマーシャリングする'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- arrays [C++], marshaling
- marshaling [C++], arrays
- interop [C++], arrays
- C++ Interop, arrays
- data marshaling [C++], arrays
ms.assetid: c2b37ab1-8acf-4855-ad3c-7d2864826b14
ms.openlocfilehash: 0ccf71d40db0bc6989620d2ca126ce74311805da
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413828"
---
# <a name="how-to-marshal-arrays-using-c-interop"></a>方法: C++ Interop を使用して配列をマーシャリングする

このトピックでは、Visual C++ 相互運用性の1つのファセットについて説明します。 詳細については、「 [C++ Interop の使用 (暗黙的な PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)」を参照してください。

次のコード例では、マネージ [、アン](../preprocessor/managed-unmanaged.md) マネージ #pragma ディレクティブを使用して、マネージ関数とアンマネージ関数を同じファイルに実装しますが、これらの関数は、別々のファイルで定義されている場合と同じ方法で相互運用します。 アンマネージ関数のみを含むファイルを [/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)でコンパイルする必要はありません。

## <a name="example-pass-managed-array-to-unmanaged-function"></a>例: マネージ配列をアンマネージ関数に渡す

マネージ配列をアンマネージ関数に渡す方法を次の例に示します。 マネージ関数は、 [pin_ptr (C++/cli)](../extensions/pin-ptr-cpp-cli.md) を使用して、アンマネージ関数を呼び出す前に配列のガベージコレクションを抑制します。 アンマネージ関数に、固定されたポインターを GC ヒープに提供することにより、配列のコピーを作成する際のオーバーヘッドを回避できます。 アンマネージ関数が GC ヒープメモリにアクセスしていることを示すために、配列の内容を変更し、マネージ関数が制御を再開すると変更が反映されます。

```cpp
// PassArray1.cpp
// compile with: /clr
#ifndef _CRT_RAND_S
#define _CRT_RAND_S
#endif

#include <iostream>
#include <stdlib.h>
using namespace std;

using namespace System;

#pragma unmanaged

void TakesAnArray(int* a, int c) {
   cout << "(unmanaged) array received:\n";
   for (int i=0; i<c; i++)
      cout << "a[" << i << "] = " << a[i] << "\n";

   unsigned int number;
   errno_t err;

   cout << "(unmanaged) modifying array contents...\n";
   for (int i=0; i<c; i++) {
      err = rand_s( &number );
      if ( err == 0 )
         a[i] = number % 100;
   }
}

#pragma managed

int main() {
   array<int>^ nums = gcnew array<int>(5);

   nums[0] = 0;
   nums[1] = 1;
   nums[2] = 2;
   nums[3] = 3;
   nums[4] = 4;

   Console::WriteLine("(managed) array created:");
   for (int i=0; i<5; i++)
      Console::WriteLine("a[{0}] = {1}", i, nums[i]);

   pin_ptr<int> pp = &nums[0];
   TakesAnArray(pp, 5);

   Console::WriteLine("(managed) contents:");
   for (int i=0; i<5; i++)
      Console::WriteLine("a[{0}] = {1}", i, nums[i]);
}
```

## <a name="example-pass-unmanaged-array-to-managed-function"></a>例: アンマネージ配列をマネージ関数に渡す

次の例では、アンマネージ配列をマネージ関数に渡す方法を示します。 マネージ関数は、マネージ配列を作成して配列の内容をコピーするのではなく、配列のメモリに直接アクセスします。これにより、マネージ関数によって行われた変更を、制御を取り戻すときにアンマネージ関数に反映させることができます。

```cpp
// PassArray2.cpp
// compile with: /clr
#include <iostream>
using namespace std;

using namespace System;

#pragma managed

void ManagedTakesAnArray(int* a, int c) {
   Console::WriteLine("(managed) array received:");
   for (int i=0; i<c; i++)
      Console::WriteLine("a[{0}] = {1}", i, a[i]);

   cout << "(managed) modifying array contents...\n";
   Random^ r = gcnew Random(DateTime::Now.Second);
   for (int i=0; i<c; i++)
      a[i] = r->Next(100);
}

#pragma unmanaged

void NativeFunc() {
   int nums[5] = { 0, 1, 2, 3, 4 };

   printf_s("(unmanaged) array created:\n");
   for (int i=0; i<5; i++)
      printf_s("a[%d] = %d\n", i, nums[i]);

   ManagedTakesAnArray(nums, 5);

   printf_s("(ummanaged) contents:\n");
   for (int i=0; i<5; i++)
      printf_s("a[%d] = %d\n", i, nums[i]);
}

#pragma managed

int main() {
   NativeFunc();
}
```

## <a name="see-also"></a>関連項目

[C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)
