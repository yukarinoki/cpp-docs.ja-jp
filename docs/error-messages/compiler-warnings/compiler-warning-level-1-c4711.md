---
title: コンパイラの警告 (レベル 1) C4711 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4711
dev_langs:
- C++
helpviewer_keywords:
- C4711
ms.assetid: 270506ab-fead-4328-b714-2978113be238
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d184d5043dad1138f774ca7288a773bcc38c6d9f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069948"
---
# <a name="compiler-warning-level-1-c4711"></a>コンパイラの警告 (レベル 1) C4711

関数 'function' がインライン展開の選択

コンパイラは実行のマークされていますが、指定された関数のインライン展開インライン化します。

場合に、C4711 が有効になっている[/Ob2](../../build/reference/ob-inline-function-expansion.md)を指定します。

インライン展開は、コンパイラの裁量で実行されます。 これは、情報提供の警告です。

既定では、この警告はオフに設定されています。 警告を有効にするには、 [#pragma warning](../../preprocessor/warning.md)します。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。