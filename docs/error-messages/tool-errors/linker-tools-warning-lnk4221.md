---
title: リンカー ツールの警告 LNK4221
ms.date: 08/19/2019
f1_keywords:
- LNK4221
helpviewer_keywords:
- LNK4221
ms.assetid: 8e2eb2de-9532-4b85-908a-8c9ff5c4cccb
ms.openlocfilehash: 299c3ef76006b347d6770d45ca317ff0eb941ffa
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630803"
---
# <a name="linker-tools-warning-lnk4221"></a>リンカー ツールの警告 LNK4221

このオブジェクトファイルには未定義のパブリックシンボルが定義されていないため、このライブラリを使用するリンク操作では使用されません。

次の2つのコードスニペットについて考えてみます。

```
// a.cpp
#include <atlbase.h>
```

```
// b.cpp
#include <atlbase.h>
int function()
{
   return 0;
}
```

ファイルをコンパイルして2つのオブジェクトファイルを作成するには、コマンドプロンプトで**cl/c を**実行します。 **リンク/lib/out:** LNK4221 を実行してオブジェクトファイルをリンクした場合は、警告が表示されます。 **リンク/lib/out: .lib の**.obj を実行してオブジェクトをリンクした場合、警告は表示されません。

リンカーは後入れ先出し (LIFO) 方式で動作するため、2番目のシナリオでは警告は発行されません。 最初のシナリオでは、b .obj は .obj の前に処理され、.obj には追加する新しいシンボルはありません。 リンカーに対して最初に .obj を処理するように指示することにより、警告を回避できます。

::: moniker range=">=vs-2019"

このエラーの一般的な原因は、2つのソースファイルでオプション[/yc (プリコンパイル済みヘッダーファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)を指定し、[**プリコンパイル済み**ヘッダー] フィールドで指定したヘッダーファイル名が同じである場合です。 この問題の一般的な原因は、pch を扱うことです。既定では、.pch には .pch が含まれており、新しいシンボルは追加されません。 別のソースファイルに **/yc と/yc**が含まれていて、関連付けられた .obj ファイルが pch の前に処理された場合、リンカーは LNK4221 をスローします。

::: moniker-end

::: moniker range="<=vs-2017"

このエラーの一般的な原因は、2つのソースファイルでオプション[/yc (プリコンパイル済みヘッダーファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)を指定し、[**プリコンパイル済み**ヘッダー] フィールドで指定したヘッダーファイル名が同じである場合です。 この問題の一般的な原因は、既定では stdafx.h に*stdafx.h*が含まれており、新しいシンボルは追加されないためです。 別のソースファイルに*stdafx.h*と **/yc**が含まれていて、関連付けられた .obj ファイルが stdafx.h の前に処理された場合、リンカーは LNK4221 をスローします。

::: moniker-end

この問題を解決する方法の1つは、プリコンパイル済みヘッダーごとに、 **/yc**を含むソースファイルが1つだけであることを確認することです。 他のすべてのソースファイルはプリコンパイル済みヘッダーを使用する必要があります。 この設定を変更する方法の詳細については、「 [/yu (プリコンパイル済みヘッダーファイルの使用)](../../build/reference/yu-use-precompiled-header-file.md)」を参照してください。
