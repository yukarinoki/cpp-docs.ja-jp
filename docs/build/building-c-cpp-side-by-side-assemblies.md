---
title: C/C++ side-by-side アセンブリのビルド
ms.date: 11/04/2016
helpviewer_keywords:
- side-by-side applications [C++]
ms.assetid: 7fa20b16-3737-4f76-a0b5-1dacea19a1e8
ms.openlocfilehash: d5d7652b6424177191275f8f80d7b1f6cf02b261
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221131"
---
# <a name="building-cc-side-by-side-assemblies"></a>C/C++ side-by-side アセンブリのビルド

A[サイド バイ サイド アセンブリ](/windows/desktop/SbsCs/about-side-by-side-assemblies-)リソースのコレクションです: Dll、windows のクラス、COM サーバー、タイプ ライブラリ、またはインターフェイスのグループ-実行時に使用するアプリケーションで使用できます。 アセンブリ Dll を再パッケージ化の主な利点は、更新プログラムのリリースが発生した場合、サービスが現在インストールされているアセンブリを行うことが、アセンブリの複数のバージョンは、同時にアプリケーションで使用できます。

AC++アプリケーションは、アプリケーションのさまざまな部分の 1 つまたは複数の Dll を使用します。 、実行時に、メイン プロセスに Dll が読み込まれ、必要なコードが実行されます。 アプリケーションは、要求された Dll を見つけ、読み込むと、要求された DLL と共にロードがあるその他の依存 Dll を理解するには、オペレーティング システムに依存します。 Windows オペレーティング システムのバージョンで Windows XP、Windows Server 2003、および Windows Vista より前のオペレーティング システム ローダー依存 Dll を検索、アプリケーションのローカル フォルダーまたはシステム パスで指定した別のフォルダーのいずれかで。 Windows XP、Windows Server 2003、および Windows Vista の場合で、オペレーティング システム ローダーを使用して依存 Dll の検索もできます、[マニフェスト](/windows/desktop/sbscs/manifests)ファイルとこれらの Dll を含むサイド バイ サイド アセンブリを検索します。

既定で、Visual Studio を使用して、DLL のビルド時に、[アプリケーション マニフェスト](/windows/desktop/SbsCs/application-manifests)ID 2 RT_MANIFEST のリソースとして埋め込まれています。 、実行可能ファイルと同じ動作は、このマニフェストは、他のアセンブリでこの DLL の依存関係を記述します。 これには、DLL でサイド バイ サイド アセンブリの一部でないし、この DLL に依存するアプリケーションは、アプリケーション マニフェストを使用して、読み込んでが代わりに、システム パスにこの DLL を検索するオペレーティング システム ローダーに依存するしないことが前提としています。

> [!NOTE]
> ID 2 のリソースとして埋め込まれたマニフェストに、アプリケーション マニフェストが使用される dll は重要です。 DLL は実行時に動的に読み込まれた場合 (たとえばを使用して、 [LoadLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibrarya)関数)、オペレーティング システム ローダーが DLL のマニフェストで指定された依存アセンブリを読み込みます。 Dll の外部のアプリケーション マニフェストは、中にはチェックされません、`LoadLibrary`呼び出します。 マニフェストが埋め込まれていない場合、ローダーしようと不適切なバージョンのアセンブリを読み込んだり、依存アセンブリの検索に失敗します。

1 つまたは複数の関連の Dll が対応するサイド バイ サイド アセンブリに再パッケージ化する[アセンブリ マニフェスト](/windows/desktop/SbsCs/assembly-manifests)ファイルの他のサイド バイ サイド アセンブリの依存関係と同様に、アセンブリを形成するについて説明しますアセンブリ。

> [!NOTE]
> アセンブリに 1 つの DLL が含まれている場合は、id が 1 に、この DLL にリソースとしてアセンブリ マニフェストを埋め込むし、プライベート アセンブリ、DLL と同じ名前を指定することをお勧めします。 たとえば、DLL の名前が mylibrary.dll の場合は、名前属性の値はで使用される、 \<assemblyIdentity > mylibrary、マニフェストの要素があります。 場合によって、ライブラリに .dll 以外の拡張子がある場合 (たとえば、.ocx ライブラリを作成、MFC ActiveX コントロール プロジェクト)、外部アセンブリ マニフェストを作成できます。 この場合、アセンブリとそのマニフェストの名前 (たとえば、MyAssembly、MyAssembly.manifest、および mylibrary.ocx) DLL の名前とは異なる必要があります。 ただし、拡張子.dll を付けがあり、このアセンブリの将来のメンテナンス コストを削減するリソースとしてマニフェストを埋め込むには、このようなライブラリの名前を変更することはお勧めもします。 オペレーティング システムでプライベート アセンブリを検索する方法の詳細については、次を参照してください。 [Assembly Searching Sequence](/windows/desktop/SbsCs/assembly-searching-sequence)します。

この変更は、対応する Dll の展開を許可することがあります、[プライベート アセンブリ](/windows/desktop/Msi/private-assemblies)アプリケーション ローカル フォルダーまたはとして、[アセンブリを共有](/windows/desktop/Msi/shared-assemblies)WinSxS アセンブリ キャッシュにします。 この新しいアセンブリの正しい実行時の動作を実現するために従う必要はいくつかの手順記述されて[サイド バイ サイド アセンブリを作成するためのガイドライン](/windows/desktop/SbsCs/guidelines-for-creating-side-by-side-assemblies)します。 アセンブリが正しく作成した後は、いずれかを共有またはプライベート アセンブリとしてに依存しているアプリケーションと共にデプロイできます。 共有アセンブリとサイド バイ サイド アセンブリをインストールするときにガイドラインが記載されているいずれかに従ってことがあります[Windows XP でのサイド バイ サイドでの共有用の Win32 アセンブリのインストール](/windows/desktop/Msi/installing-win32-assemblies-for-side-by-side-sharing-on-windows-xp)使用または[マージ モジュール](/windows/desktop/msi/merge-modules). プライベート アセンブリとサイド バイ サイド アセンブリをインストールするときに可能性がありますだけコピーする、対応する DLL、リソース、およびアセンブリ マニフェストのインストール プロセスの一環として、対象のコンピューター上のアプリケーション ローカル フォルダーにこのアセンブリができること実行時に、ローダーによって検出された (を参照してください[Assembly Searching Sequence](/windows/desktop/SbsCs/assembly-searching-sequence))。 別の方法は、使用する[Windows インストーラー](/windows/desktop/Msi/windows-installer-portal)しで説明されているガイドラインに従う[Windows XP 上のアプリケーションの秘密を使用するための Win32 アセンブリのインストール](/windows/desktop/Msi/installing-win32-assemblies-for-the-private-use-of-an-application-on-windows-xp)します。

## <a name="see-also"></a>関連項目

[C/C++ 分離アプリケーションのビルド](building-c-cpp-isolated-applications.md)<br/>
[C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
