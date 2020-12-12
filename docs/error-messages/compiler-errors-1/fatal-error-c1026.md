---
description: '詳細情報: 致命的なエラー C1026'
title: 致命的なエラー C1026
ms.date: 11/04/2016
f1_keywords:
- C1026
helpviewer_keywords:
- C1026
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
ms.openlocfilehash: 08816f21879cf6dfbeb0389700d9a8ffdc7a40d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345512"
---
# <a name="fatal-error-c1026"></a>致命的なエラー C1026

プログラムの解析でコンパイラ内でスタック オーバーフローが発生しました。プログラムが複雑すぎます。

プログラムを解析するために必要な領域が、コンパイラスタックオーバーフローを発生させました。

次のようにして、式の複雑さを軽減します。

- ステートメントとステートメントの入れ子を減らす **`for`** **`switch`** 。 より深い入れ子になったステートメントを個別の関数に配置します。

- コンマ演算子や関数呼び出しを含む長い式を分割します。
