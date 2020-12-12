---
description: 詳細については、「コンパイラエラー C2337」を参照してください。
title: コンパイラ エラー C2337
ms.date: 09/19/2019
f1_keywords:
- C2337
helpviewer_keywords:
- C2337
ms.assetid: eccc9178-a15e-42cd-bbd0-3cea7cf2d55b
ms.openlocfilehash: 44def6fe9c220699e3687ce9b843f977528b5e15
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234853"
---
# <a name="compiler-error-c2337"></a>コンパイラ エラー C2337

> '*attribute name*': 属性が見つかりません

コードでは、このコンテキストでサポートされていない属性を使用しています。 または、このバージョンのコンパイラでは属性を使用できません。 この問題を解決するには、サポートされていない属性を削除します。

次の例では C2337 が生成されます。

```cpp
// C2337.cpp
// compile with: /c
[emitidl];
[module(name="x")];
[grasshopper]   // C2337, not a supported attribute
class a{};
```
