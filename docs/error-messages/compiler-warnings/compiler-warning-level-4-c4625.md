---
description: '詳細情報: コンパイラの警告 (レベル 4) C4625'
title: コンパイラの警告 (レベル 4) C4625
ms.date: 11/04/2016
f1_keywords:
- C4625
helpviewer_keywords:
- C4625
ms.assetid: 4cc99e50-846c-4784-97da-48b977067851
ms.openlocfilehash: 1b154e1f2e52c21affd47c1b0fc30d29b290269e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134226"
---
# <a name="compiler-warning-level-4-c4625"></a>コンパイラの警告 (レベル 4) C4625

'derived class': 基底クラスのコピー コンストラクターがアクセスできないか削除されているため、コピー コンストラクターは暗黙的に削除済みとして定義されました

コピー コンストラクターは基底クラスで削除されているかアクセスできないため、派生クラスでは生成されません。 この型のオブジェクトをコピーしようとすると、コンパイラ エラーが発生します。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

## <a name="example"></a>例

次の例では C4625 が生成され、その修正方法が示されています。

```cpp
// C4625.cpp
// compile with: /W4 /c
#pragma warning(default : 4625)

struct A {
   A() {}

private:
   A(const A&) {}
};

struct C : private virtual A {};
struct B :  C {};   // C4625 no copy constructor

struct D : A {};
struct E :  D {};   // OK
```
