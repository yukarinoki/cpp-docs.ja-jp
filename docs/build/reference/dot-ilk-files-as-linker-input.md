---
title: リンカー入力としての .ilk ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- ILK files
- .ilk files
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
ms.openlocfilehash: 6c0eb5627d7dd1b414351dc65685c0c5071d249e
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422508"
---
# <a name="ilk-files-as-linker-input"></a>リンカー入力としての .ilk ファイル

段階的にリンクする場合、リンクは、最初のインクリメンタル リンク中に作成された .ilk 状態ファイルを更新します。 このファイルが .exe ファイルまたは .dll ファイルとして同じ基本名と拡張子 .ilk が。 以降のインクリメンタル リンク時に、リンクは .ilk ファイルを更新します。 .Ilk ファイルが見つからない場合、リンクがフル リンクを実行し、新しい .ilk ファイルを作成します。 .Ilk ファイルが使用できない場合は、リンクはノンインクリメンタルのリンクを実行します。 詳細については、インクリメンタル リンクは、次を参照してください。、[インクリメンタル リンクを行う (/incremental)](../../build/reference/incremental-link-incrementally.md)オプション。

## <a name="see-also"></a>関連項目

[LINK の入力ファイル](../../build/reference/link-input-files.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)
