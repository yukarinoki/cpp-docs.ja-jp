---
title: コンパイラ エラー C3454 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3454
dev_langs:
- C++
helpviewer_keywords:
- C3454
ms.assetid: dc4e6d57-5b4d-4114-8d6f-22f9ae62925b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f85ff8c33cc43bdc1af9a3bf02d9240a0fd5e09c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098772"
---
# <a name="compiler-error-c3454"></a>コンパイラ エラー C3454

[attribute] はクラス宣言では使用できません

クラスは、属性になるように定義する必要があります。

詳細については、「 [attribute](../../windows/attribute.md)」を参照してください。

## <a name="example"></a>例

次の例では C3454 が生成されます。

```
// C3454.cpp
// compile with: /clr /c
using namespace System;

[attribute]   // C3454
ref class Attr1;

[attribute]   // OK
ref class Attr2 {};
```