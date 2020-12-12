---
description: 詳細については、「コンパイラエラー C2743」を参照してください。
title: コンパイラエラー C2743
ms.date: 11/04/2016
f1_keywords:
- C2743
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
ms.openlocfilehash: 2619d4a0dd2b89d36f11944b59c2ab4993d95fd0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123059"
---
# <a name="compiler-error-c2743"></a>コンパイラエラー C2743

' type ': __clrcall デストラクターまたはコピーコンストラクターでネイティブ型をキャッチすることはできません

**/Clr** でコンパイルされたモジュールがネイティブ型の例外をキャッチしようとしましたが、型のデストラクターまたはコピーコンストラクターが呼び出し規約を使用して `__clrcall` います。

**/Clr** を指定してコンパイルする場合、例外処理では、ネイティブ型のメンバー関数が [__clrcall](../../cpp/clrcall.md)ではなく [__cdecl](../../cpp/cdecl.md)されることを想定しています。 呼び出し規約を使用するメンバー関数を持つネイティブ型は `__clrcall` 、 **/clr** でコンパイルされたモジュールでキャッチできません。

詳細については、「 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。

## <a name="example"></a>例

次の例では、C2743 が生成されます。

```cpp
// C2743.cpp
// compile with: /clr
public struct S {
   __clrcall ~S() {}
};

public struct T {
   ~T() {}
};

int main() {
   try {}
   catch(S) {}   // C2743
   // try the following line instead
   // catch(T) {}

   try {}
   catch(S*) {}   // OK
}
```
