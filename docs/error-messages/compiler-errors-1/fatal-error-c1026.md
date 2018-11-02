---
title: 致命的なエラー C1026
ms.date: 11/04/2016
f1_keywords:
- C1026
helpviewer_keywords:
- C1026
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
ms.openlocfilehash: b1a659967a9a62cb79e1084f7d1fa1729bae14da
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666189"
---
# <a name="fatal-error-c1026"></a>致命的なエラー C1026

プログラムの解析でコンパイラ内でスタック オーバーフローが発生しました。プログラムが複雑すぎます。

プログラムの解析に必要な領域には、コンパイラ スタック オーバーフローが発生します。

式の複雑さを軽減するには。

- 内に入れ子の減少`for`と`switch`ステートメント。 別の関数より深く入れ子になったステートメントを配置します。

- コンマ演算子や関数呼び出しを含む長い式を分割します。