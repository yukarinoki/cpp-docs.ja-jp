---
description: 詳細については、「コンパイラエラー C3452」を参照してください。
title: コンパイラ エラー C3452
ms.date: 11/04/2016
f1_keywords:
- C3452
helpviewer_keywords:
- C3452
ms.assetid: e5293dcf-cb70-4133-ae2a-0bb496950ba0
ms.openlocfilehash: 7153088ccd132112f47823cd1eb1147480615fc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315986"
---
# <a name="compiler-error-c3452"></a>コンパイラ エラー C3452

リスト引数メンバーは定数ではありません

定数 (コンパイル時に評価できる値) を必要としていた属性に引数が渡されました。

## <a name="example"></a>例

次の例では C3452 が生成されます。

```cpp
// C3452.cpp
// compile with: /c
int i;
[module( name="mod", type=dll, custom={i} ) ];   // C3452
// try the following line instead
// [module( name="mod", type=dll, custom={"a"} ) ];
```
