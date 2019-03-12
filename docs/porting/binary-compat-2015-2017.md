---
title: Visual Studio 2015 と Visual Studio 2017 の間の C++ バイナリ互換性
ms.date: 09/24/2018
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
ms.openlocfilehash: d0291ef75bda2e4da994e40ad55d94ae1042e57e
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740510"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2017"></a>Visual Studio 2015 と Visual Studio 2017 の間の C++ バイナリ互換性

以前のバージョンの Visual Studio では、バージョンの異なるコンパイラ ツールセットやランタイム ライブラリで構築されたオブジェクト ファイル (OBJ)、スタティック ライブラリ (LIB)、ダイナミック ライブラリ (DLL)、実行可能ファイル (EXE) の間のバイナリ互換性が保証されていませんでした。 これが Visual Studio 2017 で変わりました。 Visual Studio 2015 と Visual Studio 2017 では、C++ ツールセットのメジャー番号が 14 になります (Visual Studio 2015 は v140、Visual Studio 2017 は v141)。 これは、ランタイム ライブラリといずれかのバージョンのコンパイラでコンパイルされたアプリケーションの両方に、ほとんどの部分において、バイナリ互換性があるという事実を反映するものです。 つまり、たとえば Visual Studio 2015 の DLL がある場合、Visual Studio 2017 でビルドされたアプリケーションからこの DLL を使用するために再コンパイルする必要はありません。

このルールには例外が 2 つあります。 以下の場合、バイナリ互換性は保証されません。

1. スタティック ライブラリまたはオブジェクト ファイルが `/GL` コンパイラ スイッチでコンパイルされる場合。

2. アプリケーションのコンパイルとリンクで使用されたツールセットよりもバージョンが新しいツールセットで構築されたライブラリを使用する場合。 たとえば、コンパイラ バージョン 19.12 でコンパイルしてリンクされたプログラムは、19.0 から 19.12 でコンパイルされたライブラリを使用することができます。 また、バイナリ互換性は Visual Studio 2015 と Visual Studio 2017 の間にのみ存在します。Visual Studio 2013 以前で生成されたライブラリと 19.x のプログラムとのリンクはサポートされていません。

## <a name="see-also"></a>関連項目

[Visual C++ の変更履歴](../porting/visual-cpp-change-history-2003-2015.md)
