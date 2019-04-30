---
title: コンパイラの警告 (レベル 1) C4606
ms.date: 11/04/2016
f1_keywords:
- C4606
helpviewer_keywords:
- C4606
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
ms.openlocfilehash: e471ca3e478d1166b150e49bf25efa4b9d5803cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402516"
---
# <a name="compiler-warning-level-1-c4606"></a>コンパイラの警告 (レベル 1) C4606

\#pragma 警告: 'warning_number' を無視する場合コード分析の警告が警告レベルに関連付けられていません。

コード分析の警告のみ`error`、 `once`、および`default`でサポートされる、[警告](../../preprocessor/warning.md)プラグマ。

## <a name="example"></a>例

次の例では、C4606 が生成されます。

```
// C4606.cpp
// compile with: /c /W1
#pragma warning(1: 6001)   // C4606
#pragma warning(once: 6001)   // OK
```