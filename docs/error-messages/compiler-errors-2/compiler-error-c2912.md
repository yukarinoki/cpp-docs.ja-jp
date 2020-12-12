---
description: 詳細については、「コンパイラエラー C2912」を参照してください。
title: コンパイラ エラー C2912
ms.date: 11/04/2016
f1_keywords:
- C2912
helpviewer_keywords:
- C2912
ms.assetid: bd55cecd-ab1a-4636-ab8a-a00393fe7b3d
ms.openlocfilehash: 405c4acb5da6aa83e4b5d45e2297f1259a0d932e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270525"
---
# <a name="compiler-error-c2912"></a>コンパイラ エラー C2912

明示的な特殊化 'declaration' は関数テンプレートの特殊化ではありません

template 宣言がない関数は特殊化できません。

次の例では C2912 が生成されます。

```cpp
// C2912.cpp
// compile with: /c
void f(char);
template<> void f(char);   // C2912
template<class T> void f(T);   // OK
```

このエラーは、Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果として生成されることもあります。すべての明示的な特殊化で、そのパラメーターとしてプライマリ テンプレートのパラメーターと一致するパラメーターを選択する必要があります。

```cpp
// C2912b.cpp
class CF {
public:
   template <class A> CF(const A& a) {}   // primary template

   // attempted explicit specialization
   template <> CF(const char* p) {}   // C2912

   // try the following line instead
   // template <> CF(const char& p) {}
};
```
