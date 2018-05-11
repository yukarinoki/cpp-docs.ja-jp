---
title: リンカ ツール エラー LNK1181 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1181
dev_langs:
- C++
helpviewer_keywords:
- LNK1181
ms.assetid: 984b0db6-e331-4284-b2a7-a212fe96c486
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 617678e5453acdafaf72875857b0e0f9b84a110a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1181"></a>リンカ ツール エラー LNK1181
入力ファイル 'filename' を開くことができません。  
  
 リンカーが見つかりませんでした`filename`が存在しないか、パスが見つかりませんでした。  
  
 LNK1181 含めるエラーの一般的な原因がいくつか:  
  
-   `filename` リンカーのコマンドラインは、ファイルに追加の依存関係が存在しないのでが参照されます。  
  
-   A **/LIBPATH**ステートメントを含むディレクトリを指定する`filename`がありません。  
  
 上記の問題を解決するのには、リンカーのコマンドラインで参照されているすべてのファイルが、システムに存在を確認します。  あることを確認、 **/LIBPATH**リンカーの依存ファイルを含むディレクトリごとにステートメントです。  
  
 LNK1181 の他の考えられる原因は、長いファイル名に埋め込まれたスペースが引用符で囲まれていないことです。  その場合は、リンカーだけ最初のスペースでは、最大のファイル名が認識され、ファイル拡張子を想定します .obj。このような状況を解決するには長いファイル名を囲む (パスとファイル名) 引用符で囲んで指定します。  
  
 詳細については、次を参照してください。[リンカー入力としての .lib ファイル](../../build/reference/dot-lib-files-as-linker-input.md)です。  
  
## <a name="see-also"></a>関連項目  
 [/LIBPATH (追加ライブラリのパス)](../../build/reference/libpath-additional-libpath.md)