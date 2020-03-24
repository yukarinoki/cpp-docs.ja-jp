---
title: コンパイラの警告 (レベル 1) C4711
ms.date: 11/04/2016
f1_keywords:
- C4711
helpviewer_keywords:
- C4711
ms.assetid: 270506ab-fead-4328-b714-2978113be238
ms.openlocfilehash: 9e2adf3583012a670f936c2b86a9ddc393fe53c6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175338"
---
# <a name="compiler-warning-level-1-c4711"></a>コンパイラの警告 (レベル 1) C4711

インライン展開のために選択された関数 ' function '

コンパイラは、インライン展開のマークが付けられていませんが、指定された関数でインライン展開を実行しました。

C4711 は、 [/ob2](../../build/reference/ob-inline-function-expansion.md)が指定されている場合に有効になります。

インライン展開は、コンパイラの判断で実行されます。 これは、情報提供の警告です。

既定では、この警告はオフに設定されています。 警告を有効にするには[#pragma 警告](../../preprocessor/warning.md)を使用します。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。
