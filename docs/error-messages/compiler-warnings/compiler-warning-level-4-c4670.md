---
title: コンパイラの警告 (レベル 4) C4670
ms.date: 11/04/2016
f1_keywords:
- C4670
helpviewer_keywords:
- C4670
ms.assetid: e172b134-b1fb-4dfe-8e9d-209ea08b73c7
ms.openlocfilehash: 1ce32ef4d07ea5e2c6f328578837f805eed5c897
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408135"
---
# <a name="compiler-warning-level-4-c4670"></a>コンパイラの警告 (レベル 4) C4670

'identifier': 基底クラスはアクセスできません

**try** ブロックでスローされる､指定されたオブジェクトの基底クラスにはアクセスできません。 オブジェクトがスローされる場合、そのオブジェクトはインスタンスを生成できません。 基底クラスが正しいアクセス指定子を使用して継承されているかどうかを確認してください。

次の例では C4670 警告が生成されます。

```
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