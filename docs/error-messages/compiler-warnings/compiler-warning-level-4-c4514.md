---
description: '詳細情報: コンパイラの警告 (レベル 4) C4514'
title: コンパイラの警告 (レベル 4) C4514
ms.date: 11/04/2016
f1_keywords:
- C4514
helpviewer_keywords:
- C4514
ms.assetid: cdae966a-9cd4-4e31-af30-2a014e68f614
ms.openlocfilehash: 5d0ba77f6e2d2f0288f92994f0daffde36545c27
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241223"
---
# <a name="compiler-warning-level-4-c4514"></a>コンパイラの警告 (レベル 4) C4514

' function ': 参照されていないインライン関数は削除されました

呼び出されていないインライン関数がオプティマイザーによって削除されました。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

次の例では、C4514 が生成されます。

```cpp
// C4514.cpp
// compile with: /W4
#pragma warning(default : 4514)
class A
{
   public:
      void func()   // C4514, remove the function to resolve
      {
      }
};

int main()
{
}
```
