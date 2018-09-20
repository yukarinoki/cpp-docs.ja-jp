---
title: OpenMP ライブラリ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: f89abf97-67e3-4327-bc30-43f85b9533a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c9a4ccfefeaeb9446731027db44b849233bfefd6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391216"
---
# <a name="openmp-libraries"></a>OpenMP ライブラリ

Visual C の OpenMP のランタイム ライブラリを構成する .lib ファイルについて説明します。

次のライブラリには、ビジュアルの C++ OpenMP のランタイム ライブラリ関数が含まれます。

|OpenMP ライブラリ|特性|
|------------------------------|---------------------|
|VCOMP します。LIB|マルチ スレッド、動的リンク (VCOMP 用インポート ライブラリ。LIB)。|
|VCOMPD します。LIB|マルチ スレッド、動的リンク (VCOMPD 用インポート ライブラリ。カバー) (デバッグ)|

_DEBUG がコンパイル時に定義されている場合、 `#include omp.h` VCOMPD、ソース コードでは、します。LIB を既定のライブラリとなります。 それ以外の場合、VCOMP します。LIB が使用されます。

使用することができます[/NODEFAULTLIB (Ignore Libraries)](../../../build/reference/nodefaultlib-ignore-libraries.md)を既定のライブラリを削除し、任意のライブラリで明示的にリンクします。

OpenMP Dll は、Visual C 再頒布可能パッケージ ディレクトリには、OpenMP を使用するアプリケーションで配布する必要があります。

## <a name="see-also"></a>関連項目

[ライブラリ リファレンス](../../../parallel/openmp/reference/openmp-library-reference.md)