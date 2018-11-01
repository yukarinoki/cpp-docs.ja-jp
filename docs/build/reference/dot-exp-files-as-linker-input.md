---
title: リンカー入力としての .exp ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- exporting functions
- import libraries, linker files
- linking [C++], exports
- exporting functions, information about exported functions
- exporting data, export (.exp) files
- functions [C++], exporting
- .exp files [C++]
- EXP files
ms.assetid: 399f5636-0a4d-462e-b500-5f5b9ae5ad22
ms.openlocfilehash: 4f70aad2fa91431da771f8e5be47956ae2db45a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661933"
---
# <a name="exp-files-as-linker-input"></a>リンカー入力としての .exp ファイル

エクスポート (.exp) ファイルには、エクスポートされた関数とデータ項目に関する情報が含まれます。 LIB、インポート ライブラリを作成する場合も、.exp ファイルを作成します。 .Exp ファイルにエクスポートし、直接または間接的に別のプログラムからインポートするプログラムをリンクするときに使用します。 .Exp ファイルとリンクする場合のリンクが LIB 既に作成されている 1 つと想定しているため、インポート ライブラリを生成してされません。 .Exp ファイルとライブラリのインポートに関する詳細については、次を参照してください。[ライブラリのインポートとエクスポート ファイル](../../build/reference/working-with-import-libraries-and-export-files.md)します。

## <a name="see-also"></a>関連項目

[LINK の入力ファイル](../../build/reference/link-input-files.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)