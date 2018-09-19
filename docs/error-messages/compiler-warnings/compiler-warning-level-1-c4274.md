---
title: コンパイラの警告 (レベル 1) C4274 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4274
dev_langs:
- C++
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5f6db0ee96674beda51ab02c8651e6f4960a0bf8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094690"
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