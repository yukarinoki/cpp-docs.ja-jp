---
title: '例外処理 : 独自関数からの例外のスロー'
ms.date: 11/04/2016
helpviewer_keywords:
- throwing exceptions [MFC], from functions
- functions [MFC], throwing exceptions
- exceptions [MFC], throwing
ms.assetid: 492976e8-8804-4234-8e8f-30dffd0501be
ms.openlocfilehash: 6484594df7636fd52ac46ab1cc212c8e2ec0278e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359278"
---
# <a name="exceptions-throwing-exceptions-from-your-own-functions"></a>例外処理 : 独自関数からの例外のスロー

MFC 例外処理パラダイムを使用して、MFC やその他のライブラリの関数によってスローされた例外をキャッチするためだけに使用できます。 例外が発生する可能性がある関数を作成する場合は、ライブラリ コードによってスローされた例外をキャッチするだけでなく、独自のコードから例外をスローすることもできます。

例外がスローされると、現在の関数の実行が停止され、最も内側の例外フレームの**catch**ブロックに直接ジャンプします。 例外メカニズムは、関数からの通常の出口パスをバイパスします。 したがって、通常の出口で削除されるメモリ ブロックは必ず削除する必要があります。

#### <a name="to-throw-an-exception"></a>例外をスローするには

1. などの`AfxThrowMemoryException`MFC ヘルパー関数の 1 つを使用します。 これらの関数は、適切な型の事前割り当て例外オブジェクトをスローします。

   次の例では、関数は 2 つのメモリ ブロックを割り当てようとし、いずれかの割り当てが失敗した場合に例外をスローします。

   [!code-cpp[NVC_MFCExceptions#17](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_1.cpp)]

   最初の割り当てが失敗した場合は、メモリ例外をスローするだけです。 最初の割り当てが成功しても、2 番目の割り当てが失敗した場合は、例外をスローする前に最初の割り当てブロックを解放する必要があります。 両方の割り当てが成功した場合は、正常に処理を続行し、関数を終了するときにブロックを解放できます。

     - - または -

1. ユーザー定義の例外を使用して、問題の状態を示します。 例外として、クラス全体を含め、任意の型の項目をスローできます。

   次の例では、Wave デバイスを介してサウンドを再生しようとし、障害が発生した場合に例外をスローします。

   [!code-cpp[NVC_MFCExceptions#18](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_2.cpp)]

> [!NOTE]
> MFC の既定の例外処理は、オブジェクト (および -derived クラスの`CException``CException`オブジェクト) へのポインターにのみ適用されます。 上記の例では、MFC の例外メカニズムをバイパスします。

## <a name="see-also"></a>関連項目

[例外処理](../mfc/exception-handling-in-mfc.md)
