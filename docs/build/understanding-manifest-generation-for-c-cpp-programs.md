---
title: C/C++ プログラムのマニフェスト生成を理解する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifests [C++]
ms.assetid: a1f24221-5b09-4824-be48-92eae5644b53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb6a65c718b88e4072c0ddad19411bb8ea4ddcff
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32381632"
---
# <a name="understanding-manifest-generation-for-cc-programs"></a>C/C++ プログラムのマニフェスト生成についての理解
A[マニフェスト](http://msdn.microsoft.com/library/aa375365)アプリケーションまたはアセンブリの内部、外部 XML ファイルまたはリソースが可能な XML ドキュメントが埋め込まれています。 マニフェスト、[分離アプリケーション](http://msdn.microsoft.com/library/aa375190)の名前と、アプリケーションから実行時にバインドする共有のサイド バイ サイド アセンブリのバージョンを管理するために使用します。 サイド バイ サイド アセンブリのマニフェストは、名前、バージョン、リソース、およびその他のアセンブリをその依存関係を指定します。  
  
 分離アプリケーションまたはサイド バイ サイド アセンブリ マニフェストを作成する 2 つの方法ができます。 最初に、アセンブリの作成者は、次の規則と名前付けに関する要件は、マニフェスト ファイルを手動で作成できます。 代わりに、プログラムは、CRT、MFC、ATL または他のユーザーなどの Visual C のアセンブリにのみ依存、する場合、マニフェストを生成できます自動的に、リンカーによって。  
  
 Visual C ライブラリのヘッダーには、アセンブリ情報が含まれ、最終的なバイナリのマニフェストを形成する、リンカーによってこのアセンブリ情報が使用されるアプリケーション コードでは、ライブラリが含まれている、ときにします。 リンカーは、バイナリ内のファイルをマニフェストが埋め込まれませんし、のみ外部ファイルとしてマニフェストを生成できます。 すべてのシナリオのマニフェストを持つ外部ファイルとしては使用できません。 たとえば、プライベート アセンブリがマニフェストに埋め込まれていることをお勧めします。 コードをビルドする (nmake の) を使用するようコマンド ライン ビルドでは、マニフェストを埋め込むことができるマニフェスト ツールを使用します。詳細については、次を参照してください。[コマンドラインでのマニフェストの生成](../build/manifest-generation-at-the-command-line.md)です。 ビルド時[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]、マニフェスト ツールのプロパティを設定して、マニフェストを埋め込むことができます、**プロジェクト プロパティ**ダイアログ; 参照してください[Visual Studio でのマニフェストの生成](../build/manifest-generation-in-visual-studio.md)です。  
  
## <a name="see-also"></a>関連項目  
 [分離アプリケーションとサイド バイ サイド アセンブリの概念](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)