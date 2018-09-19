---
title: コンパイラの警告 (レベル 1) C4364 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4364
dev_langs:
- C++
helpviewer_keywords:
- C4364
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e37c7f37e1b51296bd5c3ae2cbdb85a93326f027
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087254"
---
# <a name="compiler-warning-level-1-c4364"></a>コンパイラの警告 (レベル 1) C4364

\#アセンブリ 'file' location(line_number) as_friend 属性なしで以前に確認されたを使用してください。as_friend は適用されません。

A`#using`ディレクティブが指定したメタデータ ファイルは、繰り返されましたが、`as_friend`修飾子は、最初に見つかったでは使用されませんでした。 コンパイラは、2 つ目を無視`as_friend`します。

詳細については、次を参照してください。[フレンド アセンブリ (C++)](../../dotnet/friend-assemblies-cpp.md)します。

## <a name="example"></a>例

コンポーネントを作成する例を次に示します。

```
// C4364.cpp
// compile with: /clr /LD
ref class A {};
```

## <a name="example"></a>例

次の例では、C4364 が生成されます。

```
// C4364_b.cpp
// compile with: /clr /W1 /c
#using " C4364.dll"
#using " C4364.dll" as_friend   // C4364
```