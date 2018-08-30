---
title: C/C++ プログラムのマニフェスト生成の理解 |Microsoft Docs
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
ms.openlocfilehash: 691a2adf5269be0047ee6eee474406b036cad200
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222596"
---
# <a name="understanding-manifest-generation-for-cc-programs"></a>C/C++ プログラムのマニフェスト生成についての理解
A[マニフェスト](https://msdn.microsoft.com/library/aa375365)はアプリケーションまたはアセンブリ内、外部の XML ファイルまたはリソースが可能な XML ドキュメントに埋め込まれます。 マニフェストを[分離アプリケーション](/windows/desktop/SbsCs/isolated-applications)名前と、アプリケーションから実行時にバインドする共有のサイド バイ サイド アセンブリのバージョンを管理するために使用します。 サイド バイ サイド アセンブリのマニフェストでは、名前、バージョン、リソース、およびその他のアセンブリをその依存関係を指定します。  
  
 分離アプリケーションまたはサイド バイ サイド アセンブリのマニフェストを作成する 2 つの方法はあります。 最初に、アセンブリの作成者は、次の規則と名前付けに関する要件のマニフェスト ファイルを手動で作成できます。 または、プログラムがのみ CRT、MFC、ATL、または他のユーザーなどの Visual C のアセンブリを依存している場合、マニフェストを生成できます自動的に、リンカーによって。  
  
 Visual C ライブラリのヘッダーには、アセンブリ情報が含まれ、最終的なバイナリのマニフェストを形成する、リンカーによってこのアセンブリ情報が使用されるアプリケーション コードでは、ライブラリが含まれている、ときにします。 リンカーは、バイナリ内のマニフェスト ファイルが埋め込まれません、のみを外部ファイルとしてマニフェストを生成できます。 外部ファイルとしてマニフェストを持つすべてのシナリオは機能しません。 たとえば、プライベート アセンブリのマニフェストが埋め込まれたことをお勧めします。 コードをビルドする nmake を使用するようなコマンド ライン ビルドでマニフェストを埋め込むことができます。 マニフェストのツールを使用して詳細については、次を参照してください。[コマンドラインでマニフェストの生成](../build/manifest-generation-at-the-command-line.md)します。 マニフェスト ツールのプロパティを設定して、マニフェストを埋め込むことが Visual Studio でビルドする場合、**プロジェクトのプロパティ**ダイアログ; を参照してください[Visual Studio でのマニフェスト生成](../build/manifest-generation-in-visual-studio.md)します。  
  
## <a name="see-also"></a>関連項目  
 [分離アプリケーションとサイド バイ サイド アセンブリの概念](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)