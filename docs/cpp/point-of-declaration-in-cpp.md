---
title: C++ での宣言の位置
ms.date: 11/04/2016
helpviewer_keywords:
- point of declaration
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
ms.openlocfilehash: d6cb4c3813d88c8b29fbcb2e0827805f406e6c81
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50560655"
---
# <a name="point-of-declaration-in-c"></a>C++ での宣言の位置

名前は宣言子の直後、ただし初期化子 (省略可能) よりも前の位置で宣言されるものと見なされます (宣言子の詳細については、次を参照してください[宣言と定義](declarations-and-definitions-cpp.md)。)。

次の例について考えます。

```cpp
// point_of_declaration1.cpp
// compile with: /W1
double dVar = 7.0;
int main()
{
   double dVar = dVar;   // C4700
}
```

場合は、宣言の位置が*後*、初期化では、次に、ローカル`dVar`7.0 では、グローバル変数の値に初期化が`dVar`します。 しかし、実際にはそうでないため、`dVar` は未定義の値に初期化されます。

## <a name="see-also"></a>関連項目

[スコープ](../cpp/scope-visual-cpp.md)