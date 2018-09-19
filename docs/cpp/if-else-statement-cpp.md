---
title: if-else ステートメント (C++) |Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- else_cpp
- if_cpp
dev_langs:
- C++
helpviewer_keywords:
- if keyword [C++]
- else keyword [C++]
- if keyword [C++], if-else
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e55788e280eb60f176a286cf9d1693e93447a077
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031460"
---
# <a name="if-else-statement-c"></a>if-else ステートメント (C++)

条件分岐を制御します。 内のステートメント、 *if ブロック*が実行された場合にのみ、 *if 式*0 以外の値 (または TRUE) に評価されます。 場合の値*式*0 以外の場合、 *statement1*とブロック内の他のステートメントが実行され、存在する場合、他のブロックはスキップされます。 場合の値*式*0 の場合は、if ブロックはスキップされ、他のブロックが存在する場合が実行されます。 0 以外に評価される式は、
- true
- null 以外のポインター
- 0 以外の算術値、または
- 算術演算子、ブール値またはポインターに明確な変換を定義するクラス型を入力します。 (変換については、次を参照してください[標準変換](../cpp/standard-conversions.md)。)。

## <a name="syntax"></a>構文

```
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

// Visual Studio 2017 version 15.3 and later:
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

// Visual Studio 2017 version 15.3 and later:
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
    void do_somthing(){}
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
## <a name="if_with_init"></a> 場合、初期化子と共にステートメント

**Visual Studio 2017 バージョン 15.3 以降**(で使用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md)):**場合**ステートメントは、式を宣言し、名前付きの変数の初期化を含めることもできます。 変数が if ブロックのスコープ内だけに必要なときは、この形式の if ステートメントを使用します。

```cpp
## Example

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

すべてのフォーム、**場合**ステートメントでは、*式*構造体以外の値であるが評価され、すべての副作用を含めています。 制御が渡される、**場合**プログラムに次のステートメントにしない限りのいずれか、*ステートメント*が含まれて、 [break](../cpp/break-statement-cpp.md)、 [を続行](../cpp/continue-statement-cpp.md)、または[goto](../cpp/goto-statement-cpp.md)します。

**他**の句、`if...else`ステートメントは、最も近いの関連付け前**場合**ステートメントがない、対応するのと同じスコープ内で**他**ステートメント。

## <a name="a-nameifconstexpr-if-constexpr-statements"></a><a name="if_constexpr"> 場合 constexpr ステートメント

**Visual Studio 2017 バージョン 15.3 以降**(で使用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md)): 関数テンプレートで使用することができます、**場合 constexpr**ことがなくコンパイル時の分岐決定を行うステートメント複数の関数オーバー ロードを使用することです。 たとえば、1 つの関数を記述する、そのハンドル パラメーターのアンパック (ゼロのパラメーター オーバー ロードは必要ありません)。

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

[選択ステートメント](../cpp/selection-statements-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[switch ステートメント (C++)](../cpp/switch-statement-cpp.md)