---
title: C ランタイム エラー R6030 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6030
dev_langs:
- C++
helpviewer_keywords:
- R6030
ms.assetid: 0238a6c3-a033-4046-8adc-f8f99d961153
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ae8eb17fc9d074604586582be08c43289b680b4f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33299537"
---
# <a name="c-runtime-error-r6030"></a>C ランタイム エラー R6030
CRT 初期化されていません  
  
> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン内部の問題があるためです。 この問題は、ほとんどの場合またはによって発生、特定のセキュリティ ソフトウェア プログラムまれに、プログラムのバグです。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   この問題を緩和するための具体的な手順、セキュリティ ソフトウェアがあります。 詳細については、セキュリティ ソフトウェア ベンダーの web サイトを確認してください。 また、セキュリティ ソフトウェアの更新バージョンを確認したり、別のセキュリティ ソフトウェアを実行してください。  
> -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [** を修復またはプログラムを再インストールします。  
> -   確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。  
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリ ベンダーにお問い合わせください。  
  
 **プログラマのための情報**  
  
 このエラーは、C ランタイム (CRT) を使用しているが、CRT スタートアップ コードが実行されなかった場合に発生します。 リンカー切り替えた場合、このエラーを取得することは[/ENTRY](../../build/reference/entry-entry-point-symbol.md)が既定の開始アドレスを通常の上書きに使用**mainCRTStartup**、 **wmainCRTStartup**用、コンソールの EXE、 **WinMainCRTStartup**または**wWinMainCRTStartup**の Windows の EXE または **_DllMainCRTStartup** dll の場合。 上記の関数のいずれかがスタートアップ時に呼び出された場合を除き、C ランタイムは初期化できません。 C ランタイム ライブラリにリンクし、標準を使用するときに、これらのスタートアップ関数は、既定によって呼び出されます通常**メイン**、 **wmain**、 **WinMain**、または**DllMain**エントリ ポイントです。  
  
 別のプログラムは、特定の DLL ライブラリ呼び出しをトラップするコード インジェクション テクニックを使用する場合にエラーが発生することもできます。 関与するレベルのセキュリティ プログラムによっては、この手法を使用します。 Visual Studio 2015 より前に、の Visual C のバージョンを静的にリンクされた CRT ライブラリを使用して、問題に対処することが、これは、セキュリティおよびアプリケーションの更新プログラムの上の理由から推奨されません。 この問題を修正すると、エンドユーザーの操作が必要があります。