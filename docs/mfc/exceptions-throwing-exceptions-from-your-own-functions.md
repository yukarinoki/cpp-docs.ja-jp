---
title: '例外処理: 独自関数からの例外のスロー |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- throwing exceptions [MFC], from functions
- functions [MFC], throwing exceptions
- exceptions [MFC], throwing
ms.assetid: 492976e8-8804-4234-8e8f-30dffd0501be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a6ef86f54442031b4383e6a0b8cc6f57e4e53d58
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418425"
---
# <a name="exceptions-throwing-exceptions-from-your-own-functions"></a>例外処理 : 独自関数からの例外のスロー

MFC やその他のライブラリ内の関数によってスローされた例外をキャッチするためだけに MFC 例外処理のパラダイムを使用することになります。 ライブラリ コードによってスローされた例外をキャッチするだけでなく例外的な状況が発生することができます関数を記述する場合、独自のコードから例外をスローすることができます。

現在の関数の実行が停止しに直接ジャンプ、例外がスローされたときに、**キャッチ**最も内側の例外フレームのブロック。 例外処理機構は、関数からの正常終了のパスをバイパスします。 そのため、通常の終了時に削除されるメモリ ブロックを削除することを確認する必要があります。

#### <a name="to-throw-an-exception"></a>例外をスローするには

1. MFC のヘルパー関数のいずれかのような使用`AfxThrowMemoryException`します。 これらの関数は、適切な型の事前割り当て済みの例外オブジェクトをスローします。

     次の例では、関数は、2 つのメモリ ブロックの割り当てが試行され、いずれかの割り当てに失敗した場合に例外をスローします。

     [!code-cpp[NVC_MFCExceptions#17](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_1.cpp)]

     最初の割り当てに失敗した場合、メモリの例外をスローすることができます。 最初の割り当てが成功したが、2 つ目ができない場合は、例外をスローする前に、最初の割り当てブロックを解放する必要があります。 両方の割り当てが成功した場合は、通常どおり続行して、関数の終了時にブロックを解放します。

     - または

1. ユーザー定義の例外を使用して、問題の状況を示します。 でも、クラス全体は、あらゆる種類の項目は、例外としてスローできます。

     次の例では、wave デバイスを介してサウンドを再生しようとしていますし、障害が発生した場合に例外をスローします。

     [!code-cpp[NVC_MFCExceptions#18](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_2.cpp)]

> [!NOTE]
>  MFC の例外の既定の処理がへのポインターにのみ適用されます`CException`オブジェクト (とオブジェクトの`CException`-派生クラス)。 上記の例では、MFC の例外処理機構がバイパスされます。

## <a name="see-also"></a>関連項目

[例外処理](../mfc/exception-handling-in-mfc.md)

