---
title: -REBASE |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /rebase
dev_langs:
- C++
helpviewer_keywords:
- base addresses [C++]
- -REBASE editbin option
- REBASE editbin option
- DLLs [C++], linking
- executable files [C++], base address
- /REBASE editbin option [C++]
ms.assetid: 3f89d874-af5c-485b-974b-fd205f6e1a4b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4a5e2b68768b01d71532c358a14c53d8a033e1ed
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377090"
---
# <a name="rebase"></a>/REBASE
```  
/REBASE[:modifiers]  
```  
  
## <a name="remarks"></a>コメント  
 このオプションは、指定したファイルのベース アドレスを設定します。 EDITBIN には、最も近い 64 KB に切り上げ各ファイルのサイズに従って連続したアドレス空間に新しいベース アドレスが割り当てられます。 詳細については、ベース アドレスは、次を参照してください。、[ベース アドレス](../../build/reference/base-base-address.md)(/base) リンカー オプション。  
  
 プログラムの実行可能ファイルや Dll を指定して、*ファイル*される基に順番 EDITBIN コマンドラインの引数。 1 つ以上を指定することができます必要に応じて*修飾子*それぞれをコンマで区切られた、(**、**)。  
  
|修飾子|アクション|  
|--------------|------------|  
|ベース **= * * * アドレス*|ファイルにベース アドレスを再割り当てするための開始アドレスを提供します。 指定*アドレス*10 進数または C 言語表記でします。 ベースが指定されていない場合 0x400000 は、既定のベース アドレスを開始します。 ダウンが使用されている基本の場合を指定する必要があります、および*アドレス*ベース アドレスの範囲の末尾を設定します。|  
|BASEFILE|COFFBASE をという名前のファイルを作成します。TXT、するオプションを/base リンクの必要な形式のテキスト ファイルです。|  
|下方向 (↓) キー|EDITBIN 下向きにベース アドレスの終了アドレスからを再割り当てするように指示します。 ファイルは、最上位の考えられるアドレス、アドレスの範囲の最後の下にある最初のファイルで、指定された順序で再度割り当てられます。 ファイルのための十分なアドレスの容量を確認するのには下ベースを使用する必要があります。 指定したファイルに必要なアドレス空間を特定するのには、ファイル上/REBASE EDITBIN で実行し、表示されている合計サイズを 64 KB を追加します。|  
  
## <a name="see-also"></a>関連項目  
 [EDITBIN オプション](../../build/reference/editbin-options.md)