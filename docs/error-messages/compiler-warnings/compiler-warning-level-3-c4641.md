---
title: コンパイラの警告 (レベル 3) C4641 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4641
dev_langs:
- C++
helpviewer_keywords:
- C4641
ms.assetid: 28fe5c3e-6039-42da-9100-1312b5b15aea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f44e94868f6a7b379fb1a2f75bbd28ce011b54c9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112110"
---
# <a name="compiler-warning-level-3-c4641"></a>コンパイラの警告 (レベル 3) C4641

XML ドキュメント コメントは、あいまいな相互参照

コンパイラは、明確に参照を解決できませんでした。 この警告を解決するには、参照を明確に必要なパラメーター情報を指定します。

詳細については、「 [XML Documentation](../../ide/xml-documentation-visual-cpp.md)」を参照してください。

## <a name="example"></a>例

次の例では、C4641 が生成されます。

```
// C4641.cpp
// compile with: /W3 /doc /clr /c

/// <see cref="f" />   // C4641
// try the following line instead
// /// <see cref="f(int)" />
public ref class GR {
public:
   void f( int ) {}
   void f( char ) {}
};
```