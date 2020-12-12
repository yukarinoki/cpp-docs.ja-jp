---
description: 詳細については、「DHTML コントロールの ATL サポート」を参照してください。
title: DHTML コントロールに対する ATL のサポート
ms.date: 11/04/2016
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
- DHTML controls
ms.assetid: 4ba98098-da5d-4362-96ad-8372f816c307
ms.openlocfilehash: 7527527bc5574470fd361bae2375c25ce9345f3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148591"
---
# <a name="atl-support-for-dhtml-controls"></a>DHTML コントロールに対する ATL のサポート

ATL を使用すると、ダイナミック HTML (DHTML) 機能を持つコントロールを作成できます。 ATL DHTML コントロール:

- WebBrowser コントロールをホストします。

- DHTML コントロールのユーザーインターフェイス (UI) を使用して、HTML を指定します。

- [IWebBrowser2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752127\(v=vs.85\))インターフェイスを使用して、WebBrowser オブジェクトとそのメソッドにアクセスします。

- C++ コードと HTML 間の通信を管理します。

DHTML コントロールは、他の ATL コントロールに似ていますが、DHTML コントロールには追加のディスパッチインターフェイスが含まれています。 既定の DHTML プロジェクトに用意されているインターフェイスの図解は、「 [Dhtml コントロールプロジェクトの要素の識別](../atl/identifying-the-elements-of-the-dhtml-control-project.md) 」の図を参照してください。

ATL DHTML コントロールは、Web ブラウザーやその他のコンテナー (ActiveX コントロールテストコンテナーなど) で表示できます。

## <a name="in-this-section"></a>このセクションの内容

[DHTML コントロールプロジェクトの要素の識別](../atl/identifying-the-elements-of-the-dhtml-control-project.md)<br/>
DHTML コントロールプロジェクトの要素について説明します。

[呼び出し (DHTML から C++ コードを)](../atl/calling-cpp-code-from-dhtml.md)<br/>
DHTML コントロールから C++ コードを呼び出す例を示します。

[ATL DHTML コントロールの作成](../atl/creating-an-atl-dhtml-control.md)<br/>
DHTML コントロールを作成する手順を示します。

[ATL DHTML コントロールのテスト](../atl/testing-the-atl-dhtml-control.md)<br/>
最初の DHTML コントロールプロジェクトをビルドしてテストする方法について説明します。

[ATL DHTML コントロールの変更](../atl/modifying-the-atl-dhtml-control.md)<br/>
コントロールにいくつかの機能を追加する方法について説明します。

[変更された ATL DHTML コントロールのテスト](../atl/testing-the-modified-atl-dhtml-control.md)<br/>
コントロールの追加された機能をビルドしてテストする方法について説明します。

## <a name="related-sections"></a>関連項目

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Active Template Library を使用してプログラミングする方法に関する概念説明のトピックへのリンクを提供します。
