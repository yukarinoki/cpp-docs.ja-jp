---
title: コンパイラの警告 C4868
ms.date: 10/26/2017
f1_keywords:
- C4868
ms.assetid: fc6aa7e5-34dd-4ec2-88bd-16e430361dc7
ms.openlocfilehash: d0bc8716e53e71c52f6a31036a95d0b4cefedd79
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388710"
---
# <a name="compiler-warning-level-4-c4868"></a>コンパイラの警告 (レベル 4) C4868

> '_ファイル_(*line_number*)' コンパイラは、中かっこで囲んだ初期化子リストで左から右の評価順序を強制しない可能性があります

中かっこで囲んだ初期化子リストの要素では、左から右の順序で評価します。 2 つのケースをコンパイラはこの順序を保証することができません: オブジェクトの値によって渡された要素の一部は、1 つは2 番目でコンパイルする場合は、`/clr`オブジェクトのフィールドまたは配列要素は要素の一部であるとします。 コンパイラは、左から右に評価を保証できない場合に警告 C4868 を出力します。

この警告は、Visual C 2015 Update 2 で行ったコンパイラ準拠作業の結果として生成できます。 C4868 Visual C 2015 Update 2 の前にコンパイルされたコードを生成できます。

既定では、この警告はオフに設定されています。 使用`/Wall`この警告をアクティブ化します。

この警告を解決するには、まず初期化子リストの要素の左から右に評価が要素の評価が順序に依存、副作用を生成する場合など、必要かどうかを検討します。 多くの場合、要素が評価される順序に目に見える影響はありません。

評価の順序は、左から右にある必要がある場合、は、、要素を渡すことであることを検討してください`const`代わりに参照します。 この変更は、次のコード サンプルで警告を排除します。

## <a name="example"></a>例

この例では、C4868 を生成し、その修正方法を示しています。

```cpp
// C4868.cpp
// compile with: /c /Wall
#include <cstdio>

class HasCopyConstructor
{
public:
    int x;

    HasCopyConstructor(int x): x(x) {}

    HasCopyConstructor(const HasCopyConstructor& h): x(h.x)
    {
        printf("Constructing %d\n", h.x);
    }
};

class TripWarning4868
{
public:
    // note that taking "HasCopyConstructor" parameters by-value will trigger copy-construction.
    TripWarning4868(HasCopyConstructor a, HasCopyConstructor b) {}

    // This variation will not trigger the warning:
    // TripWarning4868(const HasCopyConstructor& a, const HasCopyConstructor& b) {}
};

int main()
{
    HasCopyConstructor a{1};
    HasCopyConstructor b{2};

    // the warning will indicate the below line, the usage of the braced initializer list.
    TripWarning4868 warningOnThisLine{a, b};
};
```