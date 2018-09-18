---
title: C++ では、宣言の位置 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- point of declaration
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68ac24fcfe35701dd75d74800661aa5e41c005f8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072068"
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