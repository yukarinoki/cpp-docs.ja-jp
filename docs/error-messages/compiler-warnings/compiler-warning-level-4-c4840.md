---
title: コンパイラの警告 (レベル 4) C4840
ms.date: 09/13/2018
f1_keywords:
- C4840
helpviewer_keywords:
- C4840
ms.openlocfilehash: 649083d66d0c7a0ef11c742e56cbfb70e2e9b75f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185205"
---
# <a name="compiler-warning-level-4-c4840"></a>コンパイラの警告 (レベル 4) C4840

> 可変個引数関数への引数としてのクラス '*type*' のポータブルでない使用

## <a name="remarks"></a>解説

可変個引数関数に渡されるクラスまたは構造体は、普通にコピー可能である必要があります。 このようなオブジェクトを渡すときには、コンパイラは単にビットごとのコピーを作成し、コンストラクターまたはデストラクターを呼び出しません。

この警告は、Visual Studio 2017 以降で使用できます。

## <a name="example"></a>例

次の例では、C4840 を生成し、その修正方法を示しています。

```cpp
// C4840.cpp
// compile by using: cl /EHsc /W4 C4840.cpp
#include <stdio.h>

int main()
{
    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);

    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                       // as an argument to a variadic function
    // To correct the error, you can perform a static cast
    // to convert the object before passing it:
    printf("%i\n", static_cast<int>(s));
}
```

`CStringW`を使用して作成および管理された文字列の場合、指定された `operator LPCWSTR()` を使用して、`CStringW` オブジェクトを、書式文字列によって予期される C スタイルの文字列ポインターにキャストする必要があります。

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```
