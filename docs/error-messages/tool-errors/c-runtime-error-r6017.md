---
title: C ランタイム エラー R6017 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6017
dev_langs:
- C++
helpviewer_keywords:
- R6017
ms.assetid: df3ec5f5-6771-4648-ba06-0e26c6a1cc6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7f726f1e01acc20899085f8f1b84f74265843bbd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302725"
---
# <a name="c-runtime-error-r6017"></a>C ランタイム エラー R6017
予期しないマルチ スレッドのロック エラーです。  
  
> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン内部の問題があるためです。 このエラーは、いくつかの理由が考えられますが、これをアプリのコードの欠陥によって発生は多くの場合。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [** を修復またはプログラムを再インストールします。  
> -   確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。  
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリ ベンダーにお問い合わせください。  
  
 **プログラマのための情報**  
  
 プロセスは、システム リソースの C ランタイム マルチ スレッドのロックにアクセスしようとしています。 中に予期しないエラーを受け取りました。 このエラーは、通常、プロセスは、ランタイム ヒープ データを誤って変更する場合に発生します。 ただし、これことができますも発生することによって、ランタイム ライブラリまたはオペレーティング システムのコードの内部エラー。  
  
 この問題を解決するには、コード内のヒープ破損のバグを確認します。 詳細と例については、次を参照してください。 [CRT デバッグ ヒープの詳細](/visualstudio/debugger/crt-debug-heap-details)です。 次に、アプリの展開に関する最新の再頒布可能パッケージを使用していることを確認します。 詳細については、次を参照してください。 [Visual c での展開](../../ide/deployment-in-visual-cpp.md)です。