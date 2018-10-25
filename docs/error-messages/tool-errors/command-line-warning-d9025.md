---
title: コマンドラインの警告 D9025 |Microsoft Docs
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
ms.openlocfilehash: c5bcc7cbe6fcd8a61e15e80c43f27703957a1e88
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50083088"
---
# <a name="command-line-warning-d9025"></a>コマンド ラインの警告 D9025

'option2' と ' option1' をオーバーライドします。

*Option1*オプションが指定されましたが、によってオーバーライドされた、 *option2*します。 *Option2*オプションを使用しました。

2 つのオプションは、矛盾または互換性のないディレクティブを指定する場合は、指定されている一番右にコマンドラインでのオプションで、ディレクティブが使用されます。

開発環境からコンパイルするときに、この警告を取得していないことを確認して、競合するオプションの発信元は、次を考慮してください。

- コードまたはプロジェクトのプロジェクト設定のいずれかのオプションを指定できます。 コンパイラを見る場合[コマンド ライン プロパティ ページ](../../ide/command-line-property-pages.md)で競合するオプションを参照する場合と、**オプションをすべて**オプションがオプションで、プロジェクトのプロパティ ページ、それ以外の場合、設定し、フィールドソース コードで設定されます。

   プロジェクトのプロパティ ページで、オプションの設定された場合、は、(ソリューション エクスプ ローラーでプロジェクト ノード) で、コンパイラのプリプロセッサのプロパティ ページで確認します。  そこに設定をすることを確認します (ソリューション エクスプ ローラー) でソース コード ファイルごとにプリプロセッサ プロパティ ページの設定を確認のオプションが表示されない場合に追加されませんがあります。

   オプションは、コードで設定されている場合は、コードまたは windows ヘッダー設定でした。  前処理済みファイルの作成を行うこともできます ([/P](../../build/reference/p-preprocess-to-a-file.md))、シンボルを検索します。