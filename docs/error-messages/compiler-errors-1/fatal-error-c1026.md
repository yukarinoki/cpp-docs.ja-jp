---
title: 致命的なエラー C1026 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1026
dev_langs:
- C++
helpviewer_keywords:
- C1026
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db9167383df48dad274ef8941defaa53f51d3bfa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068989"
---
# <a name="fatal-error-c1026"></a>致命的なエラー C1026

プログラムの解析でコンパイラ内でスタック オーバーフローが発生しました。プログラムが複雑すぎます。

プログラムの解析に必要な領域には、コンパイラ スタック オーバーフローが発生します。

式の複雑さを軽減するには。

- 内に入れ子の減少`for`と`switch`ステートメント。 別の関数より深く入れ子になったステートメントを配置します。

- コンマ演算子や関数呼び出しを含む長い式を分割します。