---
description: 詳細については、「コンパイラエラー C2506」を参照してください。
title: コンパイラ エラー C2506
ms.date: 11/04/2016
f1_keywords:
- C2506
helpviewer_keywords:
- C2506
ms.assetid: cfed21cd-2404-46f2-985e-d0c2c3820830
ms.openlocfilehash: 28af99e418d8c058fa9b28b5fd581a44c0180065
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212988"
---
# <a name="compiler-error-c2506"></a>コンパイラ エラー C2506

' member ': ' __declspec (修飾子) ' はこのシンボルに適用できません

マネージクラスの静的メンバーに対して、プロセスごとまたは appdomain ごとの宣言を行うことはできません。

詳細については、「 [appdomain](../../cpp/appdomain.md) 」を参照してください。

## <a name="example"></a>例

次の例では、C2506 が生成されます。

```cpp
// C2506.cpp
// compile with: /clr /c
ref struct R {
   __declspec(process) static int n;   // C2506
   int o;   // OK
};
```
