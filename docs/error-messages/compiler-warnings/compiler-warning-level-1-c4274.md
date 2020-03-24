---
title: コンパイラの警告 (レベル 1) C4274
ms.date: 11/04/2016
f1_keywords:
- C4274
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
ms.openlocfilehash: 5f2350f275f883e7bf18aa1621d08b34132e8dfb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175847"
---
# <a name="compiler-warning-level-1-c4274"></a>コンパイラの警告 (レベル 1) C4274

\#ident は無視されます。#pragma コメント (exestr、' string ') のドキュメントを参照してください。

オブジェクトまたは実行可能ファイルにユーザーが指定した文字列を挿入する `#ident` ディレクティブは、非推奨とされます。 その結果、コンパイラはディレクティブを無視します。

> [!CAUTION]
>  警告 C4274 は、 [#pragma コメント (exestr, ' string ')](../../preprocessor/comment-c-cpp.md)ディレクティブを使用することをアドバイスします。 ただし、このアドバイスは非推奨とされ、コンパイラの将来のリリースで修正される予定です。 `#pragma` ディレクティブを使用する場合、リンカーツール (setup.exe) はディレクティブによって生成されたコメントレコードを無視し、警告[LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)を発行します。 `#ident` ディレクティブの代わりに、アプリケーションでファイルバージョンリソース文字列を使用することをお勧めします。

## <a name="to-correct-this-error"></a>このエラーを解決するには

- `#ident "`*文字列*`"` ディレクティブを削除します。

## <a name="see-also"></a>参照

[コメント (C/C++)](../../preprocessor/comment-c-cpp.md)<br/>
[リンカー ツールの警告 LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)<br/>
[リソース ファイルの操作](../../windows/working-with-resource-files.md)
