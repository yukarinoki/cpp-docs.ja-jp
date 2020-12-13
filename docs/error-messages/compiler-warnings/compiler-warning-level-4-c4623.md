---
description: '詳細情報: コンパイラの警告 (レベル 4) C4623'
title: コンパイラの警告 (レベル 4) C4623
ms.date: 11/04/2016
f1_keywords:
- C4623
helpviewer_keywords:
- C4623
ms.assetid: e630d8d0-f6ea-469c-a74f-07b027587225
ms.openlocfilehash: 3e10b83af1ba38d50307abdc87f3fde3b9b30417
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134239"
---
# <a name="compiler-warning-level-4-c4623"></a>コンパイラの警告 (レベル 4) C4623

'`derived class`' : 基底クラスの既定のコンストラクターがアクセスできないか削除されているため、既定のコンストラクターは暗黙的に削除済みとして定義されました

コンストラクターは基底クラスでアクセスできないため、派生クラスでは生成されません。 スタックにこの型のオブジェクトを作成しようとすると、コンパイル エラーが発生します。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

## <a name="example"></a>例

次の例では C4623 警告が生成されます。

```cpp
// C4623.cpp
// compile with: /W4
#pragma warning(default : 4623)
class B {
   B();
};

class C {
public:
   C();
};

class D : public B {};   // C4623 - to fix, make B's constructor public
class E : public C {};   // OK - class C constructor is public

int main() {
   // D d;  will cause an error
}
```
