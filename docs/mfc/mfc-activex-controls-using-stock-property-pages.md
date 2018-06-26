---
title: 'MFC ActiveX コントロール: ストック プロパティ ページを使用して |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CLSID_CPicturePropPage
- CLSID_CColorPropPage
- CLSID_CFontPropPage
dev_langs:
- C++
helpviewer_keywords:
- picture stock property pages [MFC]
- CLSID_CFontPropPage [MFC]
- color stock property pages [MFC]
- CLSID_CColorPropPage [MFC]
- fonts [MFC], ActiveX controls
- stock properties [MFC], stock property pages
- CLSID_CPicturePropPage [MFC]
- MFC ActiveX controls [MFC], property pages
ms.assetid: 22638d86-ff3e-4124-933e-54b7c2a25968
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5eb8dc1bbdc496072df829531b0f10aaaca069a8
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932196"
---
# <a name="mfc-activex-controls-using-stock-property-pages"></a>MFC ActiveX コントロール : ストック プロパティ ページの使用
この記事では、ActiveX コントロールとその使用方法の使用可能なストック プロパティ ページについて説明します。  
  
 ActiveX コントロールのプロパティ ページを使用する方法については、次の記事を参照してください。  
  
-   [MFC ActiveX コントロール: プロパティ ページ](../mfc/mfc-activex-controls-property-pages.md)  
  
-   [MFC ActiveX コントロール: カスタム プロパティ ページの追加](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)  
  
 MFC ActiveX コントロールで使用するための 3 つのストック プロパティ ページの提供: `CLSID_CColorPropPage`、 `CLSID_CFontPropPage`、および`CLSID_CPicturePropPage`です。 これらのページでは、株価の色、フォント、および画像のプロパティのユーザー インターフェイスがそれぞれ表示されます。  
  
 これらのプロパティ ページをコントロールに組み込むするには、プロパティ ページ Id のコントロールの配列を初期化するコードをその Id を追加します。 次の例では、このコードは、コントロール実装ファイルにあります (です。CPP)、3 つすべてのストック プロパティ ページおよび既定のプロパティ ページを格納する配列を初期化します (名前付き`CMyPropPage`この例では)。  
  
 [!code-cpp[NVC_MFC_AxOpt#21](../mfc/codesnippet/cpp/mfc-activex-controls-using-stock-property-pages_1.cpp)]  
  
 BEGIN_PROPPAGEIDS マクロでのプロパティ ページの数は 4 であることに注意してください。 これは、ActiveX コントロールでサポートされているプロパティ ページの数を表します。  
  
 このような変更が完了したら、プロジェクトをリビルドします。 フォント、画像、および色のプロパティのプロパティ ページがコントロールに追加します。  
  
> [!NOTE]
>  コントロールのストック プロパティ ページにアクセスできない場合は、MFC DLL (MFCxx.DLL) が正常に登録されていません、現在のオペレーティング システム可能性があります。 これは、通常、現在実行されている 1 つから別のオペレーティング システムで Visual C のインストールから発生します。  
  
> [!TIP]
>  ストック プロパティ ページが表示されない場合 (前のメモを参照)、DLL への完全なパス名をコマンドラインから RegSvr32.exe を実行して、DLL を登録します。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX コントロール: ストック プロパティの追加](../mfc/mfc-activex-controls-adding-stock-properties.md)

