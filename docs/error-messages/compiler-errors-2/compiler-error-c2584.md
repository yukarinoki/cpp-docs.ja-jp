---
title: コンパイラ エラー C2584
ms.date: 11/04/2016
f1_keywords:
- C2584
helpviewer_keywords:
- C2584
ms.assetid: 836e2c0a-86c0-4742-b432-beb0191ad20e
ms.openlocfilehash: b61ad65555b5d5232468206f6170223c5f160a34
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360477"
---
# <a name="compiler-error-c2584"></a>コンパイラ エラー C2584

'Class': 'Base2' がベースにアクセスできる直接既に 'Base1' のベース

`Class` 既にから直接派生`Base1`します。 `Base2` 派生`Base1`します。 `Class` 派生できません`Base2`(直接) から継承しないことになりますので`Base1`ここでも、これは無効ため`Base1`直接基底クラスでは既にします。

## <a name="example"></a>例

次の例では、C2584 が生成されます。

```
// C2584.cpp
// compile with: /c
struct A1 {
   virtual int MyFunction();
};

struct A2 {
    virtual int MyFunction();
};

struct B1: public virtual A1, virtual A2 {
    virtual int MyFunction();
};

struct B2: public virtual A2, virtual A1 {
    virtual int MyFunction();
};

struct C: virtual B1, B2 {
    virtual int MyFunction();
};

struct Z : virtual B2, virtual C {   // C2584
// try the following line insted
// struct Z : virtual C {
    virtual int MyFunction();
};
```