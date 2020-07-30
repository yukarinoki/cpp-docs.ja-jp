---
title: アサーションとユーザー指定のメッセージ (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- user-supplied messages [C++], run time
- user-supplied messages [C++], preprocessor time
- '#error%2C assert%2C static_assert [C++]'
- user-supplied messages [C++], compile time
ms.assetid: ebf7d885-61c8-4233-b0ae-1c9a38e0f385
ms.openlocfilehash: a4861b3e1d17835f11f5e148d6b62051a6747f80
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226022"
---
# <a name="assertion-and-user-supplied-messages-c"></a>アサーションとユーザー指定のメッセージ (C++)

C++ 言語では、アプリケーションのデバッグに役立つ3つのエラー処理機構 ( [#error ディレクティブ](../preprocessor/hash-error-directive-c-cpp.md)、 [static_assert](../cpp/static-assert.md)キーワード、 [assert マクロ、_assert、_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)マクロ) がサポートされています。 3 つの機構すべてはエラー メッセージを発行し、2 つはソフトウェアのアサーションもテストします。 ソフトウェアのアサーションは、プログラムの特定位置にある true となるはずの条件を指定します。 コンパイル時にアサーションが失敗した場合、コンパイラで診断メッセージが発行され、コンパイル エラーが発生します。 ランタイムのアサーションが失敗した場合、オペレーティング システムで診断メッセージが発行され、アプリケーションを終了します。

## <a name="remarks"></a>解説

アプリケーションの有効期間は、プリプロセス、コンパイル、および実行時フェーズで構成されます。 各エラー処理機構は、これらのいずれかのフェーズで使用できるデバッグ情報にアクセスします。 効果的にデバッグするには、そのフェーズに関する適切な情報を提供する機能を選択します:

- [#Error ディレクティブ](../preprocessor/hash-error-directive-c-cpp.md)は、前処理時に有効です。 これは無条件にユーザー指定のメッセージを出力し、コンパイルはエラーで失敗します。 メッセージは、プリプロセッサ ディレクティブが操作するテキストを含むことができますが、結果の式は評価されません。

- [Static_assert](../cpp/static-assert.md)宣言は、コンパイル時に有効です。 これはブール型に変換できるユーザー指定の整数式で表されるソフトウェアのアサーションをテストします。 式がゼロ (false) に評価されると、ユーザー指定のメッセージが表示され、コンパイルはエラーで失敗します。

   宣言は、テンプレート **`static_assert`** 引数をユーザー指定の式に含めることができるため、テンプレートをデバッグする場合に特に便利です。

- [Assert マクロ、_assert、_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)マクロは実行時に有効になります。 ユーザーが指定した式が評価され、結果がゼロの場合、システムは診断メッセージを発行し、アプリケーションを閉じます。 [_ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)や _ASSERTE など、他の多くのマクロはこのマクロに似ていますが、システム定義またはユーザー定義の診断メッセージは異なります。

## <a name="see-also"></a>関連項目

[#error ディレクティブ (C/c + +)](../preprocessor/hash-error-directive-c-cpp.md)<br/>
[assert マクロ、_assert、_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)<br/>
[_ASSERT、_ASSERTE、_ASSERT_EXPR マクロ](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)<br/>
[static_assert](../cpp/static-assert.md)<br/>
[_STATIC_ASSERT マクロ](../c-runtime-library/reference/static-assert-macro.md)<br/>
[テンプレート](../cpp/templates-cpp.md)
