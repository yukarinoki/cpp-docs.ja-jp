---
title: Visual Studio 2015 と Visual Studio 2019 の間の C++ バイナリ互換性
ms.date: 10/17/2019
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
ms.openlocfilehash: 6365ded349ad08a167b76ca9f6ab43e6e7752987
ms.sourcegitcommit: 8178d22701047d24f69f10d01ba37490e3d67241
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72587896"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2019"></a>Visual Studio 2015 と Visual Studio 2019 の間の C++ バイナリ互換性

Visual Studio 2013 以前では、バージョンの異なるコンパイラ ツールセットやランタイム ライブラリで構築されたオブジェクト ファイル (OBJ)、スタティック ライブラリ (LIB)、ダイナミック ライブラリ (DLL)、実行可能ファイル (EXE) の間のバイナリ互換性が保証されていませんでした。 

Visual Studio 2015 以降では、C++ ツールセットのメジャー番号が 14 になります (Visual Studio 2015 は v140、Visual Studio 2017 は v141、Visual Studio 2019 は v142)。 これは、ランタイム ライブラリといずれかのバージョンのコンパイラでコンパイルされたアプリケーションの両方に、バイナリ互換性があるという事実を反映するものです。 つまり、Visual Studio 2015 でビルドされたサードパーティのライブラリがある場合、Visual Studio 2017 または Visual Studio 2019 でビルドされたアプリケーションからこのライブラリを使用するために再コンパイルする必要はありません。

このルールの唯一の例外として、`/GL` コンパイラ スイッチでコンパイルされたスタティック ライブラリまたはオブジェクト ファイルは、バイナリ互換性がありません。 

サポート対象のさまざまなバージョンの MSVC ツールセットでビルドされたバイナリを混在させると、アプリケーションの実行基盤の Visual C++ 再頒布可能パッケージには、アプリまたはそれが使用するすべてのライブラリのビルドに使用されるツールセットのいずれのバージョンよりも古いものは使用できません。 

## <a name="upgrade-microsoft-visual-c-redistributable-from-visual-studio-2015-or-2017-to-visual-studio-2019"></a>Visual Studio 2015 C++または2017から visual studio 2019 に Microsoft visual 再頒布可能パッケージをアップグレードする

バイナリの互換性を維持し、メジャーバージョン (14) を visual Studio 2015、2017、 C++および2019のビジュアル再頒布可能パッケージと同じように保持しているのC++で、いつでも、ビジュアル再頒布可能パッケージの1つのバージョンのみをインストールできます。 新しいバージョンでは、インストールされている古いものが上書きされます。 Visual Studio 2015 またはC++ 2017 からの再配布可能なビジュアルがあり、後で2019をインストールした場合、2019バージョンは古いバージョンを上書きします。 最新バージョンには、セキュリティ修正プログラムなど、最新の機能とバグ修正がすべて含まれているため、常に最新バージョンにアップグレードすることをお勧めします。

同様に、新しいバージョンのビジュアルC++再頒布可能パッケージが既に存在するコンピューターにインストールすることはできません。 既に 2019 C++が搭載されているコンピューターに visual Studio 2015 または2017からビジュアル再配布可能パッケージをインストールすると、インストールエラーが発生します。 このエラーは次のようになります。

```
*0x80070666 - Another version of this product is already installed. Installation of this version cannot continue. To configure or remove the existing version of this product, use Add/Remove Programs on the Control Panel.*.
```

このエラーは仕様によるものです。 最新のものをインストールしておくことをお勧めします。

## <a name="see-also"></a>関連項目

* [Visual C++ の変更履歴](../porting/visual-cpp-change-history-2003-2015.md)
* [サポートされてC++いる最新の Visual 再頒布可能パッケージのダウンロード](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads) 
