---
title: 定義と宣言 (C++)
ms.date: 11/04/2016
ms.assetid: 56b809c0-e602-4f18-9ca5-cd7a8fbaaf30
ms.openlocfilehash: c35c0adaa1b81e5bf9bfd9e779037bc6068b3174
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221706"
---
# <a name="definitions-and-declarations-c"></a>定義と宣言 (C++)

**Microsoft 固有の仕様**

DLL インターフェイスは、システム内の何らかのプログラムによってエクスポートされることがわかっているすべての項目 (関数とデータ) を参照します。つまり、またはとして宣言されているすべての項目です **`dllimport`** **`dllexport`** 。 DLL インターフェイスに含まれるすべての宣言では、 **`dllimport`** 属性または属性のいずれかを指定する必要があり **`dllexport`** ます。 ただし、定義では属性のみを指定する必要があり **`dllexport`** ます。 たとえば、次の関数定義はコンパイラ エラーになります。

```
__declspec( dllimport ) int func() {   // Error; dllimport
                                       // prohibited on definition.
   return 1;
}
```

次のコードでも、エラーが生成します。

```
__declspec( dllimport ) int i = 10;  // Error; this is a definition.
```

ただし、次に示す構文は、正しい構文です。

```
__declspec( dllexport ) int i = 10;  // Okay--export definition
```

の使用は **`dllexport`** 定義を意味し、は **`dllimport`** 宣言を意味します。 宣言を強制するには、キーワードを使用する必要があります。 **`extern`** **`dllexport`** それ以外の場合は、定義が暗黙的に指定されます。 そのため、次の例は正しいコードになります。

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

extern DllExport int k; // These are both correct and imply a
DllImport int j;        // declaration.
```

次の例に、上記の例をさらに明確に示します。

```
static __declspec( dllimport ) int l; // Error; not declared extern.

void func() {
    static __declspec( dllimport ) int s;  // Error; not declared
                                           // extern.
    __declspec( dllimport ) int m;         // Okay; this is a
                                           // declaration.
    __declspec( dllexport ) int n;         // Error; implies external
                                           // definition in local scope.
    extern __declspec( dllimport ) int i;  // Okay; this is a
                                           // declaration.
    extern __declspec( dllexport ) int k;  // Okay; extern implies
                                           // declaration.
    __declspec( dllexport ) int x = 5;     // Error; implies external
                                           // definition in local scope.
}
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[dllexport、dllimport](../cpp/dllexport-dllimport.md)
