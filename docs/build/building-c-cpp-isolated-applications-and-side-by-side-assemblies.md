---
title: C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド
ms.date: 05/06/2019
helpviewer_keywords:
- isolated applications [C++]
- WinSxS [C++]
- native assembly cache [C++]
- builds [C++], isolated applications
- side-by-side applications [C++]
- builds [C++], side-by-side assemblies
ms.assetid: 9465904e-76f7-48bd-bb3f-c55d8f1699b6
ms.openlocfilehash: 8164ede1379e573b08f699cd55c199f6fa228823
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220977"
---
# <a name="building-cc-isolated-applications-and-side-by-side-assemblies"></a>C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド

Visual Studio の概念に基づく Windows クライアント アプリケーションのデプロイ モデルをサポートしている[分離アプリケーション](/windows/desktop/SbsCs/isolated-applications)と[サイド バイ サイド アセンブリ](/windows/desktop/SbsCs/about-side-by-side-assemblies-)します。 既定では、Visual Studio でビルドすべてネイティブ C/C++アプリケーションを使用する分離アプリケーションとして[マニフェスト](/windows/desktop/sbscs/manifests)Visual で依存関係を記述するC++ライブラリ。

C/C++ プログラムを分離アプリケーションとしてビルドすることには、さまざまな利点があります。 たとえば、分離アプリケーションは、他の C/C++ アプリケーションによって Visual C++ ライブラリがインストールまたはアンインストールされる場合に影響を受けません。 分離アプリケーションで使用される Visual C++ ライブラリは、アプリケーションのローカル フォルダーに、またはネイティブ アセンブリ キャッシュ (WinSxS) へのインストールによって、再配布される場合もあります。ただし、 [発行者構成ファイル](/windows/desktop/SbsCs/publisher-configuration)を使用することによって、既に配置されているアプリケーションの Visual C++ ライブラリのサービス提供を簡略化できます。 分離アプリケーションの配置モデルにより、特定のコンピューターで実行されている C/C++ アプリケーションで最新バージョンの Visual C++ ライブラリが使用されるようにすることが簡単になります。一方で、アプリケーションが依存する DLL に対する明示的なバージョン バインディングは、引き続きシステム管理者およびアプリケーション作成者が制御できます。

このセクションでは、C/C++ アプリケーションを分離アプリケーションとしてビルドし、マニフェストを使用して Visual C++ ライブラリにバインドされるようにする方法について説明します。 このセクションの情報は主にネイティブ、または、非管理対象に適用されますC++アプリケーション。 ネイティブの展開についてはC++、Visual Studio でビルドされたアプリケーションを参照してください[Visual の再配布C++ファイル](../windows/redistributing-visual-cpp-files.md)します。

## <a name="in-this-section"></a>このセクションの内容

[分離アプリケーションおよび side-by-side アセンブリの概念](concepts-of-isolated-applications-and-side-by-side-assemblies.md)

[C/C++ 分離アプリケーションのビルド](building-c-cpp-isolated-applications.md)

[C/C++ side-by-side アセンブリのビルド](building-c-cpp-side-by-side-assemblies.md)

[方法: 登録を必要としない COM コンポーネントをビルドする](how-to-build-registration-free-com-components.md)

[方法: COM コンポーネントを使用する分離アプリケーションをビルドする](how-to-build-isolated-applications-to-consume-com-components.md)

[C/C++ プログラムのマニフェスト生成についての理解](understanding-manifest-generation-for-c-cpp-programs.md)

[C/C++ 分離アプリケーションおよび side-by-side アセンブリのトラブルシューティング](troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)

## <a name="related-sections"></a>関連項目

[分離アプリケーションと side-by-side アセンブリ](/windows/desktop/SbsCs/isolated-applications-and-side-by-side-assemblies-portal)

[デスクトップ アプリケーションの配置](../windows/deploying-native-desktop-applications-visual-cpp.md)