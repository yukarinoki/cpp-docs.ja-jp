---
title: C ランタイム エラー R6018 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6018
dev_langs:
- C++
helpviewer_keywords:
- R6018
ms.assetid: f6dd40d1-a119-4d8b-b39e-97350ea23349
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4946e3a8341963ee1a1ca2c3ad65d64cfbad8080
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="c-runtime-error-r6018"></a>C ランタイム エラー R6018
ヒープの予期しないエラー  
  
> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン内部の問題があるためです。 このエラーは、いくつかの理由が考えられますが、これをアプリのコードの欠陥によって発生は多くの場合。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [** を修復またはプログラムを再インストールします。  
> -   確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。  
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリ ベンダーにお問い合わせください。  
  
 **プログラマのための情報**  
  
 プログラムでは、メモリ管理操作の実行中に予期しないエラーが発生しました。  
  
 このエラーは、通常、プログラムが実行時のヒープのデータを誤って変更する場合に発生します。 ただし、そのことができますもによるありますランタイムまたはオペレーティング システムのコードの内部エラー。  
  
 この問題を解決するには、コード内のヒープ破損のバグを確認します。 詳細と例については、次を参照してください。 [CRT デバッグ ヒープの詳細](/visualstudio/debugger/crt-debug-heap-details)です。 次に、アプリの展開に関する最新の再頒布可能パッケージを使用していることを確認します。 詳細については、次を参照してください。 [Visual c での展開](../../ide/deployment-in-visual-cpp.md)です。