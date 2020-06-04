---
title: /ALLOWBIND
ms.date: 11/04/2016
f1_keywords:
- /allowbind_bind
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
ms.openlocfilehash: 4f5b662223914cbb4970188595afb52cc2500cd4
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440383"
---
# <a name="allowbind"></a>/ALLOWBIND

DLL をバインドできるかどうかを指定します。

```

/ALLOWBIND[:NO]
```

## <a name="remarks"></a>コメント

**/Allowbind**オプションは、DLL のヘッダー内のビットを設定します。これは、イメージをバインドできることをバインドすることを示します。 バインディングを使用すると、ローダーが参照される各 DLL のアドレスの修正をリベースして実行する必要がない場合に、イメージの読み込みを高速化できます。 DLL がデジタル署名されている場合、バインドを無効にすることができます。バインディングは、署名を無効にします。 ASLR をサポートするバージョンの Windows で **/DYNAMICBASE**を使用してイメージに対してアドレス空間レイアウトのランダム化 (aslr) が有効になっている場合、バインドは無効です。

**/Allowbind: NO**を使用して、Bind .EXE が DLL をバインドできないようにします。

詳細については、「 [/allowbind](allowbind-prevent-dll-binding.md)リンカーオプション」を参照してください。

## <a name="see-also"></a>参照

[EDITBIN オプション](editbin-options.md)
