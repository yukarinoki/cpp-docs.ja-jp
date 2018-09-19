---
title: コンパイラ エラー C3813 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3813
dev_langs:
- C++
helpviewer_keywords:
- C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b8984feb5b657c26d2137eb9a3c648f1bcf442bf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066272"
---
# <a name="compiler-error-c3813"></a>コンパイラ エラー C3813

プロパティ宣言はマネージド型または WinRT 型の定義内でのみ使用できます

A[プロパティ](../../dotnet/how-to-use-properties-in-cpp-cli.md)マネージ型または Windows ランタイム内でのみ宣言できます型。 ネイティブ型では、`property` キーワードがサポートされていません。

## <a name="example"></a>例

次の例では、C3813 を生成し、その修正方法を示しています。

```cpp
// C3813.cpp
// compile by using: cl /c /clr C3813.cpp
class A
{
   property int Int; // C3813
};

ref class B
{
   property int Int; // OK - declared within managed type
};
```