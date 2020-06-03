---
title: DHTML コントロール プロジェクトの要素の識別
ms.date: 11/19/2018
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
ms.assetid: b627547a-3768-4346-9900-4b7a21fb8e27
ms.openlocfilehash: 5fabdc815989c21bdf6b0932b9d6826e28d7012a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319501"
---
# <a name="identifying-the-elements-of-the-dhtml-control-project"></a>DHTML コントロール プロジェクトの要素の識別

ほとんどの DHTML コントロール コードは、ATL コントロール用に作成されたコードとまったく同じです。 汎用コードの基本については、 [ATL チュートリアル](../atl/active-template-library-atl-tutorial.md)を参照し[、「ATL プロジェクトの作成](../atl/reference/creating-an-atl-project.md)」と[「ATL COM オブジェクトの基礎」](../atl/fundamentals-of-atl-com-objects.md)を参照してください。

DHTML コントロールは、次の点を除いて、どの ATL コントロールにも似ています。

- コントロールが実装する通常のインターフェイスに加えて、C++ コードと HTML ユーザー インターフェイス (UI) の間の通信に使用される追加のインターフェイスを実装します。 HTML UI は、このインターフェイスを使用して C++ コードを呼び出します。

- コントロール UI 用の HTML リソースを作成します。

- このクラスは、[型 IWebBrowser2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752127\(v=vs.85\))のスマート`m_spBrowser`ポインターであるメンバー変数を介して DHTML オブジェクト モデルにアクセスできるようにします。 このポインターを使用して、DHTML オブジェクト モデルの任意の部分にアクセスします。

次の図は、DLL、DHTML コントロール、Web ブラウザー、および HTML リソースの関係を示しています。

![DHTML コントロール プロジェクトの要素](../atl/media/vc52en1.gif "DHTML コントロール プロジェクトの要素")

> [!NOTE]
> この図の名前はプレースホルダです。 コントロールに表示される HTML リソースの名前とインターフェイスは、ATL コントロール ウィザードで割り当てた名前に基づいています。

この図では、要素は次のとおりです。

- **マイ DLL**ATL プロジェクト ウィザードを使用して作成された DLL。

- **DHTML**コントロール`m_spBrowser`( ) ATL オブジェクト ウィザードを使用して作成された DHTML コントロール。 このコントロールは、Web ブラウザ オブジェクトのインターフェイス`IWebBrowser2`を通じて Web ブラウザ オブジェクトとそのメソッドにアクセスします。 コントロール自体は、コントロールに必要な他の標準インターフェイスに加えて、次の 2 つのインターフェイスを公開します。

  - `IDHCTL1`コンテナーのみが使用するためにコントロールによって公開されるインターフェイス。

  - `IDHCTLUI1`C++ コードと HTML ユーザー インターフェイス間の通信用のディスパッチ インターフェイス。 Web ブラウザは、コントロールのディスパッチ インターフェイスを使用してコントロールを表示します。 を呼び出すと、コントロールのユーザー インターフェイスからこのディスパッチ インターフェイスのさまざまなメソッドを`window.external`呼び出すことができます。 このコントロールの`window.external`UI を構成する HTML 内の SCRIPT タグからアクセスします。 リソース ファイル内の外部メソッドの呼び出しの詳細については、「 [DHTML からの C++ コードの呼び出し](../atl/calling-cpp-code-from-dhtml.md)」を参照してください。

- **IDR_CTL1**HTML リソースのリソース ID。 この場合、ファイル名は DHCTL1UI.htm です。 DHTML コントロールは、標準の HTML タグと、テキスト エディターを使用して編集できる外部ウィンドウ ディスパッチ コマンドを含む HTML リソースを使用します。

- **ウェブブラウザ**Web ブラウザは、HTML リソースの HTML に基づいてコントロールの UI を表示します。 DHTML コントロールでは、Web`IWebBrowser2`ブラウザーのインターフェイスへのポインターを使用して、DHTML オブジェクト モデルへのアクセスを許可します。

ATL コントロール ウィザードは、HTML リソースと .cpp ファイルの両方に既定のコードを持つコントロールを生成します。 ウィザードで生成されたコントロールをコンパイルして実行し、Web ブラウザまたは ActiveX コントロール テスト コンテナでコントロールを表示できます。 次の図は、テスト コンテナーに 3 つのボタンが表示されている既定の ATL DHTML コントロールを示しています。

![コントロール](../atl/media/vc52en2.gif "ATL DHTML コントロール")

DHTML[コントロールの作成を開始するには、「ATL DHTML コントロールの作成](../atl/creating-an-atl-dhtml-control.md)」を参照してください。 テスト コンテナーへのアクセス方法については、「[テスト コンテナーを使用したテスト プロパティとイベント](../mfc/testing-properties-and-events-with-test-container.md)」を参照してください。

## <a name="see-also"></a>関連項目

[DHTML コントロールのサポート](../atl/atl-support-for-dhtml-controls.md)
