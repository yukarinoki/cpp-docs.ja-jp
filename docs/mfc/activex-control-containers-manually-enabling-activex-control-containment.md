---
title: 'ActiveX コントロール コンテナー: ActiveX コントロール サポートの手動で有効化 |Microsoft Docs'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- AfxEnableControlContainer method [MFC]
- ActiveX control containers [MFC], enabling
- ActiveX controls [MFC], enabling containers
ms.assetid: 833bcde9-c9ad-4709-ad12-2fc2150fb6a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f684bbb287213ad0cbe6d490c1bef869f5ffc9db
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077778"
---
# <a name="activex-control-containers-manually-enabling-activex-control-containment"></a>ActiveX コントロール コンテナー : ActiveX コントロール サポートの手動による有効化

場合は、MFC アプリケーション ウィザードを使用してアプリケーションを作成すると ActiveX コントロールのサポートを有効にしなかった、手動でこのサポートを追加する必要があります。 この記事では、既存の OLE コンテナー アプリケーションを手動で ActiveX コントロールのサポートを追加するためのプロセスについて説明します。 事前に、OLE コンテナーで ActiveX コントロールのサポートをすることがわかっている場合、情報の記事を参照してください。 [MFC ActiveX コントロール コンテナーの作成](../mfc/reference/creating-an-mfc-activex-control-container.md)です。

>[!IMPORTANT]
> ActiveX は、新規の開発が使用できないレガシ テクノロジです。 ActiveX の上書きの最新のテクノロジの詳細については、次を参照してください。 [ActiveX コントロール](activex-controls.md)します。

> [!NOTE]
>  この記事では、ダイアログ ベース ActiveX コントロール コンテナーという名前のプロジェクト コンテナーと円をという名前のプロシージャとコードの例として、埋め込みのコントロールを使用します。

ActiveX コントロールをサポートするには、2 つのプロジェクトのファイルを 1 行のコードを追加する必要があります。

- 変更のメイン ダイアログ ボックスの`InitInstance`関数 (コンテナーが見つかりませんでした。CPP) への呼び出しの MFC アプリケーション ウィザードで[AfxEnableControlContainer](reference/ole-initialization.md#afxenablecontrolcontainer)、次の例。

   [!code-cpp[NVC_MFCOleContainer#34](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_1.cpp)]
    [!code-cpp[NVC_MFCOleContainer#35](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_2.cpp)]

- インクルードには、次を追加します。H ヘッダー ファイル:

   [!code-cpp[NVC_MFCOleContainer#36](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_3.h)]

次の手順を完了すると後、をクリックして、プロジェクトをリビルド**ビルド**上、**ビルド**メニュー。

## <a name="see-also"></a>関連項目

[ActiveX コントロール コンテナー](../mfc/activex-control-containers.md)

