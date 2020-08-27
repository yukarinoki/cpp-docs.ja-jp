---
title: C (構造化) と C++ の例外の混合
description: 構造化例外処理と C++ 例外、および潜在的な問題を混在させる方法。
ms.date: 08/24/2020
helpviewer_keywords:
- exceptions [C++], mixed C and C++
- C++ exception handling, mixed-language
- structured exception handling [C++], mixed C and C++
- catch keyword [C++], mixed
- try-catch keyword [C++], mixed-language
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
ms.openlocfilehash: 98ce2335ff3b08b7a5d71e03305c481ba068e5e6
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898415"
---
# <a name="mixing-c-structured-and-c-exceptions"></a>C (構造化) と C++ の例外の混合

移植可能なコードを記述する場合は、C++ プログラムで構造化例外処理 (SEH) を使用することは推奨されません。 ただし、構造化例外と C++ ソースコードを使用してコンパイルし、 [`/EHa`](../build/reference/eh-exception-handling-model.md) 両方の種類の例外を処理するための機能が必要になる場合があります。 構造化例外ハンドラーにはオブジェクトまたは型指定された例外の概念がないため、C++ コードによってスローされる例外を処理することはできません。 ただし、C++ **`catch`** ハンドラーは構造化例外を処理できます。 C++ 例外処理構文 ( **`try`** 、 **`throw`** 、 **`catch`** ) は c コンパイラでは受け入れられませんが、構造化例外処理構文 ( **`__try`** 、 **`__except`** 、 **`__finally`** ) は c++ コンパイラでサポートされています。

[`_set_se_translator`](../c-runtime-library/reference/set-se-translator.md)構造化例外を C++ 例外として処理する方法については、「」を参照してください。

構造化例外と C++ 例外を混在させる場合は、次の潜在的な問題に注意してください。

- C++ 例外と構造化例外を同じ関数内に混在させることはできません。

- 終了ハンドラー ( **`__finally`** ブロック) は、例外がスローされた後にアンワインド中であっても、常に実行されます。

- C++ 例外処理では、アンワインドセマンティクスを有効にするコンパイラオプションを使用してコンパイルされたすべてのモジュールで、アンワインドセマンティクスをキャッチして保持でき [`/EH`](../build/reference/eh-exception-handling-model.md) ます。

- 場合によっては、すべてのオブジェクトに対してデストラクター関数が呼び出されないことがあります。 たとえば、初期化されていない関数ポインターを使用して関数呼び出しを行うときに、構造化例外が発生する可能性があります。 関数のパラメーターが呼び出しの前に構築されたオブジェクトである場合、スタックのアンワインド中に、これらのオブジェクトのデストラクターは呼び出されません。

## <a name="next-steps"></a>次のステップ

- [`setjmp` `longjmp` C++ プログラムでまたはを使用する](../cpp/using-setjmp-longjmp.md)

  `setjmp`および C++ プログラムの使用方法の詳細については、「」を参照してください `longjmp` 。

- [C++ での構造化例外の処理](../cpp/exception-handling-differences.md)

  C++ を使用して構造化例外を処理する方法の例を参照してください。

## <a name="see-also"></a>関連項目

[例外とエラー処理に関する最新の C++ のベストプラクティス](../cpp/errors-and-exception-handling-modern-cpp.md)
