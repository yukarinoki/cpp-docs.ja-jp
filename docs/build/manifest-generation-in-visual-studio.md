---
title: Visual Studio でのマニフェスト生成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifests [C++]
ms.assetid: 0af60aa9-d223-42cd-8426-b3fc543a2a81
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73b5cbe631d078dd6ee27b4f7e0a97503c36638b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32370450"
---
# <a name="manifest-generation-in-visual-studio"></a>Visual Studio でのマニフェスト生成
プロジェクトで特定のプロジェクトのマニフェスト ファイルの生成を制御できます**プロパティ ページ**ダイアログ。 **構成プロパティ** タブで、をクリックして**リンカー**、し**マニフェスト ファイル**、し**マニフェストの生成**です。 既定では、新しいプロジェクトのプロジェクトのプロパティは、マニフェスト ファイルを生成する設定されます。 ただしを使用して、プロジェクトのマニフェストの生成を無効にすることは、**マニフェストの生成**プロジェクトのプロパティです。 このプロパティを設定すると**はい**、このプロジェクトのマニフェストを生成します。 アプリケーション コードの依存関係を解決するときに、リンカーがアセンブリ情報を無視するそれ以外の場合、マニフェストを生成しません。  
  
 Visual Studio でのビルド システムでは、最終的なバイナリ アプリケーション ファイルに埋め込まれているか、外部ファイルとして生成するマニフェストを許可します。 この動作によって制御されます、**埋め込みマニフェスト**オプション、**プロジェクト プロパティ**ダイアログ。 このプロパティを設定するには、開く、**マニフェスト ツール** ノードを選択し、**の入力し、出力**です。 マニフェストが埋め込まれていない場合は、外部ファイルとして生成され、最終的なバイナリと同じディレクトリに保存します。 マニフェストが埋め込まれている場合、Visual Studio には、次のプロセスを使用して、最終的なマニフェストが埋め込まれます。  
  
1.  コンパイルした後、ソース コードがオブジェクト ファイルに、リンカーは、依存アセンブリの情報を収集します。 最終的なバイナリをリンクする際に、リンカーは、後で最終的なマニフェストの生成に使用される中間マニフェストを生成します。  
  
2.  中間マニフェストとリンクが終了したら後、は、最終的なマニフェストをマージし、外部ファイルとして保存するマニフェスト ツールが実行されます。  
  
3.  プロジェクトでは、システムを構築し、マニフェスト ツールによって生成されたマニフェストが既にバイナリに埋め込むマニフェストは別の情報を含むかどうかを検出します。  
  
4.  バイナリ内に埋め込まれたマニフェストがマニフェストのツールによって生成されたマニフェストを異なるか、バイナリに埋め込まれたマニフェストが含まれていない場合、Visual Studio 呼び出されますリンカーもう一度マニフェスト ファイルを外部としてバイナリに埋め込むには、リソースです。  
  
5.  バイナリに埋め込むマニフェストがマニフェスト ツールによって生成されたマニフェストと同じ場合は、次のビルド ステップをビルドは続行します。  
  
 マニフェストは、最終的なバイナリ文字列リソースとして埋め込まであり、最終的なバイナリを Visual Studio でのファイルとして開くことによって表示できます。 マニフェストを適切なライブラリを指していることを確認するに説明されている手順に従います[Visual C アプリケーションの依存関係を理解する](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)で説明されている推奨事項に従うか、 [のトラブルシューティング](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)セクションです。  
  
## <a name="see-also"></a>関連項目  
 [方法: マニフェストを C/C++ アプリケーションに埋め込む](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md)   
 [プライベート アセンブリの概要](http://msdn.microsoft.com/library/ff951638)   
 [マニフェスト ツール](http://msdn.microsoft.com/library/aa375649)   
 [C/C++ プログラムのマニフェスト生成についての理解](../build/understanding-manifest-generation-for-c-cpp-programs.md)