---
title: OpenMP ライブラリ |Microsoft ドキュメント
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
ms.openlocfilehash: 46bd287ff8a020a4d5d7775afdb12f5571d43294
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694772"
---
# <a name="openmp-libraries"></a>OpenMP ライブラリ
Visual C の OpenMP ランタイム ライブラリを構成する .lib ファイルについて説明します。  
  
 次のライブラリには、ビジュアルの C++ OpenMP のランタイム ライブラリ関数が含まれます。  
  
|OpenMP のランタイム ライブラリ|特性|  
|------------------------------|---------------------|  
|VCOMP です。LIB|マルチ スレッド、動的リンク (VCOMP 用インポート ライブラリ。LIB)。|  
|VCOMPD です。LIB|マルチ スレッド、動的リンク (VCOMPD 用インポート ライブラリ。カバー) (デバッグ)|  
  
 _DEBUG がコンパイル時に定義されている場合、 `#include omp.h` VCOMPD のソース コードでは、します。LIB 既定 lib になります。 それ以外の場合、VCOMP です。LIB が使用されます。  
  
 使用することができます[/NODEFAULTLIB (ライブラリの無視)](../../../build/reference/nodefaultlib-ignore-libraries.md)既定 lib を削除して、任意のライブラリで明示的にリンクします。  
  
 OpenMP Dll は、Visual C 再頒布可能パッケージ ディレクトリにおよび、OpenMP を使用するアプリケーションを配布する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [ライブラリ リファレンス](../../../parallel/openmp/reference/openmp-library-reference.md)