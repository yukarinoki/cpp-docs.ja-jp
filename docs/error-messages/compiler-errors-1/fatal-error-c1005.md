---
title: 致命的なエラー C1005
ms.date: 11/04/2016
f1_keywords:
- C1005
helpviewer_keywords:
- C1005
ms.assetid: 150daf8e-a38a-4669-9c1a-a05b5a1f65ef
ms.openlocfilehash: a8b0fe71dcfb6253327de247d24ef9d90c59181d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204868"
---
# <a name="fatal-error-c1005"></a>致命的なエラー C1005

コンパイラの中間ファイルの文字列がバッファーの大きさを超えました。

コンパイラの中間ファイル内の文字列で、バッファーがオーバーフローしました。

このエラーは、 [/Fd](../../build/reference/fd-program-database-file-name.md) または [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) コンパイラ オプションに渡すパラメーターが 256 バイトを超えている場合に発生することがあります。
