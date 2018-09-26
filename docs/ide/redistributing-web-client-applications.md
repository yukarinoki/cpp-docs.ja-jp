---
title: Web クライアント アプリケーションの再頒布 | Microsoft Docs
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
ms.openlocfilehash: cdde0f8d4edc13e8c1e1a53d8f4393dc7c2dac40
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372471"
---
# <a name="redistributing-web-client-applications"></a>Web クライアント アプリケーションの再頒布

アプリケーションで WebBrowser コントロールが実装された MFC クラスを使用している場合 (たとえば、`CHtmlView` または `CHtmlEditView`)、ターゲット コンピューターに最低でも Microsoft Internet Explorer 4.0 以降がインストールされている必要があります。

Internet Explorer の最新バージョンがインストールされていると、ターゲット コンピューターには最新の共通コントロール ファイルが含まれていることも保証されます。

Internet Explorer の最小限のコンポーネントのインストールについては、次のサポート技術情報の記事を参照してください。

- Q185375, HOWTO: Create a Single EXE Install of Internet Explorer ([http://support.microsoft.com/support/kb/articles/q185/3/75.asp](http://support.microsoft.com/support/kb/articles/q185/3/75.asp)) (方法: Internet Explorer の単一の EXE インストールを作成する)

サポート技術情報の記事は、MSDN ライブラリまたは [http://support.microsoft.com](http://support.microsoft.com) で参照できます。

## <a name="see-also"></a>参照

[デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)