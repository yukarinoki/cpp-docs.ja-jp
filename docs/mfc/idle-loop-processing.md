---
title: アイドリング ループ処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, background processing
- PeekMessage method [MFC], elsewhere than message loop
- PeekMessage method [MFC]
- MFC, messages
- messages [MFC], loops
- OnIdle method [MFC]
- processing [MFC], background
- idle loop processing [MFC]
- idle processing [MFC]
- threading [MFC], alternatives to multithreading
- processing, during idle loop
- processing [MFC]
- background processing [MFC]
ms.assetid: 5c7c46c1-6107-4304-895f-480983bb1e44
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 20be85f7089f2a53b067d7287780159de51a8c86
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929557"
---
# <a name="idle-loop-processing"></a>アイドリング ループ処理
多くのアプリケーションを実行時間のかかる処理"、"バック グラウンドします。 場合によってパフォーマンスに関する考慮事項では、このような作業のマルチ スレッドを使用してによって決まります。 MFC では、アイドル時間作業などの単純なタスクには推奨されませんので、スレッドが開発に余分なオーバーヘッドを含む、 [OnIdle](../mfc/reference/cwinthread-class.md#onidle)関数。 この記事は、アイドル状態の処理について説明します。 マルチ スレッド処理、参照の詳細については[マルチ スレッド トピック](../parallel/multithreading-support-for-older-code-visual-cpp.md)です。  
  
 バック グラウンド処理の種類によっては、ユーザーは、それ以外の場合と対話していないアプリケーション間隔中に適切に行われます。 アプリケーションでは、Microsoft Windows オペレーティング システム用に開発された、アプリケーションは、小さなフラグメントの数を時間のかかるプロセスを分割してアイドル時の処理を実行できます。 各フラグメントを処理した後、アプリケーションは、実行制御を使用して Windows を生成、 [PeekMessage](http://msdn.microsoft.com/library/windows/desktop/ms644943)ループします。  
  
 この記事では、アイドル、アプリケーションで処理を行う 2 つの方法について説明します。  
  
-   使用して**PeekMessage** MFC のメイン メッセージ ループにします。  
  
-   別の埋め込み**PeekMessage**アプリケーション内の他の場所をループします。  
  
##  <a name="_core_peekmessage_in_the_mfc_message_loop"></a> MFC のメッセージ ループで PeekMessage  
 MFC で開発したアプリケーションは、メインのメッセージ ループ、`CWinThread`クラスには、呼び出すメッセージ ループが含まれています、 [PeekMessage](http://msdn.microsoft.com/library/windows/desktop/ms644943) Win32 API です。 これは、ループの呼び出しにも、`OnIdle`のメンバー関数`CWinThread`メッセージ間です。 アプリケーションはオーバーライドすることでこのアイドル時間でメッセージを処理することができます、`OnIdle`関数。  
  
> [!NOTE]
>  `Run`、 `OnIdle`、およびその他の特定のメンバー関数は、クラスのメンバーであるようになりました`CWinThread`クラスのではなく`CWinApp`です。 `CWinApp` は、`CWinThread` から派生しています。  
  
 アイドル処理の詳細については、次を参照してください。 [OnIdle](../mfc/reference/cwinthread-class.md#onidle)で、 *『 MFC リファレンス*です。  
  
##  <a name="_core_peekmessage_elsewhere_in_your_application"></a> PeekMessage、アプリケーションで別の場所  
 アプリケーションでアイドル処理を実行するための別の方法には、関数のいずれかでメッセージ ループを埋め込むことが含まれます。 このメッセージ ループが非常にループと同様に MFC のメイン メッセージで見つかった[CWinThread::Run](../mfc/reference/cwinthread-class.md#run)です。 つまり、MFC で開発されたアプリケーション内のようなループは、メイン メッセージ ループと同じ機能の多くを実行する必要があります。 次のコード フラグメントでは、MFC と互換性があるメッセージ ループを記述を示しています。  
  
 [!code-cpp[NVC_MFCDocView#8](../mfc/codesnippet/cpp/idle-loop-processing_1.cpp)]  
  
 関数の場合に埋め込まれた、このコードは、アイドル状態の処理を行うにがある限り、ループ処理します。 そのループ内で入れ子になったループを繰り返し呼び出す`PeekMessage`です。 その呼び出しは、0 以外の値を返す、限り、ループを呼び出す`CWinThread::PumpMessage`を通常のメッセージの変換とディスパッチを実行します。 `PumpMessage`は文書化、Visual C インストールの \atlmfc\src\mfc ディレクトリに ThrdCore.Cpp ファイルの場合は、そのソース コードを確認することができます。  
  
 1 回、内側のループの終了、外側のループ処理を実行アイドル状態に 1 つまたは複数の呼び出しと`OnIdle`です。 最初の呼び出しは、MFC の目的です。 追加の呼び出しを行うことができます`OnIdle`バック グラウンド作業を行います。  
  
 アイドル処理の詳細については、次を参照してください。 [OnIdle](../mfc/reference/cwinthread-class.md#onidle) MFC ライブラリ リファレンスです。  
  
## <a name="see-also"></a>関連項目  
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)

