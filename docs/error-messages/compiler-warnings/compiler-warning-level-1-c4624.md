---
title: コンパイラの警告 (レベル 1) C4624
ms.date: 11/04/2016
f1_keywords:
- C4624
helpviewer_keywords:
- C4624
ms.assetid: 14f61769-d92e-482b-9515-debd87b30a66
ms.openlocfilehash: 5d6e89efb042b8f757feec3911b160961e51f72a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199694"
---
# <a name="compiler-warning-level-1-c4624"></a>コンパイラの警告 (レベル 1) C4624

'derived class' : 基底クラスのデストラクターへのアクセスまたはその削除ができないため、デストラクターを暗黙的に削除済みとして定義しました

デストラクターは基底クラスでアクセスできないか削除されているため、派生クラスでは生成されません。 スタックにこの型のオブジェクトを作成しようとすると、コンパイル エラーが発生します。

次の例では、C4624 を生成し、その修正方法を示しています。

```cpp
// C4624.cpp
// compile with: /W1 /c
class B {
// Uncomment the following line to fix.
// public:
   ~B();
};

class D : public B {};   // C4624 B's destructor not public
```
