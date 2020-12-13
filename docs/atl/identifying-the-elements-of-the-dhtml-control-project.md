---
description: 詳細については、「DHTML コントロールプロジェクトの要素の識別」を参照してください。
title: DHTML コントロールプロジェクトの要素の識別
ms.date: 11/19/2018
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
ms.assetid: b627547a-3768-4346-9900-4b7a21fb8e27
ms.openlocfilehash: 7f04857378564a86fc875e9874b79f6ae6c6a625
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148019"
---
# <a name="identifying-the-elements-of-the-dhtml-control-project"></a>DHTML コントロールプロジェクトの要素の識別

ほとんどの DHTML コントロールコードは、ATL コントロールに対して作成されたものとまったく同じです。 一般的なコードの基本を理解するには、 [atl チュートリアル](../atl/active-template-library-atl-tutorial.md)を実行し、atl [プロジェクトの作成](../atl/reference/creating-an-atl-project.md) と [atl COM オブジェクトの基礎](../atl/fundamentals-of-atl-com-objects.md)に関するセクションを参照してください。

DHTML コントロールは、次の点を除いて、ATL コントロールに似ています。

- コントロールは、コントロールが実装する通常のインターフェイスに加えて、C++ コードと HTML ユーザーインターフェイス (UI) 間の通信に使用される追加のインターフェイスを実装します。 HTML UI は、このインターフェイスを使用して C++ コードを呼び出します。

- これにより、コントロール UI 用の HTML リソースが作成されます。

- これにより、 `m_spBrowser` [IWebBrowser2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752127\(v=vs.85\))型のスマートポインターであるメンバー変数を介して、DHTML オブジェクトモデルにアクセスできるようになります。 このポインターを使用して、DHTML オブジェクトモデルの任意の部分にアクセスします。

次の図は、DLL、DHTML コントロール、Web ブラウザー、HTML リソースの関係を示しています。

![DHTML コントロール プロジェクトの要素](../atl/media/vc52en1.gif "DHTML コントロール プロジェクトの要素")

> [!NOTE]
> このグラフィックには、プレースホルダーという名前が付いています。 HTML リソースの名前とコントロールで公開されているインターフェイスは、ATL コントロールウィザードで割り当てた名前に基づいています。

この図では、次の要素があります。

- **マイ DLL** ATL プロジェクトウィザードを使用して作成された DLL。

- **Dhtml コントロール** ( `m_spBrowser` ) ATL オブジェクトウィザードを使用して作成された dhtml コントロールです。 このコントロールは、web ブラウザーオブジェクトのインターフェイス () を使用して、Web ブラウザーオブジェクトとそのメソッドにアクセスし `IWebBrowser2` ます。 コントロール自体は、コントロールに必要な他の標準インターフェイスに加えて、次の2つのインターフェイスを公開します。

  - `IDHCTL1` コンテナーだけが使用するために、コントロールによって公開されるインターフェイス。

  - `IDHCTLUI1` C++ コードと HTML ユーザーインターフェイスの間で通信を行うためのディスパッチインターフェイス。 Web ブラウザーは、コントロールのディスパッチインターフェイスを使用してコントロールを表示します。 を呼び出すことによって、このディスパッチインターフェイスのさまざまなメソッドをコントロールのユーザーインターフェイスから呼び出すことができ `window.external` ます。その後、このディスパッチインターフェイスのメソッド名を呼び出します。 `window.external`このコントロールの UI を構成する HTML 内のスクリプトタグからにアクセスします。 リソースファイルでの外部メソッドの呼び出しの詳細については、「 [DHTML からの C++ コードの呼び出し](../atl/calling-cpp-code-from-dhtml.md)」を参照してください。

- **IDR_CTL1** HTML リソースのリソース ID。 ファイル名 (この場合は DHCTL1UI.htm)。 DHTML コントロールは、テキストエディターを使用して編集できる標準の HTML タグと外部ウィンドウのディスパッチコマンドを含む HTML リソースを使用します。

- **Web ブラウザー** Web ブラウザーでは、HTML リソースの HTML に基づいて、コントロールの UI が表示されます。 Dhtml オブジェクトモデルへのアクセスを許可するには、Web ブラウザーのインターフェイスへのポインターを `IWebBrowser2` dhtml コントロールで使用できます。

ATL コントロールウィザードでは、HTML リソースと .cpp ファイルの両方に既定のコードを持つコントロールが生成されます。 ウィザードで生成されたコントロールをコンパイルして実行し、Web ブラウザーまたは ActiveX コントロールテストコンテナーでコントロールを表示できます。 次の図は、テストコンテナーに3つのボタンが表示された既定の ATL DHTML コントロールを示しています。

![ATL DHTML コントロール](../atl/media/vc52en2.gif "ATL DHTML コントロール")

DHTML コントロールの構築を開始するには [、「ATL Dhtml コントロールの作成](../atl/creating-an-atl-dhtml-control.md) 」を参照してください。 テストコンテナーにアクセスする方法の詳細については [、「テストコンテナーでのプロパティとイベントのテスト](../mfc/testing-properties-and-events-with-test-container.md) 」を参照してください。

## <a name="see-also"></a>関連項目

[DHTML コントロールのサポート](../atl/atl-support-for-dhtml-controls.md)
