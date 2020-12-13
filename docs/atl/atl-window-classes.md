---
description: '詳細情報: ATL ウィンドウクラス'
title: ATL ウィンドウ クラス
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], subclassing
- windows [C++], superclassing
- windows [C++], ATL
- subclassing ATL window classes
- superclassing
- superclassing, ATL
ms.assetid: 1d12b708-de3e-49d5-9e41-42fe4769fa62
ms.openlocfilehash: e8e7b8c9d8492c133c305bf46abe493d993d398c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148552"
---
# <a name="atl-window-classes"></a>ATL ウィンドウ クラス

ATL には、windows の使用および実装を可能にするいくつかのクラスが含まれています。 これらのクラスは、他の ATL クラスと同様に、コードにオーバーヘッドを課すことのない効率的な実装を提供します。

ここでは、ATL ウィンドウクラスとその使用方法について説明します。

## <a name="in-this-section"></a>このセクションの内容

[ATL ウィンドウクラスの概要](../atl/introduction-to-atl-window-classes.md)<br/>
各 ATL ウィンドウクラスについて簡単に説明し、それぞれの参照資料へのリンクを示します。

[ウィンドウの使用](../atl/using-a-window.md)<br/>
を使用してウィンドウを操作する方法について説明し `CWindow` ます。

[ウィンドウの実装](../atl/implementing-a-window.md)<br/>
メッセージハンドラー、メッセージマップ、およびを使用する方法について説明し `CWindowImpl` ます。 Superclassing とサブクラスの詳細について説明します。

[ダイアログボックスの実装](../atl/implementing-a-dialog-box.md)<br/>
ダイアログボックスクラスを追加する2つの方法について説明し、コードサンプルを示します。

[包含ウィンドウの使用](../atl/using-contained-windows.md)<br/>
ATL の包含ウィンドウについて説明します。これは、独自のクラスで処理するのではなく、コンテナーオブジェクトにメッセージを委任するウィンドウです。

[ウィンドウの特徴について](../atl/understanding-window-traits.md)<br/>
ATL のウィンドウの特徴クラスについて説明します。 これらのクラスは、ウィンドウオブジェクトの作成に使用されるスタイルを標準化するための簡単な方法を提供します。

## <a name="related-sections"></a>関連項目

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Active Template Library を使用してプログラミングする方法に関する概念説明のトピックへのリンクを提供します。

[Windows サポートクラス](../atl/windows-support-classes.md)<br/>
ATL のウィンドウとメッセージマップをサポートする追加の ATL クラスを示します。
