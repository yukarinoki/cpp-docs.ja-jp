---
title: コンパイラの警告 C4577
description: コンパイラの警告 C4577 の説明と解決策。
ms.date: 09/18/2019
f1_keywords:
- C4577
helpviewer_keywords:
- C4577
ms.openlocfilehash: fb9d412196e7764326a397a4bf6e76c8723ac2ae
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87196254"
---
# <a name="compiler-warning-level-1-c4577"></a>コンパイラの警告 (レベル 1) C4577

> 例外処理モードが指定されていない ' noexcept ' が使用されています。例外での終了は保証されていません。 /EHsc を指定する

コンパイラは仕様を検出しました **`noexcept`** が、標準 C++ 例外処理が指定されていませんでした。 コンパイラは、 [/ehsc](../../build/reference/eh-exception-handling-model.md)コンパイラオプションが指定されていない限り、C++ 標準に従った例外処理を完全にサポートしていません。 この問題を解決するには、 **/ehsc**コンパイラオプションを設定します。

この警告は Visual Studio 2015 で新しく追加されたものであり、既定ではオフになっています。 詳細については、「[既定でオフになっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。
