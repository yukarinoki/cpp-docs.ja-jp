---
title: 致命的なエラー C1026
ms.date: 11/04/2016
f1_keywords:
- C1026
helpviewer_keywords:
- C1026
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
ms.openlocfilehash: a7c7a5da01c8b4a44c307a00f53530acb12a8009
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204654"
---
# <a name="fatal-error-c1026"></a>致命的なエラー C1026

プログラムの解析でコンパイラ内でスタック オーバーフローが発生しました。プログラムが複雑すぎます。

プログラムを解析するために必要な領域が、コンパイラスタックオーバーフローを発生させました。

次のようにして、式の複雑さを軽減します。

- `for` および `switch` ステートメントの入れ子を減らす。 より深い入れ子になったステートメントを個別の関数に配置します。

- コンマ演算子や関数呼び出しを含む長い式を分割します。
