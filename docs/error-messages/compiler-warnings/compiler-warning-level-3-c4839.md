---
title: コンパイラの警告 (レベル 3) C4839
ms.date: 09/13/2018
f1_keywords:
- C4839
helpviewer_keywords:
- C4839
ms.assetid: f4f99066-9258-4330-81a8-f4a75a1d95ee
ms.openlocfilehash: 2c238dc16359583bf55f7590d2ce7c0363d66df7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198576"
---
# <a name="compiler-warning-level-3-c4839"></a>コンパイラの警告 (レベル 3) C4839

> 可変個引数関数の引数としてのクラス '*type*' の非標準の使用

`printf` などの可変個引数関数に渡されるクラスまたは構造体は、普通にコピー可能である必要があります。 このようなオブジェクトを渡すときには、コンパイラは単にビットごとのコピーを作成し、コンストラクターまたはデストラクターを呼び出しません。

この警告は、Visual Studio 2017 以降で使用できます。

## <a name="example"></a>例

次の例では、C4839 が生成されます。

```cpp
// C4839.cpp
// compile by using: cl /EHsc /W3 C4839.cpp
#include <atomic>
#include <memory>
#include <stdio.h>

int main()
{
    std::atomic<int> i(0);
    printf("%i\n", i); // error C4839: non-standard use of class 'std::atomic<int>'
                        // as an argument to a variadic function
                        // note: the constructor and destructor will not be called;
                        // a bitwise copy of the class will be passed as the argument
                        // error C2280: 'std::atomic<int>::atomic(const std::atomic<int> &)':
                        // attempting to reference a deleted function
}
```

エラーを解決するために、普通にコピー可能な型を返すメンバー関数を呼び出すことができます。

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

`CStringW`を使用して作成および管理された文字列の場合は、指定された `operator LPCWSTR()` を使用して、`CStringW` オブジェクトを書式指定文字列によって予期される C ポインターにキャストする必要があります。

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```
