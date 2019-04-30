---
title: コンパイラ エラー C2912
ms.date: 11/04/2016
f1_keywords:
- C2912
helpviewer_keywords:
- C2912
ms.assetid: bd55cecd-ab1a-4636-ab8a-a00393fe7b3d
ms.openlocfilehash: b7f87ae2df5350fcfb2b7a662f517d8d7bd51ef8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408395"
---
# <a name="compiler-error-c2912"></a>コンパイラ エラー C2912

明示的な特殊化 'declaration' は関数テンプレートの特殊化ではありません

template 宣言がない関数は特殊化できません。

次の例では C2912 が生成されます。

```
// C2912.cpp
// compile with: /c
void f(char);
template<> void f(char);   // C2912
template<class T> void f(T);   // OK
```

このエラーは、Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果として生成されることもあります。すべての明示的な特殊化で、そのパラメーターとしてプライマリ テンプレートのパラメーターと一致するパラメーターを選択する必要があります。

```
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