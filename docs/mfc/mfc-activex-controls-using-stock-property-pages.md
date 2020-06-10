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
ms.openlocfilehash: 18e482ca93166246df7569be9babff93d983dfd5
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618060"
---
# <a name="mfc-activex-controls-using-stock-property-pages"></a>MFC ActiveX コントロール : ストック プロパティ ページの使用

この記事では、ActiveX コントロールで使用できるストックプロパティページとその使用方法について説明します。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX を置き換える最新テクノロジの詳細については、「 [Activex コントロール](activex-controls.md)」を参照してください。

ActiveX コントロールでのプロパティページの使用の詳細については、次の記事を参照してください。

- [MFC ActiveX コントロール: プロパティ ページ](mfc-activex-controls-property-pages.md)

- [MFC ActiveX コントロール : カスタム プロパティ ページの追加](mfc-activex-controls-adding-another-custom-property-page.md)

MFC には、ActiveX コントロールで使用する3つのストックプロパティページ `CLSID_CColorPropPage` (、、および) が用意されて `CLSID_CFontPropPage` `CLSID_CPicturePropPage` います。 これらのページには、株価、フォント、および画像の各プロパティのユーザーインターフェイスがそれぞれ表示されます。

これらのプロパティページをコントロールに組み込むには、コントロールのプロパティページ Id の配列を初期化するコードにその Id を追加します。 次の例では、このコードはコントロール実装ファイル () にあります。CPP) を初期化し、次の3つのストックプロパティページと既定のプロパティページ (この例ではという名前) をすべて格納するように配列を初期化し `CMyPropPage` ます。

[!code-cpp[NVC_MFC_AxOpt#21](codesnippet/cpp/mfc-activex-controls-using-stock-property-pages_1.cpp)]

BEGIN_PROPPAGEIDS マクロでは、プロパティページの数が4であることに注意してください。 これは、ActiveX コントロールでサポートされているプロパティページの数を表します。

これらの変更が行われたら、プロジェクトをリビルドします。 コントロールに、フォント、画像、および色のプロパティのプロパティページが用意されました。

> [!NOTE]
> コントロールのストックプロパティページにアクセスできない場合は、MFC DLL (Mfcxx.dll) が現在のオペレーティングシステムに正しく登録されていないことが原因である可能性があります。 通常、これは、現在実行されているオペレーティングシステムとは異なるオペレーティングシステムで Visual C++ をインストールした場合に発生します。

> [!TIP]
> ストックプロパティページが表示されていない場合 (前のメモを参照) は、dll への完全なパス名を指定してコマンドラインから RegSvr32 を実行し、DLL を登録します。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)<br/>
[MFC ActiveX コントロール: ストック プロパティの追加](mfc-activex-controls-adding-stock-properties.md)
