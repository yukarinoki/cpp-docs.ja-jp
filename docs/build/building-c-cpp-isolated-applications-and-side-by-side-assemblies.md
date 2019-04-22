---
title: C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド
ms.date: 11/04/2016
helpviewer_keywords:
- isolated applications [C++]
- WinSxS [C++]
- native assembly cache [C++]
- builds [C++], isolated applications
- side-by-side applications [C++]
- builds [C++], side-by-side assemblies
ms.assetid: 9465904e-76f7-48bd-bb3f-c55d8f1699b6
ms.openlocfilehash: b962796c3bf32bc312d3047535ae90a40a37094d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58772463"
---
# <a name="building-cc-isolated-applications-and-side-by-side-assemblies"></a>C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド

Visual C++ では、 [分離アプリケーション](/windows/desktop/SbsCs/isolated-applications) および [side-by-side アセンブリ](/windows/desktop/SbsCs/about-side-by-side-assemblies-)という概念に基づく、Windows クライアント アプリケーションの配置モデルがサポートされます。 既定では、Visual C++ では、すべてのネイティブ C/C++ アプリケーションは、 [マニフェスト](/windows/desktop/sbscs/manifests) を使用して Visual C++ ライブラリへの依存関係を記述する分離アプリケーションとしてビルドされます。

C/C++ プログラムを分離アプリケーションとしてビルドすることには、さまざまな利点があります。 たとえば、分離アプリケーションは、他の C/C++ アプリケーションによって Visual C++ ライブラリがインストールまたはアンインストールされる場合に影響を受けません。 分離アプリケーションで使用される Visual C++ ライブラリは、アプリケーションのローカル フォルダーに、またはネイティブ アセンブリ キャッシュ (WinSxS) へのインストールによって、再配布される場合もあります。ただし、 [発行者構成ファイル](/windows/desktop/SbsCs/publisher-configuration)を使用することによって、既に配置されているアプリケーションの Visual C++ ライブラリのサービス提供を簡略化できます。 分離アプリケーションの配置モデルにより、特定のコンピューターで実行されている C/C++ アプリケーションで最新バージョンの Visual C++ ライブラリが使用されるようにすることが簡単になります。一方で、アプリケーションが依存する DLL に対する明示的なバージョン バインディングは、引き続きシステム管理者およびアプリケーション作成者が制御できます。

このセクションでは、C/C++ アプリケーションを分離アプリケーションとしてビルドし、マニフェストを使用して Visual C++ ライブラリにバインドされるようにする方法について説明します。 このセクションの情報は、主にネイティブ (アンマネージ) Visual C++ アプリケーションに適用されます。 Visual C++ でビルドされたネイティブ アプリケーションの配置の詳細については、「 [Redistributing Visual C++ Files](../windows/redistributing-visual-cpp-files.md)」を参照してください。

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