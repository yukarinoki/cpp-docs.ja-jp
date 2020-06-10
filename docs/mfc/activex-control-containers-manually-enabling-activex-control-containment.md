---
title: 'ActiveX コントロール コンテナー : ActiveX コントロール サポートの手動による有効化'
ms.date: 09/12/2018
helpviewer_keywords:
- AfxEnableControlContainer method [MFC]
- ActiveX control containers [MFC], enabling
- ActiveX controls [MFC], enabling containers
ms.assetid: 833bcde9-c9ad-4709-ad12-2fc2150fb6a5
ms.openlocfilehash: a8092a77020695163ce4fbacf7eeea2650ae9f86
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625112"
---
# <a name="activex-control-containers-manually-enabling-activex-control-containment"></a>ActiveX コントロール コンテナー : ActiveX コントロール サポートの手動による有効化

MFC アプリケーションウィザードを使用してアプリケーションを生成したときに ActiveX コントロールのサポートを有効にしなかった場合は、このサポートを手動で追加する必要があります。 この記事では、既存の OLE コンテナーアプリケーションに ActiveX コントロールコンテインメントを手動で追加するプロセスについて説明します。 OLE コンテナーで ActiveX コントロールのサポートが必要であることが事前にわかっている場合は、 [MFC Activex コントロールコンテナーの作成](reference/creating-an-mfc-activex-control-container.md)に関する記事を参照してください。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX を置き換える最新テクノロジの詳細については、「 [Activex コントロール](activex-controls.md)」を参照してください。

> [!NOTE]
> この記事では、コンテナーという名前のダイアログベースの ActiveX コントロールコンテナープロジェクトと、手順とコードの例として、Circ という名前の埋め込みコントロールを使用します。

ActiveX コントロールをサポートするには、プロジェクトのファイルの2つに1行のコードを追加する必要があります。

- メインダイアログの `InitInstance` 関数を変更します (コンテナーにあります)。CPP)。次の例のように、MFC アプリケーションウィザードによって[AfxEnableControlContainer](reference/ole-initialization.md#afxenablecontrolcontainer)が呼び出されます。

   [!code-cpp[NVC_MFCOleContainer#34](codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_1.cpp)]
    [!code-cpp[NVC_MFCOleContainer#35](codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_2.cpp)]

- プロジェクトの STDAFX.H に次のを追加します。H ヘッダーファイル:

   [!code-cpp[NVC_MFCOleContainer#36](codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_3.h)]

これらの手順を完了したら、[**ビルド**] メニューの [**ビルド**] をクリックして、プロジェクトをリビルドします。

## <a name="see-also"></a>関連項目

[ActiveX コントロールコンテナー](activex-control-containers.md)
