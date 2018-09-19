---
title: リンカー ツールの警告 LNK4070 |Microsoft Docs
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
ms.openlocfilehash: 9cfb4ae1c5440742c491d9615a2b4929a9b04f66
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106961"
---
# <a name="linker-tools-warning-lnk4070"></a>リンカー ツールの警告 LNK4070

/OUT:filename ディレクティブ。Exp 関数は、出力ファイル名 'filename'; によって異なります。ディレクティブは無視されます。

`filename`で指定されている、[名前](../../build/reference/name-c-cpp.md)または[ライブラリ](../../build/reference/library.md).exp ファイルが作成されたときにステートメントと、出力は異なります`filename`が既定で使用されますか、で指定されました。[/Out](../../build/reference/out-output-file-name.md)オプション。

開発環境で、プロジェクトの .def ファイルが更新されたしない出力ファイルの名前を変更する場合、この警告が表示されます。 この警告を解決するのには、.def ファイルを手動で更新します。

結果の DLL を使用するクライアント プログラムには、問題が発生します。