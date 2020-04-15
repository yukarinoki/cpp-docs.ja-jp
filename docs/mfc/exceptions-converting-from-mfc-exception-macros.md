---
title: '例外処理 : 古いコードの変換'
ms.date: 08/27/2018
helpviewer_keywords:
- converting exceptions [MFC]
- exception objects [MFC]
- conversions [MFC], code written with MFC macros
- keywords [MFC], macros
- macrosv, C++ keywords
- exception objects [MFC], deleting
- CException class [MFC], deleting CException class objects
- exceptions [MFC], converting
- exceptions [MFC], deleting exception objects
- catch blocks [MFC], delimiting
- exception handling [MFC], converting exceptions
ms.assetid: bd3ac3b3-f3ce-4fdd-a168-a2cff13ed796
ms.openlocfilehash: 330f66b1f46542082637645ad53da016b434d4a2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372013"
---
# <a name="exceptions-converting-from-mfc-exception-macros"></a>例外処理 : 古いコードの変換

これは高度なトピックです。

この資料では、 Microsoft Foundation クラス マクロを使用して記述された既存のコード **(TRY、** **CATCH**、 **THROW**など) を変換して、 C++ の例外処理**キーワードを****使用**する方法について**説明します。** 取り上げるトピックは次のとおりです。

- [変換の利点](#_core_advantages_of_converting)

- [例外マクロを含むコードを C++ 例外を使用するように変換する](#_core_doing_the_conversion)

## <a name="advantages-of-converting"></a><a name="_core_advantages_of_converting"></a>変換の利点

MFC バージョン 3.0 のマクロ実装と以前のバージョンの実装の違いに注意する必要がありますが、既存のコードを変換する必要はありません。 これらの相違点とコード動作の後の変更については、「[例外: バージョン 3.0 の例外マクロの変更」を](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)参照してください。

変換の主な利点は次のとおりです。

- C++ の例外処理キーワードを使用するコードは、少し小さいにコンパイルされます。EXE または .Dll。

- C++ の例外処理キーワードは、より多目的性があります: マクロは、そこから派生した`CException`クラスとクラスの例外のみを処理するのに対し、コピーできる任意のデータ型 **(int** **、float** **、char**など) の例外を処理できます。

マクロとキーワードの主な違いは、マクロを使用するコードは、例外がスコープ外になるとキャッチされた例外を自動的に削除することです。 キーワードを使用するコードは使用しないため、キャッチされた例外を明示的に削除する必要があります。 詳細については、「例外 :[例外のキャッチと削除 」を参照してください](../mfc/exceptions-catching-and-deleting-exceptions.md)。

もう 1 つの違いは構文です。 マクロとキーワードの構文は、次の 3 点で異なります。

1. マクロ引数と例外宣言:

   **CATCH**マクロ呼び出しには、次の構文があります。

   **キャッチ***exception_class**(exception_class、exception_object_pointer_name)* **)**

   クラス名とオブジェクト ポインター名の間のコンマに注意してください。

   **catch**キーワードの例外宣言では、次の構文を使用します。

   **キャッチ***(exception_typeexception_name)* *exception_name* **)**

   この例外宣言ステートメントは、catch ブロックが処理する例外の種類を示します。

2. キャッチブロックの区切り:

   マクロでは **、CATCH**マクロ (引数を持つ) が最初の catch ブロックを開始します。**AND_CATCH**マクロは後続の catch ブロックを開始し **、END_CATCH**マクロは catch ブロックのシーケンスを終了します。

   キーワードを使用すると **、catch**キーワード (例外宣言を含む) が各 catch ブロックを開始します。 **END_CATCH**マクロに対応するものはありません。catch ブロックは、右中かっこで終わります。

3. スロー式:

   マクロは**THROW_LAST**を使用して現在の例外を再スローします。 引数を指定しない**throw**キーワードも同じ効果を持ちます。

## <a name="doing-the-conversion"></a><a name="_core_doing_the_conversion"></a>変換を行う

#### <a name="to-convert-code-using-macros-to-use-the-c-exception-handling-keywords"></a>C++ 例外処理キーワードを使用するようにマクロを使用してコードを変換するには

1. MFC マクロの**TRY**、**キャッチ****、AND_CATCH、END_CATCH、****スロー**、および**THROW_LAST**のすべての出現箇所を探します。 **END_CATCH**

2. 次のマクロをすべて置換または削除します。

   **TRY** (**試してみる**と置き換える)

   **キャッチ**(**キャッチ**で置き換える)

   **AND_CATCH** (**キャッチ**で置き換える)

   **END_CATCH** (削除)

   **スロー** (**スロー**で置き換える)

   **THROW_LAST** (**スロー**に置き換える)

3. マクロ引数を変更して、有効な例外宣言を形成します。

   たとえば、

   [!code-cpp[NVC_MFCExceptions#6](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_1.cpp)]

   to

   [!code-cpp[NVC_MFCExceptions#7](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_2.cpp)]

4. 必要に応じて例外オブジェクトを削除するように、catch ブロック内のコードを変更します。 詳細については、「例外 :[例外のキャッチと削除 」を参照してください](../mfc/exceptions-catching-and-deleting-exceptions.md)。

MFC 例外マクロを使用した例外処理コードの例を次に示します。 次の例のコードではマクロが使用されるため、例外`e`は自動的に削除されます。

[!code-cpp[NVC_MFCExceptions#8](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_3.cpp)]

次の例のコードでは、C++ 例外キーワードを使用するため、例外を明示的に削除する必要があります。

[!code-cpp[NVC_MFCExceptions#9](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_4.cpp)]

詳細については、「[例外 : MFC マクロと C++ 例外の使用](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)」を参照してください。

## <a name="see-also"></a>関連項目

[例外処理](../mfc/exception-handling-in-mfc.md)<br/>
