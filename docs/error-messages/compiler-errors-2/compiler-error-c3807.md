---
title: コンパイラ エラー C3807
ms.date: 11/04/2016
f1_keywords:
- C3807
helpviewer_keywords:
- C3807
ms.assetid: 7e2b0aab-8c61-4e71-b9c1-fcaeb6a1b5ea
ms.openlocfilehash: b5599914666af95a29667acc1ad4ad35eef7608f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591127"
---
# <a name="compiler-error-c3807"></a>コンパイラ エラー C3807

'type': ComImport 属性を持つクラスを 'type2' から派生させることはできません、インターフェイスの実装のみが許可されています。

派生した型<xref:System.Runtime.InteropServices.ComImportAttribute>のみインターフェイスを実装できます。

## <a name="example"></a>例

次の例では、C3807 が生成されます。

```
// C3807.cpp
// compile with: /clr /c
ref struct S {};
interface struct I {};

[System::Runtime::InteropServices::ComImportAttribute()]
ref struct S1 : S {};   // C3807
ref struct S2 : I {};
```