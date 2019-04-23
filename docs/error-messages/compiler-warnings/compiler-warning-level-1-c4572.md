---
title: コンパイラの警告 (レベル 1) C4572
ms.date: 11/04/2016
f1_keywords:
- C4572
helpviewer_keywords:
- C4572
ms.assetid: 482dee5a-29bd-4fc3-b769-9dfd4cd2a964
ms.openlocfilehash: e32509e4d32eef4f53b8d43a7db769844f1182c7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59779467"
---
# <a name="compiler-warning-level-1-c4572"></a>コンパイラの警告 (レベル 1) C4572

[...] [ParamArray] 属性は/clr を使用して非推奨します。その代わりに

可変個引数リストを指定するため、古いスタイルが使用されました。 CLR をコンパイルする際の代わりに省略記号構文を使用して、<xref:System.ParamArrayAttribute>します。 詳細については、次を参照してください[可変個引数リスト (...)。(C +/CLI CLI)](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md).

## <a name="example"></a>例

次の例では、C4572 が生成されます。

```
// C4572.cpp
// compile with: /clr /W1
void Func([System::ParamArray] array<int> ^);   // C4572
void Func2(... array<int> ^){}   // OK

int main() {
   Func2(1, 2, 3);
}
```