---
description: 詳細情報:/リベース
title: /REBASE
ms.date: 11/04/2016
f1_keywords:
- /rebase
helpviewer_keywords:
- base addresses [C++]
- -REBASE editbin option
- REBASE editbin option
- DLLs [C++], linking
- executable files [C++], base address
- /REBASE editbin option [C++]
ms.assetid: 3f89d874-af5c-485b-974b-fd205f6e1a4b
ms.openlocfilehash: 6cbbf0a21bd9306167fb165b63c22e810518e161
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225337"
---
# <a name="rebase"></a>/REBASE

```
/REBASE[:modifiers]
```

## <a name="remarks"></a>解説

このオプションは、指定されたファイルのベースアドレスを設定します。 EDITBIN では、各ファイルのサイズに応じて、連続するアドレス空間に新しいベースアドレスが割り当てられます。これは、最も近い 64 KB に切り上げられます。 ベースアドレスの詳細については、「 [ベースアドレス](base-base-address.md) (/base) リンカーオプション」を参照してください。

プログラムの実行可能ファイルと Dll を、EDITBIN コマンドラインの [ *ファイル* ] 引数に基づいて指定します。 必要に応じて、1つまたは複数の *修飾子* をコンマ (**,**) で区切って指定できます。

|修飾子|アクション|
|--------------|------------|
|**BASE =**<em>アドレス</em>|ファイルにベースアドレスを再割り当てするための開始アドレスを提供します。 10進数または C 言語表記で *アドレス* を指定します。 BASE が指定されていない場合、既定の開始ベースアドレスは0x400000 です。 DOWN が使用されている場合は、BASE を指定する必要があり、 *address* はベースアドレスの範囲の末尾を設定します。|
|**BASEFILE**|COFFBASE.TXT という名前のファイルを作成します。これは、リンクの/BASE オプションによって想定される形式のテキストファイルです。|
|**ダウン**|は、ベースアドレスを終了アドレスから下に再割り当てするように EDITBIN に指示します。 ファイルは、指定された順序で再割り当てされます。最初のファイルは、アドレス範囲の末尾の下にある最上位のアドレスに配置されます。 ファイルのベースとして十分なアドレス空間を確保するには、ベースを DOWN と共に使用する必要があります。 指定されたファイルで必要なアドレス空間を特定するには、ファイルに対して/リベースを使用して EDITBIN を実行し、表示されている合計サイズに 64 KB を加算します。|

## <a name="see-also"></a>関連項目

[EDITBIN オプション](editbin-options.md)
