---
title: OpenMP ライブラリ
ms.date: 10/24/2018
ms.assetid: f89abf97-67e3-4327-bc30-43f85b9533a2
ms.openlocfilehash: 75f772c953a2120a02f72d8bdfc73c1baaaef390
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530339"
---
# <a name="openmp-libraries"></a>OpenMP ライブラリ

Visual C の OpenMP のランタイム ライブラリを構成する .lib ファイルについて説明します。

次のライブラリには、ビジュアルの C++ OpenMP のランタイム ライブラリ関数が含まれます。

|OpenMP ライブラリ|特性|
|------------------------------|---------------------|
|VCOMP します。LIB|マルチ スレッド、動的リンク (VCOMP 用インポート ライブラリ。LIB)。|
|VCOMPD します。LIB|マルチ スレッド、動的リンク (VCOMPD 用インポート ライブラリ。カバー) (デバッグ)|

_DEBUG がコンパイル時に定義されている場合、 `#include omp.h` VCOMPD、ソース コードでは、します。LIB を既定のライブラリとなります。 それ以外の場合、VCOMP します。LIB が使用されます。

使用することができます[/NODEFAULTLIB (ライブラリの無視)](../../../build/reference/nodefaultlib-ignore-libraries.md)を既定のライブラリを削除し、任意のライブラリで明示的にリンクします。

OpenMP Dll は、Visual C 再頒布可能パッケージ ディレクトリには、OpenMP を使用するアプリケーションで配布する必要があります。

## <a name="see-also"></a>関連項目

[ライブラリ リファレンス](openmp-library-reference.md)
