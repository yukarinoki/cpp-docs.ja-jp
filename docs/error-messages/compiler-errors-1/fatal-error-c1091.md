---
title: 致命的なエラー C1091 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1091
dev_langs:
- C++
helpviewer_keywords:
- C1091
ms.assetid: 812d4201-9154-48b0-b9af-5959c082ca33
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e93c2e6c26f8704e700465fb706867129847a460
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104253"
---
# <a name="fatal-error-c1091"></a>致命的なエラー C1091

コンパイラの制限: 文字列が長さ 'length' バイトを超えています

文字列定数が文字列の長さに対する現在の制限を超えました。

静的な文字列を 2 つ (以上) の変数に分割し、 [strcpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) を使用して実行時または宣言の一部としてその分割したものを結合することをお勧めします。