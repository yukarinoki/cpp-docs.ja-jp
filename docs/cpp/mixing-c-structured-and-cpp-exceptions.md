---
title: C (構造化) と C++ の例外の混合
ms.date: 08/14/2018
helpviewer_keywords:
- exceptions [C++], mixed C and C++
- C++ exception handling, mixed-language
- structured exception handling [C++], mixed C and C++
- catch keyword [C++], mixed
- try-catch keyword [C++], mixed-language
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
ms.openlocfilehash: 72ddde9bc284a005c77694d599a8e9a3908cb2d0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233692"
---
# <a name="mixing-c-structured-and-c-exceptions"></a>C (構造化) と C++ の例外の混合

移植可能なコードを記述する場合は、C++ プログラムで構造化例外処理 (SEH) を使用することは推奨されません。 ただし、 [/eha](../build/reference/eh-exception-handling-model.md)を使用してコンパイルし、構造化例外と C++ ソースコードを混在させ、両方の種類の例外を処理するための機能が必要になる場合があります。 構造化例外ハンドラーにはオブジェクトまたは型指定された例外の概念がないため、C++ コードによってスローされる例外を処理することはできません。 ただし、C++ **`catch`** ハンドラーは構造化例外を処理できます。 C++ 例外処理構文 ( **`try`** 、 **`throw`** 、 **`catch`** ) は c コンパイラでは受け入れられませんが、構造化例外処理構文 (**__try**、 **`__except`** 、 **`__finally`** ) は c++ コンパイラでサポートされています。

構造化例外を C++ 例外として処理する方法については、「 [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) 」を参照してください。

構造化例外と C++ 例外を混在させる場合は、次の潜在的な問題に注意してください。

- C++ の例外と構造化例外を、同じ関数内で混在させることはできません。

- 終了ハンドラー ( **`__finally`** ブロック) は、例外がスローされた後にアンワインド中であっても、常に実行されます。

- C++ 例外処理では、 [/EH](../build/reference/eh-exception-handling-model.md)コンパイラオプションを使用してコンパイルされたすべてのモジュールでアンワインドセマンティクスをキャッチおよび保持できます。これにより、アンワインドセマンティクスが可能になります。

- デストラクター関数がすべてのオブジェクトに対して呼び出されない状況もあります。 たとえば、初期化されていない関数ポインターを使用して関数呼び出しを実行しようとしたときに構造化例外が発生し、その関数が呼び出し前に構築されたパラメーターオブジェクトとしてを受け取る場合、これらのオブジェクトのデストラクターはスタックアンワインド中に呼び出されません。

## <a name="next-steps"></a>次のステップ

- [C++ プログラムでの setjmp または longjmp の使用](../cpp/using-setjmp-longjmp.md)

  `setjmp`および C++ プログラムの使用方法の詳細については、「」を参照してください `longjmp` 。

- [C++ での構造化例外の処理](../cpp/exception-handling-differences.md)

  C++ を使用して構造化例外を処理する方法の例を参照してください。

## <a name="see-also"></a>関連項目

[例外とエラー処理に関する最新の C++ のベストプラクティス](../cpp/errors-and-exception-handling-modern-cpp.md)
