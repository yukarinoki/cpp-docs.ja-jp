---
description: '詳細情報: コンパイラの警告 (レベル 1) C4274'
title: コンパイラの警告 (レベル 1) C4274
ms.date: 11/04/2016
f1_keywords:
- C4274
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
ms.openlocfilehash: aa1f6d3b07c7d788d9e47955c4bb51930522b7a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340100"
---
# <a name="compiler-warning-level-1-c4274"></a>コンパイラの警告 (レベル 1) C4274

\#ident は無視されました。#pragma コメント (exestr、' string ') のドキュメントを参照してください。

`#ident`オブジェクトまたは実行可能ファイルにユーザーが指定した文字列を挿入するディレクティブは、非推奨とされます。 その結果、コンパイラはディレクティブを無視します。

> [!CAUTION]
> 警告 C4274 は、 [#pragma コメント (exestr, ' string ')](../../preprocessor/comment-c-cpp.md) ディレクティブを使用することをアドバイスします。 ただし、このアドバイスは非推奨とされ、コンパイラの将来のリリースで修正される予定です。 ディレクティブを使用する `#pragma` と、リンカーツール (LINK.exe) は、ディレクティブによって生成されたコメントレコードを無視し、警告 [LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)を発行します。 ディレクティブの代わりに `#ident` 、アプリケーションでファイルバージョンリソース文字列を使用することをお勧めします。

## <a name="to-correct-this-error"></a>このエラーを解決するには

- `#ident "`*文字列* `"` ディレクティブを削除します。

## <a name="see-also"></a>関連項目

[コメント (C/C++)](../../preprocessor/comment-c-cpp.md)<br/>
[リンカーツールの警告 LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)<br/>
[リソース ファイルの操作](../../windows/working-with-resource-files.md)
