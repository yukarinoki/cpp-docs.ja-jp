---
description: '詳細情報: コンパイラの警告 (レベル 1) C4572'
title: コンパイラの警告 (レベル 1) C4572
ms.date: 11/04/2016
f1_keywords:
- C4572
helpviewer_keywords:
- C4572
ms.assetid: 482dee5a-29bd-4fc3-b769-9dfd4cd2a964
ms.openlocfilehash: ab447bc7ef5d702599b1583ae94ac0fa94d29a14
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332230"
---
# <a name="compiler-warning-level-1-c4572"></a>コンパイラの警告 (レベル 1) C4572

[ParamArray] 属性は/clr で非推奨とされます。 '... ' を使用してください。その代わりに

可変個引数リストを指定するための古いスタイルが使用されました。 CLR に対してコンパイルする場合は、の代わりに省略記号構文を使用し <xref:System.ParamArrayAttribute> ます。 詳細については、「 [可変個引数リスト (...) (C++/cli)](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md)」を参照してください。

## <a name="example"></a>例

次の例では、C4572 が生成されます。

```cpp
// C4572.cpp
// compile with: /clr /W1
void Func([System::ParamArray] array<int> ^);   // C4572
void Func2(... array<int> ^){}   // OK

int main() {
   Func2(1, 2, 3);
}
```
