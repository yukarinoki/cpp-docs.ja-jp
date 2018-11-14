---
title: リンカー ツールの警告 LNK4221
ms.date: 11/04/2016
f1_keywords:
- LNK4221
helpviewer_keywords:
- LNK4221
ms.assetid: 8e2eb2de-9532-4b85-908a-8c9ff5c4cccb
ms.openlocfilehash: baea8643001c550aeb3cb35dc6fe414e4330c0c1
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523469"
---
# <a name="linker-tools-warning-lnk4221"></a>リンカー ツールの警告 LNK4221

このオブジェクト ファイルが、以前に定義されていないパブリック シンボルを定義していないため、このライブラリを使用するすべてのリンク操作では使用されません。

次の 2 つのコード スニペットを検討してください。

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

ファイルをコンパイルして、2 つのオブジェクト ファイルを作成、実行**cl/c a.cpp b.cpp**コマンド プロンプトでします。 実行して、オブジェクト ファイルをリンクする場合 **/out:test.lib a.obj b.obj を/lib リンク**、LNK4221 警告が表示されます。 実行して、オブジェクトをリンクする場合**リンク/lib、/out:test.lib b.obj a.obj**警告は受け取りません。

2 番目のシナリオで警告が発行されないため、リンカーは後入れ先出し (LIFO) の方法で動作します。 最初のシナリオでは、b.obj a.obj の前に処理され、a.obj に追加する新しいシンボルがありません。 A.obj を最初に処理するようにリンカーに指示して、警告を回避できます。

このエラーの一般的な原因は 2 つのソース ファイル オプションを指定すると[/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)で指定された同じヘッダー ファイルの名前を持つ、**プリコンパイル済みヘッダーの**フィールド。 この問題の一般的な原因は、ため、既定では、stdafx.cpp が stdafx.h が含まれていて、新しいシンボルを追加できません、stdafx.h を処理します。 別のソース ファイルには、stdafx.h でが含まれている場合 **/Yc**と stdafx.obj する前に、関連付けられている .obj ファイルが処理されると、リンカー LNK4221 がスローされます。

あるでそれを含む 1 つだけのソース ファイルは、ことを確認するプリコンパイル済みヘッダーごとにこの問題は、解決するのには一方向、 **/Yc**します。 その他のすべてのソース ファイルには、プリコンパイル済みヘッダーを使用する必要があります。 この設定を変更する方法の詳細については、次を参照してください。 [/Yu (プリコンパイル済みヘッダー ファイルの使用)](../../build/reference/yu-use-precompiled-header-file.md)します。