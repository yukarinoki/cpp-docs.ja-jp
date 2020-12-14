---
description: 詳細については、「コンパイラエラー C3645」を参照してください。
title: コンパイラ エラー C3645
ms.date: 11/04/2016
f1_keywords:
- C3645
helpviewer_keywords:
- C3645
ms.assetid: 346da528-ae86-4cd0-9654-f41bee26ac0d
ms.openlocfilehash: 198b22b80a4975d8bd6fab130c075621f248a93c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203771"
---
# <a name="compiler-error-c3645"></a>コンパイラ エラー C3645

' function ': __clrcall は、ネイティブコードにコンパイルされた関数では使用できません

関数にいくつかのキーワードが存在すると、関数がネイティブにコンパイルされます。

## <a name="example"></a>例

次の例では、C3645 が生成されます。

```cpp
// C3645.cpp
// compile with: /clr /c
#pragma unmanaged
int __clrcall dog() {}   // C3645
```
