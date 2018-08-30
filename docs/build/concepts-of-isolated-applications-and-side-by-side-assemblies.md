---
title: 分離アプリケーションとサイド バイ サイド アセンブリの概念 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- side-by-side assemblies [C++]
- isolated assemblies [C++]
ms.assetid: 945a885f-cb3e-4c8a-a0b9-2c2e3e02cc50
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62420838cca0bcb2a922b01c6951749de7449e81
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222462"
---
# <a name="concepts-of-isolated-applications-and-side-by-side-assemblies"></a>分離アプリケーションおよび side-by-side アセンブリの概念
アプリケーションと見なされます、[分離アプリケーション](/windows/desktop/SbsCs/isolated-applications)場合、すべてのコンポーネントは[サイド バイ サイド アセンブリ](/windows/desktop/SbsCs/about-side-by-side-assemblies-)します。 side-by-side アセンブリは、DLL のグループ、ウィンドウ クラス、COM サーバー、タイプ ライブラリ、インターフェイスなどのリソースのコレクションで、まとめて配置され、実行時にアプリケーションで使用できます。 通常、side-by-side アセンブリは 1 つまたは複数の DLL です。  
  
## <a name="shared-or-private"></a>共有またはプライベート  
 side-by-side アセンブリには、共有またはプライベートの 2 種類があります。 [サイド バイ サイド アセンブリを共有](https://msdn.microsoft.com/library/aa375996.aspx)アセンブリへの依存をマニフェストで指定している複数のアプリケーションで使用することがあります。 また、同時に実行されている異なるアプリケーションで、複数のバージョンの side-by-side アセンブリを共有できます。 A[プライベート アセンブリ](/windows/desktop/SbsCs/about-private-assemblies-)排他的に使用するアプリケーションのアプリケーションと一緒に配置されるアセンブリします。 プライベート アセンブリは、アプリケーションの実行可能ファイルを含むフォルダー、またはそのいずれかのサブフォルダーにインストールされます。  
  
## <a name="manifests-and-search-order"></a>マニフェストと検索順序  
 分離アプリケーションとサイド バイ サイド アセンブリの両方がで説明されている[マニフェスト](https://msdn.microsoft.com/library/aa375365)します。 マニフェストは、XML ドキュメントです。これは、外部 XML ファイルにすることも、アプリケーションまたはアセンブリにリソースとして埋め込むこともできます。 分離アプリケーションのマニフェスト ファイルは、アプリケーションが実行時にバインドする共有 side-by-side アセンブリの名前およびバージョンの管理に使用されます。 side-by-side アセンブリのマニフェストは、side-by-side アセンブリの名前、バージョン、リソース、および依存アセンブリを指定します。 共有 side-by-side アセンブリの場合、マニフェストは %WINDIR%\WinSxS\Manifests\ フォルダーにインストールされます。 プライベート アセンブリの場合は、DLL に ID = 1 のリソースとしてマニフェストを含めることをお勧めします。 プライベート アセンブリの名前は、DLL の名前と同じにできます。 詳細については、次を参照してください。[プライベート アセンブリについて](/windows/desktop/SbsCs/about-private-assemblies-)します。  
  
 実行時に、Windows は、アプリケーションのマニフェストから取得されるアセンブリ情報を使用して、対応する side-by-side アセンブリの検索および読み込みを行います。 分離アプリケーションがアセンブリの依存関係を指定する場合、オペレーティング システムでは、最初に、%WINDIR%\WinSxS\ フォルダーにあるネイティブなアセンブリ キャッシュの共有アセンブリからそのアセンブリが検索されます。 要求されたアセンブリが見つからない場合、オペレーティング システムでは、次に、アプリケーションのディレクトリ構造のフォルダーにあるプライベート アセンブリが検索されます。 詳細については、次を参照してください。 [Assembly Searching Sequence](/windows/desktop/SbsCs/assembly-searching-sequence)します。  
  
## <a name="changing-dependencies"></a>依存関係の変更  
 サイド バイ サイド アセンブリの依存関係を変更するには、変更することにより、アプリケーションを展開した後、[発行者構成ファイル](/windows/desktop/SbsCs/publisher-configuration-files)と[アプリケーション構成ファイル](/windows/desktop/SbsCs/application-configuration-files)します。 発行者構成ファイルは、発行者ポリシー ファイルとも呼ばれる XML ファイルです。これは、あるバージョンの side-by-side アセンブリを使用するアプリケーションおよびアセンブリを、同じアセンブリの別のバージョンを使用するようにグローバルにリダイレクトします。 たとえば、バグ修正やセキュリティの変更が side-by-side アセンブリに配置され、修正したバージョンを使用するようにすべてのアプリケーションをリダイレクトする場合に、依存関係を変更できます。 アプリケーション構成ファイルは、あるバージョンの side-by-side アセンブリを使用する独自のアプリケーションを、同じアセンブリの別のバージョンを使用するようにリダイレクトする XML ファイルです。 アプリケーション構成ファイルを使用すると、グローバル発行者構成ファイルで定義されているバージョンとは別のバージョンの side-by-side アセンブリを使用するように、特定のアプリケーションをリダイレクトできます。 詳細については、[構成](/windows/desktop/SbsCs/configuration)に関するページを参照してください。  
  
## <a name="visual-c-libraries"></a>Visual C++ のライブラリ  
 Visual Studio 2005 および d Visual Studio 2008 では、ATL、MFC、CRT、標準 C++、OpenMP、MSDIA などの再頒布可能ライブラリが、共有 side-by-side アセンブリとして、ネイティブなアセンブリ キャッシュに配置されていました。 現在のバージョンの再頒布可能ライブラリでは、集中配置が使用されています。 既定では、Visual C++ を使用してビルドされるすべてのアプリケーションが、最終的なバイナリ内に埋め込まれたマニフェストと共にビルドされます。マニフェストには、Visual C++ ライブラリに対するバイナリの依存関係が記述されています。 Visual C++ アプリケーションのマニフェスト生成については、「 [Understanding Manifest Generation for C/C++ Programs](../build/understanding-manifest-generation-for-c-cpp-programs.md)」を参照してください。 自身のライブラリに静的にリンクしているアプリケーション、またはローカル配置が使用されているアプリケーションについては、マニフェストは必要ありません。 配置の詳細については、「 [Deployment in Visual C++](../ide/deployment-in-visual-cpp.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)