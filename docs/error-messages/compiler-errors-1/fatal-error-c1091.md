---
description: '詳細情報: 致命的なエラー C1091'
title: 致命的なエラー C1091
ms.date: 11/04/2016
f1_keywords:
- C1091
helpviewer_keywords:
- C1091
ms.assetid: 812d4201-9154-48b0-b9af-5959c082ca33
ms.openlocfilehash: 3863600e10dcfbef274424559e2cda0ca791406b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145172"
---
# <a name="fatal-error-c1091"></a>致命的なエラー C1091

コンパイラの制限: 文字列が長さ 'length' バイトを超えています

文字列定数が文字列の長さに対する現在の制限を超えました。

静的な文字列を 2 つ (以上) の変数に分割し、 [strcpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) を使用して実行時または宣言の一部としてその分割したものを結合することをお勧めします。
