---
title: コンパイラの警告 (レベル 1) C4382 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4382
dev_langs:
- C++
helpviewer_keywords:
- C4382
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29afe066fb86d0dd99216a63c057046ec76de55b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704322"
---
# <a name="compiler-warning-level-1-c4382"></a>コンパイラの警告 (レベル 1) C4382

> スロー '*型*': _ _clrcall デストラクターまたはコピー コンス トラクターを持つ型は/clr でしかキャッチできません: 純粋なモジュール

## <a name="remarks"></a>コメント

**/Clr: 純粋な**コンパイラ オプションは Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

コンパイルしたときに **/clr** (いない **/clr: 純粋な**)、例外処理には、メンバー関数は、ネイティブ型にするが必要ですが[_ _cdecl](../../cpp/cdecl.md)および not [_ _clrcall](../../cpp/clrcall.md). 使用してメンバー関数を持つネイティブ型`__clrcall`でコンパイルされたモジュールの呼び出し規約をキャッチできない **/clr**です。

コンパイルされたモジュールのかどうか、例外がキャッチされる **/clr: 純粋な**、この警告を無視することができます。

詳細については、「[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。

## <a name="example"></a>例

次の例では、C4382 を生成します。

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