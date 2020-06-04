---
title: コンパイラの警告 (レベル 1) C4910
ms.date: 11/04/2016
f1_keywords:
- C4910
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
ms.openlocfilehash: dc5feb3613e45134a08e493b397eb738fffee8a9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174779"
---
# <a name="compiler-warning-level-1-c4910"></a>コンパイラの警告 (レベル 1) C4910

'\<identifier > ': ' __declspec (dllexport) ' と ' extern ' は、明示的なインスタンス化では互換性がありません

*\<identifier >* という明示的なテンプレートのインスタンス化は、`__declspec(dllexport)` と `extern` の両方のキーワードによって変更されます。 ただし、これらのキーワードは、相互に排他的です。 `__declspec(dllexport)` キーワードは、テンプレート クラスのインスタンス化を意味しますが、 `extern` キーワードは、テンプレート クラスを自動的にインスタンス化しないことを意味します。

## <a name="see-also"></a>参照

[明示的なインスタンス化](../../cpp/explicit-instantiation.md)<br/>
[dllexport、dllimport](../../cpp/dllexport-dllimport.md)<br/>
[一般的な規則と制約](../../cpp/general-rules-and-limitations.md)
