---
description: '詳細情報: 致命的なエラー C1005'
title: 致命的なエラー C1005
ms.date: 11/04/2016
f1_keywords:
- C1005
helpviewer_keywords:
- C1005
ms.assetid: 150daf8e-a38a-4669-9c1a-a05b5a1f65ef
ms.openlocfilehash: c57856a09aa3473c7f5ba3049a2962fb4553e4e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262673"
---
# <a name="fatal-error-c1005"></a>致命的なエラー C1005

コンパイラの中間ファイルの文字列がバッファーの大きさを超えました。

コンパイラの中間ファイル内の文字列で、バッファーがオーバーフローしました。

このエラーは、 [/Fd](../../build/reference/fd-program-database-file-name.md) または [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) コンパイラ オプションに渡すパラメーターが 256 バイトを超えている場合に発生することがあります。
