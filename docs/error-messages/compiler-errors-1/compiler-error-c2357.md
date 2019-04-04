---
title: コンパイラ エラー C2357
ms.date: 11/04/2016
f1_keywords:
- C2357
helpviewer_keywords:
- C2357
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
ms.openlocfilehash: 1872672e776ad13bf16be5ae69729f4f68d8f3b0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531782"
---
# <a name="compiler-error-c2357"></a>コンパイラ エラー C2357

'identifier': 'type' 型の関数でなければなりません

コード宣言のバージョンが、`atexit`バージョンに一致しない関数は、コンパイラによって内部で宣言されました。 宣言`atexit`次のようにします。

```
int __cdecl atexit(void (__cdecl *)());
```

詳細については、[init_seg](../../preprocessor/init-seg.md)を参照してください。

次の例では、C2357 が生成されます。

```
// C2357.cpp
// compile with: /c
// C2357 expected
#pragma warning(disable : 4075)
// Uncomment the following line to resolve.
// int __cdecl myexit(void (__cdecl *)());
#pragma init_seg(".mine$m",myexit)
```