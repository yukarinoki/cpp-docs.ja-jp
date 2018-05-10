---
title: ATL アプリケーションの再配布 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, redistributing
- redistributing ATL
- redistributing OLE DB templates
- OLE DB templates, redistributing
ms.assetid: 9a696b22-2345-43ec-826b-be7cb8cfd676
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c824dd4ae174a4418c6744e592dd62dc54b9595
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="redistributing-an-atl-application"></a>ATL アプリケーションの再配布
Visual Studio 2012 以降の Active Template Library (ATL) はヘッダーのみのライブラリです。 ATL プロジェクトには、ATL オプションへの動的リンクはありません。 再配布可能 ATL ライブラリは必要ありません。  
  
 ATL 実行可能アプリケーションを再配布する場合は、次のコマンドを実行して、.exe ファイルとそのすべてのコントロールを登録する必要があります。  
  
```  
filename /regserver  
```  
  
 `filename` は実行可能ファイルの名前です。  
  
 Visual Studio 2010 では、MinDependency または MinSize 構成用に ATL プロジェクトをビルドできます。 MinDependency 構成では、設定するときに取得、 **ATL の使用**プロパティを**ATL に静的にリンク**上、**全般**プロパティ ページとセット、 **ランタイム ライブラリ**プロパティを**マルチ スレッド (/MT)** 上、**コード生成**プロパティ ページ ([C/C++] フォルダー)。  
  
 MinSize 構成では、設定するときに取得、 **ATL の使用**プロパティを**ATL に動的にリンク**上、**全般**プロパティ ページ、またはセット、**ランタイムライブラリ**プロパティを**マルチ スレッド DLL (/MD)** 上、**コード生成**プロパティ ページ ([C/C++] フォルダー)。  
  
 MinSize により、出力ファイルは小さいことが必要 ATL100.dll と Msvcr100.dll (選択した場合、**マルチ スレッド DLL (/MD)** オプション) は、ターゲット コンピューターにします。 すべての ATL 機能を使用できるようにするために、ATL100.dll をターゲット コンピューターに登録する必要があります。 ATL100.dll には ANSI および Unicode エクスポートが含まれています。  
  
 ATL または OLE DB テンプレート プロジェクトを MinDependency ターゲット用にビルドした場合、ターゲット コンピューターへの ATL100.dll のインストールと登録は不要ですが、プログラム イメージが大きくなります。  
  
 ATL 実行可能アプリケーションを再配布する場合は、次のコマンドを実行して、.exe ファイルとそのすべてのコントロールを登録する必要があります。  
  
```  
filename /regserver  
```  
  
 `filename` は実行可能ファイルの名前です。  
  
 OLE DB テンプレート アプリケーションを再配布する場合は、ターゲット コンピューターに最新バージョンの Microsoft Data Access Components (MDAC) ファイルが必要です。 詳細については、次を参照してください。[データベース サポート ファイルの再配布](../ide/redistributing-database-support-files.md)です。  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ ファイルの再配布](../ide/redistributing-visual-cpp-files.md)