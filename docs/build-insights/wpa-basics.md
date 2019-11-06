---
title: 'C++ビルド洞察: Windows パフォーマンスアナライザーの基本'
description: Windows Performance Analyzer で基本的な操作を実行する方法についてのチュートリアルです。
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4bd91698561175d876b7a3351a0ed6e85ef73a35
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2019
ms.locfileid: "73633208"
---
# <a name="c-build-insights-windows-performance-analyzer-basics"></a>C++ビルド洞察: Windows パフォーマンスアナライザーの基本

::: moniker range="<=vs-2017"

Visual C++ Studio 2019 では、Build Insights ツールを使用できます。 そのバージョンのドキュメントを表示するには、この記事の Visual Studio バージョンセレクターコントロールを Visual Studio 2019 に設定します。

::: moniker-end
::: moniker range="vs-2019"

ビルドC++インサイトを効果的に使用するには、Windows Performance ANALYZER (WPA) に関する知識が必要です。 この記事は、一般的な WPA 操作を理解するのに役立ちます。 WPA の使用方法の詳細については、 [Windows パフォーマンスアナライザー](/windows-hardware/test/wpt/windows-performance-analyzer)のドキュメントを参照してください。

## <a name="change-the-view-mode"></a>表示モードを変更する

WPA には、トレースを調べるための2つの基本的な表示モードが用意されています。

- グラフモード、および
- テーブルモード。

ビューペインの上部にある [表示モード] アイコンを使用して、それらを切り替えることができます。

![グラフモードとテーブルモードの切り替え。](media/wpa-switching-view-mode.gif)

## <a name="select-presets"></a>プリセットの選択

ほとんどC++の BUILD Insights WPA ビューには、選択できる複数のプリセットがあります。 ビューペインの上部にあるドロップダウンメニューを使用して、必要なプリセットを選択できます。

![プリセットを選択します。](media/wpa-presets.png)

## <a name="zoom-in-and-out"></a>拡大と縮小

ビルドトレースによっては、詳細を作成するのが困難な場合があります。 興味のある領域を拡大するには、グラフを右クリックし、 **[ズーム]** を選択します。 **[ズームの取り消し]** を選択すると、いつでも前の設定に戻すことができます。 次の図は、グラフのセクションをズームインするために選択と**ズーム**コマンドを使用する例を示しています。

![グラフをズームインします。](media/wpa-zooming.gif)

## <a name="group-by-different-columns"></a>別の列でグループ化

トレースの表示方法をカスタマイズできます。 ビューペインの上部にある歯車アイコンをクリックし、ビルドエクスプローラービューエディターで列を再配置します。 このダイアログの黄色の行の上にある列は、データ行がグループ化されたものです。 黄色の線の上にある列は特殊なものです。グラフビューでは、色付きのバーに表示されます。

次の図は、リンク呼び出しの棒グラフの例を示しています。 歯車アイコンを使用して、[ビルドエクスプローラービューエディター] ダイアログを開きます。 次に、コンポーネントと名前の列エントリを黄色の行の上にドラッグします。 詳細レベルを上げるように構成を変更し、リンカー内で実際に発生した内容を確認します。

![グラフをズームインします。](media/wpa-grouping.gif)

## <a name="see-also"></a>関連項目

[ビルドインサイトC++\ を使って](get-started-with-cpp-build-insights.md)みる
[vcperf のリファレンス](vcperf-reference.md)\
[Windows パフォーマンスアナライザービューの参照](wpa-views-reference.md)\
[Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end
