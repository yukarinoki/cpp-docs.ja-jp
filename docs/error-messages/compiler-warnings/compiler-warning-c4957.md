---
title: コンパイラの警告 C4957
ms.date: 11/04/2016
f1_keywords:
- C4957
helpviewer_keywords:
- C4957
ms.assetid: a18c52d4-23e2-44f1-b4b5-f7fa5a7f3987
ms.openlocfilehash: 340c26c97d0b5b686eee487cd3fd8b6b05bdf373
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164909"
---
# <a name="compiler-warning-c4957"></a>コンパイラの警告 C4957

> '*cast*': '*cast_from*' から '*cast_to*' への明示的なキャストは検証可能ではありません

## <a name="remarks"></a>解説

キャストにより、検証不可能なイメージが生成されます。

安全なキャストもあります (ユーザー定義の変換をトリガーする `static_cast` 、 `const_cast`など)。 [safe_cast](../../extensions/safe-cast-cpp-component-extensions.md) は、検証可能なコードを生成することが保証されています。

詳細については、「[ピュアおよび検証C++可能なコード (/cli)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)」を参照してください。

**/Clr: safe**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

この警告は、エラーとして表示されます。無効にするには、 [warning](../../preprocessor/warning.md) プラグマ、または [/wd](../../build/reference/compiler-option-warning-level.md) コンパイラ オプションを使用します。

## <a name="example"></a>例

次の例では C4957 が生成されます。

```cpp
// C4957.cpp
// compile with: /clr:safe
// #pragma warning( disable : 4957 )
using namespace System;
int main() {
   Object ^ o = "Hello, World!";
   String ^ s = static_cast<String^>(o);   // C4957
   String ^ s2 = safe_cast<String^>(o);   // OK
}
```
