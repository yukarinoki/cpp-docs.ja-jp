---
title: リンカ ツール エラー LNK1181
ms.date: 08/22/2018
f1_keywords:
- LNK1181
helpviewer_keywords:
- LNK1181
ms.assetid: 984b0db6-e331-4284-b2a7-a212fe96c486
ms.openlocfilehash: 834220e6325e332a07c3865b5ff66e1bbc1b8c69
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657981"
---
# <a name="linker-tools-error-lnk1181"></a>リンカ ツール エラー LNK1181

入力ファイル 'filename' を開くことができません。

リンカーが見つかりませんでした。`filename`が存在しないか、パスが見つかりませんでした。

よくある原因のエラー LNK1181 が含まれます。

- `filename` リンカーのコマンドラインは、ファイルの追加の依存関係が存在しないために参照されます。

- A **/LIBPATH**格納されているディレクトリを指定するステートメント`filename`がありません。

上記の問題を解決するには、リンカーのコマンドラインで参照されているすべてのファイルは、システムに存在を確認します。  あることを確認、 **/LIBPATH**リンカーの依存ファイルを含む各ディレクトリに対してステートメントです。

詳細については、[リンカー入力としての .lib ファイル](../../build/reference/dot-lib-files-as-linker-input.md)を参照してください。

LNK1181 のもう 1 つの考えられる原因は、長いファイル名に埋め込まれたスペースが引用符で囲まれていないことです。  その場合は、リンカーだけ最初のスペースでは、最大のファイル名が認識され、ファイル拡張子を想定します .obj。このような状況を解決するには長いファイル名を囲む (パスとファイル名) 引用符で囲んで指定します。

コンパイルすると、 [/P (ファイルへのプリプロセス)](../../build/reference/p-preprocess-to-a-file.md)オプションにより、LNK1181 のため、そのオプションの .obj ファイルの作成を抑制します。

## <a name="see-also"></a>関連項目

[/LIBPATH (追加ライブラリのパス)](../../build/reference/libpath-additional-libpath.md)