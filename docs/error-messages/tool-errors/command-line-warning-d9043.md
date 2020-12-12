---
description: 詳細については、Command-Line Warning D9043 を参照してください。
title: コマンド ラインの警告 D9043
ms.date: 11/04/2016
f1_keywords:
- D9043
helpviewer_keywords:
- D9043
ms.assetid: 9263e28d-217b-414c-bfb6-86efd3c27a77
ms.openlocfilehash: ac61626f21465056ea96efe784e19405481f1b0f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119750"
---
# <a name="command-line-warning-d9043"></a>コマンド ラインの警告 D9043

' compiler_option ' の値 ' warning_level ' が無効です。' 4999 ' を想定しています。コード分析の警告は警告レベルに関連付けられていません

## <a name="example"></a>例

次の例では、C9043 が生成されます。

```cpp
// D9043.cpp
// compile with: /analyze /w16001
// D9043 warning expected
int main() {}
```
