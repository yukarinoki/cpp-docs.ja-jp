---
title: '方法: CLR コンソール アプリケーションを作成 (C + + CLI) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- console applications, templates
- CLR console applications, project template
ms.assetid: e89bce3c-706f-4ae0-8a90-cb1a0f674e70
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3257d690ac949edff7958615656db052c3468c01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33132571"
---
# <a name="how-to-create-clr-console-applications-ccli"></a>方法: CLR コンソール アプリケーションを作成する (C++/CLI)
コンソール アプリケーション テンプレートを使用すると、重要なプロジェクト参照とファイルが既に含まれるコンソール アプリ プロジェクトを作成できます。  
  
 通常、コンソール アプリはスタンドアロンの実行可能ファイルにコンパイルされますが、グラフィカル ユーザー インターフェイスが使用されません。 ユーザーはコマンド プロンプトでコンソール アプリを実行し、そのコマンド プロンプトを使用して、実行中のアプリに指示を発行します。 また、アプリはコマンド プロンプトで出力情報を提供します。 コンソール アプリの即時性により、ユーザー インターフェイスの実装について心配せずにプログラミング手法を学習できます。  
  
 コンソール アプリケーション テンプレートを使用してプロジェクトを作成すると、次の参照とファイルが自動的に追加されます。  
  
-   次の .NET Framework 名前空間への参照  
  
    -   [System](https://msdn.microsoft.com/en-us/library/system.appdomainmanager.appdomainmanager.aspx)- 一般的な値の型と参照データの型、イベントとイベント ハンドラー、インターフェイス、属性、および例外処理を定義する、基礎的なクラスと基底クラスが含まれます。  
  
    -   mscorlib - .NET Framework 開発をサポートするアセンブリ DLL。  
  
-   ソース ファイル :  
  
    -   コンソール (.cpp ファイル) - 作成したアプリのエントリ ポイントへのメイン ソース ファイルとエントリ ポイント。 プロジェクトの .dll ファイルと、プロジェクトの名前空間を特定します。 このファイルには、独自のコードを記述します。  
  
    -   AssemblyInfo.cpp - プロジェクトのアセンブリ メタデータの変更に使用できる属性、ファイル、リソース、型、バージョン管理情報、署名情報などが含まれます。 詳細については、次を参照してください。[アセンブリの内容](/dotnet/framework/app-domains/assembly-contents)です。  
  
    -   Stdafx.cpp - Win32.pch という名前のプリコンパイル済みヘッダー ファイルと、StdAfx.obj という名前のプリコンパイル済み型ファイルをビルドするために使用されます。  
  
-   ヘッダー ファイル :  
  
    -   Stdafx.h - Win32.pch という名前のプリコンパイル済みヘッダー ファイルと、StdAfx.obj という名前のプリコンパイル済み型ファイルをビルドするために使用されます。  
  
    -   resource.h - app.rc 用に生成されるインクルード ファイル。  
  
-   リソース ファイル :  
  
    -   app.rc - プログラムのリソース スクリプト ファイル。  
  
    -   app.ico - プログラムのアイコン ファイル。  
  
-   ReadMe.txt - プロジェクト内のファイルについて説明します。  
  
## <a name="to-create-a-common-language-runtime-clr-console-app-project"></a>共通言語ランタイム (CLR: Common Language Runtime) コンソール アプリ プロジェクトを作成するには  
  
1.  メニュー バーで、 **[ファイル]**、 **[新規作成]**、 **[プロジェクト]** の順にクリックします。  
  
2.  **[新しいプロジェクト]** ダイアログ ボックスの **[インストールされているテンプレート]** で、 **[Visual C++]** ノード、 **[CLR]** ノード、[コンソール アプリケーション] テンプレートの順に選択します。  
  
3.  **[名前]** ボックスに、アプリケーションの一意な名前を入力します。  
  
     他のプロジェクトやソリューション設定を指定できますが、必須ではありません。  
  
4.  **[OK]** を選択します。  
  
## <a name="see-also"></a>関連項目  
 [CLR プロジェクト](../ide/files-created-for-clr-projects.md)   


