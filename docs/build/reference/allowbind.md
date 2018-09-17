---
title: -ALLOWBIND |Microsoft Docs
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
ms.openlocfilehash: 0ce0a33ebb0b8b9ba34ac241c8335e9524dec08b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715575"
---
# <a name="allowbind"></a>/ALLOWBIND

DLL をバインドできるかどうかを指定します。

```

/ALLOWBIND[:NO]
```

## <a name="remarks"></a>Remarks

**/ALLOWBIND**オプションは、ビット イメージがバインドできることを Bind.exe に指示を示します DLL のヘッダーを設定します。 バインディングは、高速に読み込むリベースを各参照されている DLL をアドレスのフィックス アップを実行する、ローダーがない場合にイメージを許可できます。 デジタル署名されている場合にバインドする DLL は避けたい-バインドには、署名が無効になります。 バインディングには効果がないを使用して、イメージのアドレス空間レイアウト randomization (ASLR) が有効になっている場合 **/DYNAMICBASE** ASLR をサポートする Windows のバージョン。

使用 **/ALLOWBIND:NO** Bind.exe が DLL をバインドするを防ぐためにします。

詳細については、次を参照してください。、 [/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md)リンカー オプション。

## <a name="see-also"></a>関連項目

[EDITBIN オプション](../../build/reference/editbin-options.md)