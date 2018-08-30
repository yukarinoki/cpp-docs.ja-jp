---
title: -REBASE |Microsoft Docs
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
ms.openlocfilehash: 686306316e6950ba62ea7c44522b95f4d935be0b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43216175"
---
# <a name="rebase"></a>/REBASE
```  
/REBASE[:modifiers]  
```  
  
## <a name="remarks"></a>Remarks  
 このオプションは、指定したファイルのベース アドレスを設定します。 EDITBIN には、最も近い 64 KB に切り上げ、各ファイルのサイズに基づいて連続したアドレス空間に新しいベース アドレスが割り当てられます。 詳細については、ベース アドレスは、次を参照してください。、[ベース アドレス](../../build/reference/base-base-address.md)(/base) リンカー オプション。  
  
 プログラムの実行可能ファイルと Dll の指定、*ファイル*に基づいている順序で EDITBIN コマンドライン引数。 1 つまたは複数を指定することができます必要に応じて*修飾子*、それぞれ、コンマで区切られた (**、**)。  
  
|修飾子|アクション|  
|--------------|------------|  
|**ベース =**<em>アドレス</em>|ファイルにベース アドレスを再割り当てするには、開始アドレスを提供します。 指定*アドレス*10 進数または C 言語表記でします。 ベースが指定されていない場合 0x400000 は、既定のベース アドレスを開始します。 リストが使用されている基本の場合を指定する必要があります、および*アドレス*のベース アドレスの範囲の末尾を設定します。|  
|**BASEFILE**|COFFBASE という名前のファイルを作成します。TXT、オプションを/base の形式でテキスト ファイルですが。|  
|**ダウン**|終了アドレスのベース アドレスの下に再割り当てする EDITBIN に指示します。 ファイルは、最上位のアドレス、アドレスの範囲の最後の下にある最初のファイルで、指定された順序で再割り当ています。 ファイルのための十分なアドレスの容量を確認するのには下ベースを使用する必要があります。 指定したファイルに必要なアドレス空間を確認するのには、ファイル上/REBASE EDITBIN で実行し、表示される合計サイズを 64 KB を追加します。|  
  
## <a name="see-also"></a>関連項目  
 [EDITBIN オプション](../../build/reference/editbin-options.md)