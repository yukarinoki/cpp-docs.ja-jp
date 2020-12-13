---
description: 詳細については、「コンパイラエラー C2248」を参照してください。
title: コンパイラ エラー C2248
ms.date: 11/04/2016
f1_keywords:
- C2248
helpviewer_keywords:
- C2248
ms.assetid: 7a3ba0e8-d3b9-4bb9-95db-81ef17e31d23
ms.openlocfilehash: f2d840195fd6cdeb4cc8e1e90a06a502378ac634
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337601"
---
# <a name="compiler-error-c2248"></a>コンパイラ エラー C2248

'*member*': クラス '*class*' で宣言された '*access_level*' メンバーにアクセスできません

派生クラスのメンバーは **`private`** 、基底クラスのメンバーにアクセスできません。 **`private`** または **`protected`** クラスインスタンスのメンバーにアクセスすることはできません。

## <a name="example"></a>例

クラスの外部からクラスのプライベートメンバーまたはプロテクトメンバーにアクセスする場合、次の例では C2248 が生成されます。 この問題を解決するには、クラスの外部でこれらのメンバーに直接アクセスしないようにしてください。 パブリックメンバーのデータとメンバー関数を使用して、クラスと対話します。

```cpp
// C2248_access.cpp
// compile with: cl /EHsc /W4 C2248_access.cpp
#include <stdio.h>

class X {
public:
    int  m_publicMember;
    void setPrivateMember( int i ) {
        m_privateMember = i;
        printf_s("\n%d", m_privateMember);
    }
protected:
    int  m_protectedMember;

private:
    int  m_privateMember;
} x;

int main() {
    x.m_publicMember = 4;
    printf_s("\n%d", x.m_publicMember);
    x.m_protectedMember = 2; // C2248 m_protectedMember is protected
    x.m_privateMember = 3;   // C2248  m_privMemb is private
    x.setPrivateMember(0);   // OK uses public access function
}
```

C2248 を公開するもう1つの準拠の問題は、テンプレートのフレンドと特殊化を使用することです。 この問題を解決するには、空のテンプレートパラメーターリスト <> か、特定のテンプレートパラメーターを使用して、フレンドテンプレート関数を宣言します。

```cpp
// C2248_template.cpp
// compile with: cl /EHsc /W4 C2248_template.cpp
template<class T>
void f(T t) {
    t.i;   // C2248
}

struct S {
private:
    int i;

public:
    S() {}
    friend void f(S);   // refer to the non-template function void f(S)
    // To fix, comment out the previous line and
    // uncomment the following line.
    // friend void f<S>(S);
};

int main() {
    S s;
    f<S>(s);
}
```

C2248 を公開するもう1つの準拠の問題として、クラスのフレンドを宣言しようとしたときに、クラスがクラスのスコープ内の friend 宣言から参照できない場合があります。 この問題を解決するには、外側のクラスに友好関係を付与します。

```cpp
// C2248_enclose.cpp
// compile with: cl /W4 /c C2248_enclose.cpp
class T {
    class S {
        class E {};
    };
    friend class S::E;   // C2248
};

class A {
    class S {
        class E {};
        friend class A;  // grant friendship to enclosing class
    };
    friend class S::E;   // OK
};
```
