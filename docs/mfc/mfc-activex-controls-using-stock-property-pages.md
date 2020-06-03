---
title: 'MFC ActiveX コントロール : ストック プロパティ ページの使用'
ms.date: 09/12/2018
f1_keywords:
- CLSID_CPicturePropPage
- CLSID_CColorPropPage
- CLSID_CFontPropPage
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
ms.openlocfilehash: 13a0edb72657c9ffad00dcb909019bdfe4b87e11
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358196"
---
# <a name="mfc-activex-controls-using-stock-property-pages"></a>MFC ActiveX コントロール : ストック プロパティ ページの使用

この資料では、ActiveX コントロールで使用できるストック プロパティ ページとその使用方法について説明します。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX に取って代わる最新テクノロジの詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

ActiveX コントロールでプロパティ ページを使用する方法の詳細については、次の記事を参照してください。

- [MFC ActiveX コントロール: プロパティ ページ](../mfc/mfc-activex-controls-property-pages.md)

- [MFC ActiveX コントロール : カスタム プロパティ ページの追加](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)

MFC には、ActiveX コントロールで使用する 3 `CLSID_CColorPropPage``CLSID_CFontPropPage`つのストック`CLSID_CPicturePropPage`プロパティ ページがあります。 これらのページには、それぞれ、ストック カラー、フォント、およびピクチャプロパティのユーザー インターフェイスが表示されます。

これらのプロパティ ページをコントロールに組み込むには、コントロールのプロパティ ページ ID の配列を初期化するコードに、その ID を追加します。 次の例では、このコードはコントロール実装ファイル (.CPP) を指定すると、3 つのストック プロパティ ページと既定のプロパティ`CMyPropPage`ページ (この例で指定) がすべて含まれる配列を初期化します。

[!code-cpp[NVC_MFC_AxOpt#21](../mfc/codesnippet/cpp/mfc-activex-controls-using-stock-property-pages_1.cpp)]

BEGIN_PROPPAGEIDS マクロのプロパティ ページの数は 4 です。 これは、ActiveX コントロールでサポートされるプロパティ ページの数を表します。

これらの変更が完了したら、プロジェクトを再構築します。 これで、コントロールにフォント、ピクチャ、および色のプロパティページが追加されました。

> [!NOTE]
> コントロール のストック プロパティ ページにアクセスできない場合は、MFC DLL (MFCxx.DLL) が現在のオペレーティング システムに正しく登録されていない可能性があります。 これは通常、現在実行しているオペレーティング システムとは異なるオペレーティング システムで Visual C++ をインストールした結果です。

> [!TIP]
> ストック プロパティ ページが表示されない場合 (前の注を参照)、コマンド ラインから RegSvr32.exe を実行して DLL を登録し、DLL へのフル パス名を指定します。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX コントロール: ストック プロパティの追加](../mfc/mfc-activex-controls-adding-stock-properties.md)
