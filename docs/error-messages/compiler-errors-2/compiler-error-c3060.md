---
title: コンパイラ エラー C3060
ms.date: 11/04/2016
f1_keywords:
- C3060
helpviewer_keywords:
- C3060
ms.assetid: 6282bb92-0546-4b59-9435-d3840bf93bdb
ms.openlocfilehash: c77af7fa1220aa5211d480cddf3bf0979c642ade
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62265543"
---
# <a name="compiler-error-c3060"></a>コンパイラ エラー C3060

'member' : フレンド関数は、限定名を使用するクラス内では定義できません (宣言することのみ可能です)

修飾名を使用してフレンド関数が定義されました。これは許可されていません。

次の例では C3060 が生成されます。

```
// C3060.cpp
class A {
public:
   void func();
};

class C {
public:
   friend void A::func() { }   // C3060
   // Try the following line and the out of class definition:
   // friend void A::func();
};

// void A::func(){}
```