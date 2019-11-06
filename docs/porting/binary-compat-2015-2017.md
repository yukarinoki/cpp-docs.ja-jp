---
title: C++Visual Studio 2015 と Visual Studio 2019 間のバイナリの互換性
ms.date: 10/17/2019
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
ms.openlocfilehash: 761f6187a8b30ecb4214821c7f91d1b26e9c647c
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627021"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2019"></a>C++Visual Studio 2015 と Visual Studio 2019 間のバイナリの互換性

Visual Studio 2013 以前では、バージョンの異なるコンパイラ ツールセットやランタイム ライブラリで構築されたオブジェクト ファイル (OBJ)、スタティック ライブラリ (LIB)、ダイナミック ライブラリ (DLL)、実行可能ファイル (EXE) の間のバイナリ互換性が保証されていませんでした。 

Visual Studio 2015 以降では、C++ ツールセットのメジャー番号が 14 になります (Visual Studio 2015 は v140、Visual Studio 2017 は v141、Visual Studio 2019 は v142)。 これは、これらのいずれかのバージョンのコンパイラでコンパイルされたランタイムライブラリとアプリケーションの両方がバイナリ互換であるという事実を反映しています。 つまり、Visual Studio 2015 でビルドされたサードパーティのライブラリがある場合、Visual Studio 2017 または Visual Studio 2019 でビルドされたアプリケーションからこのライブラリを使用するために再コンパイルする必要はありません。

このルールの唯一の例外として、`/GL` コンパイラ スイッチでコンパイルされたスタティック ライブラリまたはオブジェクト ファイルは、バイナリ互換性がありません。

サポートされているさまざまなバージョンの MSVC ツールセットでビルドされC++たバイナリを混在させた場合、アプリケーションを実行するビジュアル再配布可能ファイルは、アプリのビルドに使用されるツールセットのバージョンまたはそれが使用するライブラリのいずれにも古いものにはなりません。

## <a name="upgrade-microsoft-visual-c-redistributable-from-visual-studio-2015-or-2017-to-visual-studio-2019"></a>Visual Studio 2015 C++または2017から visual studio 2019 に Microsoft visual 再頒布可能パッケージをアップグレードする

バイナリ互換性が維持されており、visual Studio 2015、2017、および2019のビジュアルC++再頒布可能パッケージのメジャーバージョン (14) は同じであるため、visual C++ Studio、、およびの再頒布可能パッケージのバージョンは、いつでもインストールできます。 新しいバージョンでは、インストールされている古いものが上書きされます。 Visual Studio 2015 またはC++ 2017 からの再配布可能なビジュアルがあり、後で2019をインストールした場合、2019バージョンは古いバージョンを上書きします。 最新バージョンには、セキュリティ修正プログラムなど、最新の機能とバグ修正がすべて含まれているため、常に最新バージョンにアップグレードすることをお勧めします。

同様に、新しいバージョンのビジュアルC++再頒布可能パッケージが既に存在するコンピューターにインストールすることはできません。 既に 2019 C++が搭載されているコンピューターに visual Studio 2015 または2017からビジュアル再配布可能パッケージをインストールすると、インストールエラーが発生します。 このエラーは次のようになります。

```
*0x80070666 - Another version of this product is already installed. Installation of this version cannot continue. To configure or remove the existing version of this product, use Add/Remove Programs on the Control Panel.*.
```

このエラーは仕様によるものです。 最新のものをインストールしておくことをお勧めします。

## <a name="see-also"></a>関連項目

* [Visual C++ の変更履歴](../porting/visual-cpp-change-history-2003-2015.md)
* [サポートされてC++いる最新の Visual 再頒布可能パッケージのダウンロード](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads) 
