---
title: 分離アプリケーションの C と C++ のビルド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 26a21eb12d9da1caaae3dbd12fe2f3ffd1194bac
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219094"
---
# <a name="building-cc-isolated-applications"></a>C/C++ 分離アプリケーションのビルド
分離アプリケーションでは、サイド バイ サイド アセンブリのみに依存し、マニフェストを使用してその依存関係にバインドします。 Windows; 上で動作するために完全に分離するアプリケーションの必要はありません。ただし、アプリケーションを完全に分離への投資、可能性があります時間を節約、今後、アプリケーションのサービスを提供する必要がある場合。 アプリケーションを完全に分離の利点の詳細については、次を参照してください。[分離アプリケーション](/windows/desktop/SbsCs/isolated-applications)します。  
  
 Visual C を使用してネイティブ C/C++ アプリケーションをビルドするときに既定では、Visual Studio プロジェクト システムには Visual C ライブラリへのアプリケーションの依存関係を記述するマニフェスト ファイルが生成されます。 これらのみの依存関係は、アプリケーションに、Visual Studio で、再構築は、分離されたアプリケーションになります。 かどうかは、アプリケーションは、その他のライブラリを使用して、実行時に、以下で説明されている手順を実行してサイド バイ サイド アセンブリとしてこれらのライブラリを再構築する必要があります[アセンブリを構築する C と C++-サイド](../build/building-c-cpp-side-by-side-assemblies.md)します。  
  
## <a name="see-also"></a>関連項目  
 [分離アプリケーションとサイド バイ サイド アセンブリの概念](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)