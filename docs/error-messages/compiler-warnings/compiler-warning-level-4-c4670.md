---
description: '詳細情報: コンパイラの警告 (レベル 4) C4670'
title: コンパイラの警告 (レベル 4) C4670
ms.date: 11/04/2016
f1_keywords:
- C4670
helpviewer_keywords:
- C4670
ms.assetid: e172b134-b1fb-4dfe-8e9d-209ea08b73c7
ms.openlocfilehash: c1d0f81f10fe63882987d660e4b9099f4ff895ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134031"
---
# <a name="compiler-warning-level-4-c4670"></a>コンパイラの警告 (レベル 4) C4670

'identifier': 基底クラスはアクセスできません

ブロックでスローされるオブジェクトの指定された基底クラス **`try`** にアクセスできません。 オブジェクトがスローされる場合、そのオブジェクトはインスタンスを生成できません。 基底クラスが正しいアクセス指定子を使用して継承されているかどうかを確認してください。

次の例では C4670 警告が生成されます。

```cpp
// C4670.cpp
// compile with: /EHsc /W4
class A
{
};

class B : /* public */ A
{
} b;   // inherits A with private access by default

int main()
{
    try
    {
       throw b;   // C4670
    }
    catch( B )
    {
    }
}
```
