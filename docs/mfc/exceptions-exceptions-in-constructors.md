---
title: '例外処理: コンス トラクターで例外 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- constructors [MFC], exceptions
- throwing exceptions [MFC], in constructors
- exceptions [MFC], in constructors
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3cab21255698c19046cfca185a0d8d7e7c530112
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421935"
---
# <a name="exceptions-exceptions-in-constructors"></a>例外処理 : コンストラクターの例外処理

コンス トラクターで例外をスローするときにで説明したように、例外をスローする前に行われたが任意のオブジェクトとメモリの割り当てをクリーンアップ[例外: 独自関数からの例外のスロー](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)します。

コンス トラクターで例外をスローするときに、コンス トラクターが呼び出された時点で、オブジェクト自体のメモリが既に割り当てられました。 そのため、コンパイラは自動的に例外がスローされた後に、オブジェクトによって占有されているメモリを解放します。

詳細については、次を参照してください。[例外: 例外処理でのオブジェクトの解放](../mfc/exceptions-freeing-objects-in-exceptions.md)します。

## <a name="see-also"></a>関連項目

[例外処理](../mfc/exception-handling-in-mfc.md)

