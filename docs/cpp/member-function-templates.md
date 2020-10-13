---
title: メンバー関数テンプレート
ms.date: 11/04/2016
helpviewer_keywords:
- function templates, member functions
ms.assetid: 83d51835-6a27-40ed-997c-7d90dc9182d8
ms.openlocfilehash: 8514c8ffe630f5bc44d8d287d6ccf08c7755e3a0
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008559"
---
# <a name="member-function-templates"></a>メンバー関数テンプレート

用語メンバー テンプレートは、メンバー関数テンプレートと入れ子になったクラス テンプレートを示します。 メンバー関数テンプレートは、クラスまたはクラス テンプレートのメンバーであるテンプレート関数です。

メンバー関数は複数のコンテキストの関数テンプレートになります。 クラス テンプレートのすべての関数はジェネリックですが、メンバー テンプレートまたはメンバー関数テンプレートとしては参照されません。 これらのメンバー関数が独自のテンプレート引数を受け取る場合、それらの関数はメンバー関数テンプレートと見なされます。

## <a name="example-declare-member-function-templates"></a>例: メンバー関数テンプレートを宣言する

非テンプレート クラスまたはテンプレート クラスのメンバー関数テンプレートは、テンプレート パラメーターを持つ関数テンプレートとして宣言されます。

```cpp
// member_function_templates.cpp
struct X
{
   template <class T> void mf(T* t) {}
};

int main()
{
   int i;
   X* x = new X();
   x->mf(&i);
}
```

## <a name="example-member-function-template-of-template-class"></a>例: テンプレートクラスのメンバー関数テンプレート

次の例は、テンプレート クラスのメンバー関数テンプレートを示します。

```cpp
// member_function_templates2.cpp
template<typename T>
class X
{
public:
   template<typename U>
   void mf(const U &u)
   {
   }
};

int main()
{
}
```

## <a name="example-define-member-templates-outside-class"></a>例: クラス外でメンバーテンプレートを定義する

```cpp
// defining_member_templates_outside_class.cpp
template<typename T>
class X
{
public:
   template<typename U>
   void mf(const U &u);
};

template<typename T> template <typename U>
void X<T>::mf(const U &u)
{
}

int main()
{
}
```

## <a name="example-templated-user-defined-conversion"></a>例: テンプレート化されたユーザー定義の変換

ローカル クラスはメンバー テンプレートを持つことができません。

メンバー テンプレート関数は、仮想関数にできません。また、基底クラスの仮想関数と同じ名前で宣言されている場合に、基底クラスから仮想関数をオーバーライドできません。

次の例は、テンプレート化されたユーザー定義の変換を示しています。

```cpp
// templated_user_defined_conversions.cpp
template <class T>
struct S
{
   template <class U> operator S<U>()
   {
      return S<U>();
   }
};

int main()
{
   S<int> s1;
   S<long> s2 = s1;  // Convert s1 using UDC and copy constructs S<long>.
}
```

## <a name="see-also"></a>関連項目

[関数テンプレート](../cpp/function-templates.md)
