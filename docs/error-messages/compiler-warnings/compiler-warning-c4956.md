---
description: 詳細については、「コンパイラの警告 C4956」を参照してください。
title: コンパイラの警告 C4956
ms.date: 11/04/2016
f1_keywords:
- C4956
helpviewer_keywords:
- C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
ms.openlocfilehash: 4a92c6329bf4cdd764fd7f419d8011d4dfde0202
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314842"
---
# <a name="compiler-warning-c4956"></a>コンパイラの警告 C4956

> '*type*': この型は検証可能ではありません

## <a name="remarks"></a>解説

この警告は、 [/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md) が指定され、コードに検証不可能な型が含まれている場合に生成されます。 **/Clr: safe** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

詳細については、「 [純粋なコードと検証可能なコード (C++/cli)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)」を参照してください。

この警告は、エラーとして表示されます。無効にするには、 [warning](../../preprocessor/warning.md) プラグマ、または [/wd](../../build/reference/compiler-option-warning-level.md) コンパイラ オプションを使用します。

## <a name="example"></a>例

次の例では C4956 が生成されます。

```cpp
// C4956.cpp
// compile with: /clr:safe
int* p;   // C4956
```
