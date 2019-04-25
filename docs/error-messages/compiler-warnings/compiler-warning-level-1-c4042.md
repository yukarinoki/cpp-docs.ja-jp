---
title: コンパイラの警告 (レベル 1) C4042
ms.date: 11/04/2016
f1_keywords:
- C4042
helpviewer_keywords:
- C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
ms.openlocfilehash: 99f4f45aad82aa9898dad4cffb60b8e3311ddc9f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152144"
---
# <a name="compiler-warning-level-1-c4042"></a>コンパイラの警告 (レベル 1) C4042

'identifier': 無効なストレージ クラスがあります。

指定されたストレージ クラスは、このコンテキストでこの識別子では使用できません。 コンパイラは、代わりに既定のストレージ クラスを使用します。

- `extern`、場合*識別子*関数です。

- **自動**場合は、*識別子*仮パラメーターまたはローカル変数です。

- ストレージ クラスのない場合、*識別子*はグローバル変数です。

この警告を発生以外のストレージ クラスを指定する**登録**パラメーターの宣言でします。

次のサンプルの生成 C4042

```
// C4042.cpp
// compile with: /W1 /LD
int func2( __declspec( thread ) int tls_i )    // C4042
// try the following line instead
// int func2( int tls_i )
{
   return tls_i;
}
```