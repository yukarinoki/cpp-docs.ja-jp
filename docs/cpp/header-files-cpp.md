---
title: ヘッダー ファイル (C++)
ms.date: 04/20/2018
helpviewer_keywords:
- header files [C++]
ms.openlocfilehash: ea163f4d47022d886e40a09c47c252ffa186aee0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153609"
---
# <a name="header-files-c"></a>ヘッダー ファイル (C++)

使用する前に、変数、関数、クラスなどのプログラム要素の名前を宣言する必要があります。 たとえば、ことはできませんを記述するだけ`x = 42`'x' を宣言する前にします。

```cpp
int x; // declaration
x = 42; // use x
```

宣言コンパイラに指示するかどうかは、 **int**、**二重**、**関数**、**クラス**またはその他のいくつかのことです。  さらに、それぞれの名前で宣言されなければなりません (直接または間接的に) が使用されているすべての .cpp ファイル。 プログラムをコンパイルするときに各 .cpp ファイルにコンパイルされますしない個別にコンパイル ユニット。 コンパイラには、どのような名前をその他のコンパイル単位で宣言したに関する情報がありません。 つまり、クラスまたは関数やグローバル変数を定義する場合は、それを使用する各追加の .cpp ファイルでこの操作をするの宣言を指定する必要があります。 操作をするのには、各宣言は、すべてのファイルでまったく同じにする必要があります。 わずかな不整合により、エラー、または意図しない動作は、リンカーは、すべてのコンパイル ユニットを 1 つのプログラムにマージしようとしたとき。

エラーの可能性を最小限に抑えるには、C++ は、使用する規則を採用*ヘッダー ファイル*宣言を格納します。 ヘッダー ファイルで宣言を作成した後、使用して、# すべての .cpp ファイルに include ディレクティブまたはその他のヘッダー ファイルには、その宣言が必要です。 #Include ディレクティブの挿入、ヘッダー ファイルのコピーをコンパイルする前に、.cpp ファイルに直接 include します。

## <a name="example"></a>例

次の例では、クラス宣言をし、別のソース ファイルで使用する一般的な方法を示します。 まず、ヘッダー ファイル`my_class.h`します。 クラスの定義が含まれていますが、定義が完了したことに注意してください。メンバー関数は、`do_something`が定義されていません。

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

次に、(通常は .cpp または同様の拡張機能) で、実装ファイルを作成します。 ファイル my_class.cpp を呼び出す、メンバーの宣言の定義を提供します。 追加、`#include`ディレクティブ my_class 宣言を挿入するためには"my_class.h"ファイルをこの時点で、.cpp ファイル、およびことがあります`<iostream>`の宣言でプルする`std::cout`します。 引用符は、ソース ファイルと同じディレクトリ内のヘッダー ファイルの使用、山かっこが標準ライブラリ ヘッダーに使用されることに注意してください。 また、多くの標準ライブラリ ヘッダーでは、.h またはその他の任意のファイル拡張子がありません。

実装ファイルは必要に応じて使用して、**を使用して**ステートメントと"my_class"または"cout"のすべてのメンションを修飾することを避けるために"n::"または"std::"です。  配置しないでください**を使用して**ヘッダー ファイル内のステートメント。

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

使用できるようになりました`my_class`別の .cpp ファイルにします。 私たち # ヘッダー ファイルに include、コンパイラは、宣言でプルできるようにします。 すべてのコンパイラ ニーズを把握するはその my_class という名前のパブリック メンバー関数を持つクラスであるの`do_something()`します。

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

コンパイラでは、.obj ファイルに各 .cpp ファイルのコンパイルが完了すると、.obj ファイルがリンカーに渡します。 リンカーは、オブジェクト ファイルをマージした場合、my_class; の 1 つだけの定義を検索します。生成 my_class.cpp、.obj ファイル内にあるし、ビルドが成功します。

## <a name="include-guards"></a>#Include guard

通常、ヘッダー ファイルがある、 *guard*または`#pragma once`ことがないに挿入した複数回、1 つの .cpp ファイルを確認するディレクティブ。

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

## <a name="what-to-put-in-a-header-file"></a>ヘッダー ファイルに記述する内容

ヘッダー ファイルを複数のファイルが含まれている可能性がある可能性があります、ために、同じ名前の複数の定義が生成する定義を含めることはできません。 次は許可されていませんまたは非常に不適切な手法と見なされます。

- 名前空間またはグローバル スコープでの組み込み型の定義
- 非インライン関数の定義
- 非 const 変数の定義
- 集計の定義
- 名前のない名前空間
- using ディレクティブ

使用、**を使用して**ディレクティブは、エラーは必ずしもが直接的または間接的にそのヘッダーが含まれています。 すべての .cpp ファイル内のスコープに名前空間をもたらすため、問題になる可能性があります。

## <a name="sample-header-file"></a>ヘッダー ファイルのサンプル

次の例では、宣言とヘッダー ファイルで使用できる定義のさまざまな種類を示します。

```cpp
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