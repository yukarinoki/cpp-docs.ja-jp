---
title: コンパイラの警告 C4957 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4957
dev_langs:
- C++
helpviewer_keywords:
- C4957
ms.assetid: a18c52d4-23e2-44f1-b4b5-f7fa5a7f3987
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 60cf1c03ace94c866b77c5340e2a04a9d8190e4d
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705219"
---
# <a name="compiler-warning-c4957"></a>コンパイラの警告 C4957

> '*キャスト*': 明示的なキャストから'*cast_from*'to'*cast_to*' は、検証できません

## <a name="remarks"></a>コメント

キャストにより、検証不可能なイメージが生成されます。

安全なキャストもあります (ユーザー定義の変換をトリガーする `static_cast` 、 `const_cast`など)。 [safe_cast](../../windows/safe-cast-cpp-component-extensions.md) は、検証可能なコードを生成することが保証されています。

詳細については、次を参照してください。[純粋なコードと検証可能なコード (C + + CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)です。

**/Clr:safe**コンパイラ オプションは Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

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