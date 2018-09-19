---
title: コンパイラ エラー C3675 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3675
dev_langs:
- C++
helpviewer_keywords:
- C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c4b6656753ab4a611dcb80d1473e0b44bf47a270
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094781"
---
# <a name="compiler-error-c3675"></a>コンパイラ エラー C3675

'function': 'property' が定義されているためには、予約されています。

Get および set アクセサー メソッドと、コンパイラは生成単純なプロパティを宣言するときに名前が、プログラムのスコープ内に存在します。  コンパイラによって生成された名前は、get _ と set _ プロパティの名前を付けることによって形成されます。  そのため、コンパイラによって生成されたアクセサーとして同じ名前を持つ関数を宣言できません。

詳細については、「 [property](../../windows/property-cpp-component-extensions.md) 」を参照してください。

## <a name="example"></a>例

次の例では、C3675 が生成されます。

```
// C3675.cpp
// compile with: /clr /c
ref struct C {
public:
   property int Size;
   int get_Size() { return 0; }   // C3675
};
```