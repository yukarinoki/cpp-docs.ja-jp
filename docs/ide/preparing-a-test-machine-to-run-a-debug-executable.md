---
title: デバッグ実行可能ファイルを実行するテスト マシンの準備中 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debug executable, preparing a test machine to run
ms.assetid: f0400989-cc2e-4dce-9788-6bdbe91c6f5a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33683ebe349fbfdcb3fd51179ed6bc3140510c00
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="preparing-a-test-machine-to-run-a-debug-executable"></a>デバッグ バージョンのアプリケーションを実行するテスト用コンピューターの準備
Visual C++ でビルドしたデバッグ バージョンのアプリケーションをテストする際は、そのアプリケーションが依存している Visual C++ ライブラリ DLL のデバッグ バージョンをテスト用のコンピューターに配置する必要があります。 を識別するための Dll であるを展開する必要が」の手順に従います[Visual C アプリケーションの依存関係を理解する](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)です。 Visual C++ ライブラリ DLL のデバッグ バージョンには、通常、"d" で終わる名前が付いています。たとえば、msvcr100.dll のデバッグ バージョンには、msvcr100d.dll という名前が付けられています。  
  
> [!NOTE]
>  アプリケーションのデバッグ バージョンは再配布できません。また、Visual C++ ライブラリ DLL のデバッグ バージョンも再配布できません。 アプリケーションおよび Visual C++ DLL のデバッグ バージョンは、Visual Studio がインストールされていないコンピューターでアプリケーションのデバッグとテストを行う目的でのみ、他のコンピューターにインストールできます。 詳細については、「 [Redistributing Visual C++ Files](../ide/redistributing-visual-cpp-files.md)」を参照してください。  
  
 アプリケーションのデバッグ バージョンと共に Visual C++ ライブラリ DLL のデバッグ バージョンを配置する場合、次の 3 とおりの方法があります。  
  
-   アプリケーションに適したライブラリ バージョンとアーキテクチャのマージ モジュールを含むセットアップ プロジェクトを使用して %windir%\system32\ ディレクトリに特定の Visual C++ DLL のデバッグ バージョンをインストールするには、集中配置を使用します。 マージ モジュールが Program Files または Program Files (x86) \common モジュール ディレクトリで見つかった\\です。 マージ モジュールのデバッグ バージョンには Microsoft_VC110_DebugCRT_x86.msm のような名前の Debug があります。 この展開の例は、「[チュートリアル: プロジェクトを配置する、Visual C++ を使ったアプリケーション セットアップ](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)です。  
  
-   Program Files または Program Files (x86) \Microsoft Visual Studio ディレクトリに用意されているファイルを使用して、アプリケーションのインストール ディレクトリ内の特定の Visual C DLL のデバッグ バージョンをインストールするローカル配置を使用して\<バージョン >\VC\redist\Debug_NonRedist\\です。  
  
    > [!NOTE]
    >  別のコンピューター上で Visual C++ 2005 または Visual C++ 2008 を使用してビルドされたアプリケーションをリモート デバッグする場合、Visual C++ ライブラリ DLL のデバッグ バージョンを共有の side-by-side アセンブリとして配置する必要があります。 セットアップ プロジェクトまたは Windows インストーラーを使用して、対応するマージ モジュールをインストールできます。  
  
-   使用して**展開**オプション、 **Configuration Manager**プロジェクトの出力やその他のファイルをリモート コンピューターにコピーする Visual Studio でのダイアログ ボックス。 
  
 Visual C++ DLL をインストールした後、ネットワーク共有でリモート デバッガーを実行できます。 リモート デバッグの詳細については、次を参照してください。[リモート デバッグ](/visualstudio/debugger/remote-debugging.md)です。  
  
## <a name="see-also"></a>関連項目  
 
 [Visual C での展開](../ide/deployment-in-visual-cpp.md)   
 [Windows インストーラーのコマンド ライン オプション](http://msdn.microsoft.com/library/windows/desktop/aa367988.aspx)   
 [配置例については](../ide/deployment-examples.md)[リモート デバッグ](/visualstudio/debugger/remote-debugging.md)