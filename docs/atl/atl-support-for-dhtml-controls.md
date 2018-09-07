---
title: DHTML コントロールに対する ATL のサポート |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
- DHTML controls
ms.assetid: 4ba98098-da5d-4362-96ad-8372f816c307
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5144a11f0b035822e6f729692569e5e861c44dcc
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43758311"
---
# <a name="atl-support-for-dhtml-controls"></a>DHTML コントロールに対する ATL のサポート

ATL を使用して、ダイナミック HTML (DHTML) 機能を持つコントロールを作成できます。 ATL DHTML コントロールの場合:

- WebBrowser コントロールをホストします。

- HTML、DHTML コントロールのユーザー インターフェイス (UI) を使用して指定します。

- WebBrowser オブジェクトとそのメソッドにアクセスすると、そのインターフェイスを通じて[IWebBrowser2](https://msdn.microsoft.com/library/aa752127.aspx)します。

- C++ コードと HTML の間の通信を管理します。

DHTML コントロールは、DHTML コントロールには、追加のディスパッチ インターフェイスが含まれています。 ただし、他の ATL コントロールに似ています。 図を参照してください。 [DHTML コントロール プロジェクトの要素の識別](../atl/identifying-the-elements-of-the-dhtml-control-project.md)DHTML の既定のプロジェクトで提供されるインターフェイスの説明についてはします。

ATL DHTML コントロールは、Web ブラウザーまたは ActiveX コントロール テスト コンテナーなどの他のコンテナーで表示できます。

## <a name="in-this-section"></a>このセクションの内容

[DHTML コントロール プロジェクトの要素の特定](../atl/identifying-the-elements-of-the-dhtml-control-project.md)  
DHTML コントロール プロジェクトの要素について説明します。

[DHTML から C++ コードを呼び出す](../atl/calling-cpp-code-from-dhtml.md)  
DHTML コントロールから C++ コードの呼び出しの例を示します。

[ATL DHTML コントロールの作成](../atl/creating-an-atl-dhtml-control.md)  
DHTML コントロールを作成する手順を一覧表示します。

[ATL DHTML コントロールのテスト](../atl/testing-the-atl-dhtml-control.md)  
ビルドおよび初期の DHTML コントロール プロジェクトをテストする方法を示します。

[ATL DHTML コントロールの変更](../atl/modifying-the-atl-dhtml-control.md)  
コントロールに一部の機能を追加する方法を示します。

[変更の ATL DHTML コントロールのテスト](../atl/testing-the-modified-atl-dhtml-control.md)  
ビルドして、コントロールの追加機能をテストする方法を示します。

## <a name="related-sections"></a>関連項目

[ATL](../atl/active-template-library-atl-concepts.md)  
Active Template Library を使用してプログラミングする方法に関する概念説明のトピックへのリンクを提供します。

