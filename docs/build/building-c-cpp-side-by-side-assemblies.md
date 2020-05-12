---
title: C/C++ side-by-side アセンブリのビルド
ms.date: 11/04/2016
helpviewer_keywords:
- side-by-side applications [C++]
ms.assetid: 7fa20b16-3737-4f76-a0b5-1dacea19a1e8
ms.openlocfilehash: 6e49ba72a397efb97437a2f7e6d721c782875c48
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493326"
---
# <a name="building-cc-side-by-side-assemblies"></a>C/C++ side-by-side アセンブリのビルド

[side-by-side アセンブリ](/windows/win32/SbsCs/about-side-by-side-assemblies-)は、DLL のグループ、ウィンドウ クラス、COM サーバー、タイプ ライブラリ、インターフェイスなどのリソースのコレクションで、実行時にアプリケーションで使用できます。 アセンブリに DLL を再パッケージ化する主な利点は、複数のバージョンのアセンブリをアプリケーションで同時に使用できることと、更新プログラムのリリース時に現在インストールされているアセンブリに対してサービスを提供できることです。

C++ アプリケーションでは、アプリケーションのさまざまな部分で 1 つまたは複数の DLL を使用できます。 実行時には、DLL がメイン プロセスに読み込まれ、必要なコードが実行されます。 アプリケーションは、要求された DLL を検索し、読み込む必要がある他の依存 DLL を認識して、要求された DLL と一緒に読み込む際に、オペレーティング システムに依存しています。 Windows XP、Windows Server 2003、および Windows Vista より前のバージョンの Windows オペレーティング システムでは、オペレーティング システム ローダーにより、アプリケーションのローカル フォルダー、またはシステム パスで指定された別のフォルダーで依存 DLL が検索されます。 Windows XP、Windows Server 2003、および Windows Vista では、オペレーティング システム ローダーにより、[マニフェスト](/windows/win32/sbscs/manifests) ファイルを使用して依存 DLL を検索し、これらの DLL を含む side-by-side アセンブリを検索することもできます。

既定では、Visual Studio を使用してビルドされた DLL には、ID = 2 の RT_MANIFEST リソースとして[アプリケーション マニフェスト](/windows/win32/SbsCs/application-manifests)が埋め込まれています。 実行可能ファイルの場合と同様に、このマニフェストには、他のアセンブリに対するこの DLL の依存関係が記述されています。 これは、DLL が side-by-side アセンブリに含まれておらず、この DLL に依存しているアプリケーションがその読み込みにアプリケーション マニフェストを使用する代わりに、オペレーティング システム ローダーに依存して、システム パスでこの DLL を検索することを前提としています。

> [!NOTE]
> アプリケーション マニフェストを使用する DLL には、ID = 2 のリソースとしてマニフェストを埋め込む必要があります。 DLL が実行時に動的に読み込まれる場合 (たとえば、[LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw) 関数を使用する場合)、オペレーティング システム ローダーでは、DLL のマニフェストに指定されている依存アセンブリが読み込まれます。 DLL の外部アプリケーション マニフェストは、`LoadLibrary` の呼び出し中にはチェックされません。 マニフェストが埋め込まれていない場合、ローダーでは、不正なバージョンのアセンブリを読み込もうとしたり、依存アセンブリが見つからなかったりすることがあります。

1 つまたは複数の関連 DLL を、対応する[アセンブリ マニフェスト](/windows/win32/SbsCs/assembly-manifests)と共に side-by-side アセンブリに再パッケージ化できます。このマニフェストには、アセンブリを形成するファイルと、他の side-by-side アセンブリに対するアセンブリの依存関係が記述されています。

> [!NOTE]
> アセンブリに 1 つの DLL が含まれている場合は、この DLL に ID = 1 のリソースとしてアセンブリ マニフェストを埋め込み、プライベート アセンブリに DLL と同じ名前を付けることをお勧めします。 たとえば、DLL の名前が mylibrary.dll の場合、マニフェストの \<assemblyIdentity> 要素で使用されている name 属性の値にも、mylibrary を指定できます。 場合によっては、ライブラリに .dll 以外の拡張子が付いている (たとえば、MFC ActiveX コントロール プロジェクトでは .ocx ライブラリが作成される) と、外部アセンブリ マニフェストを作成できます。 この場合、アセンブリとそのマニフェストの名前は DLL の名前と異なる必要があります (たとえば、MyAssembly、MyAssembly.manifest、mylibrary.ocx)。 ただし、このようなライブラリの名前を変更して拡張子 .dll を付加し、マニフェストをリソースとして埋め込んで、このアセンブリの将来のメンテナンス コストを削減することをお勧めします。 オペレーティング システムでプライベート アセンブリを検索する方法の詳細については、「[アセンブリの検索手順](/windows/win32/SbsCs/assembly-searching-sequence)」を参照してください。

この変更により、対応する DLL を[プライベート アセンブリとして](/windows/win32/Msi/private-assemblies)アプリケーションのローカル フォルダーに配置したり、[共有アセンブリ](/windows/win32/Msi/shared-assemblies)として WinSxS アセンブリ キャッシュに配置したりできます。 この新しいアセンブリの適切な実行時動作を実現するために、いくつかの手順に従う必要があります。これらについては、「[side-by-side アセンブリを作成するためのガイドライン](/windows/win32/SbsCs/guidelines-for-creating-side-by-side-assemblies)」を参照してください。 アセンブリが正しく作成されると、共有アセンブリまたはプライベート アセンブリとして、それに依存するアプリケーションと共に配置できます。 side-by-side アセンブリを共有アセンブリとしてインストールする場合は、「[Windows XP での side-by-side 共有のための Win32 アセンブリのインストール](/windows/win32/Msi/installing-win32-assemblies-for-side-by-side-sharing-on-windows-xp)」に記載されているガイドラインに従うか、または[マージ モジュール](/windows/win32/msi/merge-modules)を使用することができます。 side-by-side アセンブリをプライベート アセンブリとしてインストールする場合は、インストール プロセスの一部として、対応する DLL、リソース、およびアセンブリ マニフェストをターゲット コンピューター上のアプリケーション ローカル フォルダーにコピーするだけで、このアセンブリが実行時にローダーによって検出されるようにすることができます (「[アセンブリ検索シーケンス](/windows/win32/SbsCs/assembly-searching-sequence)」を参照してください)。 もう 1 つの方法としては、[Windows インストーラー](/windows/win32/Msi/windows-installer-portal)を使用し、「[Windows XP でアプリケーションをプライベートに使用するための Win32 アセンブリのインストール](/windows/win32/Msi/installing-win32-assemblies-for-the-private-use-of-an-application-on-windows-xp)」に記載されているガイドラインに従ってください。

## <a name="see-also"></a>関連項目

[C/C++ 分離アプリケーションのビルド](building-c-cpp-isolated-applications.md)<br/>
[C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
