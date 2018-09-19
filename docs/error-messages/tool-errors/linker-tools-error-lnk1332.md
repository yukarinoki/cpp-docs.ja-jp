---
title: リンカ ツール エラー LNK1332 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1332
dev_langs:
- C++
helpviewer_keywords:
- LNK1332
ms.assetid: b31d5ca0-c27f-4177-896b-2637dccbde24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b256c61b9e9de6bf19e754054de1f55fcdec5f0b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094521"
---
# <a name="linker-tools-error-lnk1332"></a>リンカ ツール エラー LNK1332

検出された\<数 > Windows ランタイム型が 1 つのモジュールにインポートされ、別のモジュールで定義されています。

現在のターゲットが生成されたときに、リンカーが検出されました <`count`> が 1 つのモジュールでインポートされ、また別のモジュールで定義されているそれぞれの Windows ランタイムの型。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- それぞれのエラー メッセージの推奨に従って、ビルドで LNK2039 エラーを修正します。

## <a name="see-also"></a>関連項目

[リンカー ツール エラー LNK2039](../../error-messages/tool-errors/linker-tools-error-lnk2039.md)<br/>
[リンカー ツール エラーと警告](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)