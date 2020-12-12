---
description: 詳細情報:/allowbind
title: /ALLOWBIND
ms.date: 11/04/2016
f1_keywords:
- /allowbind_bind
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
ms.openlocfilehash: 54f3056240537d765a9212e774a9a313ded49dab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179604"
---
# <a name="allowbind"></a>/ALLOWBIND

DLL をバインドできるかどうかを指定します。

```

/ALLOWBIND[:NO]
```

## <a name="remarks"></a>解説

**/Allowbind** オプションは、イメージをバインドできることを Bind.exe に示す、DLL のヘッダーのビットを設定します。 バインディングを使用すると、ローダーが参照される各 DLL のアドレスの修正をリベースして実行する必要がない場合に、イメージの読み込みを高速化できます。 DLL がデジタル署名されている場合、バインドを無効にすることができます。バインディングは、署名を無効にします。 ASLR をサポートするバージョンの Windows で **/DYNAMICBASE** を使用してイメージに対してアドレス空間レイアウトのランダム化 (aslr) が有効になっている場合、バインドは無効です。

**/Allowbind: NO** を使用して、Bind.exe が DLL をバインドできないようにします。

詳細については、「 [/allowbind](allowbind-prevent-dll-binding.md) リンカーオプション」を参照してください。

## <a name="see-also"></a>関連項目

[EDITBIN オプション](editbin-options.md)
