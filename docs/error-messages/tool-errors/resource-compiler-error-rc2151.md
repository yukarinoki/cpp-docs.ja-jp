---
title: リソース コンパイラ エラー RC2151 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2151
dev_langs:
- C++
helpviewer_keywords:
- RC2151
ms.assetid: 3c47e535-c78d-4338-aab9-9b47e2c34728
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a15f3f1237df9e4b706a2c2048dddd6d5db395d5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109783"
---
# <a name="resource-compiler-error-rc2151"></a>リソース コンパイラ エラー RC2151

文字列定数を再利用することはできません。

2 回の同じ値を使用している、 **STRINGTABLE**ステートメント。 10 進数と 16 進数の値が重複している混在させていないことを確認します。

各 ID で、 **STRINGTABLE**で一意である必要があります。 効率を最大化使用の連続する定数は、16 の倍数でを起動します。