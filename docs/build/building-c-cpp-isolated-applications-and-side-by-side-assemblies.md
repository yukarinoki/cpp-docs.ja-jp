---
title: 分離アプリケーションおよびサイド バイ サイド アセンブリ C と C++ のビルド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- isolated applications [C++]
- WinSxS [C++]
- native assembly cache [C++]
- builds [C++], isolated applications
- side-by-side applications [C++]
- builds [C++], side-by-side assemblies
ms.assetid: 9465904e-76f7-48bd-bb3f-c55d8f1699b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b3327f4d0ae20b13c97ea0916e7a2c86e7006dd
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710100"
---
# <a name="building-cc-isolated-applications-and-side-by-side-assemblies"></a>C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド

Visual C の概念に基づく Windows クライアント アプリケーションのデプロイ モデルをサポートしている[分離アプリケーション](/windows/desktop/SbsCs/isolated-applications)と[サイド バイ サイド アセンブリ](/windows/desktop/SbsCs/about-side-by-side-assemblies-)します。 既定では、Visual C すべてのネイティブ C/C++ アプリケーション分離アプリケーションとしてビルドを使用する[マニフェスト](https://msdn.microsoft.com/library/aa375365)Visual C ライブラリへの依存関係を記述します。

C/C++ プログラムを分離アプリケーションとしてビルドすることには、さまざまな利点があります。 たとえば、分離アプリケーションは、他の C/C++ アプリケーションによって Visual C++ ライブラリがインストールまたはアンインストールされる場合に影響を受けません。 アプリケーションのローカル フォルダー、またはネイティブ アセンブリ キャッシュ (WinSxS); へのインストールによっては、分離されたアプリケーションで使用される visual C のライブラリを再まだただし、Visual C ライブラリのサービスを使用して既にデプロイされているアプリケーションを簡略化の[発行者構成ファイル](/windows/desktop/SbsCs/publisher-configuration)します。 分離アプリケーションの配置モデルにより、特定のコンピューターで実行されている C/C++ アプリケーションで最新バージョンの Visual C++ ライブラリが使用されるようにすることが簡単になります。一方で、アプリケーションが依存する DLL に対する明示的なバージョン バインディングは、引き続きシステム管理者およびアプリケーション作成者が制御できます。

このセクションでは、C/C++ アプリケーションを分離アプリケーションとしてビルドし、マニフェストを使用して Visual C++ ライブラリにバインドされるようにする方法について説明します。 このセクションの情報は、主にネイティブ (アンマネージ) Visual C++ アプリケーションに適用されます。 Visual C++ でビルドされたネイティブ アプリケーションの配置の詳細については、「 [Redistributing Visual C++ Files](../ide/redistributing-visual-cpp-files.md)」を参照してください。

## <a name="in-this-section"></a>このセクションの内容

[分離アプリケーションおよび side-by-side アセンブリの概念](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)

[C/C++ 分離アプリケーションのビルド](../build/building-c-cpp-isolated-applications.md)

[C/C++ side-by-side アセンブリのビルド](../build/building-c-cpp-side-by-side-assemblies.md)

[方法 : 登録を必要としない COM をビルドする](../build/how-to-build-registration-free-com-components.md)

[方法 : COM コンポーネントを使用する分離アプリケーションをビルドする](../build/how-to-build-isolated-applications-to-consume-com-components.md)

[C/C++ プログラムのマニフェスト生成についての理解](../build/understanding-manifest-generation-for-c-cpp-programs.md)

[C/C++ 分離アプリケーションおよび side-by-side アセンブリのトラブルシューティング](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)

## <a name="related-sections"></a>関連項目

[分離アプリケーションとサイド バイ サイド アセンブリ](/windows/desktop/SbsCs/isolated-applications-and-side-by-side-assemblies-portal)

[デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)