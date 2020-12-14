---
description: '詳細情報: Catch ブロックの評価方法 (C++)'
title: Catch ブロックの評価方法 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- try-catch keyword [C++], catchable types
- catch keyword [C++], types of catch handlers
- C++ exception handling, catch handlers
- exception handling, catching and deleting exceptions
- types [C++], exception handling
ms.assetid: 202dbf07-8ace-4b3b-b3ae-4b45c275e0b4
ms.openlocfilehash: ec4544bb88eea0ee03b7b5b0ab139e267da0552d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221294"
---
# <a name="how-catch-blocks-are-evaluated-c"></a>Catch ブロックの評価方法 (C++)

C++ では任意の型の例外をスローすることができますが、一般に std::exception から派生した型をスローすることが推奨されます。 C++ 例外は、スローされた **`catch`** 例外と同じ型を指定するハンドラー、または任意の型の例外をキャッチできるハンドラーによってキャッチできます。

スローされる例外の型がクラスである場合、クラスは基底クラスも持つため、その例外は、例外の型の基底クラスを受け入れるハンドラー、および例外の型の基底クラスへの参照を受け入れるハンドラーでキャッチできます。 例外が参照によってキャッチされた場合、それは実際にスローされた例外オブジェクトにバインドされることに注意してください。それ以外の場合は、コピーになります (関数の引数とほぼ同じ)。

例外がスローされると、次の種類のハンドラーによってキャッチされる可能性があり **`catch`** ます。

- 任意の型を受け取ることができるハンドラー (省略記号構文を使用)。

- 例外オブジェクトと同じ型を受け入れるハンドラー。これはコピーであるため **`const`** 、 **`volatile`** 修飾子は無視されます。

- 例外オブジェクトと同じ型への参照を受け入れるハンドラー。

- **`const`** **`volatile`** 例外オブジェクトと同じ型のまたはフォームへの参照を受け入れるハンドラー。

- Exception オブジェクトと同じ型の基底クラスを受け取るハンドラー。これはコピーであるため **`const`** 、 **`volatile`** 修飾子は無視されます。 **`catch`** 基底クラスのハンドラーは、 **`catch`** 派生クラスのハンドラーの前に配置することはできません。

- 例外オブジェクトと同じ型の基底クラスへの参照を受け取るハンドラー。

- **`const`** **`volatile`** 例外オブジェクトと同じ型の基底クラスのまたは形式への参照を受け入れるハンドラー。

- スローされたポインター オブジェクトが標準的なポインター変換規則によって変換できるポインターを受け取るハンドラー。

指定された **`catch`** ブロックのハンドラーは **`try`** 外観の順に検査されるため、ハンドラーが表示される順序は重要です。 たとえば、派生クラスのハンドラーの前に基底クラスのハンドラーを配置するとエラーになります。 一致する **`catch`** ハンドラーが見つかると、後続のハンドラーは検証されません。 そのため、省略記号ハンドラーは、 **`catch`** そのブロックの最後のハンドラーである必要があり **`try`** ます。 次に例を示します。

```cpp
// ...
try
{
    // ...
}
catch( ... )
{
    // Handle exception here.
}
// Error: the next two handlers are never examined.
catch( const char * str )
{
    cout << "Caught exception: " << str << endl;
}
catch( CExcptClass E )
{
    // Handle CExcptClass exception here.
}
```

この例では、省略記号 **`catch`** ハンドラーだけが検査されます。

## <a name="see-also"></a>関連項目

[例外とエラー処理に関する最新の C++ のベストプラクティス](../cpp/errors-and-exception-handling-modern-cpp.md)
