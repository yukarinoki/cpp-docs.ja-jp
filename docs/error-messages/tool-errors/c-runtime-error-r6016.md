---
title: C ランタイム エラー R6016 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6016
dev_langs:
- C++
helpviewer_keywords:
- R6016
ms.assetid: 7bd3f274-d9c4-4bc4-8252-80bf168c4c3a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f366ceff24ce65e6f7869f9709f547651687c327
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="c-runtime-error-r6016"></a>C ランタイム エラー R6016
not enough space for thread data  
  
> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン、内部メモリの問題があるためです。 このエラーは、多くの理由が考えられますが、非常に低いメモリ状態をアプリのバグ、またはアドインまたはアプリで使用される拡張機能でバグの発生頻度。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   その他の実行中のアプリケーションを閉じるか、メモリを解放する、コンピューターを再起動します。  
> -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [** を修復または、アプリを再インストールします。  
> -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [** 削除、修復、またはアドインやアプリによって使用される拡張機能を再インストールします。  
> -   確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。  
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリ ベンダーにお問い合わせください。  
  
 **プログラマのための情報**  
  
 プログラムが完了するオペレーティング システムから十分なメモリを受信していないために、このエラーが発生した、 [_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md)または`_beginthreadex`呼び出し、またはスレッドでローカル ストレージが初期化されていない`_beginthread`または`_beginthreadex`です。  
  
 新規スレッドの開始時、ライブラリは、そのスレッド用に新しい内部データベースを生成する必要があります。 オペレーティング システムのメモリを使用してデータベースを展開できないと、スレッドは開始されず、スレッドの呼び出しプロセスは停止します。 これは、プロセスによって作成されたスレッドが多すぎる場合、またはスレッド ローカル ストレージが不足している場合に発生する可能性があります。  
  
 C ランタイム ライブラリ (CRT) を呼び出す実行可能ファイルを使用することをお勧め`_beginthreadex`Windows API ではなく、スレッドの作成の`CreateThread`します。 `_beginthreadex` は、スレッド ローカル ストレージで多くの CRT 関数によって使用される内部静的ストレージを初期化します。 `CreateThread` を使用してスレッドを作成すると、初期化された静的内部ストレージを必要とする CRT 関数が呼び出されたときに、R6016 でプロセスが終了する場合があります。