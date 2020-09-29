---
title: ATL Active Server Page コンポーネントの追加
ms.date: 05/09/2019
ms.assetid: 7be2204c-6e58-4099-8892-001b848c8987
ms.openlocfilehash: 0180077de7ab96cb75736d34e112731e47b9589b
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91499353"
---
# <a name="adding-an-atl-active-server-page-component"></a>ATL Active Server Page コンポーネントの追加

::: moniker range="vs-2019"

ATL Active Server Page コンポーネント ウィザードは、Visual Studio 2019 以降で使用できません。

::: moniker-end

::: moniker range="<=vs-2017"

Active Template Library (ATL) オブジェクトをプロジェクトに追加するには、プロジェクトが ATL COM アプリケーションとしてか、ATL サポートを含む MFC アプリケーションとして作成されている必要があります。 [ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)を使用して、ATL アプリケーションを作成するか、[[クラスの追加]](../../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) ダイアログ ボックスから **[MFC に ATL サポートを追加する]** を選択するか、[ATL オブジェクトを MFC アプリケーションに追加](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)して、MFC アプリケーションの ATL サポートを実装することができます。

Active Server Pages コンポーネントはインターネット インフォメーション サービス アーキテクチャの一部であり、次の高度な Web 開発機能を提供します。

- ASP コンポーネントを HTML ページに埋め込んで、ブラウザーに依存しない動的コンテンツを作成できます。

- ASP ページを使用して、標準ベースのデータベース接続を提供できます。

- Web ベースのアプリケーションに対して ASP エラー処理機能を使用することができます。

## <a name="to-add-an-atl-active-server-pages-component-to-your-project"></a>ATL Active Server Page コンポーネントをプロジェクトに追加するには

1. **ソリューション エクスプローラー**で、ATL Active Server Page コンポーネントを追加するプロジェクト名を右クリックします。

1. ショートカットメニューの [ **追加**] をクリックし、[ **クラスの追加**] をクリックします。

1. [[クラスの追加]](../../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) ダイアログ ボックスで、**[テンプレート]** ウィンドウの **[ATL Active Server Page コンポーネント]** をクリックし、次に **[開く]** をクリックして、[ATL Active Server Page コンポーネント ウィザード](../../atl/reference/atl-active-server-page-component-wizard.md)を表示します。

::: moniker-end

## <a name="see-also"></a>関連項目

[クラスの追加](../../ide/adding-a-class-visual-cpp.md)<br/>
[ATL プロジェクトでの新しいインターフェイスの追加](../../atl/reference/adding-a-new-interface-in-an-atl-project.md)<br/>
[オブジェクトへの接続ポイントの追加](../../atl/adding-connection-points-to-an-object.md)<br/>
[メソッドの追加](../../ide/adding-a-method-visual-cpp.md)<br/>
[MFC クラス](../../mfc/reference/adding-an-mfc-class.md)<br/>
[一般 C++ クラスの追加](../../ide/adding-a-generic-cpp-class.md)
