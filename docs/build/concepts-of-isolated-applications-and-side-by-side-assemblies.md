---
title: 分離アプリケーションおよび side-by-side アセンブリの概念
ms.date: 05/06/2019
helpviewer_keywords:
- side-by-side assemblies [C++]
- isolated assemblies [C++]
ms.assetid: 945a885f-cb3e-4c8a-a0b9-2c2e3e02cc50
ms.openlocfilehash: f569381b9efe9a8ca7704dc87bcb8e8102e0cde2
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220907"
---
# <a name="concepts-of-isolated-applications-and-side-by-side-assemblies"></a>分離アプリケーションおよび side-by-side アセンブリの概念

アプリケーションのコンポーネントがすべて [side-by-side アセンブリ](/windows/desktop/SbsCs/isolated-applications) である場合、そのアプリケーションは [分離アプリケーション](/windows/desktop/SbsCs/about-side-by-side-assemblies-)と見なされます。 side-by-side アセンブリは、DLL のグループ、ウィンドウ クラス、COM サーバー、タイプ ライブラリ、インターフェイスなどのリソースのコレクションで、まとめて配置され、実行時にアプリケーションで使用できます。 通常、side-by-side アセンブリは 1 つまたは複数の DLL です。

## <a name="shared-or-private"></a>共有またはプライベート

side-by-side アセンブリには、共有またはプライベートの 2 種類があります。 [共有 side-by-side アセンブリ](https://msdn.microsoft.com/library/aa375996.aspx) は、そのアセンブリへの依存をマニフェストで指定している複数のアプリケーションで使用できます。 また、同時に実行されている異なるアプリケーションで、複数のバージョンの side-by-side アセンブリを共有できます。 [プライベート アセンブリ](/windows/desktop/SbsCs/about-private-assemblies-) は、アプリケーションと一緒に配置されるアセンブリで、そのアプリケーションのみが排他的に使用します。 プライベート アセンブリは、アプリケーションの実行可能ファイルを含むフォルダー、またはそのいずれかのサブフォルダーにインストールされます。

## <a name="manifests-and-search-order"></a>マニフェストと検索順序

分離アプリケーションと side-by-side アセンブリは、いずれも [マニフェスト](/windows/desktop/sbscs/manifests)に記述されています。 マニフェストは、XML ドキュメントです。これは、外部 XML ファイルにすることも、アプリケーションまたはアセンブリにリソースとして埋め込むこともできます。 分離アプリケーションのマニフェスト ファイルは、アプリケーションが実行時にバインドする共有 side-by-side アセンブリの名前およびバージョンの管理に使用されます。 side-by-side アセンブリのマニフェストは、side-by-side アセンブリの名前、バージョン、リソース、および依存アセンブリを指定します。 共有 side-by-side アセンブリの場合、マニフェストは %WINDIR%\WinSxS\Manifests\ フォルダーにインストールされます。 プライベート アセンブリの場合は、DLL に ID = 1 のリソースとしてマニフェストを含めることをお勧めします。 プライベート アセンブリの名前は、DLL の名前と同じにできます。 詳細については、次を参照してください。[プライベート アセンブリについて](/windows/desktop/SbsCs/about-private-assemblies-)します。

実行時に、Windows は、アプリケーションのマニフェストから取得されるアセンブリ情報を使用して、対応する side-by-side アセンブリの検索および読み込みを行います。 分離アプリケーションがアセンブリの依存関係を指定する場合、オペレーティング システムでは、最初に、%WINDIR%\WinSxS\ フォルダーにあるネイティブなアセンブリ キャッシュの共有アセンブリからそのアセンブリが検索されます。 要求されたアセンブリが見つからない場合、オペレーティング システムでは、次に、アプリケーションのディレクトリ構造のフォルダーにあるプライベート アセンブリが検索されます。 詳細については、「 [Assembly Searching Sequence (アセンブリの検索手順)](/windows/desktop/SbsCs/assembly-searching-sequence)」を参照してください。

## <a name="changing-dependencies"></a>依存関係の変更

アプリケーションが配置された後に、 [発行者構成ファイル](/windows/desktop/SbsCs/publisher-configuration-files) および [アプリケーション構成ファイル](/windows/desktop/SbsCs/application-configuration-files)を変更して、side-by-side アセンブリの依存関係を変更できます。 発行者構成ファイルは、発行者ポリシー ファイルとも呼ばれる XML ファイルです。これは、あるバージョンの side-by-side アセンブリを使用するアプリケーションおよびアセンブリを、同じアセンブリの別のバージョンを使用するようにグローバルにリダイレクトします。 たとえば、バグ修正やセキュリティの変更が side-by-side アセンブリに配置され、修正したバージョンを使用するようにすべてのアプリケーションをリダイレクトする場合に、依存関係を変更できます。 アプリケーション構成ファイルは、あるバージョンの side-by-side アセンブリを使用する独自のアプリケーションを、同じアセンブリの別のバージョンを使用するようにリダイレクトする XML ファイルです。 アプリケーション構成ファイルを使用すると、グローバル発行者構成ファイルで定義されているバージョンとは別のバージョンの side-by-side アセンブリを使用するように、特定のアプリケーションをリダイレクトできます。 詳細については、「 [Configuration (構成)](/windows/desktop/SbsCs/configuration)」を参照してください。

## <a name="visual-c-libraries"></a>Visual C++ のライブラリ

Visual Studio 2005 および d Visual Studio 2008 では、ATL、MFC、CRT、標準 C++、OpenMP、MSDIA などの再頒布可能ライブラリが、共有 side-by-side アセンブリとして、ネイティブなアセンブリ キャッシュに配置されていました。 現在のバージョンの再頒布可能ライブラリでは、集中配置が使用されています。 既定では、Visual Studio を使用して作成されたすべてのアプリケーションが、最終的なバイナリに埋め込まれたマニフェストと共にビルドは、マニフェストは、ビジュアルに、バイナリの依存関係をについて説明しますC++ライブラリ。 マニフェスト生成を理解するC++アプリケーションを参照してください[Understanding Manifest Generation for C/C++プログラム](understanding-manifest-generation-for-c-cpp-programs.md)します。 自身のライブラリに静的にリンクしているアプリケーション、またはローカル配置が使用されているアプリケーションについては、マニフェストは必要ありません。 配置の詳細については、「 [Deployment in Visual C++](../windows/deployment-in-visual-cpp.md)」を参照してください。

## <a name="see-also"></a>関連項目

[C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
