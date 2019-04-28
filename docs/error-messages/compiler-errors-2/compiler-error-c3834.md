---
title: コンパイラ エラー C3834
ms.date: 11/04/2016
f1_keywords:
- C3834
helpviewer_keywords:
- C3834
ms.assetid: 059e0dc4-300b-4e74-b6c2-41a57831fe2a
ms.openlocfilehash: 9f2bb96beaac8ede75863084c8ebf8345c940f53
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327510"
---
# <a name="compiler-error-c3834"></a>コンパイラ エラー C3834

不正の明示的な; ピンされたポインターへキャストピンされたローカル変数を使用して、代わりに

固定ポインターに明示的なキャストは許可されません。

## <a name="example"></a>例

次の例では、C3834 が生成されます。

```
// C3834.cpp
// compile with: /clr
int main() {
   int x = 33;

   pin_ptr<int> p = safe_cast<pin_ptr<int> >(&x);   // C3834
   pin_ptr<int> p2 = &x;   // OK
}
```
