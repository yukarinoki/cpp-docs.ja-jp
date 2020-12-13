---
description: '詳細情報: コンパイラの警告 (レベル 1) C4606'
title: コンパイラの警告 (レベル 1) C4606
ms.date: 11/04/2016
f1_keywords:
- C4606
helpviewer_keywords:
- C4606
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
ms.openlocfilehash: b347be103d2a84dba2143861cb35b67f3d38fb9c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341738"
---
# <a name="compiler-warning-level-1-c4606"></a>コンパイラの警告 (レベル 1) C4606

\#プラグマ警告: ' warning_number ' は無視されます。コード分析の警告は警告レベルに関連付けられていません

コード分析の警告の場合、、、 `error` `once` およびのみ `default` が [warning](../../preprocessor/warning.md) プラグマでサポートされます。

## <a name="example"></a>例

次の例では、C4606 が生成されます。

```cpp
// C4606.cpp
// compile with: /c /W1
#pragma warning(1: 6001)   // C4606
#pragma warning(once: 6001)   // OK
```
