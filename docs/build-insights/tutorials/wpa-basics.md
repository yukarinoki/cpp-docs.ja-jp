---
title: 'チュートリアル: Windows パフォーマンス アナライザーの基本'
description: Windows Performance Analyzer で基本的な操作を実行する方法についてのチュートリアルです。
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 75f45244b9e9b38b7dc65b604940199acafa0ede
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922219"
---
# <a name="tutorial-windows-performance-analyzer-basics"></a>チュートリアル: Windows パフォーマンス アナライザーの基本

::: moniker range="<=msvc-150"

C++ Build Insights ツールは、Visual Studio 2019 で使用できます。 このバージョンのドキュメントを表示するには、この記事の Visual Studio の **[バージョン]** セレクター コントロールを Visual Studio 2019 に設定してください。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range="msvc-160"

C++ Build Insights を効果的に使用するには、Windows Performance Analyzer (WPA) に関するある程度の知識が必要です。 この記事は、一般的な WPA の操作を理解するのに役立ちます。 WPA の使用方法の詳細については、「[Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer)」ドキュメントを参照してください。

## <a name="change-the-view-mode"></a>表示モードを変更する

WPA には、トレースを調べるための 2 つの基本的な表示モードが用意されています。

- グラフ モード
- テーブル モード

ビュー ペインの上部にある表示モード アイコンを使用して、それらを切り替えることができます。

![グラフ モードとテーブル モードの切り替え。](media/wpa-switching-view-mode.gif)

## <a name="select-presets"></a>プリセットの選択

ほとんど C++ Build Insights WPA ビューには、選択できるプリセットが複数あります。 ビュー ペインの上部にあるドロップダウン メニューを使用して、必要なプリセットを選択できます。

![プリセットを選択します。](media/wpa-presets.png)

## <a name="zoom-in-and-out"></a>拡大と縮小

ビルド トレースは、詳細を確認するのが困難なほど大きくなる場合があります。 興味のある領域を拡大するには、グラフを右クリックして **[ズーム]** を選択します。 **[ズームを元に戻す]** を選択すれば、いつでも前の設定に戻すことができます。 次の図は、選択と **[ズーム]** コマンドを使用してグラフの選択内容を拡大する例を示しています。

![グラフの拡大を示す短いビデオ。](media/wpa-zooming.gif)

## <a name="group-by-different-columns"></a>異なる列でグループ化する

トレースの表示方法はカスタマイズできます。 ビュー ペインの上部にある歯車アイコンをクリックし、ビルド エクスプローラーのビュー エディターで列を再配置します。 このダイアログの黄色の線の上にある列によって、データ行がグループ化されます。 黄色の線のすぐ上にある列は特別なものです。グラフ ビューでは色付きのバーに表示されます。

次の図は、リンク呼び出しの棒グラフの例を示しています。 歯車アイコンを使用して、ビルド エクスプローラーのビュー エディター ダイアログを開きます。 次に、Component と Name 列エントリを黄色の線の上にドラッグします。 構成内容が変更されて詳細度が上がり、リンカー内で実際に発生した動作を確認できます。

![異なる列でグループ化する方法を示す短いビデオ。](media/wpa-grouping.gif)

## <a name="see-also"></a>関連項目

[チュートリアル: vcperf および Windows パフォーマンス アナライザー](vcperf-and-wpa.md)\
[リファレンス: vcperf コマンド](../reference/vcperf-commands.md)\
[リファレンス: Windows パフォーマンス アナライザーのビュー](../reference/wpa-views.md)\
[Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end
