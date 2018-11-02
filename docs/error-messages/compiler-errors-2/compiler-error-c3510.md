---
title: コンパイラ エラー C3510
ms.date: 11/04/2016
f1_keywords:
- C3510
helpviewer_keywords:
- C3510
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
ms.openlocfilehash: dbb65628aa6e0da94a91a59724ca8e1cd5b56491
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620879"
---
# <a name="compiler-error-c3510"></a>コンパイラ エラー C3510

依存タイプ ライブラリ 'type_lib' を見つけることができません。

[no_registry](../../preprocessor/no-registry.md)と[auto_search](../../preprocessor/auto-search.md)に渡された`#import`が、コンパイラは参照されるタイプ ライブラリを検索できませんでした。

このエラーを解決するには、すべてのタイプ ライブラリと参照されるタイプ ライブラリがコンパイラに利用できることを確認します。

次の例では、C3510 が生成されます。

次の 2 つのタイプ ライブラリがビルドされた C3510a.tlb の削除を想定していますか、パスではなく。

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

2 つ目のタイプ ライブラリのソース コード:

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

クライアント コード:

```
// C3510.cpp
#import "c3510b.tlb" no_registry auto_search   // C3510
int main() {
   C3510aLib::S_C4336 ccc;
}
```