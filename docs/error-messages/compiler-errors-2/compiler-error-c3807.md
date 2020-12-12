---
description: 詳細については、「コンパイラエラー C3807」を参照してください。
title: コンパイラ エラー C3807
ms.date: 11/04/2016
f1_keywords:
- C3807
helpviewer_keywords:
- C3807
ms.assetid: 7e2b0aab-8c61-4e71-b9c1-fcaeb6a1b5ea
ms.openlocfilehash: ffa8b52b13ae7245b62cd5aa8d7fec9285754b73
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260099"
---
# <a name="compiler-error-c3807"></a>コンパイラ エラー C3807

' type ': ComImport 属性を持つクラスは ' ' 型 ' から派生できません。インターフェイスの実装のみが許可されます。

から派生した型は、 <xref:System.Runtime.InteropServices.ComImportAttribute> インターフェイスのみを実装できます。

## <a name="example"></a>例

次の例では、C3807 が生成されます。

```cpp
// C3807.cpp
// compile with: /clr /c
ref struct S {};
interface struct I {};

[System::Runtime::InteropServices::ComImportAttribute()]
ref struct S1 : S {};   // C3807
ref struct S2 : I {};
```
