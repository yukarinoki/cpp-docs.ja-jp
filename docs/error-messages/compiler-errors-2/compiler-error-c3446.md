---
description: 詳細については、「コンパイラエラー C3446」を参照してください。
title: コンパイラエラー C3446
ms.date: 07/21/2017
f1_keywords:
- C3446
helpviewer_keywords:
- C3446
ms.assetid: 33064548-24e4-46f1-beb1-476e3c3b3fbf
ms.openlocfilehash: 442ac07c1684278e76f86531d1c28de6507eb999
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113673"
---
# <a name="compiler-error-c3446"></a>コンパイラエラー C3446

>'*class*': 既定のメンバー初期化子は、値クラスのメンバーに許可されていません

Visual Studio 2015 以前では、コンパイラは、値クラスのメンバーの既定のメンバーの初期化子を許可しました (ただし無視しました)。 値クラスの既定の初期化子は、常にメンバーを 0 に初期化します。既定のコンストラクターは許可されません。 Visual Studio 2017 年では、この例に示すように、既定メンバー初期化子は、コンパイラ エラーを発生させます。

## <a name="example"></a>例

次の例では、Visual Studio 2017 以降で C3446 が生成されます。

```cpp
// C3446.cpp
value struct V
{
       int i = 0; // error C3446: 'V::i': a default member initializer
                  // is not allowed for a member of a value class
       int j {0}; // C3446
};
```

エラーを修正するには、初期化子を削除します。

```cpp
// C3446b.cpp
value struct V
{
       int i;
       int j;
};
```
