---
title: 配置の概念 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Installer [C++]
- dependencies [C++], application deployment and
- application deployment [C++], about application deployment
- deploying applications [C++], about deploying applications
- libraries [C++], application deployment issues
ms.assetid: ebd7f246-ab54-40e8-87fa-dac02c0047b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4fa40373e268c76caca17f3466573bc3e830757
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="deployment-concepts"></a>配置の概念
このセクションでは、C++ アプリケーションの展開に関する主な考慮事項について説明します。  
  
## <a name="windows-installer-deployment-in-c"></a>C++ で Windows インストーラーの展開  
 通常、visual C プロジェクトは、展開の従来の Windows インストーラー セットアップを使用します。 Windows インストーラーの展開を準備するのには、setup.exe ファイルでアプリケーションをパッケージ化し、インストーラー パッケージ (.msi) と共に、そのファイルを配布します。 ユーザーは、アプリケーションをインストールする setup.exe を実行しています。  
  
 セットアップ プロジェクトをソリューションに追加することで、アプリケーションをパッケージ化します。構築時に、ファイルが作成をセットアップしてインストーラー パッケージをユーザーに配布します。 詳細については、次を参照してください。[配置方法の選択](../ide/choosing-a-deployment-method.md)です。  
  
## <a name="library-dependencies"></a>ライブラリの依存ファイル  
 構築時に C/C++ アプリケーションは、Visual C ライブラリで提供される機能を使用して、実行時にこれらのライブラリの存在に依存しているになります。 アプリケーションを実行するためには、その必要があります、静的または動的にライブラリにリンク、必要な Visual C。 かどうか、アプリケーションに動的に Visual C ライブラリにし、そのライブラリを実行するときのリンクでなければなりません存在ため、読み込むことができます。 一方で、アプリケーションは、Visual C ライブラリに静的にリンクすることが場合、その必要はありません、ユーザーのコンピューターに存在している、対応する Dll です。 アプリケーション ファイルのサイズを増やすとなり、メンテナンスがより難しい可能性があるなど、負の値影響が生じます。 ただし、静的リンクします。 詳細については、次を参照してください。 [Dll の利点](../build/dlls-in-visual-cpp.md#advantages-of-using-dlls)です。  
  
## <a name="packaging-and-redistributing"></a>パッケージ化と再配布  
 Visual C ライブラリは、Dll としてパッケージ化し、C/C++ アプリケーションの必要なすべてのライブラリは、Visual Studio によって、開発者のコンピューターにインストールされています。 ただし、ユーザーにアプリケーションを展開するときにない可能なほとんどの場合に、アプリケーションを実行するために Visual Studio をインストールする必要があります。 正常に実行するアプリケーションで必要な Visual C の部分のみを再配布できる重要です。  
  
 パッケージ化と再配布する方法の詳細については、次のトピックを参照してください。  
  
-   [再配布する Dll の決定](../ide/determining-which-dlls-to-redistribute.md)です。  
  
-   [配置方法の選択](../ide/choosing-a-deployment-method.md)です。  
  
 展開例と推奨事項のトラブルシューティングについてを参照してください。  
  
-   [配置例については](../ide/deployment-examples.md)します。  
  
-   [トラブルシューティング C/C++ 分離アプリケーションおよびサイド バイ サイド アセンブリ](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)です。  
  
## <a name="see-also"></a>関連項目  
 [デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Visual C アプリケーションの依存関係を理解します。](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)   
 [Windows インストーラーの配置](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)