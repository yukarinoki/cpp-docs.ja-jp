---
title: コンパイラ エラー C3675
ms.date: 11/04/2016
f1_keywords:
- C3675
helpviewer_keywords:
- C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
ms.openlocfilehash: e29e536bf89aef887dc043327e4b4596703d0538
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775193"
---
# <a name="compiler-error-c3675"></a>コンパイラ エラー C3675

'function': 'property' が定義されているためには、予約されています。

Get および set アクセサー メソッドと、コンパイラは生成単純なプロパティを宣言するときに名前が、プログラムのスコープ内に存在します。  コンパイラによって生成された名前は、get _ と set _ プロパティの名前を付けることによって形成されます。  そのため、コンパイラによって生成されたアクセサーとして同じ名前を持つ関数を宣言できません。

詳細については、「 [property](../../extensions/property-cpp-component-extensions.md) 」を参照してください。

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