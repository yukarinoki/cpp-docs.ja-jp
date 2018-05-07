---
title: 配置方法の選択 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- redistributing DLLs
- manifests [C++]
- DLLs [C++], redistributing
- side-by-side assemblies [C++]
- dynamic linking [C++]
- application deployment [C++], methods
- deploying applications [C++], methods
- static linking [C++]
- libraries [C++], application deployment issues
ms.assetid: fd8eb956-f4a0-4ffb-b401-328c73e66986
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bdf024f75f03b55465ccd15670c47d3c761e56e8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="choosing-a-deployment-method"></a>配置方法の選択
Visual C アプリケーションは自己完結型で、コピー コマンドを使用して展開することができます、しない限り、展開には、Windows インストーラーを使用することをお勧めします。 Windows インストーラーでは、インストール、修復、およびアンインストールのほか、アプリケーション ファイル、依存関係、およびレジストリ エントリの分割不可能な更新もサポートされています。  
  
> [!NOTE]
>  [ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) Visual C のネイティブ アプリケーションの展開は Visual Studio で、追加の手順が必要です。 詳細については、「 [ClickOnce Deployment for Visual C++ Applications](../ide/clickonce-deployment-for-visual-cpp-applications.md)」を参照してください。  
  
## <a name="visual-c-libraries-are-shared-dlls"></a>Visual C++ ライブラリの共有 DLL  
 Visual Studio インストーラーでは、Visual C++ ライブラリが %windir%\system32\ ディレクトリにインストールされるため、このライブラリに依存する Visual C++ アプリケーションを開発する場合、そのアプリケーションは意図したとおりに実行されます。 ただし、Visual Studio がない可能性があるコンピューターにアプリケーションを配置する場合は、ライブラリがアプリケーションと共にそのコンピューターにインストールされているかどうかを確認することをお勧めします。  
  
## <a name="redistributing-visual-c-libraries"></a>Visual C++ ライブラリの再配布  
 ご利用の配置に、再頒布用にライセンスされた任意のバージョンの Visual C++ ライブラリを再頒布できます。 配置する方法は 3 つあります。  
  
-   %Windir%\system32 に共有 Dll として Visual C ライブラリをインストールする再頒布可能パッケージを使用して一元的な展開\\です。 (このフォルダーにインストールするには管理者権限が必要です)。アプリケーションをターゲット コンピューターにインストールする前に、再頒布可能パッケージを実行するスクリプトまたはセットアップ プログラムを作成できます。 再頒布可能パッケージは、x86 プラットフォーム、x64 プラットフォーム、および ARM プラットフォーム (VCRedist_x86.exe、VCRedist_x64.exe、または VCRedist_arm.exe) で使用できます。 Visual Studio には、%programfiles (x86) %\Microsoft Visual Studio でのこれらのパッケージが含まれています`version`\VC\Redist\\`locale ID`\\です。 ダウンロードすることも、 [Microsoft ダウンロード センター](http://go.microsoft.com/fwlink/p/?linkid=132793)です。 (ダウンロード センターで、検索ボックスを使用して、検索、"Visual C 再頒布可能パッケージ*Visual Studio のバージョンと更新*"アプリケーションに一致します。 たとえば、Visual Studio 2015 update 3 を使用するアプリケーションをビルドする場合、検索"Visual C 再頒布可能パッケージ 2015 update 3"です)。再頒布可能パッケージを使用する方法については、次を参照してください。[チュートリアル: Visual c 再頒布可能パッケージを、ビジュアル C++ を使ったアプリケーションを展開](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md)です。  
  
-   %Windir%\system32 に共有 DLL として特定の Visual C ライブラリをインストールするの各マージ モジュールを使用した集中配置\\です。 (このフォルダーにインストールするには管理者権限が必要です)。マージ モジュールは、アプリケーションの .msi インストーラー ファイルの一部になります。 Visual C 再頒布可能マージ モジュールは、Visual Studio で、\Program Files (x86) \common モジュールに含まれて\\です。 詳細については、次を参照してください。[の再配布してモジュールを使用してマージ](../ide/redistributing-components-by-using-merge-modules.md)です。  
  
-   ローカル配置、Visual Studio のインストールから特定の Visual C Dll をコピーする — 通常は \Program Files (x86) \Microsoft Visual Studio で`version`\VC\Redist\\`platform`\\`library`\—andアプリケーションの実行可能ファイルと同じフォルダー内のターゲット コンピューターにインストールします。 この配置方法を使用すると、管理者権限を持たないユーザーによるインストール、またはネットワーク共有から実行できるアプリケーションに対するインストールが可能です。  
  
 再頒布可能マージ モジュールを使用する、展開し、管理者権限を持たないユーザーがインストールが実行される場合、は、Visual C Dll がインストールされていないと、アプリケーションは実行されません。 また、ユーザー単位でのインストールを許可するマージ モジュールでビルドされたアプリケーション インストーラーでは、システムのすべてのユーザーに影響を及ぼす共有の場所にライブラリがインストールされます。 ローカル配置を使用して、他のユーザーに影響するか、管理者権限を必要とすることがなく、特定のユーザーのアプリケーションのディレクトリに必要な Visual C Dll をインストールすることができます。 保守性の問題を作成できるこのため、Visual C 再頒布可能 Dll のローカル配置勧めしません。  
  
 Visual C++ ライブラリの配置が不適切だと、そのライブラリに依存するアプリケーションの実行時に実行時エラーが発生する可能性があります。 説明する検索順序を使用して、オペレーティング システムには、アプリケーションが読み込まれると[LoadLibraryEx](http://go.microsoft.com/fwlink/p/?linkid=132792)  
  
## <a name="dynamic-linking-is-better-than-static-linking"></a>動的リンクを静的リンクに優先させる  
 Visual C ライブラリを再配布する場合、静的リンクは避けることをお勧めします。 アプリケーションのパフォーマンスが静的リンクによって大きく向上することはほぼありませんが、サービスのコストは、ほとんどの場合、高くなります。 たとえば、セキュリティの強化によって更新されるライブラリに静的にリンクしているアプリケーションについて考えます。このアプリケーションは、再コンパイルして再配置しなければ、セキュリティ強化のメリットを得ることはできません。 代わりに、アプリケーションをライブラリに動的にリンクさせて、配置される場所でライブラリを更新できるようにすることをお勧めします。  
  
## <a name="see-also"></a>関連項目  
 [デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [ClickOnce のセキュリティと配置](/visualstudio/deployment/clickonce-security-and-deployment)   
 [配置例](../ide/deployment-examples.md)