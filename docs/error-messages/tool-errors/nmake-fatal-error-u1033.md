---
title: NMAKE の致命的なエラー U1033
ms.date: 11/04/2016
f1_keywords:
- U1033
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
ms.openlocfilehash: 4511b15c84479c3531a3bea85964e2768de0181f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173388"
---
# <a name="nmake-fatal-error-u1033"></a>NMAKE の致命的なエラー U1033

構文エラー: 予期しない ' string ' です

この文字列は、メイクファイルの有効な構文の一部ではありません。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. インラインファイルの山かっこ ( **<<** ) の終わりのセットが行の先頭にない場合、次のエラーが発生します。

    ```
    syntax error : 'EOF' unexpected
    ```

1. メイクファイル内のマクロ定義に等号 ( **=** ) が前の名前で含まれていない場合、または定義されている名前が何も展開しないマクロの場合、次のエラーが発生します。

    ```
    syntax error : '=' unexpected
    ```

1. [ツール] のコメント行にセミコロン ( **;** ) がある場合。INI が行の先頭にない場合、次のエラーが発生します。

    ```
    syntax error : ';' unexpected
    ```

1. メイクファイルがワードプロセッサによってフォーマットされている場合、次のエラーが発生する可能性があります。

    ```
    syntax error : ':' unexpected
    ```
