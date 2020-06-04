---
title: '例外処理 : MFC 3.0 での変更点'
ms.date: 11/04/2016
helpviewer_keywords:
- C++ exception handling [MFC], upgrade considerations
- CATCH macro [MFC]
- exceptions [MFC], what's changed
- THROW_LAST macro [MFC]
ms.assetid: 3aa20d8c-229e-449c-995c-ab879eac84bc
ms.openlocfilehash: 82320b0c7ccd6766e016f0437633339f8f8f61d6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365491"
---
# <a name="exceptions-changes-to-exception-macros-in-version-30"></a>例外処理 : MFC 3.0 での変更点

これは高度なトピックです。

MFC バージョン 3.0 以降では、例外処理マクロが C++ 例外を使用するように変更されています。 この資料では、これらの変更がマクロを使用する既存のコードの動作にどのように影響するかを説明します。

この記事では、次のトピックについて説明します。

- [例外の種類と CATCH マクロ](#_core_exception_types_and_the_catch_macro)

- [例外を再スローする](#_core_re.2d.throwing_exceptions)

## <a name="exception-types-and-the-catch-macro"></a><a name="_core_exception_types_and_the_catch_macro"></a>例外の種類と CATCH マクロ

以前のバージョンの MFC では **、CATCH**マクロは MFC ランタイム型情報を使用して例外の型を決定していました。例外のタイプは、つまり catch サイトで決定されます。 ただし、C++ 例外を除き、スロー サイトでは、スローされる例外オブジェクトの型によって例外の型が常に決定されます。 これは、スローされたオブジェクトへのポインターの型がスローされたオブジェクトの型と異なるまれなケースでは、互換性が低下します。

次の例は、MFC バージョン 3.0 と以前のバージョンのこの違いの結果を示しています。

[!code-cpp[NVC_MFCExceptions#1](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_1.cpp)]

このコードは、バージョン 3.0 では、一致する例外宣言を持つ最初の**catch**ブロックに常に渡されるため、動作が異なります。 スロー式の結果

[!code-cpp[NVC_MFCExceptions#19](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_2.cpp)]

は`CException*`、 として構築されていても、 としてスローされます`CCustomException`。 MFC**CATCH**バージョン 2.5 以前の CATCH`CObject::IsKindOf`マクロは、実行時に型をテストするために使用します。 式が

[!code-cpp[NVC_MFCExceptions#20](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_3.cpp)]

は true の場合、最初の catch ブロックが例外をキャッチします。 C++ 例外を使用して例外処理マクロの多くを実装するバージョン 3.0 では、2 番目の catch`CException`ブロックがスローされた .

このようなコードは一般的ではありません。 通常、例外オブジェクトがジェネリック`CException*`を受け入れる別の関数に渡され、"プリスロー" 処理が実行され、最後に例外がスローされた場合に表示されます。

この問題を回避するには、throw 式を関数から呼び出し元のコードに移動し、例外が生成された時点でコンパイラが認識している実際の型の例外をスローします。

## <a name="re-throwing-exceptions"></a><a name="_core_re.2d.throwing_exceptions"></a>例外の再スロー

catch ブロックは、キャッチした例外ポインターと同じ例外ポインターをスローできません。

たとえば、このコードは以前のバージョンでは有効でしたが、バージョン 3.0 では予期しない結果が発生します。

[!code-cpp[NVC_MFCExceptions#2](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_4.cpp)]

catch ブロックで**THROW**を使用`e`すると、ポインターが削除され、外部のキャッチ・サイトが無効なポインターを受け取ります。 **THROW_LAST**を使用して、`e`を再スローします。

詳細については、「[例外: 例外のキャッチと削除](../mfc/exceptions-catching-and-deleting-exceptions.md)」を参照してください。

## <a name="see-also"></a>関連項目

[例外処理](../mfc/exception-handling-in-mfc.md)
