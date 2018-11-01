---
title: C/C++ 分離アプリケーションのビルド
ms.date: 11/04/2016
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
ms.openlocfilehash: 6ff9ada45a1ddd7c0aa1da62f6dd7f6a7b7bf371
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534928"
---
# <a name="building-cc-isolated-applications"></a>C/C++ 分離アプリケーションのビルド

分離アプリケーションでは、サイド バイ サイド アセンブリのみに依存し、マニフェストを使用してその依存関係にバインドします。 Windows; 上で動作するために完全に分離するアプリケーションの必要はありません。ただし、アプリケーションを完全に分離への投資、可能性があります時間を節約、今後、アプリケーションのサービスを提供する必要がある場合。 アプリケーションを完全に分離の利点の詳細については、次を参照してください。[分離アプリケーション](/windows/desktop/SbsCs/isolated-applications)します。

Visual C を使用してネイティブ C/C++ アプリケーションをビルドするときに既定では、Visual Studio プロジェクト システムには Visual C ライブラリへのアプリケーションの依存関係を記述するマニフェスト ファイルが生成されます。 これらのみの依存関係は、アプリケーションに、Visual Studio で、再構築は、分離されたアプリケーションになります。 かどうかは、アプリケーションは、その他のライブラリを使用して、実行時に、以下で説明されている手順を実行してサイド バイ サイド アセンブリとしてこれらのライブラリを再構築する必要があります[アセンブリを構築する C と C++-サイド](../build/building-c-cpp-side-by-side-assemblies.md)します。

## <a name="see-also"></a>関連項目

[分離アプリケーションおよび side-by-side アセンブリの概念](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)