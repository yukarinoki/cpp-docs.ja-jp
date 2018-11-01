---
title: リンカー入力としての .res ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- RES files as linker input
- .res files as linker input
- linking [C++], resource files
- resource files, linking
ms.assetid: 9c37ab00-97df-4d9a-91cd-6bf132970683
ms.openlocfilehash: 3cbddba1273d579454560f176df00b09b03c89bf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575094"
---
# <a name="res-files-as-linker-input"></a>リンカー入力としての .res ファイル

プログラムをリンクするときに、.res ファイルを指定できます。 リソース コンパイラ (RC) では、.res ファイルが作成されます。 リンクは、COFF に .res ファイルを自動的に変換します。 CVTRES.exe ツールは、LINK.exe と同じディレクトリ内、または、PATH 環境変数で指定したディレクトリである必要があります。

## <a name="see-also"></a>関連項目

[LINK の入力ファイル](../../build/reference/link-input-files.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)