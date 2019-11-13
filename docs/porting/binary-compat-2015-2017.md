---
title: C++Visual Studio 2015、2017、および2019間のバイナリの互換性
description: Visual Studio 2015、2017、およびC++ 2019 でのコンパイル済みファイル間のバイナリ互換性のしくみについて説明します。 Microsoft Visual C++再頒布可能パッケージの1つは、3つのバージョンすべてに対応しています。
ms.date: 11/11/2019
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
ms.openlocfilehash: 118ad0a32d5dc8c344967f9a67f2d5b05aa806c0
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73965563"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-2017-and-2019"></a>C++Visual Studio 2015、2017、および2019間のバイナリの互換性

Visual Studio 2013 以前C++の Microsoft (MSVC) コンパイラツールセットでは、バージョン間のバイナリの互換性は保証されません。 異なるバージョンでビルドされたオブジェクトファイル、スタティックライブラリ、動的ライブラリ、および実行可能ファイルをリンクすることはできません。 ABIs、オブジェクト形式、およびランタイムライブラリには互換性がありません。

この動作は、Visual Studio 2015、2017、および2019で変更されています。 これらのいずれかのバージョンのコンパイラによってコンパイルされたランタイムライブラリとアプリは、バイナリと互換性があります。 C++ツールセットのメジャー番号に反映されます。これは、3つのすべてのバージョンで14です。 (ツールセットのバージョンは、Visual Studio 2015 の場合は v140、2017の場合は v141、2019の場合は v142) です。 たとえば、Visual Studio 2015 によってビルドされたサードパーティ製のライブラリがあるとします。 Visual Studio 2017 または2019でビルドされたアプリケーションで引き続き使用できます。 一致するツールセットを使用して再コンパイルする必要はありません。 最新バージョンの Microsoft Visual C++再頒布可能パッケージ (再頒布可能パッケージ) は、すべてのバージョンで動作します。

この規則には例外があります。 `/GL` コンパイラスイッチを使用してコンパイルされたスタティックライブラリまたはオブジェクトファイルは、バージョン間ではバイナリ互換ではあり*ません*。

アプリが使用する再頒布可能パッケージには、重要なバイナリ互換性制限があります。 これは、サポートされているさまざまなバージョンのツールセットでビルドされたバイナリを混合する場合に適用されます。 再頒布可能バージョンは、すべてのアプリコンポーネントで使用される最新のツールセットと同じである必要があります。

## <a name="upgrade-the-microsoft-visual-c-redistributable-from-visual-studio-2015-or-2017-to-visual-studio-2019"></a>Visual Studio 2015 またC++は2017から visual studio 2019 に Microsoft visual 再頒布可能パッケージをアップグレードする

Microsoft Visual C++再頒布可能パッケージのメジャーバージョン番号は、visual Studio 2015、2017、および2019でも同じです。 つまり、再頒布可能パッケージのインスタンスは一度に1つしかインストールできません。 新しいバージョンは、既にインストールされている古いバージョンを上書きします。 たとえば、1つのアプリで Visual Studio 2015 から再頒布可能パッケージをインストールできます。 次に、別のアプリが Visual Studio 2019 から再頒布可能パッケージをインストールします。 2019バージョンでは古いバージョンが上書きされますが、バイナリに互換性があるため、以前のアプリは正常に動作します。 最新バージョンの再頒布可能パッケージには、最新の機能、セキュリティ更新プログラム、およびバグ修正がすべて含まれていることを確認します。 そのため、常に使用可能な最新バージョンにアップグレードすることをお勧めします。

同様に、新しいバージョンが既にインストールされている場合は、古い再頒布可能パッケージをインストールすることはできません。 実行しようとすると、インストーラーによってエラーが報告されます。 既に2019バージョンを搭載しているコンピューターに2015または2017再頒布可能パッケージをインストールすると、次のようなエラーが表示されます。

```Output
0x80070666 - Another version of this product is already installed. Installation of this version cannot continue. To configure or remove the existing version of this product, use Add/Remove Programs on the Control Panel.
```

このエラーは仕様によるものです。 最新バージョンをインストールしておくことをお勧めします。 インストーラーがこのエラーから自動的に回復できることを確認します。

## <a name="see-also"></a>関連項目

[ビジュアルC++の変更履歴](../porting/visual-cpp-change-history-2003-2015.md)\
[サポートされてC++いる最新の Visual 再頒布可能パッケージのダウンロード](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads)
