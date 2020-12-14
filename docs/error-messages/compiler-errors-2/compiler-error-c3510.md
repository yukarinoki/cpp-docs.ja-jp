---
description: 詳細については、「コンパイラエラー C3510」を参照してください。
title: コンパイラ エラー C3510
ms.date: 11/04/2016
f1_keywords:
- C3510
helpviewer_keywords:
- C3510
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
ms.openlocfilehash: 97727f22e94993cff051c57b5692e9a14c9ab930
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315427"
---
# <a name="compiler-error-c3510"></a>コンパイラ エラー C3510

依存タイプライブラリ ' type_lib ' が見つかりません

[no_registry](../../preprocessor/no-registry.md) と [auto_search](../../preprocessor/auto-search.md) はに渡されました `#import` が、コンパイラは参照されているタイプライブラリを見つけることができませんでした。

このエラーを解決するには、すべてのタイプライブラリと参照されるタイプライブラリがコンパイラで使用可能であることを確認します。

次の例では、C3510 が生成されます。

次の2つのタイプライブラリがビルドされ、パスで C3510a が削除されたものとします。

```
// C3510a.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]
library C3510aLib
{
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]
   enum E_C3510
   {
      one, two, three
   };
};
```

次に、2番目のタイプライブラリのソースコードを次に示します。

```
// C3510b.idl
// post-build command: del /f C3510a.tlb
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]
library C3510bLib
{
   importlib ("C3510a.tlb");
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]
   struct S_C3510 {
      enum E_C3510 e;
   };
};
```

次に、クライアントコードを次に示します。

```cpp
// C3510.cpp
#import "c3510b.tlb" no_registry auto_search   // C3510
int main() {
   C3510aLib::S_C4336 ccc;
}
```
