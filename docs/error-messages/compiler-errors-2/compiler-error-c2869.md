---
description: 詳細については、「コンパイラエラー C2869」を参照してください。
title: コンパイラ エラー C2869
ms.date: 11/04/2016
f1_keywords:
- C2869
helpviewer_keywords:
- C2869
ms.assetid: 6e30c001-47f3-4101-b9f1-cc542c9fffae
ms.openlocfilehash: 53171af019de9e099e2135747a8ce4d63c526b1e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333779"
---
# <a name="compiler-error-c2869"></a>コンパイラ エラー C2869

' name ': 名前空間として既に定義されています

名前空間として既に使用されている名前を再利用することはできません。

次の例では、C2869 が生成されます。

```cpp
// C2869.cpp
// compile with: /c
namespace A { int i; };

class A {};   // C2869, A is already used
```
