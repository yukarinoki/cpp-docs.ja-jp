---
title: コンパイラ エラー C3813
ms.date: 11/04/2016
f1_keywords:
- C3813
helpviewer_keywords:
- C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
ms.openlocfilehash: c16ce501e25040a7ac7672a9ea131b4fe89570f5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165614"
---
# <a name="compiler-error-c3813"></a>コンパイラ エラー C3813

プロパティ宣言はマネージド型または WinRT 型の定義内でのみ使用できます

[プロパティ](../../dotnet/how-to-use-properties-in-cpp-cli.md)は、マネージ型または Windows ランタイム型内でのみ宣言できます。 ネイティブ型では、`property` キーワードがサポートされていません。

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
