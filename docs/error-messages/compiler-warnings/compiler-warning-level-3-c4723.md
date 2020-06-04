---
title: コンパイラの警告 (レベル 3) C4723
ms.date: 11/04/2016
f1_keywords:
- C4723
helpviewer_keywords:
- C4723
ms.assetid: 07669d14-3fd8-4a43-94bc-b61c50e58460
ms.openlocfilehash: 3a47c6f7e83abfc785d602d8ee0734be5d0fa962
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174090"
---
# <a name="compiler-warning-level-3-c4723"></a>コンパイラの警告 (レベル 3) C4723

0による除算の可能性

除算演算の2番目のオペランドは、コンパイル時に0と評価され、未定義の結果を提供します。

この警告は、 [/og](../../build/reference/og-global-optimizations.md)または/Og. を意味する最適化オプションを使用した場合にのみ発行されます。

コンパイラで、ゼロオペランドが生成された可能性があります。
