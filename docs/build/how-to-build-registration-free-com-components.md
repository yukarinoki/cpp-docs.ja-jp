---
title: '方法: Registration-free COM コンポーネントの構築 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1eaf9417f4d2b3b825933589556055772b84e057
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197414"
---
# <a name="how-to-build-registration-free-com-components"></a>方法 : 登録を必要としない COM をビルドする
登録を必要としない COM コンポーネントは、Dll に組み込まれているマニフェストのある COM コンポーネントです。  
  
### <a name="to-build-manifests-into-com-components"></a>COM コンポーネントにマニフェストをビルドするには  
  
1.  COM コンポーネントのプロジェクト プロパティ ページを開きます。  
  
2.  展開、**構成プロパティ**ノードの順に展開し、**マニフェスト ツール**ノード。  
  
3.  選択、**入力し、出力**プロパティ ページ、および設定して、**埋め込みマニフェスト**プロパティを等しく**はい**します。  
  
4.  **[OK]** をクリックします。  
  
5.  ソリューションをビルドします。  
  
## <a name="see-also"></a>関連項目  
 [分離アプリケーション](/windows/desktop/SbsCs/isolated-applications)   
 [サイド バイ サイド アセンブリの概要](/windows/desktop/SbsCs/about-side-by-side-assemblies-)   
 [方法 : COM コンポーネントを使用する分離アプリケーションをビルドする](../build/how-to-build-isolated-applications-to-consume-com-components.md)