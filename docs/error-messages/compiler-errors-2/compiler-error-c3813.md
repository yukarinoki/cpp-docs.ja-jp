---
description: 詳細については、「コンパイラエラー C3813」を参照してください。
title: コンパイラ エラー C3813
ms.date: 11/04/2016
f1_keywords:
- C3813
helpviewer_keywords:
- C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
ms.openlocfilehash: ae7157166083a4a86d9a5b170cbff3e127c87abb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180995"
---
# <a name="compiler-error-c3813"></a>コンパイラ エラー C3813

プロパティ宣言はマネージド型または WinRT 型の定義内でのみ使用できます

[プロパティ](../../dotnet/how-to-use-properties-in-cpp-cli.md)は、マネージ型または Windows ランタイム型内でのみ宣言できます。 ネイティブ型では、キーワードはサポートされていません **`property`** 。

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
