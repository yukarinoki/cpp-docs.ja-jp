---
title: '例外処理: 独自関数から例外をスローする |Microsoft ドキュメント'
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
ms.openlocfilehash: dae6f2c0d1cab021cc91854a34f10423a1122dec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-throwing-exceptions-from-your-own-functions"></a>例外処理 : 独自関数からの例外のスロー
MFC またはその他のライブラリ内の関数によってスローされる例外をキャッチするだけの MFC 例外処理のパラダイムを使用して行うことができます。 ライブラリ コードによってスローされる例外をキャッチするだけでなく例外条件を発生する可能性がある関数を作成している場合に、独自のコードから例外をスローできます。  
  
 現在の関数の実行が停止しに直接移動することで例外がスローされたときに、**キャッチ**最も内側の例外のフレームのブロックです。 例外処理機構は、関数からの正常終了パスをバイパスします。 そのため、通常の終了時に削除されるメモリ ブロックを削除することを確認する必要があります。  
  
#### <a name="to-throw-an-exception"></a>例外をスローするには  
  
1.  MFC ヘルパー関数のいずれかのような使用`AfxThrowMemoryException`です。 これらの関数は、適切な型の事前に割り当てられた例外オブジェクトをスローします。  
  
     次の例では、関数は、2 つのメモリ ブロックの割り当てを試行し、いずれかの割り当てに失敗した場合、例外をスローします。  
  
     [!code-cpp[NVC_MFCExceptions#17](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_1.cpp)]  
  
     最初の割り当てが失敗した場合、単にメモリ例外がスローすることができます。 最初の割り当てが成功したが、2 つ目が失敗した場合は、例外をスローする前に最初の割り当てブロックを解放する必要があります。 両方の割り当てが成功した場合は、通常どおりに実行し、関数の終了時にブロックを解放できます。  
  
     - または  
  
2.  ユーザー定義の例外を使用して、問題の状況を示します。 でも、クラス全体の任意の型の項目は、例外としてスローできます。  
  
     次の例では、wave デバイスからサウンドを再生しようとしていますし、エラーが発生した場合、例外をスローします。  
  
     [!code-cpp[NVC_MFCExceptions#18](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_2.cpp)]  
  
> [!NOTE]
>  MFC の例外の既定の処理がへのポインターにのみ適用されます`CException`オブジェクト (のおよびオブジェクト`CException`-派生クラス)。 上記の例では、MFC の例外処理機構をバイパスします。  
  
## <a name="see-also"></a>関連項目  
 [例外処理](../mfc/exception-handling-in-mfc.md)

