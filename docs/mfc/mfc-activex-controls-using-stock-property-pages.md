---
title: 'MFC ActiveX コントロール: ストック プロパティ ページを使用して |Microsoft Docs'
ms.custom: ''
ms.date: 09/12/2018
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
ms.openlocfilehash: dc7957e69821a409d5ad56bd10c222cbe85fbc54
ms.sourcegitcommit: a3c9e7888b8f437a170327c4c175733ad9eb0454
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2018
ms.locfileid: "50204406"
---
# <a name="mfc-activex-controls-using-stock-property-pages"></a>MFC ActiveX コントロール : ストック プロパティ ページの使用

この記事では、ストック プロパティ ページを使用できる ActiveX コントロールとその使用方法について説明します。

>[!IMPORTANT]
> ActiveX は、新規の開発が使用できないレガシ テクノロジです。 ActiveX の置き換えの最新のテクノロジの詳細については、次を参照してください。 [ActiveX コントロール](activex-controls.md)します。

ActiveX コントロールのプロパティ ページの使用に関する詳細については、次の記事を参照してください。

- [MFC ActiveX コントロール: プロパティ ページ](../mfc/mfc-activex-controls-property-pages.md)

- [MFC ActiveX コントロール: カスタム プロパティ ページの追加](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)

MFC ActiveX コントロールで使用するための 3 つのストック プロパティ ページの提供: `CLSID_CColorPropPage`、 `CLSID_CFontPropPage`、および`CLSID_CPicturePropPage`します。 これらのページでは、株価の色、フォント、および画像のプロパティのユーザー インターフェイスをそれぞれ表示されます。

これらのプロパティ ページをコントロールに組み込むするには、プロパティ ページ Id のコントロールの配列を初期化するコードをその Id を追加します。 次の例では、コントロール実装ファイル内にあるこのコードは、(します。CPP) では、次の 3 つすべてのストック プロパティ ページと既定のプロパティ ページを格納する配列を初期化します (名前付き`CMyPropPage`この例では)。

[!code-cpp[NVC_MFC_AxOpt#21](../mfc/codesnippet/cpp/mfc-activex-controls-using-stock-property-pages_1.cpp)]

BEGIN_PROPPAGEIDS マクロでのプロパティ ページの数は 4 であることに注意してください。 これは、ActiveX コントロールでサポートされるプロパティ ページの数を表します。

このような変更が行われた後、プロジェクトをリビルドします。 フォント、画像、および色のプロパティのプロパティ ページがコントロールに追加します。

> [!NOTE]
>  コントロールのストック プロパティ ページにアクセスできない場合は、MFC DLL (MFCxx.DLL) に適切に登録、現在のオペレーティング システムとされていない可能性があります。 通常、この結果から、現在実行されているものと異なるオペレーティング システムで Visual C をインストールします。

> [!TIP]
>  ストック プロパティ ページが表示されない場合 (前のメモを参照)、DLL への完全なパス名をコマンドラインから RegSvr32.exe を実行している DLL を登録します。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX コントロール: ストック プロパティの追加](../mfc/mfc-activex-controls-adding-stock-properties.md)

