---
description: '詳細情報: コンパイラの警告 (レベル 4) C4840'
title: コンパイラの警告 (レベル 4) C4840
ms.date: 09/13/2018
f1_keywords:
- C4840
helpviewer_keywords:
- C4840
ms.openlocfilehash: a365dc38aff1ab9811407924f7f6e554d91c6f1e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330467"
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

を使用して作成および管理される文字列の場合 `CStringW` 、指定されたを使用して、 `operator LPCWSTR()` 書式指定 `CStringW` 文字列によって予期される C スタイルの文字列ポインターにオブジェクトをキャストする必要があります。

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```
