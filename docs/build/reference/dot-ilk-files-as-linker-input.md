---
title: .リンカー入力として ilk ファイル |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ILK files
- .ilk files
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f3b8de3758daf59a543cdcc9f3b73e1d6c6f0ce8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720591"
---
# <a name="ilk-files-as-linker-input"></a>リンカー入力としての .ilk ファイル

段階的にリンクする場合、リンクは、最初のインクリメンタル リンク中に作成された .ilk 状態ファイルを更新します。 このファイルが .exe ファイルまたは .dll ファイルとして同じ基本名と拡張子 .ilk が。 以降のインクリメンタル リンク時に、リンクは .ilk ファイルを更新します。 .Ilk ファイルが見つからない場合、リンクがフル リンクを実行し、新しい .ilk ファイルを作成します。 .Ilk ファイルが使用できない場合は、リンクはノンインクリメンタルのリンクを実行します。 詳細については、インクリメンタル リンクは、次を参照してください。、[インクリメンタル リンクを行う (/incremental)](../../build/reference/incremental-link-incrementally.md)オプション。

## <a name="see-also"></a>関連項目

[LINK の入力ファイル](../../build/reference/link-input-files.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)