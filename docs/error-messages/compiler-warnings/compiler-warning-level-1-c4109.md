---
description: '詳細情報: コンパイラの警告 (レベル 1) C4109'
title: コンパイラの警告 (レベル 1) C4109
ms.date: 11/04/2016
f1_keywords:
- C4109
helpviewer_keywords:
- C4109
ms.assetid: 9e8d95c6-e05d-47e0-bd87-78974b3cc06c
ms.openlocfilehash: 2063b6d9f85e497892bad27bc1b553872a309b17
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267509"
---
# <a name="compiler-warning-level-1-c4109"></a>コンパイラの警告 (レベル 1) C4109

予期しない識別子 'identifier' が含まれていました

予期しない識別子を表すプラグマは無視されます。

## <a name="example"></a>例

```cpp
// C4109.cpp
// compile with: /W1 /LD
#pragma init_seg( abc ) // C4109
```
