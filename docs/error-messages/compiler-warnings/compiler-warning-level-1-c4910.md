---
title: コンパイラの警告 (レベル 1) C4910
ms.date: 11/04/2016
f1_keywords:
- C4910
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
ms.openlocfilehash: b17df9d7a9997e5d8ef37a4721de8693968cbbdf
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214452"
---
# <a name="compiler-warning-level-1-c4910"></a>コンパイラの警告 (レベル 1) C4910

' \<identifier> ': ' __declspec (dllexport) ' と ' extern ' は、明示的なインスタンス化では互換性がありません

という名前の明示的なテンプレートのインスタンス化 *\<identifier>* は、との両方のキーワードによって変更され `__declspec(dllexport)` **`extern`** ます。 ただし、これらのキーワードは、相互に排他的です。 キーワードは、 `__declspec(dllexport)` テンプレートクラスをインスタンス化することを意味しますが、キーワードは、 **`extern`** テンプレートクラスを自動的にインスタンス化しないことを意味します。

## <a name="see-also"></a>関連項目

[明示的なインスタンス化](../../cpp/explicit-instantiation.md)<br/>
[dllexport、dllimport](../../cpp/dllexport-dllimport.md)<br/>
[一般的な規則と制限事項](../../cpp/general-rules-and-limitations.md)
