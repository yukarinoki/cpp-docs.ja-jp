---
description: 詳細については、「」を参照してください。リンカー入力としての Exp ファイル
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
ms.openlocfilehash: 03104d6b4265484e54373484b6c9bbdabf0e1afc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192812"
---
# <a name="exp-files-as-linker-input"></a>リンカー入力としての .exp ファイル

エクスポート (.exp) ファイルには、エクスポートされた関数とデータ項目に関する情報が含まれています。 LIB によってインポートライブラリが作成されると、.exp ファイルも作成されます。 ファイルを直接または間接的に別のプログラムからエクスポートしてインポートするプログラムをリンクする場合は、.exp ファイルを使用します。 .Exp ファイルとリンクする場合は、LIB で既に作成されているものと見なされるため、インポートライブラリは作成されません。 .Exp ファイルとインポートライブラリの詳細については、「 [インポートライブラリの操作」および「ファイルのエクスポート](working-with-import-libraries-and-export-files.md)」を参照してください。

## <a name="see-also"></a>関連項目

[リンク入力ファイル](link-input-files.md)<br/>
[MSVC リンカー オプション](linker-options.md)
