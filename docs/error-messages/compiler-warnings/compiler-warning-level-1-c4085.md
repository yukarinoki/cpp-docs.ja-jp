---
description: '詳細情報: コンパイラの警告 (レベル 1) C4085'
title: コンパイラの警告 (レベル 1) C4085
ms.date: 11/04/2016
f1_keywords:
- C4085
helpviewer_keywords:
- C4085
ms.assetid: 2bc6eb25-058f-4597-b351-fd69587b5170
ms.openlocfilehash: 81a752e1497f0b65e99de53b14879220b58678ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155437"
---
# <a name="compiler-warning-level-1-c4085"></a>コンパイラの警告 (レベル 1) C4085

プラグマに、'on' か 'off' のパラメーターが必要です。

プラグマには、 **on** または **off** パラメーターが必要です。 このプラグマは無視されます。

次の例では C4085 が生成されます。

```cpp
// C4085.cpp
// compile with: /W1 /LD
#pragma optimize( "t", maybe )  // C4085
```
