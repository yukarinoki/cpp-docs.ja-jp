---
description: '詳細情報: 致命的なエラー C1017'
title: 致命的なエラー C1017
ms.date: 11/04/2016
f1_keywords:
- C1017
helpviewer_keywords:
- C1017
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
ms.openlocfilehash: a36a5cb11b10ca3ecca00d0379595060918d6a45
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262387"
---
# <a name="fatal-error-c1017"></a>致命的なエラー C1017

整数定数式が無効です。

ディレクティブ内の式が `#if` 存在しないか、または定数に評価されませんでした。

を使用して定義された定数は `#define` `#if` 、、 `#elif` 、またはディレクティブで使用される場合、整数定数に評価される値を持つ必要があり `#else` ます。

次の例では、C1017 が生成されます。

```cpp
// C1017.cpp
#define CONSTANT_NAME "YES"
#if CONSTANT_NAME   // C1017
#endif
```

考えられる解決策:

```cpp
// C1017b.cpp
// compile with: /c
#define CONSTANT_NAME 1
#if CONSTANT_NAME
#endif
```

は `CONSTANT_NAME` 整数ではなく文字列に評価されるため、 `#if` ディレクティブは致命的なエラー C1017 を生成します。

それ以外の場合、プリプロセッサは未定義の定数を0として評価します。 次の例に示すように、これによって意図しない結果が発生する可能性があります。 `YES` は未定義であるため、0に評価されます。 式は `#if` `CONSTANT_NAME` false と評価され、で使用されるコード `YES` はプリプロセッサによって削除されます。 `NO` も未定義 (ゼロ) であるため、は `#elif` `CONSTANT_NAME==NO` true () に評価され `0 == 0` 、プリプロセッサがステートメントの部分にコードを残して、意図した `#elif` 動作とは逆になります。

```cpp
// C1017c.cpp
// compile with: /c
#define CONSTANT_NAME YES
#if CONSTANT_NAME
   // Code to use on YES...
#elif CONSTANT_NAME==NO
   // Code to use on NO...
#endif
```

コンパイラがプリプロセッサディレクティブをどのように処理するかを正確に確認するには、 [/p](../../build/reference/p-preprocess-to-a-file.md)、 [/e](../../build/reference/e-preprocess-to-stdout.md)、または [/ep](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)を使用します。
