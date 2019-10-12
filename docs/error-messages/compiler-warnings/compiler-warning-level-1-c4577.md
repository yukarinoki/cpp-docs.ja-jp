---
title: コンパイラの警告 C4577
description: コンパイラの警告 C4577 の説明と解決策。
ms.date: 09/18/2019
helpviewer_keywords:
- C4577
ms.openlocfilehash: 637023f4c27f93238fbbd13b4a0e652e6cd958e0
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71241127"
---
# <a name="compiler-warning-level-1-c4577"></a>コンパイラの警告 (レベル 1) C4577

> 例外処理モードが指定されていない ' noexcept ' が使用されています。例外での終了は保証されていません。 /EHsc を指定する

コンパイラは`noexcept`仕様を検出しましたC++が、標準の例外処理が指定されていませんでした。 [/Ehsc](../../build/reference/eh-exception-handling-model.md) コンパイラオプションが指定されていないC++場合、コンパイラは標準に従って例外処理を完全にサポートしません。 この問題を解決するには、 **/ehsc**コンパイラオプションを設定します。

この警告は Visual Studio 2015 で新しく追加されたものであり、既定ではオフになっています。 詳細については、「[既定でオフになっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。
