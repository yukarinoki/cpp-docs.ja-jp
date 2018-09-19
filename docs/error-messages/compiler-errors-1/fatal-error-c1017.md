---
title: 致命的なエラー C1017 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1017
dev_langs:
- C++
helpviewer_keywords:
- C1017
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc2cb8ef9c7c9fe8eea7c506e55c49878b9bd809
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108536"
---
# <a name="fatal-error-c1017"></a>致命的なエラー C1017

整数定数式が無効です。

内の式、`#if`ディレクティブが存在していなかったか、定数に評価されなかった。

使用して定義されている定数`#define`値で使用されている場合は、整数の定数に評価される必要があります、 `#if`、 `#elif`、または`#else`ディレクティブ。

次の例では、C1017 が生成されます。

```
// C1017.cpp
#define CONSTANT_NAME "YES"
#if CONSTANT_NAME   // C1017
#endif
```

考えられる解決方法:

```
// C1017b.cpp
// compile with: /c
#define CONSTANT_NAME 1
#if CONSTANT_NAME
#endif
```

`CONSTANT_NAME`文字列と、整数に評価、`#if`ディレクティブには、致命的なエラー C1017 が生成されます。

それ以外の場合は、プリプロセッサは、0 として定数 undefined を評価します。 次の例に示すように、意図しない結果ができます。 `YES` 0 と評価のためには、定義されません。 式`#if``CONSTANT_NAME`が false になり、コードで使用される`YES`プリプロセッサによって削除されます。 `NO` 定義されていない (ゼロ) があるため`#elif` `CONSTANT_NAME==NO` true に評価されます (`0 == 0`) でコードを離れるプリプロセッサの原因、`#elif`ステートメントの部分: 目的の動作は正反対です。

```
// C1017c.cpp
// compile with: /c
#define CONSTANT_NAME YES
#if CONSTANT_NAME
   // Code to use on YES...
#elif CONSTANT_NAME==NO
   // Code to use on NO...
#endif
```

コンパイラがプリプロセッサ ディレクティブを処理する方法だけを表示する[/P](../../build/reference/p-preprocess-to-a-file.md)、 [/E](../../build/reference/e-preprocess-to-stdout.md)、または[/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)します。