---
title: コンパイラ エラー C2775
ms.date: 11/04/2016
f1_keywords:
- C2775
helpviewer_keywords:
- C2775
ms.assetid: 9c488508-ade0-48f1-b94f-d538d15f807a
ms.openlocfilehash: b0f04a64354f549115c8636cf6130d6e96470016
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257193"
---
# <a name="compiler-error-c2775"></a>コンパイラ エラー C2775

'identifier': このプロパティに関連付けられた 'get' メソッドはありません

宣言されたデータ メンバー、[プロパティ](../../cpp/property-cpp.md)拡張属性がない、`get`関数指定が、その値を取得しようとする式。

次の例では、C2775 が生成されます。

```
// C2775.cpp
struct A {
   __declspec(property(put=PutProp2, get=GetProp2)) int prop2;
   int GetProp2(){return 0;}
   void PutProp2(int){}

   __declspec(property(put=PutProp)) int prop;
   int PutProp(void){}

};

int main() {
   A* pa = new A;
   int x;
   x = pa->prop;   // C2775
   x = pa->prop2;
}
```