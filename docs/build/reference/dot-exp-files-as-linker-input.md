---
title: .リンカー入力として exp ファイル |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4badc93f38d5ce76dcc294ad4ae216c8e3f6454c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45724010"
---
# <a name="exp-files-as-linker-input"></a>リンカー入力としての .exp ファイル

エクスポート (.exp) ファイルには、エクスポートされた関数とデータ項目に関する情報が含まれます。 LIB、インポート ライブラリを作成する場合も、.exp ファイルを作成します。 .Exp ファイルにエクスポートし、直接または間接的に別のプログラムからインポートするプログラムをリンクするときに使用します。 .Exp ファイルとリンクする場合のリンクが LIB 既に作成されている 1 つと想定しているため、インポート ライブラリを生成してされません。 .Exp ファイルとライブラリのインポートに関する詳細については、次を参照してください。[ライブラリのインポートとエクスポート ファイル](../../build/reference/working-with-import-libraries-and-export-files.md)します。

## <a name="see-also"></a>関連項目

[LINK の入力ファイル](../../build/reference/link-input-files.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)