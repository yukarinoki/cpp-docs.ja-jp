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
ms.openlocfilehash: 8a936a0af9927aa0dc453a93c98676a77f4ad6dc
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621763"
---
# <a name="exceptions-converting-from-mfc-exception-macros"></a>例外処理 : 古いコードの変換

これは高度なトピックです。

この記事では、Microsoft Foundation Class マクロ ( **try**、 **catch**、 **throw**など) で記述された既存のコードを変換し、C++ 例外処理キーワードの**try**、 **catch**、および**throw**を使用する方法について説明します。 取り上げるトピックは次のとおりです。

- [変換の利点](#_core_advantages_of_converting)

- [C++ 例外を使用するためのコードから例外マクロへの変換](#_core_doing_the_conversion)

## <a name="advantages-of-converting"></a><a name="_core_advantages_of_converting"></a>変換の利点

既存のコードを変換する必要はないかもしれませんが、MFC バージョン3.0 のマクロ実装と、以前のバージョンの実装の違いに注意する必要があります。 これらの違いおよびコードの動作の後続の変更については、 [「例外: バージョン3.0 での例外マクロの変更](exceptions-changes-to-exception-macros-in-version-3-0.md)点」で説明されています。

変換の主な利点は次のとおりです。

- C++ の例外処理キーワードを使用するコードは、少し小さいにコンパイルされます。EXE または。DLL.

- C++ の例外処理キーワードは、より汎用性があります。コピー可能な任意のデータ型 (**int**、 **float**、 **char**など) の例外を処理できます。一方、マクロは、派生クラスと派生クラスの例外のみを処理し `CException` ます。

マクロとキーワードの大きな違いは、マクロを "自動的に" 使用するコードは、例外がスコープ外に出たときにキャッチされた例外を削除するということです。 キーワードを使用するコードは、キャッチされた例外を明示的に削除する必要があります。 詳細については、例外の[キャッチと削除](exceptions-catching-and-deleting-exceptions.md)に関する記事を参照してください。

もう1つの違いは構文です。 マクロとキーワードの構文は、次の3つの点で異なります。

1. マクロ引数と例外宣言:

   **CATCH**マクロの呼び出しの構文は次のとおりです。

   **CATCH (** *exception_class*、 *exception_object_pointer_name* **)**

   クラス名とオブジェクトポインター名の間にコンマがあることに注意してください。

   **Catch**キーワードの例外宣言では、次の構文を使用します。

   **catch (** *exception_type* *exception_name* **)**

   この例外宣言ステートメントは、catch ブロックが処理する例外の種類を示します。

2. Catch ブロックの Delimitation:

   マクロを使用すると、 **catch**マクロ (引数を含む) が最初の catch ブロックを開始します。**AND_CATCH**マクロは後続の catch ブロックを開始し、 **END_CATCH**マクロは catch ブロックのシーケンスを終了します。

   キーワードを使用すると、 **catch**キーワード (例外宣言を含む) が各 catch ブロックを開始します。 **END_CATCH**マクロに対応するものがありません。catch ブロックは、右中かっこで終わります。

3. Throw 式:

   マクロは、現在の例外を再スローするために**THROW_LAST**を使用します。 引数を指定せずに**throw**キーワードを指定すると、同じ効果があります。

## <a name="doing-the-conversion"></a><a name="_core_doing_the_conversion"></a>変換の実行

#### <a name="to-convert-code-using-macros-to-use-the-c-exception-handling-keywords"></a>マクロを使用してコードを変換し、C++ 例外処理キーワードを使用するには

1. すべての MFC マクロ**TRY**、 **CATCH**、 **AND_CATCH**、 **END_CATCH**、 **THROW**、および**THROW_LAST**を検索します。

2. 次のマクロのすべての出現箇所を置換または削除します。

   **Try** ( **try**に置き換える)

   **Catch** ( **catch**に置き換える)

   **AND_CATCH** ( **CATCH**に置き換える)

   **END_CATCH** (削除)

   **Throw** ( **throw**に置き換える)

   **THROW_LAST** ( **THROW**に置き換える)

3. マクロの引数を変更して、有効な例外宣言を形成するようにします。

   たとえば、

   [!code-cpp[NVC_MFCExceptions#6](codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_1.cpp)]

   to

   [!code-cpp[NVC_MFCExceptions#7](codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_2.cpp)]

4. Catch ブロック内のコードを変更して、必要に応じて例外オブジェクトが削除されるようにします。 詳細については、例外の[キャッチと削除](exceptions-catching-and-deleting-exceptions.md)に関する記事を参照してください。

MFC 例外マクロを使用した例外処理コードの例を次に示します。 次の例のコードではマクロを使用しているため、例外は自動的に削除されることに注意して `e` ください。

[!code-cpp[NVC_MFCExceptions#8](codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_3.cpp)]

次の例のコードでは、C++ 例外キーワードを使用しているため、例外を明示的に削除する必要があります。

[!code-cpp[NVC_MFCExceptions#9](codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_4.cpp)]

詳細については、「[例外: MFC マクロと C++ 例外の使用](exceptions-using-mfc-macros-and-cpp-exceptions.md)」を参照してください。

## <a name="see-also"></a>関連項目

[例外処理](exception-handling-in-mfc.md)<br/>
