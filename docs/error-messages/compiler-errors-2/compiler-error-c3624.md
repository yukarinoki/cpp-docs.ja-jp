---
title: コンパイラ エラー C3624 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3624
dev_langs:
- C++
helpviewer_keywords:
- C3624
ms.assetid: eaac6a4f-eb11-4e4d-ab12-124ba995c5cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f38aece68d3ca3adff03ec0512cb78afc2e5ffa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030041"
---
# <a name="compiler-error-c3624"></a>コンパイラ エラー C3624

'type': この型の使用には、アセンブリ 'assembly' に参照が必要です。

コードをコンパイルするために必要なアセンブリ (参照) が指定されていません。アセンブリを渡して、 [#using](../../preprocessor/hash-using-directive-cpp.md)ディレクティブ。

## <a name="example"></a>例

次の例では、C3624 が生成されます。

```
// C3624.cpp
// compile with: /clr /c
#using <System.Windows.Forms.dll>

// Uncomment the following 2 lines to resolve.
// #using <System.dll>
// #using <System.Drawing.dll>

using namespace System;

public ref class MyForm : public Windows::Forms::Form {};   // C3624
```
