---
title: リソース コンパイラの致命的なエラー RC1120
ms.date: 11/04/2016
f1_keywords:
- RC1120
helpviewer_keywords:
- RC1120
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
ms.openlocfilehash: 855a76ff63145695a7063944701d7acc684e0084
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173011"
---
# <a name="resource-compiler-fatal-error-rc1120"></a>リソース コンパイラの致命的なエラー RC1120

メモリが不足しています。必要なバイト数

リソースコンパイラは、ヒープに格納されている項目のストレージを使い果たしました。 通常、これはシンボルの数が多すぎることが原因です。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>修復の可能性がある解決策

1. Windows スワップファイルの領域を増やします。 スワップファイルの領域を増やす方法の詳細については、Windows ヘルプの「仮想メモリ」を参照してください。

1. 不要なインクルードファイル (特に不要な `#define`s および関数プロトタイプ) を削除します。

1. 現在のファイルを2つ以上のファイルに分割し、個別にコンパイルします。

1. システムで実行されている他のプログラムやドライバーを削除します。これにより、大量のメモリが消費される可能性があります。
