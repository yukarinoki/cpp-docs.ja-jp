---
title: コンパイラの警告 (レベル 1) C4382
ms.date: 11/04/2016
f1_keywords:
- C4382
helpviewer_keywords:
- C4382
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
ms.openlocfilehash: 7b8dbf77defab2a711ad931057c740193908474b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186973"
---
# <a name="compiler-warning-level-1-c4382"></a>コンパイラの警告 (レベル 1) C4382

> '*type*' をスローしています: __clrcall デストラクターまたはコピーコンストラクターを持つ型は、/clr: pure モジュールでのみキャッチできます

## <a name="remarks"></a>解説

**/Clr: pure**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

**/Clr (** **/clr: pure**ではなく) を使用してコンパイルした場合、例外処理では、ネイティブ型のメンバー関数が[__clrcall](../../cpp/clrcall.md)ではなく[__cdecl](../../cpp/cdecl.md)されることを想定しています。 `__clrcall` 呼び出し規約を使用するメンバー関数を持つネイティブ型は、 **/clr**でコンパイルされたモジュールでキャッチできません。

**/Clr: pure**を指定してコンパイルされたモジュールで例外がキャッチされる場合は、この警告を無視してもかまいません。

詳細については、「 [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。

## <a name="example"></a>例

次の例では、C4382 が生成されます。

```cpp
// C4382.cpp
// compile with: /clr /W1 /c
struct S {
   __clrcall ~S() {}
};

struct T {
   ~T() {}
};

int main() {
   S s;
   throw s;   // C4382

   S * ps = &s;
   throw ps;   // OK

   T t;
   throw t;   // OK
}
```
