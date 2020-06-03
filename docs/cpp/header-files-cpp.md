---
title: ヘッダー ファイル (C++)
ms.date: 12/11/2019
helpviewer_keywords:
- header files [C++]
ms.openlocfilehash: 4ab6a2b2626cde94f35678bc9ec789b80d493b8f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367238"
---
# <a name="header-files-c"></a>ヘッダー ファイル (C++)

変数、関数、クラスなどのプログラム要素の名前は、使用する前に宣言する必要があります。 たとえば、最初に 'x'`x = 42`を宣言せずに記述することはできません。

```cpp
int x; // declaration
x = 42; // use x
```

この宣言は、要素が**int** **、double**、**関数**、**クラス**、またはその他のものかどうかをコンパイラに通知します。  さらに、各名前は、使用されるすべての .cpp ファイルで (直接的または間接的に) 宣言する必要があります。 プログラムをコンパイルすると、各 .cpp ファイルは個別にコンパイルされ、コンパイル単位になります。 コンパイラは、他のコンパイル単位で宣言されている名前を認識していません。 つまり、クラス、関数、またはグローバル変数を定義する場合は、その変数を使用する追加の .cpp ファイルに、その宣言を記述する必要があります。 その各宣言は、すべてのファイルでまったく同一でなければなりません。 リンカーがすべてのコンパイル単位を 1 つのプログラムにマージしようとすると、若干の不整合が発生すると、エラーまたは意図しない動作が発生します。

エラーの可能性を最小限に抑えるために、C++ では *、宣言*を格納するヘッダー ファイルを使用するという規則が採用されています。 ヘッダー ファイルで宣言を行い、その宣言を必要とするすべての .cpp ファイルまたはその他のヘッダー ファイルで #include ディレクティブを使用します。 #include ディレクティブは、コンパイルの前にヘッダー ファイルのコピーを .cpp ファイルに直接挿入します。

> [!NOTE]
> Visual Studio 2019 では、C++20*モジュール*機能が改善され、最終的にヘッダー ファイルの置き換えとして導入されました。 詳細については、「 [C++ モジュールの概要](modules-cpp.md)」を参照してください。

## <a name="example"></a>例

クラスを宣言し、別のソース ファイルで使用する一般的な方法を次の例に示します。 まず、ヘッダー ファイルから`my_class.h`始めます。 クラス定義が含まれていますが、定義が不完全であることに注意してください。メンバー関数`do_something`が定義されていません。

```cpp
// my_class.h
namespace N
{
    class my_class
    {
    public:
        void do_something();
    };

}
```

次に、実装ファイル (通常は .cpp または同様の拡張子を持つ) を作成します。 ファイルを my_class.cpp と呼び、メンバー宣言の定義を提供します。 この時点で`#include`.cpp ファイルにmy_class宣言を挿入するために、"my_class.h" ファイルのディレクティブを追加し、 の`<iostream>``std::cout`宣言を取り込みます。 引用符はソース ファイルと同じディレクトリ内のヘッダー ファイルに使用され、山かっこは標準ライブラリ ヘッダーに使用されます。 また、多くの標準ライブラリヘッダーには.hやその他のファイル拡張子はありません。

実装ファイルでは、オプションで**using**ステートメントを使用して、"my_class" または "cout" のすべての言及を "N:"または "std::" で修飾する必要がなくなります。  ヘッダーファイルに**using**ステートメントを入れないでください。

```cpp
// my_class.cpp
#include "my_class.h" // header in local directory
#include <iostream> // header in standard library

using namespace N;
using namespace std;

void my_class::do_something()
{
    cout << "Doing something!" << endl;
}
```

これで、別の`my_class`.cpp ファイルで使用できます。 コンパイラが宣言を取り込むには、ヘッダー ファイルを#includeします。 コンパイラが知る必要があるのは、my_classが、`do_something()`というパブリック メンバー関数を持つクラスであるということです。

```cpp
// my_program.cpp
#include "my_class.h"

using namespace N;

int main()
{
    my_class mc;
    mc.do_something();
    return 0;
}
```

コンパイラは、各 .cpp ファイルのコンパイルを .obj ファイルに変換した後、.obj ファイルをリンカーに渡します。 リンカーがオブジェクトファイルをマージすると、my_classの定義が 1 つだけ見つかります。これは my_class.cpp 用に生成された .obj ファイルに含まれ、ビルドは成功します。

## <a name="include-guards"></a>警備員を含める

通常、ヘッダー ファイルには *、* 単一の`#pragma once`.cpp ファイルに複数回挿入されないように、インクルード ガードまたはディレクティブがあります。

```cpp
// my_class.h
#ifndef MY_CLASS_H // include guard
#define MY_CLASS_H

namespace N
{
    class my_class
    {
    public:
        void do_something();
    };
}

#endif /* MY_CLASS_H */
```

## <a name="what-to-put-in-a-header-file"></a>ヘッダー ファイルに入れる内容

ヘッダー ファイルは複数のファイルによって含まれる可能性があるため、同じ名前の複数の定義を生成する定義を含めることはできません。 次の手順は許可されていないか、非常に悪い習慣と見なされます。

- 名前空間またはグローバル スコープでの組み込み型定義
- 非インライン関数定義
- 非定数変数定義
- 集約定義
- 名前のない名前空間
- using ディレクティブ

**using**ディレクティブを使用すると、必ずしもエラーが発生するわけではありませんが、直接または間接的にそのヘッダーを含むすべての .cpp ファイル内のスコープに名前空間が持ち込まれるため、問題が発生する可能性があります。

## <a name="sample-header-file"></a>サンプル ヘッダー ファイル

次の例は、ヘッダー ファイルで使用できるさまざまな種類の宣言と定義を示しています。

```cpp
// sample.h
#pragma once
#include <vector> // #include directive
#include <string>

namespace N  // namespace declaration
{
    inline namespace P
    {
        //...
    }

    enum class colors : short { red, blue, purple, azure };

    const double PI = 3.14;  // const and constexpr definitions
    constexpr int MeaningOfLife{ 42 };
    constexpr int get_meaning()
    {
        static_assert(MeaningOfLife == 42, "unexpected!"); // static_assert
        return MeaningOfLife;
    }
    using vstr = std::vector<int>;  // type alias
    extern double d; // extern variable

#define LOG   // macro definition

#ifdef LOG   // conditional compilation directive
    void print_to_log();
#endif

    class my_class   // regular class definition,
    {                // but no non-inline function definitions

        friend class other_class;
    public:
        void do_something();   // definition in my_class.cpp
        inline void put_value(int i) { vals.push_back(i); } // inline OK

    private:
        vstr vals;
        int i;
    };

    struct RGB
    {
        short r{ 0 };  // member initialization
        short g{ 0 };
        short b{ 0 };
    };

    template <typename T>  // template definition
    class value_store
    {
    public:
        value_store<T>() = default;
        void write_value(T val)
        {
            //... function definition OK in template
        }
    private:
        std::vector<T> vals;
    };

    template <typename T>  // template declaration
    class value_widget;
}
```
