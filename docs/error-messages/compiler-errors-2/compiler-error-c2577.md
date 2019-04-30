---
title: コンパイラ エラー C2577
ms.date: 11/04/2016
f1_keywords:
- C2577
helpviewer_keywords:
- C2577
ms.assetid: fc79ef83-8362-40a2-9257-8037c3195ce4
ms.openlocfilehash: 4406aa90b26bc517308132ae9cccd003d44a9aad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408460"
---
# <a name="compiler-error-c2577"></a>コンパイラ エラー C2577

'member': デストラクターまたはファイナライザーは、戻り値の型を含めることはできません

デストラクターまたはファイナライザーの値を返すことができません`void`またはその他の種類。 削除、`return`デストラクターの定義からのステートメント。

## <a name="example"></a>例

次の例では、C2577 が生成されます。

```
// C2577.cpp
// compile with: /c
class A {
public:
   A() {}
   ~A(){
      return 0;   // C2577
   }
};
```