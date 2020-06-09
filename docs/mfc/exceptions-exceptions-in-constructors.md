---
title: '例外処理 : コンストラクターの例外処理'
ms.date: 11/04/2016
helpviewer_keywords:
- constructors [MFC], exceptions
- throwing exceptions [MFC], in constructors
- exceptions [MFC], in constructors
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
ms.openlocfilehash: 4089f4d44f03c7de3432f137b5d28f74189e1cb9
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624610"
---
# <a name="exceptions-exceptions-in-constructors"></a>例外処理 : コンストラクターの例外処理

コンストラクターで例外をスローする場合は、「[例外: 独自の関数からの例外のスロー](exceptions-throwing-exceptions-from-your-own-functions.md)」で説明されているように、例外をスローする前に作成したオブジェクトとメモリ割り当てをすべてクリーンアップします。

コンストラクターで例外をスローする場合、オブジェクト自体のメモリは、コンストラクターが呼び出されたときに既に割り当てられています。 そのため、コンパイラは、例外がスローされた後、オブジェクトによって占有されているメモリの割り当てを自動的に解除します。

詳細については、「[例外: 例外でのオブジェクトの解放](exceptions-freeing-objects-in-exceptions.md)」を参照してください。

## <a name="see-also"></a>関連項目

[例外処理](exception-handling-in-mfc.md)
