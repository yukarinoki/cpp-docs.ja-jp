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
ms.openlocfilehash: 4108d24b2c285b9d55d514dffae7b2efda1b3f86
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227063"
---
# <a name="try-throw-and-catch-statements-c"></a>try、throw、および catch ステートメント (C++)

C++ で例外処理を実装するには **`try`** 、、、およびの各式を使用し **`throw`** **`catch`** ます。

最初に、ブロックを使用し **`try`** て、例外をスローする可能性のある1つ以上のステートメントを囲みます。

式は、 **`throw`** ブロックで例外的な条件 (多くの場合、エラー) が発生したことを通知し **`try`** ます。 任意の型のオブジェクトを式のオペランドとして使用でき **`throw`** ます。 通常、このオブジェクトを使用してエラーに関する情報を通知します。 ほとんどの場合、 [std:: exception](../standard-library/exception-class.md)クラス、または標準ライブラリで定義されている派生クラスの1つを使用することをお勧めします。 これらのいずれのクラスも適さない場合は、`std::exception` から派生させた独自の例外クラスを使用することをお勧めします。

スローされる可能性のある例外を処理するには、ブロックの直後に1つ以上のブロックを実装し **`catch`** **`try`** ます。 各 **`catch`** ブロックは、処理できる例外の種類を指定します。

この例は、 **`try`** ブロックとそのハンドラーを示しています。 `GetNetworkResource()` では、ネットワーク接続を介してデータを取得するとします。また、2 つの型の例外として `std::exception` から派生させたユーザー定義のクラスを使用するとします。 ステートメント内の参照によって例外がキャッチされていることに注意して **`const`** **`catch`** ください。 例外は値でスローし、const 参照でキャッチすることをお勧めします。

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

## <a name="remarks"></a>解説

句の後のコード **`try`** は、コードの保護されたセクションです。 この **`throw`** 式は、例外を*スロー*します (つまり、を発生させます)。 句の後のコードブロック **`catch`** は、例外ハンドラーです。 これは、式と式の型に互換性がある場合にスローされる例外を*キャッチ*するハンドラーです **`throw`** **`catch`** 。 ブロック内の型の一致を制御する規則の一覧につい **`catch`** ては、「 [Catch ブロックの評価方法](../cpp/how-catch-blocks-are-evaluated-cpp.md)」を参照してください。 ステートメントで **`catch`** 型の代わりに省略記号 (...) を指定した場合、 **`catch`** ブロックはすべての種類の例外を処理します。 [/Eha](../build/reference/eh-exception-handling-model.md)オプションを使用してコンパイルすると、C 構造化例外、システム生成、またはアプリケーションによって生成される非同期例外 (メモリ保護、0除算、浮動小数点違反など) が含まれることがあります。 **`catch`** 一致する型を検索するためにブロックがプログラムの順序で処理されるため、省略記号ハンドラーは、関連付けられているブロックの最後のハンドラーである必要があり **`try`** ます。 `catch(...)` は慎重に使用してください。プログラムの実行が継続されるには、キャッチした特定の例外を処理する方法を catch ブロックに記述する必要があります。 `catch(...)` ブロックは通常、プログラムの実行を停止する前に、エラーを記録して特別なクリーンアップを実行するために使用します。

オペランドが指定されてい **`throw`** ない式は、現在処理中の例外を再スローします。 この方法は例外を再スローするときにお勧めします。元の例外のポリモーフィックな型情報が保持されるためです。 このような式は、ハンドラー **`catch`** またはハンドラーから呼び出された関数でのみ使用してください **`catch`** 。 再スローされた例外オブジェクトはコピーではなく元の例外オブジェクトです。

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

[例外とエラー処理に関する最新の C++ のベストプラクティス](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[未処理の C++ 例外](../cpp/unhandled-cpp-exceptions.md)<br/>
[__uncaught_exception](../c-runtime-library/reference/uncaught-exception.md)
