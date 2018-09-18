---
title: コンパイラの警告 (レベル 1) C4910 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e6db959e467ea449a66feb3ee07c202f4dee002
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018952"
---
# <a name="compiler-warning-level-1-c4910"></a>コンパイラの警告 (レベル 1) C4910

'\<識別子 >': '関数' と 'extern' 明示的なインスタンス化の互換性がありません

という名前の明示的なテンプレートをインスタンス化*\<識別子 >* 両方で変更されたが、`__declspec(dllexport)`と`extern`キーワード。 ただし、これらのキーワードは、相互に排他的です。 `__declspec(dllexport)` キーワードは、テンプレート クラスのインスタンス化を意味しますが、 `extern` キーワードは、テンプレート クラスを自動的にインスタンス化しないことを意味します。

## <a name="see-also"></a>関連項目

[明示的なインスタンス化](../../cpp/explicit-instantiation.md)<br/>
[dllexport、dllimport](../../cpp/dllexport-dllimport.md)<br/>
[一般的な規則と制約](../../cpp/general-rules-and-limitations.md)