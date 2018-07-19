---
title: ラムダ、関数オブジェクト、および制限関数を使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 25346cc9-869d-4ada-aad3-e2228cad3d6c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e3e5ab742335cfd6bb47a5105995d7339c7c36a
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687453"
---
# <a name="using-lambdas-function-objects-and-restricted-functions"></a>ラムダ、関数オブジェクト、および制限関数の使用
呼び出しで引数としては、アクセラレータで実行する C++ AMP コードを指定してください。、 [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each)メソッドです。 その引数としてラムダ式または関数オブジェクト (ファンクター) を指定できます。 また、ラムダ式や関数オブジェクトでは、C++ AMP 制限関数を呼び出すことができます。 このトピックでは、配列追加アルゴリズムを使用して、ラムダ、関数オブジェクト、および制限関数の概要を示します。 次の例では、C++ AMP コードを使用しないアルゴリズムを示します。 同じ長さの 2 個の 1 次元配列が作成されます。 対応する整数の要素が加算され、3 番目の 1 次元配列に格納されます。 C++ AMP は使用されません。  
  
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
  
 ラムダ式には、1 個のインデックス パラメーターと `restrict(amp)` が含まれている必要があります。 例では、 [array_view](../../parallel/amp/reference/array-view-class.md) `sum`オブジェクトが 1 のランク。 そのため、ラムダ ステートメントに対するパラメーターは、[インデックス](../../parallel/amp/reference/index-class.md)ランク 1 を持つオブジェクト。 実行時に、ラムダ式は 1 回実行の各要素に対して、 [array_view](../../parallel/amp/reference/array-view-class.md)オブジェクト。 詳細については、次を参照してください。[ラムダ式の構文](../../cpp/lambda-expression-syntax.md)です。  
  
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

 関数オブジェクトには、コンストラクターと、関数呼び出し演算子のオーバーロードが含まれている必要があります。 関数呼び出し演算子には、1 個のインデックス パラメーターが含まれている必要があります。 関数オブジェクトのインスタンスが 2 番目の引数として渡される、 [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each)メソッドです。 この例では次の 3 つ[array_view](../../parallel/amp/reference/array-view-class.md)オブジェクトが関数オブジェクトのコンス トラクターに渡されます。 [Array_view](../../parallel/amp/reference/array-view-class.md)オブジェクト`sum`1 のランクがあります。 したがって、関数呼び出し演算子のパラメーターは、[インデックス](../../parallel/amp/reference/index-class.md)ランク 1 を持つオブジェクト。 実行時に、関数は 1 回実行の各要素に対して、 [array_view](../../parallel/amp/reference/array-view-class.md)オブジェクト。 詳細については、次を参照してください。[関数を呼び出す](../../cpp/function-call-cpp.md)と[C++ 標準ライブラリ内の関数オブジェクト](../../standard-library/function-objects-in-the-stl.md)です。  
  
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
  
 制限付きの関数を含める必要があります`restrict(amp)`しで説明されている制限に準拠している[(C++ AMP) を制限する](../../cpp/restrict-cpp-amp.md)です。  
  
## <a name="see-also"></a>関連項目  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [ラムダ式の構文](../../cpp/lambda-expression-syntax.md)   
 [関数呼び出し](../../cpp/function-call-cpp.md)   
 [C++ 標準ライブラリ内の関数オブジェクト](../../standard-library/function-objects-in-the-stl.md)   
 [restrict (C++ AMP)](../../cpp/restrict-cpp-amp.md)

