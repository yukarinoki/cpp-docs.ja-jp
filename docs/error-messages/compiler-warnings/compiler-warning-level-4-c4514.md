---
title: コンパイラの警告 (レベル 4) C4514
ms.date: 11/04/2016
f1_keywords:
- C4514
helpviewer_keywords:
- C4514
ms.assetid: cdae966a-9cd4-4e31-af30-2a014e68f614
ms.openlocfilehash: 6e31f321ca53ac194ce5077f7f9c80e8099c5d78
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2019
ms.locfileid: "74683228"
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