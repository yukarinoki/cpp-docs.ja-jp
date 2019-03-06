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
ms.openlocfilehash: 170adfe54b34d14f84b54c717bc9f75fe0b7ab37
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57418478"
---
# <a name="exp-files-as-linker-input"></a>リンカー入力としての .exp ファイル

エクスポート (.exp) ファイルには、エクスポートされた関数とデータ項目に関する情報が含まれます。 LIB、インポート ライブラリを作成する場合も、.exp ファイルを作成します。 .Exp ファイルにエクスポートし、直接または間接的に別のプログラムからインポートするプログラムをリンクするときに使用します。 .Exp ファイルとリンクする場合のリンクが LIB 既に作成されている 1 つと想定しているため、インポート ライブラリを生成してされません。 .Exp ファイルとライブラリのインポートに関する詳細については、次を参照してください。[ライブラリのインポートとエクスポート ファイル](../../build/reference/working-with-import-libraries-and-export-files.md)します。

## <a name="see-also"></a>関連項目

[LINK の入力ファイル](../../build/reference/link-input-files.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)
