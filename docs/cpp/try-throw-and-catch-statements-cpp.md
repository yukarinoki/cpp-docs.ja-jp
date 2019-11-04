---
title: try、throw、および catch ステートメント (C++)
ms.date: 11/04/2016
f1_keywords:
- catch_cpp
- try_cpp
- throw_cpp
helpviewer_keywords:
- catch keyword [C++]
- keywords [C++], exception handling
- C++ exception handling, statement syntax
- try-catch keyword [C++], about try-catch exception handling
- throw keyword [C++]
- try-catch keyword [C++]
- try-catch keyword [C++], exception handling
- throwing exceptions [C++], throw keyword
- try-catch keyword [C++], throw keyword [C++]s
- throwing exceptions [C++], implementing C++ exception handling
- throwing exceptions [C++]
- throw keyword [C++], throw() vs. throw(...)
ms.assetid: 15e6a87b-b8a5-4032-a7ef-946c644ba12a
ms.openlocfilehash: a55c1f2d5c2e73028b337d17b74fe1280f670707
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266785"
---
# <a name="try-throw-and-catch-statements-c"></a>try、throw、および catch ステートメント (C++)

C++ の例外処理を実装するには、使用する**try**、**throw**、および**catch**式。

まず、使用して、**try**例外をスローする 1 つまたは複数のステートメントを囲むブロックします。

**throw**ことを通知する例外条件 — 多くの場合、エラー-で発生しました、**try**ブロック。 オペランドとして任意の型のオブジェクトを使用することができます、**throw**式。 通常、このオブジェクトを使用してエラーに関する情報を通知します。 ほとんどの場合で使用すること勧め、 [std::exception](../standard-library/exception-class.md)クラスまたは標準ライブラリで定義されている派生クラスのいずれか。 これらのいずれのクラスも適さない場合は、`std::exception` から派生させた独自の例外クラスを使用することをお勧めします。

スローされる可能性がある例外を処理するには、1 つまたは複数を実装**catch**ブロックの直後、**try**ブロックします。 各**catch**ブロックが処理できる例外の種類を指定します。

この例では、**try**ブロックとそのハンドラー。 `GetNetworkResource()` では、ネットワーク接続を介してデータを取得するとします。また、2 つの型の例外として `std::exception` から派生させたユーザー定義のクラスを使用するとします。 通知が、例外をキャッチする**const**で参照、**catch**ステートメント。 例外は値でスローし、const 参照でキャッチすることをお勧めします。

## <a name="example"></a>例

```cpp
MyData md;
try {
   // Code that could throw an exception
   md = GetNetworkResource();
}
catch (const networkIOException& e) {
   // Code that executes when an exception of type
   // networkIOException is thrown in the try block
   // ...
   // Log error message in the exception object
   cerr << e.what();
}
catch (const myDataFormatException& e) {
   // Code that handles another exception type
   // ...
   cerr << e.what();
}

// The following syntax shows a throw expression
MyData GetNetworkResource()
{
   // ...
   if (IOSuccess == false)
      throw networkIOException("Unable to connect");
   // ...
   if (readError)
      throw myDataFormatException("Format error");
   // ...
}
```

## <a name="remarks"></a>Remarks

後のコード、**try**句は、コードの保護されたセクションです。 **throw**式*をスローします*-は、発生させる-例外。 コード ブロックの後、**catch**句は、例外ハンドラー。 これは、ハンドラーを*catch*場合にスローされる例外の種類、**throw**と**catch**式は、互換性のあります。 型の一致を制御する規則の一覧については**catch**ブロックを参照してください[方法 Catch ブロックの評価](../cpp/how-catch-blocks-are-evaluated-cpp.md)します。 場合、**catch**ステートメントを型の代わりに省略記号 (...) を指定します、**catch**ブロックは、すべての種類の例外を処理します。 コンパイルするとき、 [/EHa](../build/reference/eh-exception-handling-model.md)オプション、C 構造化例外とメモリの保護、0 による除算、および浮動小数点の違反など、システムによって生成された、またはアプリケーションによって生成される非同期例外が含まれます. **catch**ブロックの一致する種類を検索するプログラムの順序で処理は、省略記号ボタン ハンドラーが関連付けられている最後のハンドラーにする必要があります、**try**ブロックします。 `catch(...)` は慎重に使用してください。プログラムの実行が継続されるには、キャッチした特定の例外を処理する方法を catch ブロックに記述する必要があります。 `catch(...)` ブロックは通常、プログラムの実行を停止する前に、エラーを記録して特別なクリーンアップを実行するために使用します。

**try**オペランドを持たない式は、現在処理中の例外を再スローします。 この方法は例外を再スローするときにお勧めします。元の例外のポリモーフィックな型情報が保持されるためです。 このような式でのみ使用する必要があります、**catch**ハンドラーまたはから呼び出される関数を**catch**ハンドラー。 再スローされた例外オブジェクトはコピーではなく元の例外オブジェクトです。

```cpp
try {
   throw CSomeOtherException();
}
catch(...) {
   // Catch all exceptions - dangerous!!!
   // Respond (perhaps only partially) to the exception, then
   // re-throw to pass the exception to some other handler
   // ...
   throw;
}
```

## <a name="see-also"></a>関連項目

[C++ 例外処理](../cpp/cpp-exception-handling.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[未処理の C++ 例外](../cpp/unhandled-cpp-exceptions.md)<br/>
[__uncaught_exception](../c-runtime-library/reference/uncaught-exception.md)