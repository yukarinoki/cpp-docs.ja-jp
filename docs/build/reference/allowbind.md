---
title: -ALLOWBIND |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /allowbind
dev_langs:
- C++
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af4a9f3d898d0087f0e8e861ccfe72e4adadb1de
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="allowbind"></a>/ALLOWBIND
DLL をバインドできるかどうかを指定します。  
  
```  
  
/ALLOWBIND[:NO]  
```  
  
## <a name="remarks"></a>コメント  
 **/ALLOWBIND**オプションは、ビットを示す Bind.exe にバインドする、イメージが許可されている DLL のヘッダーを設定します。 バインディングは、読み込みも高速、ローダーが再配置して、参照される各 DLL のアドレスのフィックス アップを実行する必要があるないときにイメージを許可できます。 デジタル署名されている場合にバインドする DLL は好ましくありません-バインドには、署名が無効になります。 バインドも何も起こりませんアドレス space layout randomization (機能) が有効な場合、イメージを使用して **/DYNAMICBASE** ASLR をサポートする Windows のバージョンにします。  
  
 使用して **/ALLOWBIND:NO**を Bind.exe が DLL をバインドするを防ぐためにします。  
  
 詳細については、次を参照してください。、 [/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md)リンカー オプション。  
  
## <a name="see-also"></a>関連項目  
 [EDITBIN オプション](../../build/reference/editbin-options.md)