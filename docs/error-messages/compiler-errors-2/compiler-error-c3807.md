---
title: コンパイラ エラー C3807 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3807
dev_langs:
- C++
helpviewer_keywords:
- C3807
ms.assetid: 7e2b0aab-8c61-4e71-b9c1-fcaeb6a1b5ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7531d5e758828a83bc94ed88b137033182bbfea6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041113"
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