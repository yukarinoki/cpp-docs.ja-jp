---
title: 関数またはマクロの選択に関する推奨事項 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.functions
dev_langs:
- C++
helpviewer_keywords:
- functions [CRT], vs. macros
- macros, vs. functions
ms.assetid: 18a633d6-cf1c-470c-a649-fa7677473e2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8e347da977b58621529564f6e6d8646bd72063a0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023268"
---
# <a name="recommendations-for-choosing-between-functions-and-macros"></a>関数またはマクロの選択に関する推奨事項

Microsoft ランタイム ライブラリ ルーチンのほとんどは、コンパイルまたはアセンブル済みの関数ですが、いくつかのルーチンはマクロとして実装されます。 ヘッダー ファイルでルーチンの関数バージョンとマクロ バージョンの両方を宣言するときは、マクロ定義が常に関数の宣言の後に示されるため、マクロ定義が優先されます。 関数とマクロの両方として実装されているルーチンを呼び出す場合は、次の 2 つの方法で、関数バージョンを使用するようにコンパイラに強制することができます。

- ルーチンの名前をかっこで囲む。

    ```C
    #include <ctype.h>
    a = _toupper(a);    // Use macro version of toupper.
    a = (_toupper)(a);  // Force compiler to use
                        // function version of toupper.
    ```

- `#undef` ディレクティブを使用してマクロ定義を「未定義」にする。

    ```C
    #include <ctype.h>
    #undef _toupper
    ```

関数実装とマクロ実装のライブラリ ルーチンのどちらかを選択する必要がある場合は、次のトレードオフを考慮してください。

- **速度とサイズ** マクロを使用する主な利点は、実行時間が短縮されることです。 プリプロセス中、マクロは使用されるたびにインライン展開されます (その定義によって置き換えられます)。 関数定義は、関数が呼び出される回数に関係なく、1 回だけ行われます。 マクロによって、コード サイズは増えますが、関数呼び出しに伴うオーバーヘッドはありません。

- **関数の評価** 関数ではアドレスが評価されますが、マクロでは評価されません。 したがって、ポインターが必要なコンテキストでマクロ名を使用することはできません。 たとえば、関数のポインターは宣言できますが、マクロのポインターは宣言できません。

- **型チェック** 関数を宣言するときに、コンパイラは引数の型を確認できます。 マクロは宣言できないため、コンパイラはマクロに渡す引数の数を確認できますが、マクロの引数の型を確認することはできません。

## <a name="see-also"></a>参照

[CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)