---
description: 詳細については、「コンパイラエラー C3624」を参照してください。
title: コンパイラ エラー C3624
ms.date: 11/04/2016
f1_keywords:
- C3624
helpviewer_keywords:
- C3624
ms.assetid: eaac6a4f-eb11-4e4d-ab12-124ba995c5cf
ms.openlocfilehash: f18b3b7bc013214a1bc9a417e2154cd2d5b4970b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318937"
---
# <a name="compiler-error-c3624"></a>コンパイラ エラー C3624

' type ': この型を使用するには、アセンブリ ' assembly ' への参照が必要です

コードをコンパイルするために必要なアセンブリ (参照) が指定されていません。アセンブリを [#using](../../preprocessor/hash-using-directive-cpp.md) ディレクティブに渡します。

## <a name="example"></a>例

次の例では、C3624 が生成されます。

```cpp
// C3624.cpp
// compile with: /clr /c
#using <System.Windows.Forms.dll>

// Uncomment the following 2 lines to resolve.
// #using <System.dll>
// #using <System.Drawing.dll>

using namespace System;

public ref class MyForm : public Windows::Forms::Form {};   // C3624
```
