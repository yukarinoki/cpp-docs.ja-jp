---
title: コンパイラ エラー C3510 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3510
dev_langs:
- C++
helpviewer_keywords:
- C3510
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5cc134823abf2657426b0c1be9cfbe6d92a74035
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111332"
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