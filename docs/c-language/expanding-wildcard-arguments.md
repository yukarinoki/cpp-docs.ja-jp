---
title: ワイルドカード引数の展開
description: リンカー オプションを使用してプログラム内のワイルドカード コマンド ライン引数を処理する方法について説明します。
ms.date: 11/20/2020
helpviewer_keywords:
- asterisk wildcard
- question mark, wildcard
- expanding wildcard arguments
- wildcards, expanding
ms.openlocfilehash: b847a5dd8af577a4e30edcd9bc7fc34add296c17
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483309"
---
# <a name="expanding-wildcard-arguments"></a>ワイルドカード引数の展開

ワイルドカード引数の展開は Microsoft 固有の機能です。

C プログラムを実行する際、2 つのワイルドカード (疑問符 ( **`?`** ) とアスタリスク ( **`*`** )) のいずれかを使用して、コマンド ラインでファイル名とパスの引数を指定できます。

既定では、ワイルドカードはコマンド ライン引数では展開されません。 *`setargv.obj`* または *`wsetargv.obj`* ファイルとリンクすることで、通常の引数ベクター `argv` の読み込みルーチンを、ワイルドカードを展開するバージョンと置き換えることができます。 プログラムで `main` 関数を使用している場合は、 *`setargv.obj`* とリンクします。 プログラムで `wmain` 関数を使用している場合は、 *`wsetargv.obj`* とリンクします。 これら両方の動作は同等です。 

*`setargv.obj`* または *`wsetargv.obj`* とリンクするには、 **`/link`** オプションを使用します。 次に例を示します。

**`cl example.c /link setargv.obj`**

ワイルドカードはオペレーティング システム コマンドと同じように展開されます

## <a name="see-also"></a>関連項目

[リンク オプション](../c-runtime-library/link-options.md)\
[`main` 関数とプログラム実行](../c-language/main-function-and-program-execution.md)
