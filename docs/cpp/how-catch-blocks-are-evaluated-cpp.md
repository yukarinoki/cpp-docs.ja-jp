---
title: Catch ブロックの評価方法 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- try-catch keyword [C++], catchable types
- catch keyword [C++], types of catch handlers
- C++ exception handling, catch handlers
- exception handling, catching and deleting exceptions
- types [C++], exception handling
ms.assetid: 202dbf07-8ace-4b3b-b3ae-4b45c275e0b4
ms.openlocfilehash: 7504439c565d4dfb720bc2fa7e097e3230733423
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153685"
---
# <a name="how-catch-blocks-are-evaluated-c"></a>Catch ブロックの評価方法 (C++)

C++ では任意の型の例外をスローすることができますが、一般に std::exception から派生した型をスローすることが推奨されます。 C++ 例外をキャッチできる、**catch**または任意の種類の例外をキャッチできるハンドラーによってスローされた例外として、同じ型を指定するハンドラー。

スローされる例外の型がクラスである場合、クラスは基底クラスも持つため、その例外は、例外の型の基底クラスを受け入れるハンドラー、および例外の型の基底クラスへの参照を受け入れるハンドラーでキャッチできます。 例外が参照によってキャッチされた場合、それは実際にスローされた例外オブジェクトにバインドされることに注意してください。それ以外の場合は、コピーになります (関数の引数とほぼ同じ)。

例外がスローされたときに、次の種類のによってキャッチできます**catch**ハンドラー。

- 任意の型を受け取ることができるハンドラー (省略記号構文を使用)。

- 例外オブジェクトと同じ型を受け入れるハンドラーこれは、コピーであるため**const**と**volatile**修飾子は無視されます。

- 例外オブジェクトと同じ型への参照を受け入れるハンドラー。

- 参照を受け入れるハンドラー、 **const**または**volatile**例外オブジェクトと同じ型の形式。

- 例外オブジェクトと同じ型の基本クラスを受け入れるハンドラーこれは、コピー後**const**と**volatile**修飾子は無視されます。 **catch**基底クラスのハンドラーの前にする必要があります、**catch**派生クラスのハンドラー。

- 例外オブジェクトと同じ型の基底クラスへの参照を受け取るハンドラー。

- 参照を受け入れるハンドラー、 **const**または**volatile**例外オブジェクトと同じ型の基底クラスの形式。

- スローされたポインター オブジェクトが標準的なポインター変換規則によって変換できるポインターを受け取るハンドラー。

順序**catch**ハンドラーの表示は、重要ではためのハンドラーを特定**try**ブロックは、それらの外観の順序でチェックされます。 たとえば、派生クラスのハンドラーの前に基底クラスのハンドラーを配置するとエラーになります。 一致すた後**catch**ハンドラーが見つかると、後続のハンドラーはチェックされません。 その結果、省略記号**catch**ハンドラーは、最後のハンドラーである必要があります、**try**ブロックします。 例えば:

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

この例では、省略記号で**catch**ハンドラーが唯一のハンドラーが解析されます。

## <a name="see-also"></a>関連項目

[C++ 例外処理](../cpp/cpp-exception-handling.md)
