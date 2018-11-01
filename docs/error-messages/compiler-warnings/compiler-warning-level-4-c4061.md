---
title: コンパイラの警告 (レベル 4) C4061
ms.date: 11/30/2017
f1_keywords:
- C4061
helpviewer_keywords:
- C4061
ms.assetid: a99cf88e-7941-4519-8b1b-f6889d914b2f
ms.openlocfilehash: 8b730d561134b8b7ca4454ee74f99216fbc72cb4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50453272"
---
# <a name="compiler-warning-level-4-c4061"></a>コンパイラの警告 (レベル 4) C4061

> 列挙子 '*識別子*'列挙型のスイッチは' in*列挙*' case ラベルによって明示的に処理されません。

列挙子関連付けられたハンドラーがない、`switch`ステートメント。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

## <a name="example"></a>例

次の例には、C4061; が生成されます。修正に不足している列挙子の case を追加します。

```cpp
// C4061.cpp
// compile with: /W4
#pragma warning(default : 4061)

enum E { a, b, c };
void func ( E e )
{
   switch(e)
   {
      case a:
      case b:
      default:
         break;
   }   // C4061 c' not handled
}

int main()
{
}
```