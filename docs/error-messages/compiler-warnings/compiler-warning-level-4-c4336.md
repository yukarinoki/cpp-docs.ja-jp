---
description: '詳細情報: コンパイラの警告 (レベル 4) C4336'
title: コンパイラの警告 (レベル 4) C4336
ms.date: 11/04/2016
f1_keywords:
- C4336
helpviewer_keywords:
- C4336
ms.assetid: 93f199dd-d6dd-42c0-82d8-c12d101a7235
ms.openlocfilehash: d41ca5584864327b3012e79af97f2857e3f93d42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257720"
---
# <a name="compiler-warning-level-4-c4336"></a>コンパイラの警告 (レベル 4) C4336

' type_lib2 ' をインポートする前に、クロス参照タイプライブラリ ' type_lib1 ' をインポートします

[#Import](../../preprocessor/hash-import-directive-cpp.md)ディレクティブを使用して、タイプライブラリが参照されました。 ただし、このタイプライブラリには、で参照されていない別のタイプライブラリへの参照が含まれていました `#import` 。 この他の .tlb ファイルは、コンパイラによって検出されました。

次の2つのファイルから作成されたディスク上に2つのタイプライブラリがあるとします (midl.exe でコンパイル)。

```
// c4336a.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]
library c4336aLib
{
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]
   enum E_C4336
   {
      one, two, three
   };
};
```

2番目のタイプライブラリ:

```
// c4336b.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]
library C4336bLib
{
   importlib ("c4336a.tlb");
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]
   struct S_C4336
   {
      enum E_C4336 e;
   };
};
```

次の例では、C4336 が生成されます。

```cpp
// C4336.cpp
// compile with: /W4 /LD
// #import "C4336a.tlb"
#import "C4336b.tlb"   // C4336, uncomment previous line to resolve
```
