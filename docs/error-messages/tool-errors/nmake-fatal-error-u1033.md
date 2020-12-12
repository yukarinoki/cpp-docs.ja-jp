---
description: 詳細については、「NMAKE の致命的なエラー U1033」を参照してください。
title: NMAKE の致命的なエラー U1033
ms.date: 11/04/2016
f1_keywords:
- U1033
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
ms.openlocfilehash: e616e98a21c92137fab4b167318a9305a2175bb2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272137"
---
# <a name="nmake-fatal-error-u1033"></a>NMAKE の致命的なエラー U1033

構文エラー: 予期しない ' string ' です

この文字列は、メイクファイルの有効な構文の一部ではありません。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. インラインファイルの山かっこ () の終わりのセット **<<** が行の先頭にない場合、次のエラーが発生します。

    ```
    syntax error : 'EOF' unexpected
    ```

1. メイクファイルのマクロ定義に、前の名前のない等号 () が含まれている場合、 **=** または定義されている名前が、何も展開しないマクロの場合、次のエラーが発生します。

    ```
    syntax error : '=' unexpected
    ```

1. TOOLS.INI のコメント行のセミコロン (**;**) が行の先頭にない場合、次のエラーが発生します。

    ```
    syntax error : ';' unexpected
    ```

1. メイクファイルがワードプロセッサによってフォーマットされている場合、次のエラーが発生する可能性があります。

    ```
    syntax error : ':' unexpected
    ```
