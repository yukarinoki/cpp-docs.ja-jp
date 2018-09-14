---
title: コンパイラの警告 (レベル 4) C4840 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2018
ms.topic: error-reference
f1_keywords:
- C4840
dev_langs:
- C++
helpviewer_keywords:
- C4840
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0baf70ac7fd4d07958478d2eef455c7dc395e221
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601827"
---
# <a name="compiler-warning-level-4-c4840"></a>コンパイラの警告 (レベル 4) C4840

> クラスの移植性のない使用*型*' 可変個引数関数に引数として
  
## <a name="remarks"></a>Remarks

クラスまたは可変個引数関数に渡される構造体は普通にコピー可能である必要があります。 このようなオブジェクトを渡すときには、コンパイラは単にビットごとのコピーを作成し、コンストラクターまたはデストラクターを呼び出しません。

この警告は、Visual Studio 2017 以降を使用できます。

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

構築および管理を使用して文字列`CStringW`、提供された`operator LPCWSTR()`にキャストするために使用する必要があります、`CStringW`オブジェクトを書式設定文字列によって予期されている C スタイル文字列ポインター。

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```