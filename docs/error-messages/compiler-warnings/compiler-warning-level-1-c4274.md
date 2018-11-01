---
title: コンパイラの警告 (レベル 1) C4274
ms.date: 11/04/2016
f1_keywords:
- C4274
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
ms.openlocfilehash: dcdf804ac6e02d2bb161751db054d7f1f62ddbb5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564594"
---
# <a name="compiler-warning-level-1-c4274"></a>コンパイラの警告 (レベル 1) C4274

\#ident が無視されます。#pragma comment (exestr, 'string') のドキュメントを参照してください。

`#ident`ディレクティブで、ユーザー指定の文字列を挿入すると、オブジェクトまたは実行可能ファイルで、これが非推奨とされます。 その結果、コンパイラでは、ディレクティブは無視されます。

> [!CAUTION]
>  警告 C4274 では、使用するように勧める、 [#pragma comment (exestr, 'string')](../../preprocessor/comment-c-cpp.md)ディレクティブ。 ただし、このアドバイスは非推奨し、コンパイラの将来のリリースで変更されます。 使用する場合、`#pragma`ディレクティブ、リンカー ツール (LINK.exe) ディレクティブによって生成された、このコメント レコードを無視し、警告[LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)します。 代わりに、`#ident`ディレクティブ、お勧め、アプリケーションでは、ファイル バージョン リソース文字列を使用することです。

## <a name="to-correct-this-error"></a>このエラーを解決するには

- 削除、 `#ident "`*文字列*`"`ディレクティブ。

## <a name="see-also"></a>関連項目

[コメント (C/C++)](../../preprocessor/comment-c-cpp.md)<br/>
[リンカー ツールの警告 LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)<br/>
[リソース ファイルの操作](../../windows/working-with-resource-files.md)