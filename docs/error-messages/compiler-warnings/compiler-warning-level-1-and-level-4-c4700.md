---
description: '詳細情報: コンパイラの警告 (レベル1およびレベル 4) C4700'
title: コンパイラの警告 (レベル 1 およびレベル 4) C4700
ms.date: 02/21/2018
f1_keywords:
- C4700
helpviewer_keywords:
- C4700
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
ms.openlocfilehash: 7ba19bdd6d8e25e095f796adc8cdb60b5cc8d325
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241600"
---
# <a name="compiler-warning-level-1-and-level-4-c4700"></a>コンパイラの警告 (レベル 1 およびレベル 4) C4700

> 初期化されていないローカル変数 '*name*' が使用されています

ローカル変数 *名* が *使用* されています。つまり、値が割り当てられる前に、読み取りが行われています。 C および C++ では、ローカル変数は既定では初期化されません。 初期化されていない変数には任意の値を含めることができ、その使用によって未定義の動作が発生します。 Warning C4700 は、ほとんどの場合、プログラムで予測できない結果やクラッシュを引き起こす可能性があるバグを示します。

この問題を解決するには、宣言時にローカル変数を初期化するか、使用する前に値を割り当てることができます。 関数を使用すると、参照パラメーターとして渡される変数、またはそのアドレスがポインターパラメーターとして渡されるときに、変数を初期化できます。

## <a name="example"></a>例

このサンプルでは、変数 t、u、および v が初期化される前に使用され、結果として生成される可能性のあるガベージ値の種類を示す C4700 が生成されます。 変数 x、y、および z では、使用前に初期化されるため、警告は発生しません。

```cpp
// c4700.cpp
// compile by using: cl /EHsc /W4 c4700.cpp
#include <iostream>

// function takes an int reference to initialize
void initialize(int& i)
{
    i = 21;
}

int main()
{
    int s, t, u, v;   // Danger, uninitialized variables

    s = t + u + v;    // C4700: t, u, v used before initialization
    std::cout << "Value in s: " << s << std::endl;

    int w, x;         // Danger, uninitialized variables
    initialize(x);    // fix: call function to init x before use
    int y{10};        // fix: initialize y, z when declared
    int z{11};        // This C++11 syntax is recommended over int z = 11;

    w = x + y + z;    // Okay, all values initialized before use
    std::cout << "Value in w: " << w << std::endl;
}
```

このコードを実行すると、t、u、および v は初期化されず、s の出力は予測できません。

```Output
Value in s: 37816963
Value in w: 42
```
