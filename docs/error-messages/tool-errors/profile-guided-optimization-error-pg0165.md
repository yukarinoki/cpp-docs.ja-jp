---
title: ガイド付き最適化のプロファイルのエラー PG0165
ms.date: 11/04/2016
f1_keywords:
- PG0165
helpviewer_keywords:
- PG0165
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
ms.openlocfilehash: f39bbe6540ebec10cd25c41ac2fe9f2acfca9b13
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434520"
---
# <a name="profile-guided-optimization-error-pg0165"></a>ガイド付き最適化のプロファイルのエラー PG0165

'Filename.pgd' を読み込んでいます: ' PGD バージョンがサポートされていません (バージョンの不一致)' です。

PGD ファイルは、特定のコンパイラ ツールセットに固有です。 別のコンパイラを使用したものを使用しているときにこのエラーは生成*Filename*.pgd します。 このエラーは、このコンパイラ ツールセットからデータを使用できないことを示します*Filename*.pgd を現在のプログラムを最適化します。

この問題を解決するには、再生成*Filename*.pgd、現在のコンパイラ ツールセットを使用しています。