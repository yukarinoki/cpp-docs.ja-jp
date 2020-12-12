---
description: '詳細情報: コンパイラの警告 (レベル 1) C4081'
title: コンパイラの警告 (レベル 1) C4081
ms.date: 11/04/2016
f1_keywords:
- C4081
helpviewer_keywords:
- C4081
ms.assetid: 6f656373-a080-4989-bbc9-e2f894b03293
ms.openlocfilehash: 01c03255361676cfbe9876c73d77a7e2c9356eda
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278156"
---
# <a name="compiler-warning-level-1-c4081"></a>コンパイラの警告 (レベル 1) C4081

'token1' が必要でしたが、'token2' が見つかりました

コンパイラでは、このコンテキストで別のトークンが必要でした。

## <a name="example"></a>例

```cpp
// C4081.cpp
// compile with: /W1 /LD
#pragma optimize) "l", on )   // C4081
```
