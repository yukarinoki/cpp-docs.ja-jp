---
title: OpenMP ライブラリ リファレンス
ms.date: 03/20/2019
ms.assetid: a25188c6-edde-43d0-84b5-780e797b08fc
ms.openlocfilehash: 6f4bbeca54bff1fc44a3576362edca9c30926d5a
ms.sourcegitcommit: 14b292596bc9b9b883a9c58cd3e366b282a1f7b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60124695"
---
# <a name="openmp-library-reference"></a>OpenMP ライブラリ リファレンス

OpenMP API で使用される構成要素へのリンクを提供します。

OpenMP の標準の Visual C の実装には、次の構成要素が含まれています。

|構成体|説明|
|---------------|-----------------|
|[ディレクティブ](openmp-directives.md)|OpenMP API で使用するディレクティブへのリンクを提供します。|
|[句](openmp-directives.md)|OpenMP API で使用される句へのリンクを提供します。|
|[関数](openmp-functions.md)|OpenMP API で使用される関数へのリンクを提供します。|
|[環境変数](openmp-environment-variables.md)|OpenMP API で使用される環境変数へのリンクを提供します。|

ビジュアルC++OpenMP ランタイム ライブラリ関数は、次のライブラリに含まれています。

|OpenMP ライブラリ|特性|
|------------------------------|---------------------|
|VCOMP します。LIB|マルチ スレッド、動的リンク (VCOMP 用インポート ライブラリ。LIB)。|
|VCOMPD します。LIB|マルチ スレッド、動的リンク (VCOMPD 用インポート ライブラリ。カバー) (デバッグ)|

_DEBUG がコンパイル時に定義されている場合、 `#include omp.h` VCOMPD、ソース コードでは、します。LIB 既定 lib、それ以外の場合、VCOMP になります。LIB が使用されます。

使用することができます[/NODEFAULTLIB (ライブラリの無視)](../../../build/reference/nodefaultlib-ignore-libraries.md)を既定のライブラリを削除し、任意のライブラリで明示的にリンクします。

OpenMP Dll は、Visual C 再頒布可能パッケージ ディレクトリには、OpenMP を使用するアプリケーションで配布する必要があります。

## <a name="see-also"></a>関連項目

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)