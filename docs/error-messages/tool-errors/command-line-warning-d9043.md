---
title: コマンド ラインの警告 D9043
ms.date: 11/04/2016
f1_keywords:
- D9043
helpviewer_keywords:
- D9043
ms.assetid: 9263e28d-217b-414c-bfb6-86efd3c27a77
ms.openlocfilehash: 62834c5f245bc1c0f6197638e4608b7fe71e7eb1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586031"
---
# <a name="command-line-warning-d9043"></a>コマンド ラインの警告 D9043

無効な値 'warning_level' の 'compiler_option';'4999;' と仮定した場合コード分析の警告が警告レベルに関連付けられていません。

## <a name="example"></a>例

次の例では、c9043 エラーが生成されます。

```
// D9043.cpp
// compile with: /analyze /w16001
// D9043 warning expected
int main() {}
```