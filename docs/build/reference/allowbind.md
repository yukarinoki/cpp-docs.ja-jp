---
title: /ALLOWBIND
ms.date: 11/04/2016
f1_keywords:
- /allowbind
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
ms.openlocfilehash: 3d38b2a70fc3510b2c26942dc3e5e6fdd76a28e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550528"
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