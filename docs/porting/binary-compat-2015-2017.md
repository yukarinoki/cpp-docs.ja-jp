---
title: C++Visual Studio 2015 と Visual Studio 2019 間のバイナリの互換性
description: Visual Studio 2015、2017、およびC++ 2019 でのコンパイル済みファイル間のバイナリ互換性のしくみについて説明します。 Microsoft Visual C++再頒布可能パッケージの1つは、3つのバージョンすべてに対応しています。
ms.date: 11/07/2019
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
ms.openlocfilehash: e41c34abe25deefe100f525044faeac0b0c3054a
ms.sourcegitcommit: eb254b4462a58d219376ff501bf768bd1adc07ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2019
ms.locfileid: "73912882"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2019"></a>C++Visual Studio 2015 と Visual Studio 2019 間のバイナリの互換性

Microsoft Visual Studio 2013 以前では、異なるバージョンのコンパイラツールセットを使用して構築されたオブジェクトファイル (Obj)、スタティックライブラリ (lib)、ダイナミックリンクライブラリ (Dll)、実行可能ファイル (Exe) の間でバイナリの互換性が保証されていません。およびランタイムライブラリ。

Visual Studio 2015 以降では、C++ ツールセットのメジャー番号が 14 になります (Visual Studio 2015 は v140、Visual Studio 2017 は v141、Visual Studio 2019 は v142)。 この番号付けは、これらのいずれかのバージョンのコンパイラでコンパイルされたランタイムライブラリとアプリケーションの両方がバイナリ互換であるという事実を反映しています。 そのため、Visual Studio 2015 でビルドされたサードパーティ製のライブラリがある場合は、Visual Studio 2017 または Visual Studio 2019 でビルドされたアプリケーションから使用するために再コンパイルする必要はありません。

この規則の唯一の例外は、`/GL` コンパイラスイッチを使用してコンパイルされたスタティックライブラリまたはオブジェクトファイルが、バイナリと互換性が*ない*ことです。

サポートされているさまざまなバージョンの Microsoft C++ (MSVC) ツールセットでビルドされC++たバイナリを混在させる場合、アプリケーションを実行するビジュアル再配布可能パッケージは、アプリのビルドに使用されるツールセットのバージョンまたは使用するすべてのライブラリのバージョンよりも古いものにすることはできません。

## <a name="upgrade-the-microsoft-visual-c-redistributable-from-visual-studio-2015-or-2017-to-visual-studio-2019"></a>Visual Studio 2015 またC++は2017から visual studio 2019 に Microsoft visual 再頒布可能パッケージをアップグレードする

Visual Studio 2015、2017、および2019の Microsoft Visual C++再頒布可能パッケージではバイナリ互換性が維持されており、メジャーバージョン (14) は同じであるため、 C++一度にインストールできるビジュアル再頒布可能パッケージのバージョンは1つだけです。 新しいバージョンでは、既にインストールされている古いバージョンが上書きされます。 Visual Studio 2015 またはC++ 2017 からビジュアルを再配布できる場合、後で visual studio 2019 をインストールすると、2019バージョンによって古いバージョンが上書きされます。 最新バージョンには、最新の機能とバグ修正 (セキュリティ修正プログラムを含む) がすべて含まれていることを確認するため、常に最新バージョンにアップグレードすることをお勧めします。

同様に、新しいバージョンが既にインストールされているC++コンピューターに、以前のバージョンのビジュアル再頒布可能パッケージをインストールすることはできません。 既に 2019 C++バージョンがインストールされているコンピューターに visual Studio 2015 または2017からビジュアル再配布可能パッケージをインストールすると、インストールエラーがトリガーされます。 このエラーは次のようになります。

```Output
0x80070666 - Another version of this product is already installed. Installation of this version cannot continue. To configure or remove the existing version of this product, use Add/Remove Programs on the Control Panel.
```

このエラーは仕様によるものです。 最新バージョンをインストールしておくことをお勧めします。

## <a name="see-also"></a>関連項目

* [Visual C++ の変更履歴](../porting/visual-cpp-change-history-2003-2015.md)
* [サポートされてC++いる最新の Visual 再頒布可能パッケージのダウンロード](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads) 
