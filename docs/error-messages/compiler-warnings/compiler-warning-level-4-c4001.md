---
title: コンパイラの警告 (レベル 4) C4001 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4001
dev_langs:
- C++
helpviewer_keywords:
- C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c325656b9e61ee324a3b9f171413f1020440f9ab
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025413"
---
# <a name="compiler-warning-level-4-c4001"></a>コンパイラの警告 (レベル 4) C4001

標準の拡張機能を単一行コメントの使用

> [!NOTE]
> この警告は、単一行コメントは C99 標準であるために、Visual Studio 2017 バージョン 15.5 で削除されます。

単一行コメントには、C++ の標準および C99 以降、C で標準です。
厳密な ANSI 互換 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))、単一行のコメントを含む C# ファイルは、標準の拡張機能の使用率に起因 C4001 を生成します。 単一行コメントは、C++ の標準であるため単一行コメントを含む C# ファイル生成しない C4001 Microsoft 拡張機能 (/Ze) でコンパイルするとします。

## <a name="example"></a>例

警告を無効にするをコメント解除します[#pragma warning(disable:4001)](../../preprocessor/warning.md)します。

```
// C4001.cpp
// compile with: /W4 /Za /TC
// #pragma warning(disable:4001)
int main()
{
   // single-line comment in main
   // C4001
}
```