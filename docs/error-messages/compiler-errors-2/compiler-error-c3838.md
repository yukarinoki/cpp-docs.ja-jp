---
description: 詳細については、「コンパイラエラー C3838」を参照してください。
title: コンパイラ エラー C3838
ms.date: 11/04/2016
f1_keywords:
- C3838
helpviewer_keywords:
- C3838
ms.assetid: d6f470c2-131a-4a8c-843a-254acd43da83
ms.openlocfilehash: 9ea5f250b7a881ab9be6724f84dac418eefc705e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249147"
---
# <a name="compiler-error-c3838"></a>コンパイラ エラー C3838

' type ' から明示的に継承することはできません

指定されたは、 `type` どのクラスの基底クラスとしても機能しません。

## <a name="example"></a>例

次の例では、C3838 が生成されます。

```cpp
// C3838a.cpp
// compile with: /clr /c
public ref class B : public System::Enum {};   // C3838
```
