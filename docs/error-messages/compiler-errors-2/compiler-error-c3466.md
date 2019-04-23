---
title: コンパイラ エラー C3466
ms.date: 11/04/2016
f1_keywords:
- C3466
helpviewer_keywords:
- C3466
ms.assetid: 69a877d9-a749-474b-bfc3-8d3fd53ba8fd
ms.openlocfilehash: 6eae1c44d8dae9118258c83c5919947803f49215
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777251"
---
# <a name="compiler-error-c3466"></a>コンパイラ エラー C3466

'type': ジェネリック クラスの特殊化を転送することはできません

型のジェネリック クラスの特殊化の転送を使用することはできません。

詳細については、次を参照してください。 [Type Forwarding (C +/cli CLI)](../../extensions/type-forwarding-cpp-cli.md)します。

## <a name="example"></a>例

コンポーネントを作成する例を次に示します。

```
// C3466.cpp
// compile with: /clr /LD
generic<typename T>
public ref class GR {};

public ref class GR2 {};
```

## <a name="example"></a>例

次の例では C3466 が生成されます。

```
// C3466_b.cpp
// compile with: /clr /c
#using "C3466.dll"
[assembly:TypeForwardedTo(GR<int>::typeid)];   // C3466
[assembly:TypeForwardedTo(GR2::typeid)];   // OK
```