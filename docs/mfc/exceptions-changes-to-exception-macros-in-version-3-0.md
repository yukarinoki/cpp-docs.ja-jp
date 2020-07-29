---
title: '例外処理 : MFC 3.0 での変更点'
ms.date: 11/04/2016
helpviewer_keywords:
- C++ exception handling [MFC], upgrade considerations
- CATCH macro [MFC]
- exceptions [MFC], what's changed
- THROW_LAST macro [MFC]
ms.assetid: 3aa20d8c-229e-449c-995c-ab879eac84bc
ms.openlocfilehash: 72b343641b0b43d408c5820ca2a2af1de94ce327
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225060"
---
# <a name="exceptions-changes-to-exception-macros-in-version-30"></a>例外処理 : MFC 3.0 での変更点

これは高度なトピックです。

MFC バージョン3.0 以降では、C++ 例外を使用するように例外処理マクロが変更されています。 この記事では、これらの変更がマクロを使用する既存のコードの動作にどのように影響するかを示します。

この記事では、次のトピックについて説明します。

- [例外の種類と CATCH マクロ](#_core_exception_types_and_the_catch_macro)

- [例外の再スロー](#_core_re.2d.throwing_exceptions)

## <a name="exception-types-and-the-catch-macro"></a><a name="_core_exception_types_and_the_catch_macro"></a>例外の種類と CATCH マクロ

MFC の以前のバージョンでは、 **CATCH**マクロは mfc ランタイム型情報を使用して例外の型を特定していました。例外の型は、つまりキャッチサイトで決定されます。 ただし、C++ 例外では、例外の型は常にスローされる例外オブジェクトの型によってスローサイトで決定されます。 これにより、スローされたオブジェクトへのポインターの型が、スローされたオブジェクトの型と異なる場合に、非互換性が発生します。

次の例は、MFC バージョン3.0 とそれ以前のバージョンとの違いの結果を示しています。

[!code-cpp[NVC_MFCExceptions#1](codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_1.cpp)]

コントロールは、常に **`catch`** 一致する例外宣言を使用して最初のブロックに渡されるため、このコードの動作はバージョン3.0 で異なります。 Throw 式の結果

[!code-cpp[NVC_MFCExceptions#19](codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_2.cpp)]

は、として構築されている場合でも、としてスローされ `CException*` `CCustomException` ます。 MFC バージョン2.5 以前の**CATCH**マクロは、を使用して `CObject::IsKindOf` 、実行時に型をテストします。 式

[!code-cpp[NVC_MFCExceptions#20](codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_3.cpp)]

true の場合、最初の catch ブロックは例外をキャッチします。 C++ 例外を使用して多くの例外処理マクロを実装するバージョン3.0 では、2番目の catch ブロックがスローされたと一致し `CException` ます。

このようなコードは一般的ではありません。 これは通常、汎用を受け入れる別の関数に例外オブジェクトが渡され `CException*` 、"プリスロー" 処理を実行し、最後に例外をスローしたときに表示されます。

この問題を回避するには、関数から呼び出し元のコードに throw 式を移動し、例外が生成されたときにコンパイラに認識されている実際の型の例外をスローします。

## <a name="re-throwing-exceptions"></a><a name="_core_re.2d.throwing_exceptions"></a>例外の再スロー

Catch ブロックは、キャッチされたのと同じ例外ポインターをスローすることはできません。

たとえば、このコードは以前のバージョンでは有効でしたが、バージョン3.0 では予期しない結果になります。

[!code-cpp[NVC_MFCExceptions#2](codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_4.cpp)]

Catch ブロックで**THROW**を使用すると、 `e` 外部の catch サイトが無効なポインターを受け取るようにポインターが削除されます。 再スローするには**THROW_LAST**を使用し `e` ます。

詳細については、「[例外: 例外のキャッチと削除](exceptions-catching-and-deleting-exceptions.md)」を参照してください。

## <a name="see-also"></a>関連項目

[例外処理](exception-handling-in-mfc.md)
