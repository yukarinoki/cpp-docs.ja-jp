---
title: MFC プロジェクトへの ATL サポートの追加
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.adding.atl.mfc
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: b5fe15d6-7752-4818-b9f9-62482ad35c95
ms.openlocfilehash: 94303d1dfc7c06171def1224982f5e0aa5716ce4
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924469"
---
# <a name="adding-atl-support-to-your-mfc-project"></a>MFC プロジェクトへの ATL サポートの追加

MFC ベースのアプリケーションを既に作成している場合は、IDE を使用して Active Template Library (ATL) のサポートを簡単に追加できます。

> [!NOTE]
> このサポートは、MFC の実行可能ファイルまたは DLL プロジェクトに追加された単純な COM オブジェクトにのみ適用されます。 他の COM オブジェクト (ActiveX コントロールを含む) を MFC プロジェクトに追加することはできますが、オブジェクトが想定どおりに動作しない可能性があります。

::: moniker range=">=msvc-160"

1. ソリューションエクスプローラーで、プロジェクトノードを右クリックします。

1. ショートカット メニューの **[追加]** 、 **[新しい項目]** を順にクリックします。

1. 左ペインで [ **atl** ] を選択し、中央のペインで [ **atl サポート** ] を選択します。

::: moniker-end

::: moniker range="<=msvc-150"

### <a name="to-add-atl-support-to-your-mfc-project"></a>MFC プロジェクトに ATL サポートを追加するには

1. ソリューションエクスプローラーで、プロジェクトノードを右クリックします。

1. ショートカットメニューの [ **追加** ] をクリックし、[ **クラスの追加** ] をクリックします。

1. 左ペインで [ **atl** ] を選択し、中央のペインで [ **MFC プロジェクトに Atl サポートを追加** ] を選択します。

::: moniker-end

ATL サポートを追加して MFC プロジェクトのコードを変更する方法の詳細については、「atl[ウィザードによって追加された Atl サポートの詳細](../../mfc/reference/details-of-atl-support-added-by-the-atl-wizard.md)」を参照してください。

## <a name="see-also"></a>こちらもご覧ください

[クラスの追加](../../ide/adding-a-class-visual-cpp.md)<br/>
[コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[仮想関数のオーバーライド](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[クラス各部へのジャンプ](../../ide/navigate-code-cpp.md)
