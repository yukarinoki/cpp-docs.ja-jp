---
description: 詳細については、「リソースコンパイラの致命的なエラー RC1120」を参照してください。
title: リソース コンパイラの致命的なエラー RC1120
ms.date: 11/04/2016
f1_keywords:
- RC1120
helpviewer_keywords:
- RC1120
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
ms.openlocfilehash: bc0c90bf5d8dd4290ab20369235c53fcd2c80182
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272033"
---
# <a name="resource-compiler-fatal-error-rc1120"></a>リソース コンパイラの致命的なエラー RC1120

メモリが不足しています。必要なバイト数

リソースコンパイラは、ヒープに格納されている項目のストレージを使い果たしました。 通常、これはシンボルの数が多すぎることが原因です。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. Windows スワップファイルの領域を増やします。 スワップファイルの領域を増やす方法の詳細については、Windows ヘルプの「仮想メモリ」を参照してください。

1. 不要なインクルードファイル (特に、不要なおよび関数プロトタイプ) を削除し `#define` ます。

1. 現在のファイルを2つ以上のファイルに分割し、個別にコンパイルします。

1. システムで実行されている他のプログラムやドライバーを削除します。これにより、大量のメモリが消費される可能性があります。
