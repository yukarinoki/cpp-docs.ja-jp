---
description: 詳細については、「setjmp と longjmp の使用」を参照してください。
title: Setjmp と longjmp の使用
ms.date: 08/14/2018
f1_keywords:
- longjmp_cpp
- setjmp_cpp
helpviewer_keywords:
- C++ exception handling, setjmp/longjmp functions
- setjmpex.h
- longjmp function in C++ programs
- setjmp.h
- setjmp function
- setjmp function, C++ programs
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
ms.openlocfilehash: 5d0f62eeed8b2401309f339a59872c7dd0ac3107
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116744"
---
# <a name="using-setjmp-and-longjmp"></a>Setjmp と longjmp の使用

[Setjmp](../c-runtime-library/reference/setjmp.md)と [longjmp](../c-runtime-library/reference/longjmp.md)を一緒に使用すると、非ローカルのを実行する方法が提供され **`goto`** ます。 通常、これらは、標準の呼び出し規約または戻り値の規則を使用せずに、以前に呼び出されたルーチンのエラー処理または復旧コードに実行制御を渡すために、C コードで使用されます。

> [!CAUTION]
> `setjmp`と `longjmp` は、c++ コンパイラ間で移植スタックフレームオブジェクトの適切な破棄をサポートしていないため、およびローカル変数の最適化を防ぐことによってパフォーマンスが低下する可能性があるため、c++ プログラムでは使用しないことをお勧めします。 代わりにを使用し、を構築することをお勧めし **`try`** **`catch`** ます。

`setjmp`C++ プログラムでおよびを使用する場合 `longjmp` \<setjmp.h> は、 \<setjmpex.h> 関数と構造化例外処理 (SEH) または c++ 例外処理の間で正しい相互作用を確保するために、またはも含めます。

**Microsoft 固有の仕様**

[/EH](../build/reference/eh-exception-handling-model.md)オプションを使用して C++ コードをコンパイルすると、ローカルオブジェクトのデストラクターがスタックアンワインド中に呼び出されます。 ただし、 **/ehs** または **/ehsc** を使用してコンパイルする場合、および [noexcept](../cpp/noexcept-cpp.md) 呼び出しを使用する関数の1つでは、 `longjmp` オプティマイザーの状態によっては、その関数のデストラクターのアンワインドが発生しない可能性があります。

移植性のあるコードでは、 `longjmp` 呼び出しが実行されるときに、フレームベースのオブジェクトの適切な破棄は、標準では保証されず、他のコンパイラではサポートされない可能性があります。 警告レベル4でを呼び出すと、警告 `setjmp` C4611 が発生します。 ' _setjmp ' 間の相互作用と、C++ オブジェクトの破棄は、移植不可です。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[C (構造化) と C++ の例外の混合](../cpp/mixing-c-structured-and-cpp-exceptions.md)
