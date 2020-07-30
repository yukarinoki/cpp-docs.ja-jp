---
title: コンパイラの警告 (レベル 4) C4800
ms.date: 03/14/2019
f1_keywords:
- C4800
helpviewer_keywords:
- C4800
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
ms.openlocfilehash: a516be2e6e1966c3249ed21cc6d480ddea8b5ec1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220016"
---
# <a name="compiler-warning-level-4-c4800"></a>コンパイラの警告 (レベル 4) C4800

::: moniker range=">= vs-2019"
Visual Studio 2019 以降: 
> '*Type*' から bool への暗黙的な変換です。 考えられる情報の損失
::: moniker-end

C4800 は、Visual Studio 2015 以前のレベル3の警告です。
> '*type*': ブール値 ' true ' または ' false ' に強制的に値を指定します (パフォーマンス警告)

この警告は、値が暗黙的に型に変換されるときに生成され **`bool`** ます。 通常、このメッセージは、変数 **`int`** に **`bool`** **`int`** 値とが含まれ、 **`true`** **`false`** 型として再宣言できる変数に変数を割り当てることによって発生し **`bool`** ます。 型を使用するように式を書き直すことができない場合は、式 **`bool`** に "" を追加し `!=0` ます。これにより、式の型が指定され **`bool`** ます。 式を型にキャストし **`bool`** ても、警告は無効になりません。これは仕様です。

::: moniker range=">= vs-2017"
この警告は、Visual Studio 2017 では生成されません。
::: moniker-end

::: moniker range=">= vs-2019"
この警告は、Visual Studio 2019 以降、既定ではオフになっています。 __/W__*n*__4800__を使用して C4800 をレベル*n*の警告として有効にするか、 [/Wall](../../build/reference/compiler-option-warning-level.md)を使用して既定でオフになっているすべての警告を有効にします。 詳細については、「[既定でオフになっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。
::: moniker-end

## <a name="example"></a>例

次の例では、C4800 を生成し、その修正方法を示しています。

```cpp
// C4800.cpp
// compile with: /W4 /w44800
int main() {
   int i = 0;

   // To fix, instead try:
   // bool i = 0;

   bool j = i;   // C4800
   j++;
}
```
