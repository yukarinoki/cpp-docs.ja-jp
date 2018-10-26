---
title: OpenMP ライブラリ |Microsoft Docs
ms.custom: ''
ms.date: 10/24/2018
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
ms.openlocfilehash: 7620b0ea710a5474fbbbf614691ceeb1e5cc945e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062003"
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
