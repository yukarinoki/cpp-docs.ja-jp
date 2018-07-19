---
title: C と C++ の側バイ サイド アセンブリをビルド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- side-by-side applications [C++]
ms.assetid: 7fa20b16-3737-4f76-a0b5-1dacea19a1e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a45062af5648c7b3565d959fd1d2dce13aeca4b3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364022"
---
# <a name="building-cc-side-by-side-assemblies"></a>C/C++ side-by-side アセンブリのビルド
A[サイド バイ サイド アセンブリ](http://msdn.microsoft.com/library/windows/desktop/ff951640)リソースのコレクションは、— Dll、windows クラス、COM サーバー、タイプ ライブラリ、またはインターフェイスのグループ-実行時に使用するアプリケーションを使用できます。 アセンブリ内の Dll を再パッケージ化の主な利点は、アセンブリの複数のバージョンは、同時にアプリケーションで使用できます、更新プログラムのリリースが発生した場合、現在インストールされているサービス アセンブリを行うことです。  
  
 Visual C アプリケーションでは、アプリケーションのさまざまな部分に 1 つまたは複数の Dll を使用できます。 実行時に、Dll は、メインのプロセスに読み込まれ、必要なコードを実行します。 アプリケーションは、要求された Dll を検索、理解しておく必要を読み込むとし、要求された DLL と共にロードの他の依存する Dll をオペレーティング システムに依存します。 オペレーティング システムのバージョンの Windows で Windows XP、Windows Server 2003、および Windows Vista より前にオペレーティング システム ローダー依存 Dll を検索アプリケーションのローカル フォルダーまたはシステム パスに指定された別のフォルダーのいずれかでします。 Windows XP、Windows Server 2003、および Windows Vista の場合は、オペレーティング システム ローダーも検索できます依存 Dll を使用して、[マニフェスト](http://msdn.microsoft.com/library/windows/desktop/aa375365)ファイルとこれらの Dll を含むサイド バイ サイド アセンブリを検索します。  
  
 既定で、Visual Studio が、DLL のビルド時に、[アプリケーション マニフェスト](http://msdn.microsoft.com/library/windows/desktop/aa374191)2 に等しい ID を持つ、RT_MANIFEST のリソースとして埋め込まれます。 実行可能ファイルと同じ動作は、このマニフェストは、他のアセンブリに対するこの DLL の依存関係を記述します。 これには、DLL がサイド バイ サイド アセンブリの一部ではないと、この DLL に依存するアプリケーションがそれを読み込むには、オペレーティング システム ローダーをシステム パスにこの DLL を検索する代わりに必要にアプリケーション マニフェストを使用する予定はないことが前提としています。  
  
> [!NOTE]
>  Id が 2 に等しいリソースとして埋め込まれたマニフェストに、アプリケーション マニフェストが使用される dll 重要です。 DLL が実行時に動的に読み込まれている場合 (たとえばを使用して、 [LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175)関数)、オペレーティング システム ローダーが DLL のマニフェストで指定された依存アセンブリを読み込みます。 Dll の外部のアプリケーション マニフェストがオフの中に、`LoadLibrary`呼び出します。 マニフェストが埋め込まれていない場合、ローダーしようと間違ったバージョンのアセンブリの読み込みまたは依存アセンブリの検索に失敗します。  
  
 1 つまたは複数の Dll を再パッケージ化に対応するサイド バイ サイド アセンブリが関連[アセンブリ マニフェスト](http://msdn.microsoft.com/library/windows/desktop/aa374219)、どのファイル フォームの 他のサイド バイ サイド アセンブリだけでなく、アセンブリの依存関係を記述します。アセンブリ。  
  
> [!NOTE]
>  アセンブリに 1 つの DLL が含まれている場合は、id が 1 に、この DLL にリソースとしてアセンブリ マニフェストを埋め込むし、プライベート アセンブリ DLL と同じ名前を指定することをお勧めします。 たとえば、DLL の名前が mylibrary.dll の場合は、name 属性の値で使用、 \<assemblyIdentity > マニフェストの要素は mylibrary にもあります。 場合によっては、ライブラリに .dll 以外の拡張子があるときに (たとえば、MFC ActiveX コントロール プロジェクトが .ocx ライブラリを作成する)、外部アセンブリ マニフェストを作成することができます。 ここでは、アセンブリと自らのマニフェストの名前 (たとえば、MyAssembly、MyAssembly.manifest、および mylibrary.ocx) DLL の名前と異なる必要があります。 ただし、拡張子.dll を付けを持ち、このアセンブリの今後のメンテナンス コストを削減するリソースとしてマニフェストを埋め込むには、このようなライブラリの名前を変更することはお勧めもします。 オペレーティング システムがプライベート アセンブリを検索する方法の詳細については、次を参照してください。 [Assembly Searching Sequence](http://msdn.microsoft.com/library/windows/desktop/aa374224)です。  
  
 この変更は、対応する Dll の展開を許可することがあります、[プライベート アセンブリ](http://msdn.microsoft.com/library/windows/desktop/aa370850)アプリケーション ローカル フォルダーまたはとして、[アセンブリを共有](http://msdn.microsoft.com/library/windows/desktop/aa371839)WinSxS アセンブリ キャッシュにします。 この新しいアセンブリの正しい実行時の動作を実現するための後に指定する必要があるいくつかの手順これらに記述されている[サイド バイ サイド アセンブリを作成するためのガイドライン](http://msdn.microsoft.com/library/windows/desktop/aa375155)です。 アセンブリが正しく作成した後は、どちらか、共有またはプライベートのアセンブリに依存するアプリケーションと連携してとしてデプロイできます。 共有アセンブリとしてをサイド バイ サイド アセンブリをインストールする場合のガイドラインが記載されているいずれかに従って可能性があります[Windows XP でのサイド バイ サイドの共有の Win32 アセンブリをインストールする](http://msdn.microsoft.com/library/windows/desktop/aa369532)使用または[マージ モジュール](http://msdn.microsoft.com/library/windows/desktop/aa369820). プライベート アセンブリとしてをサイド バイ サイド アセンブリをインストールする場合可能性がありますだけコピーする、対応する DLL、リソース、およびアセンブリ マニフェストのインストール プロセスの一部として、対象のコンピューター上のアプリケーション ローカル フォルダーにこのアセンブリができることを確認実行時にローダーによって検出された (を参照してください[Assembly Searching Sequence](http://msdn.microsoft.com/library/windows/desktop/aa374224))。 別の方法は、使用する[Windows インストーラー](http://msdn.microsoft.com/library/windows/desktop/cc185688)しで説明されているガイドラインに従う[Windows XP 上のアプリケーションのプライベートを使用するための Win32 アセンブリのインストール](http://msdn.microsoft.com/library/windows/desktop/aa369534)です。  
  
## <a name="see-also"></a>関連項目  
 [配置の例](../ide/deployment-examples.md)   
 [分離アプリケーションの C と C++ のビルド](../build/building-c-cpp-isolated-applications.md)   
 [C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)