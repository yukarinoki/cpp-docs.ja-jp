---
title: コマンドラインの警告 D9025 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9025
dev_langs:
- C++
helpviewer_keywords:
- D9025
ms.assetid: 6edff72c-1508-46c2-99f4-0e4b3c5e60c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3875a2cbd065fd5ad887267bcc80748fa9845d0d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="command-line-warning-d9025"></a>コマンド ラインの警告 D9025
・ オプション '2' と ' オプション 1' をオーバーライドします。  
  
 *Option1*オプションが指定されましたが、によってオーバーライドされたし*・ オプション 2*です。 *・ オプション 2*オプションが使用されました。  
  
 2 つのオプションは、矛盾するまたは互換性のないディレクティブを指定する場合は、ディレクティブを指定または黙示にかかわらず、コマンドラインで一番右側にあるオプションが使用されます。  
  
 開発環境からコンパイルするときに、この警告を取得していないことを確認して、競合するオプションがから送信されて、次を考慮してください。  
  
-   コード内、またはプロジェクトのプロジェクト設定で、オプションを指定できます。 コンパイラを見る場合[コマンド ライン プロパティ ページ](../../ide/command-line-property-pages.md)で競合するオプションを表示する場合と、**すべてのオプション**オプションは、プロジェクトのプロパティ ページで、それ以外の場合のオプションを設定し、フィールドソース コードで設定されます。  
  
     オプションがプロジェクトのプロパティ ページで設定されている場合は、(ソリューション エクスプ ローラーでプロジェクト ノード) のコンパイラのプリプロセッサのプロパティ ページで確認します。  設定がある、設定を確認してプリプロセッサ プロパティ ページ内の各ソース コード ファイル (ソリューション エクスプ ローラー) を確認するオプションが表示されない場合に追加されませんがあります。  
  
     コード内のオプションが設定されている場合は、コード内、または windows のヘッダーで設定でした。  プリプロセス済みのファイルを作成しようとする可能性があります ([/P](../../build/reference/p-preprocess-to-a-file.md)) シンボルを検索します。