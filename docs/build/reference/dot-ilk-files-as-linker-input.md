---
title: .Ilk ファイルをリンカー入力として |Microsoft ドキュメント
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
ms.openlocfilehash: 01fea585b86114373017b6d73948cb1438b7185e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371685"
---
# <a name="ilk-files-as-linker-input"></a>リンカー入力としての .ilk ファイル
インクリメンタル リンク、リンクは、最初のインクリメンタル リンク中に作成された .ilk ステータス ファイルを更新します。 このファイルは .exe ファイルまたは .dll ファイルと同じ基本名を持ち、拡張子は .ilk がします。 以降のインクリメンタル リンク中には、リンクは .ilk ファイルを更新します。 .Ilk ファイルが見つからない場合、リンクはフル リンクを実行し、新しい .ilk ファイルを作成します。 .Ilk ファイルが使用できない場合は、リンクはノンインクリメンタルのリンクを実行します。 インクリメンタル リンクに関する詳細については、次を参照してください。、[インクリメンタル リンク (/incremental)](../../build/reference/incremental-link-incrementally.md)オプション。  
  
## <a name="see-also"></a>関連項目  
 [LINK の入力ファイル](../../build/reference/link-input-files.md)   
 [リンカー オプション](../../build/reference/linker-options.md)