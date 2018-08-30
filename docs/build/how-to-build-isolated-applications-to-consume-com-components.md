---
title: '方法: COM コンポーネントを使用する分離アプリケーションの構築 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b94a41aef1122a507a8966c475b9a87c69e3789
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43196833"
---
# <a name="how-to-build-isolated-applications-to-consume-com-components"></a>方法 : COM コンポーネントを使用する分離アプリケーションをビルドする
分離アプリケーションは、プログラムに組み込まれているマニフェストのあるアプリケーションです。 COM コンポーネントを使用する分離アプリケーションを作成することができます。  
  
### <a name="to-add-com-references-to-manifests-of-isolated-applications"></a>分離アプリケーションのマニフェストを COM 参照を追加するには  
  
1.  分離アプリケーションのプロジェクト プロパティ ページを開きます。  
  
2.  展開、**構成プロパティ**ノードの順に展開し、**マニフェスト ツール**ノード。  
  
3.  選択、**分離された COM**プロパティ ページ、および設定して、**コンポーネント ファイル名**プロパティを使用する分離アプリケーションを COM コンポーネントの名前にします。  
  
4.  **[OK]** をクリックします。  
  
### <a name="to-build-manifests-into-isolated-applications"></a>分離アプリケーション マニフェストを作成するには  
  
1.  分離アプリケーションのプロジェクト プロパティ ページを開きます。  
  
2.  展開、**構成プロパティ**ノードの順に展開し、**マニフェスト ツール**ノード。  
  
3.  選択、**入力し、出力**プロパティ ページ、および設定して、**埋め込みマニフェスト**プロパティを等しく**はい**します。  
  
4.  **[OK]** をクリックします。  
  
5.  ソリューションをビルドします。  
  
## <a name="see-also"></a>関連項目  
 [分離アプリケーション](/windows/desktop/SbsCs/isolated-applications)   
 [サイド バイ サイド アセンブリの概要](/windows/desktop/SbsCs/about-side-by-side-assemblies-)