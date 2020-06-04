---
title: リンカ ツール エラー LNK1181
ms.date: 08/22/2018
f1_keywords:
- LNK1181
helpviewer_keywords:
- LNK1181
ms.assetid: 984b0db6-e331-4284-b2a7-a212fe96c486
ms.openlocfilehash: d2b28af52a2ca2263a7bad77c8c69242396ff2b4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195254"
---
# <a name="linker-tools-error-lnk1181"></a>リンカ ツール エラー LNK1181

入力ファイル ' filename ' を開くことができません

リンカーは、存在しないかパスが見つからなかったため、`filename` を見つけることができませんでした。

エラー LNK1181 の一般的な原因には、次のものがあります。

- リンカー行に対する追加の依存関係として `filename` が参照されていますが、ファイルが存在しません。

- `filename` が含まれているディレクトリを指定する **/libpath**ステートメントがありません。

上記の問題を解決するには、リンカー行で参照されているファイルがシステムに存在することを確認します。  また、リンカーに依存するファイルが格納されている各ディレクトリに対して、 **/libpath**ステートメントがあることを確認します。

詳細については、「[リンカー入力としての .Lib ファイル](../../build/reference/dot-lib-files-as-linker-input.md)」を参照してください。

LNK1181 のもう1つの原因としては、スペースが埋め込まれている長いファイル名が引用符で囲まれていないことが考えられます。  この場合、リンカーは最初のスペースまでのファイル名のみを認識し、.obj のファイル拡張子を想定します。 この状況に対処するには、長いファイル名 (パスとファイル名) を引用符で囲みます。

[/P (ファイルを前処理する)](../../build/reference/p-preprocess-to-a-file.md)オプションを使用してコンパイルすると、LNK1181 が発生する可能性があります。これは、このオプションによって .obj ファイルの作成が抑制されるためです。

## <a name="see-also"></a>参照

[/LIBPATH (追加ライブラリのパス)](../../build/reference/libpath-additional-libpath.md)
