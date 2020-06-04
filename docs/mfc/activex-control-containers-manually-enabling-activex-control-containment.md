---
title: 'ActiveX コントロール コンテナー : ActiveX コントロール サポートの手動による有効化'
ms.date: 09/12/2018
helpviewer_keywords:
- AfxEnableControlContainer method [MFC]
- ActiveX control containers [MFC], enabling
- ActiveX controls [MFC], enabling containers
ms.assetid: 833bcde9-c9ad-4709-ad12-2fc2150fb6a5
ms.openlocfilehash: 94ad6e8356b5dab54ae97dbdd90812039d1425c9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322059"
---
# <a name="activex-control-containers-manually-enabling-activex-control-containment"></a>ActiveX コントロール コンテナー : ActiveX コントロール サポートの手動による有効化

MFC アプリケーション ウィザードを使用してアプリケーションを生成したときに ActiveX コントロール サポートを有効にしなかった場合は、このサポートを手動で追加する必要があります。 この資料では、既存の OLE コンテナー アプリケーションに ActiveX コントロールコンテインメントを手動で追加するプロセスについて説明します。 OLE コンテナで ActiveX コントロールをサポートする必要がある場合は[、「MFC ActiveX コントロール コンテナの作成](../mfc/reference/creating-an-mfc-activex-control-container.md)」を参照してください。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX に取って代わる最新テクノロジの詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

> [!NOTE]
> この記事では、プロシージャとコードの例として、Container という名前のダイアログ ベースの ActiveX コントロール コンテナー プロジェクトと Circ という名前の埋め込みコントロールを使用します。

ActiveX コントロールをサポートするには、プロジェクトの 2 つのファイルに 1 行のコードを追加する必要があります。

- メインダイアログの`InitInstance`機能を変更します (CONTAINER にあります。次の例に示すように、MFC アプリケーション ウィザードによって[AfxEnableControlContainer](reference/ole-initialization.md#afxenablecontrolcontainer)を呼び出します。

   [!code-cpp[NVC_MFCOleContainer#34](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_1.cpp)]
    [!code-cpp[NVC_MFCOleContainer#35](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_2.cpp)]

- プロジェクトの STDAFX に次の項目を追加します。H ヘッダー ファイル:

   [!code-cpp[NVC_MFCOleContainer#36](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_3.h)]

これらの手順を完了したら、[**ビルド**] メニューの [**ビルド**] をクリックしてプロジェクトを再構築します。

## <a name="see-also"></a>関連項目

[ActiveX コントロール コンテナ](../mfc/activex-control-containers.md)
