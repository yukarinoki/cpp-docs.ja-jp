---
description: 詳細については、「コンパイラエラー C3154」を参照してください。
title: コンパイラエラー C3154
ms.date: 11/04/2016
f1_keywords:
- C3154
helpviewer_keywords:
- C3154
ms.assetid: 78005c74-eaaf-4ac2-88ae-6c25d01a302a
ms.openlocfilehash: c43800aba54431041b13e70d9e94c80d98d8ee84
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203979"
---
# <a name="compiler-error-c3154"></a>コンパイラエラー C3154

省略記号の前に ', ' が必要です。 パラメーター配列関数では、非コンマ区切りの省略記号がサポートされていません。

可変個引数関数が正しく宣言されていませんでした。

詳細については、「 [可変個引数リスト (...) (C++/cli)](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3154 が生成されます。

```cpp
// C3154.cpp
// compile with: /clr
ref struct R {
   void Func(int ... array<int> ^);   // C3154
   void Func2(int i, ... array<int> ^){}   // OK
   void Func3(array<int> ^){}   // OK
   void Func4(... array<int> ^){}   // OK
};

int main() {
   R ^ r = gcnew R;
   r->Func4(1,2,3);
}
```
