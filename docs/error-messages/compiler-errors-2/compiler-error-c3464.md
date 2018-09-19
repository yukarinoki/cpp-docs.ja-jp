---
title: コンパイラ エラー C3464 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3464
dev_langs:
- C++
helpviewer_keywords:
- C3464
ms.assetid: 0ede05dc-4486-4921-8e8c-78ab5a2e09c5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05322479c076bbb929b6c742fdd379414a263376
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096588"
---
# <a name="compiler-error-c3464"></a>コンパイラ エラー C3464

'type' 入れ子になっている型のみを転送することができます

型の転送は、入れ子にされた型では動作しません。

詳細については、次を参照してください。 [Type Forwarding (C +/cli CLI)](../../windows/type-forwarding-cpp-cli.md)します。

## <a name="example"></a>例

コンポーネントを作成する例を次に示します。

```
// C3464.cpp
// compile with: /LD /clr
public ref class R {
public:
   ref class N {};
};
```

## <a name="example"></a>例

次の例では警告 C3464 が生成されます。

```
// C3464_b.cpp
// compile with: /clr /c
#using "C3464.dll"
[assembly:TypeForwardedTo(R::N::typeid)];   // C3464
[assembly:TypeForwardedTo(R::typeid)];   // OK
```