---
title: 'チュートリアル: Windows パフォーマンス アナライザの基本'
description: Windows パフォーマンス アナライザーで基本的な操作を完了する方法についてのチュートリアルです。
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ae1050b9389527a12f5bdbea6d695c0f20510127
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323399"
---
# <a name="tutorial-windows-performance-analyzer-basics"></a>チュートリアル: Windows パフォーマンス アナライザの基本

::: moniker range="<=vs-2017"

C++ ビルドインサイト ツールは、Visual Studio 2019 で使用できます。 このバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range="vs-2019"

C++ ビルドインサイトを効果的に使用するには、Windows パフォーマンス アナライザー (WPA) に関する知識が必要です。 この記事は、一般的な WPA 操作について理解するのに役立ちます。 WPA の使用方法の詳細については[、Windows パフォーマンス アナライザ](/windows-hardware/test/wpt/windows-performance-analyzer)のドキュメントを参照してください。

## <a name="change-the-view-mode"></a>表示モードを変更する

WPA には、トレースを探索するための基本的なビュー モードが 2 つ用意されています。

- グラフモード、および
- テーブルモード。

ビュー ペインの上部にあるビュー モード アイコンを使用して、これらのアイコンを切り替えることができます。

![グラフモードとテーブルモードを切り替える。](media/wpa-switching-view-mode.gif)

## <a name="select-presets"></a>プリセットを選択する

ほとんどの C++ ビルドインサイト WPA ビューには、複数のプリセットから選択できます。 ビュー ペインの上部にあるドロップダウン メニューを使用して、必要なプリセットを選択できます。

![プリセットを選択する。](media/wpa-presets.png)

## <a name="zoom-in-and-out"></a>ズームインとズームアウト

一部のビルド トレースは非常に大きいので、詳細を確認するのは難しいです。 関心のある領域を拡大するには、グラフを右クリックして [**ズーム**] を選択します。 [元に戻**すズーム**] を選択すると、いつでも前の設定に戻ることができます。 次の図は、選択項目と**ズーム**コマンドを使用してグラフのセクションを拡大表示する例を示しています。

![グラフを拡大します。](media/wpa-zooming.gif)

## <a name="group-by-different-columns"></a>異なる列でグループ化

トレースの表示方法をカスタマイズできます。 ビュー ペインの上部にある歯車アイコンをクリックし、ビルド エクスプローラ ビュー エディタで列を並べ替えます。 このダイアログボックスで黄色の線の上にある列は、データ行がグループ化されている列です。 黄色い線の真上の列は特別です:グラフビューでは、色付きのバーに表示されます。

このイメージは、リンクの呼び出しの棒グラフの例を示しています。 歯車アイコンを使用して、[ビルド エクスプローラ ビュー エディター] ダイアログを開きます。 次に、コンポーネントと名前の列のエントリを黄色の線の上にドラッグします。 詳細レベルを上げ、リンカー内部で実際に何が起こったかを確認するために、設定が変更されます。

![グラフを拡大します。](media/wpa-grouping.gif)

## <a name="see-also"></a>関連項目

[チュートリアル: vcperf と Windows パフォーマンス アナライザ](vcperf-and-wpa.md)\
[リファレンス: vcperf コマンド](/cpp/build-insights/reference/vcperf-commands)\
[リファレンス: Windows パフォーマンス アナライザービュー](/cpp/build-insights/reference/wpa-views)\
[Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end
