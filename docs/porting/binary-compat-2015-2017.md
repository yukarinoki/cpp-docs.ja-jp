---
title: Visual Studio 2015 と Visual Studio 2019 の間の C++ バイナリ互換性
ms.date: 05/03/2019
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
ms.openlocfilehash: 052874eb9273ee9a9ce1695ffdadedd9911673e1
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "65449032"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2019"></a>Visual Studio 2015 と Visual Studio 2019 の間の C++ バイナリ互換性

Visual Studio 2013 以前では、バージョンの異なるコンパイラ ツールセットやランタイム ライブラリで構築されたオブジェクト ファイル (OBJ)、スタティック ライブラリ (LIB)、ダイナミック ライブラリ (DLL)、実行可能ファイル (EXE) の間のバイナリ互換性が保証されていませんでした。 

Visual Studio 2015 以降では、C++ ツールセットのメジャー番号が 14 になります (Visual Studio 2015 は v140、Visual Studio 2017 は v141、Visual Studio 2019 は v142)。 これは、ランタイム ライブラリといずれかのバージョンのコンパイラでコンパイルされたアプリケーションの両方に、バイナリ互換性があるという事実を反映するものです。 つまり、Visual Studio 2015 でビルドされたサードパーティのライブラリがある場合、Visual Studio 2017 または Visual Studio 2019 でビルドされたアプリケーションからこのライブラリを使用するために再コンパイルする必要はありません。

このルールの唯一の例外として、`/GL` コンパイラ スイッチでコンパイルされたスタティック ライブラリまたはオブジェクト ファイルは、バイナリ互換性がありません。 

サポート対象のさまざまなバージョンの MSVC ツールセットでビルドされたバイナリを混在させると、アプリケーションの実行基盤の Visual C++ 再頒布可能パッケージには、アプリまたはそれが使用するすべてのライブラリのビルドに使用されるツールセットのいずれのバージョンよりも古いものは使用できません。 

## <a name="see-also"></a>関連項目

[Visual C++ の変更履歴](../porting/visual-cpp-change-history-2003-2015.md)
