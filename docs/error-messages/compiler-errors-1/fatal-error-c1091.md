---
title: 致命的なエラー C1091
ms.date: 11/04/2016
f1_keywords:
- C1091
helpviewer_keywords:
- C1091
ms.assetid: 812d4201-9154-48b0-b9af-5959c082ca33
ms.openlocfilehash: 76492be7abab6deb740f1670b85274b8c296c783
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203893"
---
# <a name="fatal-error-c1091"></a>致命的なエラー C1091

コンパイラの制限: 文字列が長さ 'length' バイトを超えています

文字列定数が文字列の長さに対する現在の制限を超えました。

静的な文字列を 2 つ (以上) の変数に分割し、 [strcpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) を使用して実行時または宣言の一部としてその分割したものを結合することをお勧めします。
