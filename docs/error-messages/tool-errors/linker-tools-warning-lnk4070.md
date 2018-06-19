---
title: リンカー ツールの警告 LNK4070 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4070
dev_langs:
- C++
helpviewer_keywords:
- LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e4599e96552f1b98ef0b1af8d38995ebbe5a83e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302504"
---
# <a name="linker-tools-warning-lnk4070"></a>リンカー ツールの警告 LNK4070
/OUT:filename ディレクティブです。Exp 関数は、出力ファイル名 'filename' によって異なります。ディレクティブは無視されます。  
  
 `filename`で指定されている、[名前](../../build/reference/name-c-cpp.md)または[ライブラリ](../../build/reference/library.md).exp ファイルが作成されたときにステートメントが出力を異なる`filename`が、既定で使用されますか、または、で指定されました。[/Out](../../build/reference/out-output-file-name.md)オプション。  
  
 開発環境で、ここで、プロジェクトの .def ファイルは更新されませんでした、出力ファイルの名前を変更する場合、この警告が表示されます。 この警告を解決するのには、.def ファイルを手動で更新します。  
  
 結果の DLL を使用するクライアント プログラムは、問題が発生して可能性があります。