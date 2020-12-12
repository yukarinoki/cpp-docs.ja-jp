---
description: '詳細情報: コンパイラの警告 (レベル 1) C4810'
title: コンパイラの警告 (レベル 1) C4810
ms.date: 11/04/2016
f1_keywords:
- C4810
helpviewer_keywords:
- C4810
ms.assetid: 39e2cae0-9c1c-4ac1-aaa0-5f661d06085b
ms.openlocfilehash: 4cebcf6b4cabc2539d5fcf25363f573a704ae577
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328088"
---
# <a name="compiler-warning-level-1-c4810"></a>コンパイラの警告 (レベル 1) C4810

pragma の値 pack(show) == n

この警告は、 **pack** プラグマの [show](../../preprocessor/pack.md) オプションを使用すると発行されます。 *n* は pack の現在の値です。

たとえば、次のコードは、pack プラグマで C4810 警告がどのように発生するかを示しています。

```cpp
// C4810.cpp
// compile with: /W1 /LD
// C4810 expected
#pragma pack(show)
#pragma pack(4)
#pragma pack(show)
```
