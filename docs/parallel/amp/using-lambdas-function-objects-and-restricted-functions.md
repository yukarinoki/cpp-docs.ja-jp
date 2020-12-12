---
description: 詳細については、「ラムダ、関数オブジェクト、および制限された関数の使用」を参照してください。
title: ラムダ、関数オブジェクト、および制限関数の使用
ms.date: 11/04/2016
ms.assetid: 25346cc9-869d-4ada-aad3-e2228cad3d6c
ms.openlocfilehash: bef02f30b5d5b5f11b8051c7a596ac0a141eef0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314452"
---
# <a name="using-lambdas-function-objects-and-restricted-functions"></a>ラムダ、関数オブジェクト、および制限関数の使用

アクセラレータで実行する C++ AMP コードは、 [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) メソッドの呼び出しで引数として指定されます。 その引数としてラムダ式または関数オブジェクト (ファンクター) を指定できます。 また、ラムダ式や関数オブジェクトでは、C++ AMP 制限関数を呼び出すことができます。 このトピックでは、配列追加アルゴリズムを使用して、ラムダ、関数オブジェクト、および制限関数の概要を示します。 次の例では、C++ AMP コードを使用しないアルゴリズムを示します。 同じ長さの 2 個の 1 次元配列が作成されます。 対応する整数の要素が加算され、3 番目の 1 次元配列に格納されます。 C++ AMP は使用されません。

```cpp
void CpuMethod() {

    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    for (int idx = 0; idx <5; idx++)
    {
        sumCPP[idx] = aCPP[idx] + bCPP[idx];
    }

    for (int idx = 0; idx <5; idx++)
    {
        std::cout <<sumCPP[idx] <<"\n";
    }
}
```

## <a name="lambda-expression"></a>ラムダ式

ラムダ式の使用は、C++ AMP を使用してこのコードを記述し直す際に最も直接的な方法です。

```cpp
void AddArraysWithLambda() {
    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    array_view<const int, 1> a(5, aCPP);

    array_view<const int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

    parallel_for_each(
        sum.extent,
        [=](index<1> idx) restrict(amp)
        {
             sum[idx] = a[idx] + b[idx];
        });

    for (int i = 0; i <5; i++) {
        std::cout <<sum[i] <<"\n";
    }
}
```

ラムダ式には、1 個のインデックス パラメーターと `restrict(amp)` が含まれている必要があります。 この例では、 [array_view](../../parallel/amp/reference/array-view-class.md) `sum` オブジェクトのランクは1です。 したがって、ラムダステートメントのパラメーターは、ランク1を持つ [インデックス](../../parallel/amp/reference/index-class.md) オブジェクトです。 実行時に、ラムダ式は、 [array_view](../../parallel/amp/reference/array-view-class.md) オブジェクト内の要素ごとに1回実行されます。 詳細については、「 [ラムダ式の構文](../../cpp/lambda-expression-syntax.md)」を参照してください。

## <a name="function-object"></a>Function オブジェクト

アクセラレータ コードを関数オブジェクトに組み込むことができます。

```cpp
class AdditionFunctionObject
{
public:
    AdditionFunctionObject(const array_view<int, 1>& a,
    const array_view<int, 1>& b,
    const array_view<int, 1>& sum)
    : a(a), b(b), sum(sum)
    {
    }

    void operator()(index<1> idx) restrict(amp)
    {
        sum[idx] = a[idx] + b[idx];
    }

private:
    array_view<int, 1> a;
    array_view<int, 1> b;
    array_view<int, 1> sum;
};

void AddArraysWithFunctionObject() {
    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    array_view<const int, 1> a(5, aCPP);

    array_view<const int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

    parallel_for_each(
        sum.extent,
        AdditionFunctionObject(a, b, sum));

    for (int i = 0; i <5; i++) {
        std::cout <<sum[i] <<"\n";
    }
}
```

関数オブジェクトには、コンストラクターと、関数呼び出し演算子のオーバーロードが含まれている必要があります。 関数呼び出し演算子には、1 個のインデックス パラメーターが含まれている必要があります。 関数オブジェクトのインスタンスは、 [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) メソッドに2番目の引数として渡されます。 この例では、3つの [array_view](../../parallel/amp/reference/array-view-class.md) オブジェクトが関数オブジェクトコンストラクターに渡されます。 [Array_view](../../parallel/amp/reference/array-view-class.md)オブジェクトの `sum` ランクは1です。 したがって、関数呼び出し演算子のパラメーターは、ランク1を持つ [インデックス](../../parallel/amp/reference/index-class.md) オブジェクトです。 実行時には、 [array_view](../../parallel/amp/reference/array-view-class.md) オブジェクトの各要素に対して関数が1回実行されます。 詳細については、「 [C++ 標準ライブラリ](../../standard-library/function-objects-in-the-stl.md)の[関数呼び出し](../../cpp/function-call-cpp.md)と関数オブジェクト」を参照してください。

## <a name="c-amp-restricted-function"></a>C++ AMP 制限関数

制限関数を作成し、ラムダ式や関数オブジェクトから呼び出すことにより、アクセラレータ コードを組み込むこともできます。 次のコード例では、ラムダ式からの制限関数を呼び出す方法を示します。

```cpp
void AddElementsWithRestrictedFunction(index<1> idx, array_view<int, 1> sum, array_view<int, 1> a, array_view<int, 1> b) restrict(amp)
{
    sum[idx] = a[idx] + b[idx];
}

void AddArraysWithFunction() {

    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    array_view<int, 1> a(5, aCPP);

    array_view<int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

    parallel_for_each(
        sum.extent,
        [=](index<1> idx) restrict(amp)
        {
            AddElementsWithRestrictedFunction(idx, sum, a, b);
        });

    for (int i = 0; i <5; i++) {
        std::cout <<sum[i] <<"\n";
    }
}
```

制限付きの関数には、 `restrict(amp)` 「 [制限 (C++ AMP)](../../cpp/restrict-cpp-amp.md)」で説明されている制限を含め、準拠させる必要があります。

## <a name="see-also"></a>関連項目

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[ラムダ式の構文](../../cpp/lambda-expression-syntax.md)<br/>
[関数呼び出し](../../cpp/function-call-cpp.md)<br/>
[C++ 標準ライブラリの関数オブジェクト](../../standard-library/function-objects-in-the-stl.md)<br/>
[restrict (C++ AMP)](../../cpp/restrict-cpp-amp.md)
