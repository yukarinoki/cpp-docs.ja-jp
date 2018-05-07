---
title: 'ActiveX コントロール コンテナー: ActiveX コントロール サポートの手動で有効化 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: fde0ee4dc740826c9efdf7b86cd2f021699f8820
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="activex-control-containers-manually-enabling-activex-control-containment"></a>ActiveX コントロール コンテナー : ActiveX コントロール サポートの手動による有効化
MFC アプリケーション ウィザードを使用してアプリケーションを作成すると ActiveX コントロールのサポートを有効にしなかった場合、は、このサポートを手動で追加する必要があります。 この記事では、既存の OLE コンテナー アプリケーションに ActiveX コントロール コンテナーを手動で追加するためのプロセスについて説明します。 記事を参照している場合は事前に、OLE コンテナーで ActiveX コントロールをサポートする、 [MFC ActiveX コントロール コンテナーの作成](../mfc/reference/creating-an-mfc-activex-control-container.md)です。  
  
> [!NOTE]
>  この記事では、ダイアログ ベース ActiveX コントロール コンテナーという名前のプロジェクト コンテナーと Circ をという名前のプロシージャとコードの例として、埋め込みのコントロールを使用します。  
  
 ActiveX コントロールをサポートするには、2 つのプロジェクトのファイルに 1 行のコードを追加する必要があります。  
  
-   変更のメイン ダイアログの`InitInstance`関数 (コンテナーに見つかりました。CPP) への呼び出しの MFC アプリケーション ウィザードで[AfxEnableControlContainer](reference/ole-initialization.md#afxenablecontrolcontainer)、次の例のようにします。  
  
     [!code-cpp[NVC_MFCOleContainer#34](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_1.cpp)]  
    [!code-cpp[NVC_MFCOleContainer#35](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_2.cpp)]  
  
-   次のインクルードに追加します。H ヘッダー ファイル:  
  
     [!code-cpp[NVC_MFCOleContainer#36](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_3.h)]  
  
 これらの手順を完了した後をクリックして、プロジェクトをリビルド**ビルド**上、**ビルド**メニュー。  
  
## <a name="see-also"></a>関連項目  
 [ActiveX コントロール コンテナー](../mfc/activex-control-containers.md)

