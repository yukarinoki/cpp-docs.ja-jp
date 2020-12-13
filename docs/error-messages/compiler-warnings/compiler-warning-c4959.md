---
description: 詳細については、「コンパイラの警告 C4959」を参照してください。
title: コンパイラの警告 C4959
ms.date: 11/04/2016
f1_keywords:
- C4959
helpviewer_keywords:
- C4959
ms.assetid: 3a128f3e-4d8a-4565-ba1a-5d32fdeb5982
ms.openlocfilehash: 3a4fae04ee654caf23776a7bf4d6b073853bd03a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336076"
---
# <a name="compiler-warning-c4959"></a>コンパイラの警告 C4959

> アンマネージ構造体 '*type*' は、そのメンバーにアクセスすると検証不可能なコードを生成するため、/clr: safe で定義できません

## <a name="remarks"></a>解説

アンマネージ型のメンバーにアクセスすると、検証不可能な (peverify.exe) イメージが生成されます。

詳細については、「 [純粋なコードと検証可能なコード (C++/cli)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)」を参照してください。

**/Clr: safe** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

この警告は、エラーとして表示されます。無効にするには、 [warning](../../preprocessor/warning.md) プラグマ、または [/wd](../../build/reference/compiler-option-warning-level.md) コンパイラ オプションを使用します。

## <a name="example"></a>例

次の例では C4959 が生成されます。

```cpp
// C4959.cpp
// compile with: /clr:safe

// Uncomment the following line to resolve.
// #pragma warning( disable : 4959 )
struct X {
   int data;
};

int main() {
   X x;
   x.data = 10;   // C4959
}
```
