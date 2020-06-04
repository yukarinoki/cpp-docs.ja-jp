---
title: コンパイラの警告 (レベル 4) C4800
ms.date: 03/14/2019
f1_keywords:
- C4800
helpviewer_keywords:
- C4800
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
ms.openlocfilehash: 828b38aeb184741af284f2d7722017b24f6255a3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198589"
---
# <a name="compiler-warning-level-4-c4800"></a>コンパイラの警告 (レベル 4) C4800

::: moniker range=">= vs-2019"
Visual Studio 2019 以降:
> '*Type*' から bool への暗黙的な変換です。 考えられる情報の損失
::: moniker-end

C4800 は、Visual Studio 2015 以前のレベル3の警告です。
> '*type*': ブール値 ' true ' または ' false ' に強制的に値を指定します (パフォーマンス警告)

この警告は、値が型 `bool`に暗黙的に変換されるときに生成されます。 通常、このメッセージは、`int` 変数に**true**と**false**の値のみが含まれている `bool` 変数に `int` 変数を割り当てることによって発生し、型 `bool`として再宣言することができます。 型 `bool`を使用するように式を書き直すことができない場合は、式に "`!=0`" を追加して、式の型 `bool`を指定することができます。 式を型 `bool` にキャストしても、警告は無効になりません。これは仕様です。

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
