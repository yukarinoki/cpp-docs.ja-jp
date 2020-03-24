---
title: if-else ステートメント (C++)
ms.date: 07/20/2019
description: のC++ if-else ステートメントを使用して、条件分岐を制御します。
f1_keywords:
- else_cpp
- if_cpp
helpviewer_keywords:
- if keyword [C++]
- else keyword [C++]
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
ms.openlocfilehash: fd2736d80d68249773c9aa6cf7cb9edffdaadac4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178432"
---
# <a name="if-else-statement-c"></a>if-else ステートメント (C++)

条件分岐を制御します。 If*ブロック*内のステートメントは、 *if 式*が0以外の値 (または TRUE) に評価される場合にのみ実行されます。 *Expression*の値が0以外の場合は、*ステートメント*とブロック内の他のすべてのステートメントが実行され、else ブロック (存在する場合) がスキップされます。 *Expression*の値が0の場合は、if ブロックがスキップされ、else ブロック (存在する場合) が実行されます。 0以外に評価される式は、

- TRUE
- null 以外のポインター。
- 0以外の算術値。
- 算術、ブール型、またはポインター型への明確な変換を定義するクラス型。 (変換の詳細については、「[標準変換](../cpp/standard-conversions.md)」を参照してください)。

## <a name="syntax"></a>構文

```cpp
if ( expression )
{
   statement1;
   ...
}
else  // optional
{
   statement2;
   ...
}

// C++17 - Visual Studio 2017 version 15.3 and later:
if ( initialization; expression )
{
   statement1;
   ...
}
else  // optional
{
   statement2;
   ...
}

// C++17 - Visual Studio 2017 version 15.3 and later:
if constexpr (expression)
{
    statement1;
    ...
}
else  // optional
{
   statement2;
   ...
}
```

## <a name="example"></a>例

```cpp
// if_else_statement.cpp
#include <iostream>

using namespace std;

class C
{
    public:
    void do_something(){}
};
void init(C){}
bool is_true() { return true; }
int x = 10;

int main()
{
    if (is_true())
    {
        cout << "b is true!\n";  // executed
    }
    else
    {
        cout << "b is false!\n";
    }

    // no else statement
    if (x == 10)
    {
        x = 0;
    }

    C* c;
    init(c);
    if (c)
    {
        c->do_something();
    }
    else
    {
        cout << "c is null!\n";
    }
}
```

## <a name="if-statement-with-an-initializer"></a><a name="if_with_init"></a>if ステートメントと初期化子

**Visual Studio 2017 バージョン15.3 以降**( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)で利用可能): **if**ステートメントに、名前付き変数を宣言して初期化する式を含めることもできます。 変数が if ブロックのスコープ内でのみ必要な場合は、この形式の if ステートメントを使用します。

## <a name="example"></a>例

```cpp
#include <iostream>
#include <mutex>
#include <map>
#include <string>
#include <algorithm>

using namespace std;

map<int, string> m;
mutex mx;
bool shared_flag; // guarded by mx
void unsafe_operation() {}

int main()
{

    if (auto it = m.find(10); it != m.end())
    {
        cout << it->second;
        return 0;
    }

    if (char buf[10]; fgets(buf, 10, stdin))
    {
        m[0] += buf;
    }

    if (lock_guard<mutex> lock(mx); shared_flag)
    {
        unsafe_operation();
        shared_flag = false;
    }

    string s{ "if" };
    if (auto keywords = { "if", "for", "while" }; any_of(keywords.begin(), keywords.end(), [&s](const char* kw) { return s == kw; }))
    {
        cout << "Error! Token must not be a keyword\n";
    }
}
```

**If**ステートメントのすべての形式で、構造体以外の任意の値を持つことができる*expression*は、すべての副作用を含めて評価されます。 *ステートメント*s に[break](../cpp/break-statement-cpp.md)、 [continue](../cpp/continue-statement-cpp.md)、または[goto](../cpp/goto-statement-cpp.md)が含まれて**いる場合**を除き、if ステートメントからプログラムの次のステートメントに制御が渡されます。

`if...else` ステートメントの**else**句は、対応する**else**ステートメントが含まれていない同じスコープ内の最も近い**if**ステートメントに関連付けられています。

## <a name="a-nameif_constexpr-if-constexpr-statements"></a><a name="if_constexpr"> constexpr ステートメント

**Visual Studio 2017 バージョン15.3 以降**( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)で利用可能): 関数テンプレートで**は、if constexpr**ステートメントを使用して、複数の関数オーバーロードに頼ることなく、コンパイル時の分岐決定を行うことができます。 たとえば、パラメーターのアンパックを処理する1つの関数を記述できます (ゼロパラメーターのオーバーロードは必要ありません)。

```cpp
template <class T, class... Rest>
void f(T&& t, Rest&&... r)
{
    // handle t
    do_something(t);

    // handle r conditionally
    if constexpr (sizeof...(r))
    {
        f(r...);
    }
    else
    {
        g(r...);
    }
}
```

## <a name="see-also"></a>参照

[選択ステートメント](../cpp/selection-statements-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[switch ステートメント (C++)](../cpp/switch-statement-cpp.md)
