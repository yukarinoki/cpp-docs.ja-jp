---
title: .リンカー入力として res ファイル |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- RES files as linker input
- .res files as linker input
- linking [C++], resource files
- resource files, linking
ms.assetid: 9c37ab00-97df-4d9a-91cd-6bf132970683
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a6a572013a29420670a2aef8c91c9c4bc64e871
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706316"
---
# <a name="res-files-as-linker-input"></a>リンカー入力としての .res ファイル

プログラムをリンクするときに、.res ファイルを指定できます。 リソース コンパイラ (RC) では、.res ファイルが作成されます。 リンクは、COFF に .res ファイルを自動的に変換します。 CVTRES.exe ツールは、LINK.exe と同じディレクトリ内、または、PATH 環境変数で指定したディレクトリである必要があります。

## <a name="see-also"></a>関連項目

[LINK の入力ファイル](../../build/reference/link-input-files.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)