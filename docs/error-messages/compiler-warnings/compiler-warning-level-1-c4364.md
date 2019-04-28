---
title: コンパイラの警告 (レベル 1) C4364
ms.date: 11/04/2016
f1_keywords:
- C4364
helpviewer_keywords:
- C4364
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
ms.openlocfilehash: db2774b6a73a989b4e9250719f99122826b486fe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207109"
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