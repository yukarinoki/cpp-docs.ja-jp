---
description: '詳細情報: コンパイラの警告 (レベル 1) C4910'
title: コンパイラの警告 (レベル 1) C4910
ms.date: 11/04/2016
f1_keywords:
- C4910
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
ms.openlocfilehash: 4798ba8ae8005239c9cf83e109bdb0f9e4c01928
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291455"
---
# <a name="compiler-warning-level-1-c4910"></a>コンパイラの警告 (レベル 1) C4910

' \<identifier> ': ' __declspec (dllexport) ' と ' extern ' は、明示的なインスタンス化では互換性がありません

という名前の明示的なテンプレートのインスタンス化 *\<identifier>* は、との両方のキーワードによって変更され `__declspec(dllexport)` **`extern`** ます。 ただし、これらのキーワードは、相互に排他的です。 キーワードは、 `__declspec(dllexport)` テンプレートクラスをインスタンス化することを意味しますが、キーワードは、 **`extern`** テンプレートクラスを自動的にインスタンス化しないことを意味します。

## <a name="see-also"></a>関連項目

[明示的なインスタンス化](../../cpp/explicit-instantiation.md)<br/>
[dllexport、dllimport](../../cpp/dllexport-dllimport.md)<br/>
[一般的な規則と制限事項](../../cpp/general-rules-and-limitations.md)
