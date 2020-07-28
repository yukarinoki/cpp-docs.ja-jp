---
title: '例外処理 : 例外のキャッチと削除'
ms.date: 11/04/2016
helpviewer_keywords:
- exceptions [MFC], deleting
- AND_CATCH macro [MFC]
- try-catch exception handling [MFC], catching and deleting exceptions
- exception handling [MFC], catching and deleting exceptions
- catch blocks [MFC], catching and deleting exceptions
- execution [MFC], returns from within catch block
ms.assetid: 7c233ff0-89de-4de0-a68a-9e9cdb164311
ms.openlocfilehash: 5c1edd4c5d31d9a0e8e5270d074d25b5dd129a0f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87184248"
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>例外処理 : 例外のキャッチと削除

次の手順と例は、例外をキャッチおよび削除する方法を示しています。 **`try`**、、およびキーワードの詳細につい **`catch`** ては **`throw`** 、「[例外とエラー処理のための最新の C++ のベストプラクティス](../cpp/errors-and-exception-handling-modern-cpp.md)」を参照してください。

例外ハンドラーは、処理する例外オブジェクトを削除する必要があります。そのため、例外を削除しても、そのコードが例外をキャッチするたびにメモリリークが発生します。

**`catch`** ブロックでは、次の場合に例外を削除する必要があります。

- ブロックは、 **`catch`** 新しい例外をスローします。

   もちろん、同じ例外を再度スローする場合は、例外を削除しないでください。

   [!code-cpp[NVC_MFCExceptions#3](codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]

- 実行はブロック内から返さ **`catch`** れます。

> [!NOTE]
> を削除する場合は `CException` 、 `Delete` メンバー関数を使用して例外を削除します。 キーワードを使用しないでください **`delete`** 。これは、例外がヒープ上にない場合に失敗する可能性があるためです。

#### <a name="to-catch-and-delete-exceptions"></a>例外をキャッチおよび削除するには

1. キーワードを使用して、 **`try`** ブロックを設定 **`try`** します。 ブロック内で例外をスローする可能性のあるプログラムステートメントを実行 **`try`** します。

   キーワードを使用して、 **`catch`** ブロックを設定 **`catch`** します。 例外処理コードをブロックに配置 **`catch`** します。 ブロック内のコードは、ブロック内の **`catch`** コードが **`try`** ステートメントで指定された型の例外をスローした場合にのみ実行され **`catch`** ます。

   次のスケルトンは **`try`** 、と **`catch`** ブロックが通常どのように配置されるかを示しています。

   [!code-cpp[NVC_MFCExceptions#4](codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]

   例外がスローされると、例外 **`catch`** 宣言が例外の型と一致する最初のブロックに制御が渡されます。 次に示すように、シーケンシャルブロックでは、さまざまな種類の例外を選択して処理でき **`catch`** ます。

   [!code-cpp[NVC_MFCExceptions#5](codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]

詳細については、「[例外: MFC 例外マクロからの変換](exceptions-converting-from-mfc-exception-macros.md)」を参照してください。

## <a name="see-also"></a>関連項目

[例外処理](exception-handling-in-mfc.md)
