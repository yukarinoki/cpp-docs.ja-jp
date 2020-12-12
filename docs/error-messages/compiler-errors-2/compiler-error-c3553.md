---
description: 詳細については、「コンパイラエラー C3553」を参照してください。
title: コンパイラ エラー C3553
ms.date: 11/04/2016
f1_keywords:
- C3553
helpviewer_keywords:
- C3553
ms.assetid: 7f84bf37-6419-4ad3-ab30-64266100b930
ms.openlocfilehash: 43e322b78bac05f6e301501a86ce7fbd2f27d285
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223218"
---
# <a name="compiler-error-c3553"></a>コンパイラ エラー C3553

> decltype には型ではなく式を指定してください

`decltype()` キーワードでは、型の名前ではなく、引数として式を指定する必要があります。 たとえば、次のコード フラグメントの最後のステートメントではエラー C3553 が生成されます。

```cpp
int x = 0;
decltype(x+1);
decltype(int); // C3553
```
