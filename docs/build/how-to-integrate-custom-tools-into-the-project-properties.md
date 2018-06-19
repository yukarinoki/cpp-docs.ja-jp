---
title: '方法: プロジェクトのプロパティにカスタム ツールを統合 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 04/27/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.howto.integratecustomtools
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: integrate custom tools'
ms.assetid: f32d91a4-44e9-4de3-aa9a-1c7f709ad2ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 00482aa2b4b700d15e46d0741e76dd17afc28419
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368903"
---
# <a name="how-to-integrate-custom-tools-into-the-project-properties"></a>方法: カスタム ツールをプロジェクト プロパティに統合する
カスタム ツールのオプションを追加するには、Visual Studio に**プロパティ ページ**ウィンドウでは、基になる XML スキーマ ファイルを作成します。  
  
 **構成プロパティ**のセクションで、**プロパティ ページ**ウィンドウとして知られている設定グループを表示する*ルール*です。 すべてのルールには、ツールまたは機能のグループの設定が含まれています。 たとえば、**リンカー**ルールには、リンカー ツールの設定が含まれています。 ルールの設定に分割できます*カテゴリ*です。  
  
 このドキュメントでは、Visual Studio の起動時に、プロパティが読み込まれるように、カスタム ツールのプロパティを含むセット ディレクトリにファイルを作成する方法について説明します。 ファイルを変更する方法については、次を参照してください。[プラットフォーム機能拡張の第 2 部](http://go.microsoft.com/fwlink/p/?linkid=191489)Visual Studio プロジェクトのチームのブログです。  
  
### <a name="to-add-or-change-project-properties"></a>プロジェクトのプロパティを追加または変更  
  
1.  XML エディターでは、XML ファイルを作成します。  
  
2.  Visual Studio 2017 でファイルを保存`VCTargets\1033`フォルダーです。 インストールされている Visual Studio 2017 の各エディションと言語ごとに異なるパスがあります。 たとえば、Visual Studio Enterprise edition の英語でフォルダー パスは`%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033`します。 言語および Visual Studio のエディションのパスを調整します。 内のすべてのルール、**プロパティ ページ**ウィンドウは、このフォルダーに XML ファイルで表されます。 フォルダー内のファイルの名前は一意にすることを確認します。  
  
3.  内容をコピー`%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>\cl.xml`変更を保存せずに閉じたり、および新しい XML ファイルの内容を貼り付けます。 任意の XML スキーマ ファイルを使用することができます - これは、テンプレートを使用して開始するために使用できる機能を 1 つ。  
  
4.  新しい XML ファイルでは、ニーズに合わせてコンテンツを変更します。 変更することを確認、**ルール名**と**Rule.DisplayName**ファイルの上部にあります。  
  
5.  変更を保存し、ファイルを閉じます。  
  
6.  ファイルを XML`%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>`は、Visual Studio の起動時に読み込まれます。 そのため、新しいファイルをテストするには、Visual Studio を再起動します。  
  
7.  **ソリューション エクスプ ローラー**、プロジェクトを右クリックし、クリックして**プロパティ**です。 **プロパティ ページ**ウィンドウの左側のウィンドウで、ルールの名前を持つ新しいノードがあることを確認してください。  
  
## <a name="see-also"></a>関連項目  
 [MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)
