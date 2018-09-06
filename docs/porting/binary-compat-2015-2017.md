---
title: Visual Studio 2015 と Visual Studio 2017 の間の C++ バイナリ互換性 | Microsoft Docs
ms.custom: ''
ms.date: 09/21/2017
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d7f96206288828a3e38422786585b3d66787860d
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2018
ms.locfileid: "42578402"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2017"></a>Visual Studio 2015 と Visual Studio 2017 の間の C++ バイナリ互換性

以前のバージョンの Visual Studio では、バージョンの異なるコンパイラ ツールセットやランタイム ライブラリで構築されたオブジェクト ファイル (OBJ)、スタティック ライブラリ (LIB)、ダイナミック ライブラリ (DLL)、実行可能ファイル (EXE) の間のバイナリ互換性が保証されていませんでした。 これが Visual Studio 2017 で変わりました。 Visual Studio 2015 と Visual Studio 2017 では、C++ ツールセットのメジャー番号が 14 になります (Visual Studio 2015 は v140、Visual Studio 2017 は v141)。 これは、ランタイム ライブラリといずれかのバージョンのコンパイラでコンパイルされたアプリケーションの両方に、ほとんどの部分において、バイナリ互換性があるという事実を反映するものです。 つまり、たとえば、Visual Studio 2017 で DLL を作成したら、Visual Studio 2015 でコンパイルしたアプリケーションからそれを利用できます。あるいは、2015 ツールセットでビルドしたアプリケーションで Visual Studio 2017 の再頒布可能ライブラリを利用できます。  

このルールには例外が 2 つあります。 以下の場合、バイナリ互換性は保証されません。  

1. スタティック ライブラリまたはオブジェクト ファイルが `/GL` コンパイラ スイッチでコンパイルされる場合。  

2. アプリケーションのコンパイルとリンクで使用されたツールセットよりもバージョンが新しいツールセットで構築されたライブラリを使用する場合。 たとえば、ツールセット 19.12 でコンパイルしてリンクされたプログラムは、19.0 から 19.12 でコンパイルされたライブラリを使用することができます。 Visual Studio 2013 またはそれ以前で生成されたライブラリと 19.x のプログラムのリンクはサポートされていません。

## <a name="see-also"></a>参照  

[Visual C++ の変更履歴](..\porting\visual-cpp-change-history-2003-2015.md)