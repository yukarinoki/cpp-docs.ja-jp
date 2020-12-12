---
description: '詳細情報: 例外: コンストラクターの例外'
title: '例外処理 : コンストラクターの例外処理'
ms.date: 11/04/2016
helpviewer_keywords:
- constructors [MFC], exceptions
- throwing exceptions [MFC], in constructors
- exceptions [MFC], in constructors
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
ms.openlocfilehash: 69393cc6a5cf709d359ccbdb572406e91c6788ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290597"
---
# <a name="exceptions-exceptions-in-constructors"></a>例外処理 : コンストラクターの例外処理

コンストラクターで例外をスローする場合は、「 [例外: 独自の関数からの例外のスロー](exceptions-throwing-exceptions-from-your-own-functions.md)」で説明されているように、例外をスローする前に作成したオブジェクトとメモリ割り当てをすべてクリーンアップします。

コンストラクターで例外をスローする場合、オブジェクト自体のメモリは、コンストラクターが呼び出されたときに既に割り当てられています。 そのため、コンパイラは、例外がスローされた後、オブジェクトによって占有されているメモリの割り当てを自動的に解除します。

詳細については、「 [例外: 例外でのオブジェクトの解放](exceptions-freeing-objects-in-exceptions.md)」を参照してください。

## <a name="see-also"></a>関連項目

[例外処理](exception-handling-in-mfc.md)
