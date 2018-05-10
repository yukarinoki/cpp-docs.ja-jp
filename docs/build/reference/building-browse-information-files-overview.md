---
title: 'ブラウザー情報ファイルのビルド: 概要 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- .bsc files, about .bsc files
- bsc files, about bsc files
- browse information files (.bsc)
- browse information files (.bsc), creating
ms.assetid: b5c12832-51f6-4953-8044-4264dd0fb242
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6a2306c69c219320e11259ba6303b76588db8f7b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="building-browse-information-files-overview"></a>ブラウザー情報ファイルのビルド : 概要
シンボル参照の参照情報を作成するには、コンパイラは、BSCMAKE のプロジェクトでソース ファイルごとに .sbr ファイルを作成します。Exe ファイルは、1 つの .bsc ファイル .sbr ファイルを連結します。  
  
 .Sbr ファイルと .bsc ファイルを生成する、時間がかかるため、Visual C は、既定でオフこれらの関数にします。 現在の情報を参照する場合は、[参照] オプションをオンにして、プロジェクトを再度ビルドします。  
  
 使用して[/FR](../../build/reference/fr-fr-create-dot-sbr-file.md)または[/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md) .sbr ファイルを作成するようにコンパイラに指示します。 .Bsc ファイルを作成するに呼び出せる[BSCMAKE](../../build/reference/bscmake-command-line.md)コマンドラインからです。 BSCMAKE コマンドラインから使用するブラウザー情報ファイルの操作をより正確に制御します。 参照してください[BSCMAKE リファレンス](../../build/reference/bscmake-reference.md)詳細についてはします。  
  
> [!TIP]
>  .Bsc ファイルの生成がオフのままには、.sbr ファイルの生成を有効にすることができます。 これにより、高速のビルドは .bsc ファイルの生成をオンにし、プロジェクトをビルドして新しい .bsc ファイルをすばやく作成することもできます。  
  
 時間、メモリ、および .bsc ファイルのサイズを小さくして .bsc ファイルの作成に必要なディスク領域を減らすことができます。  
  
 参照してください[[全般] プロパティ ページ (プロジェクト)](../../ide/general-property-page-project.md)開発環境でブラウザー ファイルをビルドする方法についてはします。  
  
### <a name="to-create-a-smaller-bsc-file"></a>小さい .bsc ファイルを作成するには  
  
1.  使用して[BSCMAKE コマンド ライン オプション](../../build/reference/bscmake-options.md)ブラウザー情報ファイルから情報を除外します。  
  
2.  コンパイルまたはアセンブルすると、.sbr ファイルの 1 つまたは複数のローカル シンボルを省略します。  
  
3.  オブジェクト ファイルに、現在のステージのデバッグに必要な情報が含まれていない場合は、ブラウザー情報ファイルをリビルドするときに、BSCMAKE コマンドからの .sbr ファイルを省略します。  
  
### <a name="to-combine-the-browse-information-from-several-projects-into-one-browser-file-bsc"></a>参照情報を 1 つのブラウザー ファイル (.bsc) に複数のプロジェクトを結合するには  
  
1.  いずれかが、プロジェクト レベルで .bsc ファイルをビルドしたり/n スイッチを使用して、.sbr ファイルが切り詰められていることを防ぐしないでください。  
  
2.  すべてのプロジェクトが構築された後に、入力としてのすべての .sbr ファイルで BSCMAKE を実行します。 ワイルドカードを使用します。 インスタンスの場合、それらのツールやすべて .bsc ファイルを 1 つに結合したいの .sbr ファイルをプロジェクト ディレクトリ C:\X、C:\Y、および C:\Z していたを使用して BSCMAKE C:\X\\*.sbr C:\Y\\\*.sbr C:\Z\\\*です。結合された .bsc ファイルをビルドする sbr/o c:\whatever_directory\combined.bsc です。  
  
## <a name="see-also"></a>関連項目  
 [C/C++ ビルド ツール](../../build/reference/c-cpp-build-tools.md)   
 [BSCMAKE リファレンス](../../build/reference/bscmake-reference.md)