---
title: コンパイラの警告 (レベル 1) C4772
ms.date: 11/04/2016
f1_keywords:
- C4772
helpviewer_keywords:
- C4772
ms.assetid: dafe6fd8-9faf-41f5-9d66-a55838742c14
ms.openlocfilehash: 89156b2f29fd21160e6abddc3ecb21efaee6dde1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175133"
---
# <a name="compiler-warning-level-1-c4772"></a>コンパイラの警告 (レベル 1) C4772

> \#インポートで、欠落しているタイプライブラリから型が参照されています。'*missing-type*' がプレースホルダーとして使用されています

[#Import](../../preprocessor/hash-import-directive-cpp.md)ディレクティブを使用して、タイプライブラリが参照されました。 ただし、タイプライブラリには、`#import`で参照されていない別のタイプライブラリへの参照が含まれていました。 この他の .tlb ファイルは、コンパイラによって検出されませんでした。

[/I (追加のインクルードディレクトリ)](../../build/reference/i-additional-include-directories.md)コンパイラオプションを使用してこれらのディレクトリを指定した場合、コンパイラは異なるディレクトリにタイプライブラリを見つけることができないことに注意してください。 コンパイラで異なるディレクトリのタイプライブラリを検索する場合は、これらのディレクトリを PATH 環境変数に追加します。

既定では、この警告はエラーとして発行されます。 /W0. では C4772 を抑制できません

## <a name="example"></a>例

これは、C4772 を再現するために必要な最初のタイプライブラリです。

```IDL
// c4772a.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]
library C4772aLib
{
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c100")]
   enum E_C4772a
   {
      one, two, three
   };
};
```

これは、C4772 を再現するために必要な2番目のタイプライブラリです。

```IDL
// c4772b.idl
// post-build command: del /f C4772a.tlb
// C4772a.tlb is available when c4772b.tlb is built
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]
library C4772bLib
{
   importlib ("c4772a.tlb");
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]
   struct S_C4772b
   {
      enum E_C4772a e;
   };
};
```

次の例では、C4772 が生成されます。

```cpp
// C4772.cpp
// assumes that C4772a.tlb is not available to the compiler
// #import "C4772a.tlb"
#import "C4772b.tlb"   // C4772 uncomment previous line to resolve
                       // and make sure c4772a.tlb is on disk
```
