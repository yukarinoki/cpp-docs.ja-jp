---
description: 詳細については、「コンパイラエラー C2850」を参照してください。
title: コンパイラ エラー C2850
ms.date: 11/04/2016
f1_keywords:
- C2850
helpviewer_keywords:
- C2850
ms.assetid: f3efe86c-4168-4e76-a133-3f8314c69f51
ms.openlocfilehash: 820aa0e12db5ffe7e6d7b7bf0e87282f53e8477c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260164"
---
# <a name="compiler-error-c2850"></a>コンパイラ エラー C2850

' construct ': ファイルスコープでのみ使用できます。入れ子になったコンストラクトに含まれていない可能性があります

一部のプラグマなどのコンストラクトは、グローバルスコープでのみ使用できます。

次の例では、C2850 が生成されます。

```cpp
// C2850.cpp
// compile with: /c /Yc
// try the following line instead
// #pragma hdrstop
namespace X {
   #pragma hdrstop   // C2850
};
```
