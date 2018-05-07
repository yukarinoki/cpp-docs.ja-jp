---
title: Visual C アプリケーションの ClickOnce 配置 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++], ClickOnce
- application deployment [C++], ClickOnce
- ClickOnce deployment [C++], C++ applications
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e85ec0dfc011aab4d2b3ac835bbe71782b055000
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="clickonce-deployment-for-visual-c-applications"></a>Visual C++ アプリケーションの ClickOnce 配置
Visual Studio では、Windows アプリケーションの展開に関する 2 つのテクノロジが用意されています: ClickOnce 配置または[Windows インストーラー](http://msdn.microsoft.com/library/cc185688)展開します。  
  
## <a name="clickonce-deployment-in-c"></a>C++ の ClickOnce 配置  
 Visual C 開発環境は、ClickOnce では、Visual C プロジェクトの配置を直接サポートしていませんが、ツールを使用する利用できます。  
  
> [!NOTE]
>  Visual Studio は Visual c# および Visual Basic の開発環境で ClickOnce をサポートします。 (その依存関係を含む) アプリケーションを発行するには、Visual C プロジェクトが Visual c# プロジェクトの依存関係の場合は、Visual c# 開発環境からの ClickOnce 配置を使用します。  
  
 ClickOnce を使用して Visual C アプリケーションを展開するには、最初に構築する必要が、 [ClickOnce アプリケーション マニフェスト](/visualstudio/deployment/clickonce-application-manifest)と[ClickOnce 配置マニフェスト](/visualstudio/deployment/clickonce-deployment-manifest)を使用して、 [Mage.exe (マニフェスト生成および編集ツール)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)またはのグラフィカル ユーザー インターフェイスのバージョン (詳細については、次を参照してください。 [MageUI.exe (マニフェスト生成および編集ツールのグラフィカル クライアント)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client))。  

  
 最初に、Mage.exe を使用してアプリケーション マニフェストをビルドします。作成されるファイルには拡張子 .manifest が付きます。 次に、Mage.exe を使用して配置マニフェストをビルドします。作成されるファイルには拡張子 .application が付きます。 次にマニフェストに署名します。  
  
 アプリケーション マニフェストはターゲット プロセッサを指定する必要があります (**x86**、 **x64**、または**ARM**)。 参照してください[64 ビット アプリケーションの展開の前提条件](/visualstudio/deployment/deploying-prerequisites-for-64-bit-applications)については、これらのオプションです。  
  
 また、アプリケーション マニフェストと配置マニフェストの名前は C++ アプリケーションの名前と異なっている必要があります。 これによって、Mage.exe で作成されるアプリケーション マニフェストと C++ アプリケーションの一部である外部マニフェストの間の競合を回避できます。  
  
 デプロイは、アプリケーションが依存する Visual C ライブラリをインストールする必要があります。 特定のアプリケーションの依存関係を確認するには、depends.exe または DUMPBIN ユーティリティを /DEPENDENTS オプションと共に使用します。 依存関係の詳細については、次を参照してください。 [Visual c アプリケーションの依存関係を理解する](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)です。 VCRedist.exe; を実行する必要があります。このユーティリティは、ターゲット コンピューター上の Visual C ライブラリをインストールします。  
  
 前提条件コンポーネントを配置するアプリケーションのブートス トラップ (前提条件インストーラー) をビルドする必要がありますもブートス トラップのについては、次を参照してください。[ブートス トラップ パッケージを作成する](/visualstudio/deployment/creating-bootstrapper-packages)です。  
  
 テクノロジの詳細については、次を参照してください。 [ClickOnce のセキュリティと配置](/visualstudio/deployment/clickonce-security-and-deployment)です。 ClickOnce 配置の詳細な例についてを参照してください。[チュートリアル: ClickOnce アプリケーションを手動で配置する](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)です。  
  
## <a name="see-also"></a>関連項目  
 [Mage.exe (マニフェストの生成および編集ツール)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe (マニフェスト生成および編集ツールのグラフィカル クライアント)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)   
 [Makecert.exe (証明書作成ツール)](https://msdn.microsoft.com/library/windows/desktop/aa386968)   
 [デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [アプリケーション、サービス、およびコンポーネントを展開します。](/visualstudio/deployment/deploying-applications-services-and-components)   
 [Windows インストーラーの配置](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)   
 [ClickOnce のセキュリティと配置](/visualstudio/deployment/clickonce-security-and-deployment)   
 [ブートス トラップ パッケージを作成します。](/visualstudio/deployment/creating-bootstrapper-packages)   
 [.NET プログラミング C + +/CLI (Visual C)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [ネイティブと .NET の相互運用性](../dotnet/native-and-dotnet-interoperability.md)