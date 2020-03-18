---
title: コンパイラエラー C3446
ms.date: 07/21/2017
f1_keywords:
- C3446
helpviewer_keywords:
- C3446
ms.assetid: 33064548-24e4-46f1-beb1-476e3c3b3fbf
ms.openlocfilehash: 0f9ebd274a90dffe00b0e8375cc374acf46e7a08
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447122"
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

