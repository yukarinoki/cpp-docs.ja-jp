---
title: コンパイラの警告 (レベル 3) C4723
description: 0で除算する可能性のある MSVC compiler warning C4723 について説明します。
ms.date: 07/08/2020
f1_keywords:
- C4723
helpviewer_keywords:
- C4723
ms.assetid: 07669d14-3fd8-4a43-94bc-b61c50e58460
ms.openlocfilehash: 57a5758d8a3198d7701bdead2e1bbe567b72701a
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180995"
---
# <a name="compiler-warning-level-3-c4723"></a>コンパイラの警告 (レベル 3) C4723

> `potential divide by 0`

除算演算の2番目のオペランドは、コンパイル時に0と評価され、未定義の結果を提供します。

この警告は、最適化が有効な場合にのみ発行されます。

コンパイラで、ゼロオペランドが生成された可能性があります。
