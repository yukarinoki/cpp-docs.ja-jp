---
title: Web クライアント アプリケーションの再頒布 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Web applications [C++], redistributing
- deploying applications [C++], Web applications
- Internet applications [C++], redistributing
- application deployment [C++], Web applications
ms.assetid: fe05988b-dee8-4a46-b381-016b5103a6bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92bd843b24ee13b3d606ba8bb4f4f1cc265e8e5d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="redistributing-web-client-applications"></a>Web クライアント アプリケーションの再頒布
アプリケーションで WebBrowser コントロールを実装する MFC クラスを使用するかどうか (たとえば、`CHtmlView`または`CHtmlEditView`)、Microsoft Internet Explorer 4.0 またはそれ以降はターゲット コンピューターには最低限インストールには、少なくともする必要があります。  
  
 Internet Explorer の最新バージョンのインストールもにより、ターゲット コンピューターは最新の共通のコントロール ファイル。  
  
 最小限の Internet Explorer コンポーネントのインストールについては、次のサポート技術情報の記事で使用可能なです。  
  
-   Q185375、HOWTO: 作成、Internet Explorer の 1 つの exe ファイルのインストール ([http://support.microsoft.com/support/kb/articles/q185/3/75.asp](http://support.microsoft.com/support/kb/articles/q185/3/75.asp))  
  
 MSDN ライブラリまたはでは、サポート技術情報の記事を検索できます[ http://support.microsoft.com](http://support.microsoft.com)です。  
  
## <a name="see-also"></a>関連項目  
 [デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)