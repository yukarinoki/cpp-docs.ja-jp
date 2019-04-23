---
title: コンパイラの警告 (レベル 1) C4910
ms.date: 11/04/2016
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
ms.openlocfilehash: 49cbbf3369fc4765d93e67e2dca84a4d975560d7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59027574"
---
# <a name="compiler-warning-level-1-c4910"></a>コンパイラの警告 (レベル 1) C4910

'\<identifier>' : '__declspec(dllexport)' and 'extern' are incompatible on an explicit instantiation

という名前の明示的なテンプレートをインスタンス化*\<識別子 >* 両方で変更されたが、`__declspec(dllexport)`と`extern`キーワード。 ただし、これらのキーワードは、相互に排他的です。 `__declspec(dllexport)` キーワードは、テンプレート クラスのインスタンス化を意味しますが、 `extern` キーワードは、テンプレート クラスを自動的にインスタンス化しないことを意味します。

## <a name="see-also"></a>関連項目

[明示的なインスタンス化](../../cpp/explicit-instantiation.md)<br/>
[dllexport、dllimport](../../cpp/dllexport-dllimport.md)<br/>
[一般的な規則と制約](../../cpp/general-rules-and-limitations.md)