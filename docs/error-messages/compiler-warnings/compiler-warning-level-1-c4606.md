---
title: コンパイラの警告 (レベル 1) C4606
ms.date: 11/04/2016
f1_keywords:
- C4606
helpviewer_keywords:
- C4606
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
ms.openlocfilehash: 9b38e9670157fd15dc7c4b6a96ced7ad40c43e34
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185998"
---
# <a name="compiler-warning-level-1-c4606"></a>コンパイラの警告 (レベル 1) C4606

\#プラグマ警告: ' warning_number ' は無視されます。コード分析の警告は警告レベルに関連付けられていません

コード分析の警告の場合、`error`、`once`、および `default` のみが[warning](../../preprocessor/warning.md)プラグマでサポートされます。

## <a name="example"></a>例

次の例では、C4606 が生成されます。

```cpp
// C4606.cpp
// compile with: /c /W1
#pragma warning(1: 6001)   // C4606
#pragma warning(once: 6001)   // OK
```
