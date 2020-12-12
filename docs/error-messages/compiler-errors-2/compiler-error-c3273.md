---
description: 詳細については、「コンパイラエラー C3273」を参照してください。
title: コンパイラ エラー C3273
ms.date: 11/04/2016
f1_keywords:
- C3273
helpviewer_keywords:
- C3273
ms.assetid: 1d2ce9d9-222b-4cab-94e2-d2c1a9f5ebe0
ms.openlocfilehash: 23216089bb6d4a963f04201e742af2f50818efcc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185766"
---
# <a name="compiler-error-c3273"></a>コンパイラ エラー C3273

__finally はアンマネージ コード内の例外ブロックで使用できません。

次の例では C3273 が生成されます。

```cpp
// C3273.cpp
// compile with: /GX
int main()
{
   try
   {
   }
   catch (int)
   {
   }
   __finally   // C3273, remove __finally clause
   {
   }
}
```
