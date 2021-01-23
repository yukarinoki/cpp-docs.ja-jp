---
description: pragmaMicrosoft C/c + + での check_stack ディレクティブの詳細については、こちらを参照してください。
title: check_stack pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.check_stack
- check_stack_CPP
helpviewer_keywords:
- check_stack pragma
- pragma, check_stack
- pragma, check_stack usage table
no-loc:
- pragma
ms.openlocfilehash: a395471625fed60fcf750ebac8f3159a89ba1487
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713715"
---
# <a name="check_stack-no-locpragma"></a>`check_stack` pragma

(または) が指定されている場合はスタックプローブをオフにし、 **`off`** **`-`** **`on`** (または) が指定されている場合はスタックプローブを有効にするようにコンパイラに指示 **`+`** します。

## <a name="syntax"></a>構文

> **`#pragma check_stack(`** [{ **`on`** | **`off`** }] **`)`**\
> **`#pragma check_stack`** { **`+`** | **`-`** }

## <a name="remarks"></a>解説

この処理は pragma 、が表示された後に定義された最初の関数で有効になり pragma ます。 スタック プローブは、マクロの一部でも、インラインで生成される関数の一部でもありません。

に引数を指定しない場合 **`check_stack`** pragma 、スタックチェックはコマンドラインで指定された動作に戻ります。 詳細については、「[コンパイラ オプション](../build/reference/compiler-options.md)」を参照してください。 とオプションの相互作用を `#pragma check_stack` [`/Gs`](../build/reference/gs-control-stack-checking-calls.md) 次の表にまとめます。

### <a name="using-the-check_stack-pragma"></a>check_stack プラグマの使用

| 構文 | コンパイルで<br /><br /> `/Gs` オプション? | アクション |
|--|--|--|
| `#pragma check_stack( )`<br /><br /> `#pragma check_stack` | はい | 後続の関数のスタック チェックをオフにします |
| `#pragma check_stack( )`<br /><br /> `#pragma check_stack` | いいえ | 後続の関数のスタック チェックをオンにします |
| `#pragma check_stack(on)`<br /><br /> または `#pragma check_stack +` | はい、いいえ | 後続の関数のスタック チェックをオンにします |
| `#pragma check_stack(off)`<br /><br /> または `#pragma check_stack -` | はい、いいえ | 後続の関数のスタック チェックをオフにします |

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
