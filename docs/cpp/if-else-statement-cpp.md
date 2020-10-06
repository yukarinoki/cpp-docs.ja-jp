---
title: if-else ステートメント (C++)
description: If-else、if-else with initializer、および if-constexpr ステートメントを使用して条件分岐を制御します。
ms.date: 10/02/2020
f1_keywords:
- else_cpp
- if_cpp
helpviewer_keywords:
- if keyword [C++]
- else keyword [C++]
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
ms.openlocfilehash: 20d828bf00a79687fe0a9fffbeb1a9cc56fae08c
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765296"
---
# <a name="if-else-statement-c"></a>if-else ステートメント (C++)

If-else ステートメントは、条件分岐を制御します。 が *`if-branch`* *`condition`* 0 以外の値 (または) に評価される場合にのみ、内のステートメントが実行され **`true`** ます。 の値が0以外の場合は、 *`condition`* 次のステートメントが実行され、省略可能なの後のステートメントがスキップされ **`else`** ます。 それ以外の場合、次のステートメントがスキップされ、がある場合は **`else`** 、に続くステートメントが実行され **`else`** ます。

*`condition`* 0以外に評価される式は次のとおりです。

- **`true`**
- null 以外のポインター。
- 0以外の算術値。
- 算術型、ブール型、またはポインター型への明確な変換を定義するクラス型。 (変換の詳細については、「 [標準変換](../cpp/standard-conversions.md)」を参照してください)。

## <a name="syntax"></a>構文

*`init-statement`*:\
&emsp; *`expression-statement`*\
&emsp; *`simple-declaration`*

*`condition`*:\
&emsp; *`expression`*\
&emsp;*`attribute-specifier-seq`* <sub>*opt*</sub> *`decl-specifier-seq`* 選択 *`declarator`**`brace-or-equal-initializer`*

*`statement`*:\
&emsp; *`expression-statement`*\
&emsp; *`compound-statement`*

*`expression-statement`*:\
&emsp;*`expression`*<sub>*選択*</sub>**`;`**

*`compound-statement`*:\
&emsp;**`{`** *`statement-seq`* <sub>*選択*</sub>**`}`**

*`statement-seq`*:\
&emsp; *`statement`*\
&emsp; *`statement-seq`* *`statement`*

*`if-branch`*:\
&emsp; *`statement`*

*`else-branch`*:\
&emsp; *`statement`*

*`selection-statement`*:\
&emsp;**`if`** **`constexpr`** <sub>*opt*</sub><sup>17</sup> **`(`** *`init-statement`* <sub>*opt*</sub><sup>17</sup> 17 *`condition`* **`)`***`if-branch`*\
&emsp;**`if`** **`constexpr`** <sub>*opt*</sub><sup>17</sup> **`(`** *`init-statement`* <sub>*opt*</sub><sup>17</sup> 17 *`condition`* **`)`** *`if-branch`* **`else`***`else-branch`*

<sup>17</sup> この省略可能な要素は、c++ 17 以降で使用できます。

## <a name="if-else-statements"></a>if-else ステートメント

ステートメントのすべての形式で、 **`if`** *`condition`* 構造体以外の任意の値を持つことができるすべての副作用が評価されます。 **`if`** が実行されたか、、、 *`if-branch`* *`else-branch`* またはが含まれていない限り、ステートメントからプログラムの次のステートメントに制御が渡され [`break`](../cpp/break-statement-cpp.md) [`continue`](../cpp/continue-statement-cpp.md) [`goto`](../cpp/goto-statement-cpp.md) ます。

**`else`** ステートメントの句は、 `if...else` **`if`** 同じスコープ内で、対応するステートメントが含まれていない最も近い前のステートメントに関連付けられてい **`else`** ます。

### <a name="example"></a>例

このサンプルコードでは **`if`** 、次のいずれかを使用し、使用しないステートメントをいくつか示し **`else`** ます。

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

## <a name="if-statement-with-an-initializer"></a><a name="if_with_init"></a> if ステートメントと初期化子

C++ 17 以降では、 **`if`** ステートメントに *`init-statement`* 名前付き変数を宣言して初期化する式を含めることもできます。 If ステートメントのスコープ内でのみ変数が必要な場合は、この形式の if ステートメントを使用します。 **Microsoft 固有**: このフォームは、Visual Studio 2017 バージョン15.3 以降で使用でき、少なくともコンパイラオプションが必要です [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) 。

### <a name="example"></a>例

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

## <a name="a-nameif_constexpr-if-constexpr-statements"></a><a name="if_constexpr"> constexpr ステートメントの場合

C++ 17 以降では、関数テンプレートのステートメントを使用して、 **`if constexpr`** 複数の関数オーバーロードに頼ることなく、コンパイル時の分岐を決定することができます。 **Microsoft 固有**: このフォームは、Visual Studio 2017 バージョン15.3 以降で使用でき、少なくともコンパイラオプションが必要です [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) 。

### <a name="example"></a>例

この例は、パラメーターのアンパックを処理する1つの関数を記述する方法を示しています。 ゼロパラメーターのオーバーロードは必要ありません。

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

## <a name="see-also"></a>関連項目

[選択ステートメント](../cpp/selection-statements-cpp.md)\
[Keywords](../cpp/keywords-cpp.md)\
[`switch` ステートメント (C++)](../cpp/switch-statement-cpp.md)
