---
title: '例外処理 : コンストラクターの例外処理'
ms.date: 11/04/2016
helpviewer_keywords:
- constructors [MFC], exceptions
- throwing exceptions [MFC], in constructors
- exceptions [MFC], in constructors
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
ms.openlocfilehash: 23d1f6a9a3c76cc9c0c1d4aebd5c0b0ea45c3154
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472270"
---
# <a name="exceptions-exceptions-in-constructors"></a>例外処理 : コンストラクターの例外処理

コンス トラクターで例外をスローするときにで説明したように、例外をスローする前に行われたが任意のオブジェクトとメモリの割り当てをクリーンアップ[例外: 独自関数からの例外のスロー](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)します。

コンス トラクターで例外をスローするときに、コンス トラクターが呼び出された時点で、オブジェクト自体のメモリが既に割り当てられました。 そのため、コンパイラは自動的に例外がスローされた後に、オブジェクトによって占有されているメモリを解放します。

詳細については、次を参照してください。[例外: 例外処理でのオブジェクトの解放](../mfc/exceptions-freeing-objects-in-exceptions.md)します。

## <a name="see-also"></a>関連項目

[例外処理](../mfc/exception-handling-in-mfc.md)

