---
title: ソース コードの組織 (C++ テンプレート) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 50569c5d-0219-4966-9bcf-a8689074ad1d
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 05a5b0423b79e817e16aeb0d39f1d0dcf856c1ba
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32423117"
---
# <a name="source-code-organization-c-templates"></a>ソース コードの組織 (C++ テンプレート)

クラス テンプレートを定義するときに、その必要がある場合、メンバーの定義が、コンパイラに認識されているように、ソース コードを整理する必要があります。   使用する選択肢がある、*包含モデル*または*明示的なインスタンス化*モデル。 包含モデルでは、テンプレートを使用するすべてのファイルのメンバーの定義が含まれます。 このアプローチは最も簡単なであり、テンプレートで使用できる具体的な種類の観点から最大限の柔軟性を提供します。 その欠点は、コンパイル時間かかる可能性があります。 影響がプロジェクトに大量になる/含まれるファイル自体が大きい。 明示的なインスタンス化方法では、テンプレート自体は、具象クラスや特定の種類のクラス メンバー インスタンス化します。  このアプローチは、コンパイル時間を高速化できますが、使用量をテンプレートの実行者があらかじめ有効になっているクラスだけを制限します。 一般に、コンパイル時間が問題になる場合を除き、信頼モデルを使用することをお勧めします。

## <a name="background"></a>背景

テンプレートは、コンパイラが、テンプレート、またはそのメンバーのいずれかのオブジェクト コードを生成しないという点で通常のクラスと同様にありません。 具象型でテンプレートがインスタンス化するまで、生成するものがあります。 コンパイラが検出した場合、テンプレートのインスタンス化など`MyClass<int> mc;`とその署名を持つクラスが存在しないまだ、新しいクラスが生成されます。 使用されている任意のメンバー関数のコードを生成しようとします。 これらの定義はないファイル内にあるかどうかは #included、直接または間接的に、コンパイル中は、.cpp ファイルで、コンパイラに表示されないようにします。  コンパイラの観点から見る、必ずしもエラー、関数がいる場合、リンカーはで検索して、別の翻訳単位で定義されているためです。  リンカーがそのコードを検出していない場合は、発生、**未解決の外部**エラーです。

## <a name="the-inclusion-model"></a>信頼モデル

テンプレートの定義を翻訳単位全体で表示する最も簡単で最も一般的な方法は、ヘッダー ファイル自体に定義を格納します。  テンプレートを使用するすべての .cpp ファイルが、単に #include ヘッダー。 これは、標準ライブラリで使用するアプローチです。

```cpp
#ifndef MYARRAY
#define MYARRAY
#include <iostream>

template<typename T, size_t N>
class MyArray
{
    T arr[N];
public:
    // Full definitions:
    MyArray(){}
    void Print()
    {
        for (const auto v : arr)
        {
            std::cout << v << " , ";
        }
    }

    T& operator[](int i)
   {
       return arr[i];
   } 
};
#endif
```

この方法では、コンパイラは、完全なテンプレートの定義にアクセスし、任意の型のオンデマンドでテンプレートをインスタンス化できます。 単純で比較的簡単に維持します。 ただし、包含モデルでは、コンパイル時間の観点からコストが必要です。   このコストは、大規模なプログラムに大きく場合に特に自体テンプレート ヘッダー # 他のヘッダーを includes です。 すべての .cpp ファイルを #include includes ヘッダーは関数テンプレートとすべての定義のコピーを取得します。 リンカーは一般をソートできる点できるようにするで終わらない関数の場合、複数の定義が、この作業を行う時間がかかります。 小さいプログラムでは、その余分なコンパイル時は重要ではありません。

## <a name="the-explicit-instantiation-model"></a>明示的なインスタンス化モデル

包含モデルでは、プロジェクトの実行可能なありませんと明確にテンプレートをインスタンス化に使用される型のセットがある場合は、ことができます、.h および .cpp ファイルに、テンプレート コードを分離し、.cpp ファイルで明示的にインスタンス化のテンプレートです。 これにより、オブジェクト コードを生成するユーザー インスタンスを検出した場合に、コンパイラが表示されます。

明示的なインスタンス化を作成するには、インスタンスを作成するエンティティの署名後に、キーワードのテンプレートを使用します。 これには、型またはメンバーを指定できます。 型を明示的にインスタンス化する場合は、すべてのメンバーがインスタンス化されます。

```cpp
template MyArray<double, 5>;
```

```cpp
//MyArray.h
#ifndef MYARRAY
#define MYARRAY

template<typename T, size_t N>
class MyArray
{
    T arr[N];
public:
    MyArray();
    void Print();
    T& operator[](int i);
};
#endif

//MyArray.cpp
#include "stdafx.h"
#include <iostream>
#include "MyArray.h"

using namespace std;

template<typename T, size_t N>
MyArray<T,N>::MyArray(){}

template<typename T, size_t N>
void MyArray<T,N>::Print()
{
    for(const auto v : arr)
    {
        cout << v << "'";
    }
    cout << endl;
}

template MyArray<double, 5>;template MyArray<string, 5>;
```

前の例では、明示的なインスタンス化は、.cpp ファイルの下部にあるです。 A`MyArray`に対してのみ使用することがあります**二重**または**文字列**型です。

> [!NOTE]
> C++ 11 で、**エクスポート**キーワードはテンプレート定義のコンテキストで推奨されなくなりました。 実際にはこれはほとんど影響ほとんどのコンパイラは、サポートがあるためです。
