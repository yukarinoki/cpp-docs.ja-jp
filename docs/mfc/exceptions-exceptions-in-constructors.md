---
title: '例外処理: コンス トラクターの例外 |Microsoft ドキュメント'
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
ms.openlocfilehash: 8336700cc0137efe3bc106871ebd76b8de7a99af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-exceptions-in-constructors"></a>例外処理 : コンストラクターの例外処理
コンス トラクターで例外をスローするときにどのようなオブジェクトとのメモリ割り当てを加えた例外をスローする前に」の説明に従ってクリーンアップ[例外: 独自関数から例外をスロー](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)です。  
  
 コンス トラクターで例外をスローするときに、オブジェクト自体のメモリは、コンス トラクターが呼び出されるによって既に割り当てられています。 そのため、コンパイラは自動的に例外がスローされた後に、オブジェクトが占有するメモリを解放します。  
  
 詳細については、次を参照してください。[例外: 例外処理でのオブジェクトの解放](../mfc/exceptions-freeing-objects-in-exceptions.md)です。  
  
## <a name="see-also"></a>関連項目  
 [例外処理](../mfc/exception-handling-in-mfc.md)

