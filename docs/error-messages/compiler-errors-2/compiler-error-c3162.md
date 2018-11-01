---
title: コンパイラ エラー C3162
ms.date: 11/04/2016
f1_keywords:
- C3162
helpviewer_keywords:
- C3162
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
ms.openlocfilehash: f522a2de77e03a7c5f8f8dc774d62744417344fb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540193"
---
# <a name="compiler-error-c3162"></a>コンパイラ エラー C3162

'type': デストラクターを含む参照型は、静的データ メンバー 'member' の型として使用できません

共通言語ランタイムは、クラスには、静的メンバー関数も含まれている場合は、ユーザー定義のデストラクターを実行するタイミングを知ることはできません。

オブジェクトが明示的に削除しない限り、デストラクターは実行されません。

詳細については、次のトピックを参照してください。

- [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Visual C++ の 64 ビットへの移行に関する一般的な問題](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>例

次の例では、C3162 が生成されます。

```
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