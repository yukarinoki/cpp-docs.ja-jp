---
title: リソース コンパイラ エラー RC2151
ms.date: 11/04/2016
f1_keywords:
- RC2151
helpviewer_keywords:
- RC2151
ms.assetid: 3c47e535-c78d-4338-aab9-9b47e2c34728
ms.openlocfilehash: 8eaa50bc6080e37a4a74585eb03cbe4e40893bce
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598888"
---
# <a name="resource-compiler-error-rc2151"></a>リソース コンパイラ エラー RC2151

文字列定数を再利用することはできません。

2 回の同じ値を使用している、 **STRINGTABLE**ステートメント。 10 進数と 16 進数の値が重複している混在させていないことを確認します。

各 ID で、 **STRINGTABLE**で一意である必要があります。 効率を最大化使用の連続する定数は、16 の倍数でを起動します。