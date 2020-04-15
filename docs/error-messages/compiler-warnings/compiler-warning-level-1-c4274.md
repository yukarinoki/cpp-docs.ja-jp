---
title: コンパイラの警告 (レベル 1) C4274
ms.date: 11/04/2016
f1_keywords:
- C4274
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
ms.openlocfilehash: 5d005fccc5920aea61698a65edf9284d56366a1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377076"
---
# <a name="compiler-warning-level-1-c4274"></a>コンパイラの警告 (レベル 1) C4274

\#ident は無視されます。コメントのドキュメント#pragma参照してください(exestr、 'string')

オブジェクト`#ident`または実行可能ファイルにユーザー指定の文字列を挿入するディレクティブは推奨されません。 したがって、コンパイラはディレクティブを無視します。

> [!CAUTION]
> 警告 C4274 は[、#pragma コメント (exestr、 'string')](../../preprocessor/comment-c-cpp.md)ディレクティブを使用するように助言します。 ただし、このアドバイスは非推奨であり、コンパイラの今後のリリースで改訂される予定です。 ディレクティブを`#pragma`使用すると、リンカー ツール (LINK.exe) は、ディレクティブによって生成されたコメント レコードを無視し、警告[LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)を発行します。 ディレクティブの`#ident`代わりに、アプリケーションでファイル バージョンのリソース文字列を使用することをお勧めします。

## <a name="to-correct-this-error"></a>このエラーを解決するには

- `#ident "`*string*文字列`"`ディレクティブを削除します。

## <a name="see-also"></a>関連項目

[コメント (C/C++)](../../preprocessor/comment-c-cpp.md)<br/>
[リンカーツール警告 LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)<br/>
[リソース ファイルの操作](../../windows/working-with-resource-files.md)
