---
description: 詳細については、「コンパイラエラー C3060」を参照してください。
title: コンパイラ エラー C3060
ms.date: 11/04/2016
f1_keywords:
- C3060
helpviewer_keywords:
- C3060
ms.assetid: 6282bb92-0546-4b59-9435-d3840bf93bdb
ms.openlocfilehash: a1efe037e75251ef452b0164a2b4e01ea4c38a1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281731"
---
# <a name="compiler-error-c3060"></a>コンパイラ エラー C3060

'member' : フレンド関数は、限定名を使用するクラス内では定義できません (宣言することのみ可能です)

修飾名を使用してフレンド関数が定義されました。これは許可されていません。

次の例では C3060 が生成されます。

```cpp
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
