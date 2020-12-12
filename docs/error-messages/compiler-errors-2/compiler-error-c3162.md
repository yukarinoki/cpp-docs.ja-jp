---
description: 詳細については、「コンパイラエラー C3162」を参照してください。
title: コンパイラ エラー C3162
ms.date: 11/04/2016
f1_keywords:
- C3162
helpviewer_keywords:
- C3162
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
ms.openlocfilehash: ca44b27607a34a469a5fd6fc1371e1510452247a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242315"
---
# <a name="compiler-error-c3162"></a>コンパイラ エラー C3162

' type ': デストラクターを含む参照型を静的データメンバー ' member ' の型として使用することはできません

共通言語ランタイムは、クラスに静的メンバー関数も含まれている場合に、ユーザー定義のデストラクターを実行するタイミングを認識できません。

オブジェクトを明示的に削除しない限り、デストラクターは実行されません。

詳細については、次のトピックを参照してください。

- [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Visual C++ の 64 ビットへの移行に関する一般的な問題](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>例

次の例では、C3162 が生成されます。

```cpp
// C3162.cpp
// compile with: /clr /c
ref struct A {
   ~A() { System::Console::WriteLine("in destructor"); }
   static A i;   // C3162
   static A^ a = gcnew A;   // OK
};

int main() {
   A ^ a = gcnew A;
   delete a;
}
```
