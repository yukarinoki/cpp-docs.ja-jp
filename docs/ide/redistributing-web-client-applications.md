---
title: Web クライアント アプリケーションの再頒布
ms.date: 11/04/2016
helpviewer_keywords:
- Web applications [C++], redistributing
- deploying applications [C++], Web applications
- Internet applications [C++], redistributing
- application deployment [C++], Web applications
ms.assetid: fe05988b-dee8-4a46-b381-016b5103a6bf
ms.openlocfilehash: 37ff666493ada7dada19f5731e6581603d3cb57e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512418"
---
# <a name="redistributing-web-client-applications"></a>Web クライアント アプリケーションの再頒布

アプリケーションで WebBrowser コントロールが実装された MFC クラスを使用している場合 (たとえば、`CHtmlView` または `CHtmlEditView`)、ターゲット コンピューターに最低でも Microsoft Internet Explorer 4.0 以降がインストールされている必要があります。

Internet Explorer の最新バージョンがインストールされていると、ターゲット コンピューターには最新の共通コントロール ファイルが含まれていることも保証されます。 詳しくは、「[Internet Explorer 11 のインストールと展開](/internet-explorer/ie11-deploy-guide/install-and-deploy-ie11)」をご覧ください。

## <a name="see-also"></a>参照

[デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)