---
description: '詳細情報: コンパイラの警告 (レベル 4) C4516'
title: コンパイラの警告 (レベル 4) C4516
ms.date: 11/04/2016
f1_keywords:
- C4516
helpviewer_keywords:
- C4516
ms.assetid: 6677bb1f-d26e-4ab9-8644-6b5a2a8f4ff8
ms.openlocfilehash: 945cf057b030a032afc2dd6dd3084df482f8a9a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241210"
---
# <a name="compiler-warning-level-4-c4516"></a>コンパイラの警告 (レベル 4) C4516

' class:: symbol ': アクセス宣言は推奨されていません。メンバー using 宣言は、より優れた代替手段を提供します。

ANSI C++ 委員会がアクセス宣言を宣言しています (using キーワードを [使用](../../cpp/using-declaration.md) せずに派生クラスのメンバーのアクセスを変更する)。 アクセス宣言は、今後のバージョンの C++ ではサポートされない場合があります。

次の例では、C4516 が生成されます。

```cpp
// C4516.cpp
// compile with: /W4
class A
{
public:
   void x(char);
};

class B : protected A
{
public:
   A::x;  // C4516 on access-declaration
   // use the following line instead
   // using A::x; // using-declaration, ok
};

int main()
{
}
```
