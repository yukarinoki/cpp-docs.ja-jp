---
title: 配列 (C++ コンポーネント拡張) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- cli::array
- details::array
- lang::array
dev_langs:
- C++
helpviewer_keywords:
- array keyword [C++]
- declaring arrays, about declaring arrays
- arrays [C++], multidimensional
- multidimensional arrays
- arrays [C++]
ms.assetid: 49445812-d775-4db1-a231-869598dbb955
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a17649402fa6ebe9c98d768badcf36e5700f5b75
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="arrays-c-component-extensions"></a>配列 (C++ コンポーネント拡張)
`Platform::Array<T>`型に C + + CX、または`array`c++ のキーワード + CLI は、指定した型と初期値の配列を宣言しています。  
  
## <a name="all-platforms"></a>すべてのプラットフォーム  
 右山かっこ (>)、宣言の後に、オブジェクトのハンドル (^) 修飾子を使用して配列を宣言する必要があります。  
 配列の要素の数は、型の一部ではないです。 1 つの配列変数は、さまざまなサイズの配列を参照できます。  
  
 異なり、標準の C++ 添字演算子はポインターの算術演算のシノニムではありませんは可換です。  
  
 配列の詳細についてを参照してください。  
  
-   [方法: C++/CLI で配列を使用する](../dotnet/how-to-use-arrays-in-cpp-cli.md)  
    
-   [可変個引数リスト (...) (C++/CLI)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 配列のメンバーである、`Platform`名前空間。 配列には、1 次元のみ指定できます。  
  
### <a name="syntax"></a>構文  
  
 構文の最初の例では、`ref new`集計キーワードに配列を割り当てます。 2 番目の例では、ローカルの配列を宣言します。  
  
```  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = 
    ref new[Platform::]Array<initialization-type> [{initialization-list [,...]}]  
  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = 
    {initialization-list [,...]}  
```  
  
 *修飾子*[オプション]  
 1 つ以上のこれらのストレージ クラス指定子:[変更可能な](../cpp/mutable-data-members-cpp.md)、[揮発性](../cpp/volatile-cpp.md)、 [const](../cpp/const-cpp.md)、 [extern](../cpp/using-extern-to-specify-linkage.md)、[静的](../cpp/static-members-cpp.md).  
  
 `array-type`  
 配列変数の型。 有効な種類は Windows ランタイム クラスと基本型、ref クラスと構造体、値クラスと構造体、およびネイティブ ポインター (`type*`)。  
  
 `rank` [オプション]  
 配列の次元の数。 1 にする必要があります。  
  
 `identifier`  
 配列変数の名前。  
  
 `initialization-type`  
 配列を初期化する値の型。 通常、`array-type`と`initialization-type`は同じ型です。 ただし、指定できる型からの変換がある場合は、異なる`initialization-type`に`array-type`— たとえば場合、`initialization-type`から派生した`array-type`です。  
  
 `initialization-list` [オプション]  
 配列の要素の初期化は中かっこ内の値のコンマ区切りのリスト。 たとえば場合、`rank-size-list`された`(3)`、3 つの要素の 1 次元配列を宣言しています`initialization list`可能性があります`{1,2,3}`です。  
  
### <a name="remarks"></a>コメント  
  
 型がで参照カウントの配列であるかどうかをコンパイル時に検出できます`__is_ref_array(type)`です。 詳細については、次を参照してください。[型の特徴のコンパイラ サポート](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)です。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/ZW**  
  
### <a name="examples"></a>使用例  
 次の例では、100 個の要素のある 1 次元配列を作成します。  
  
```cpp  
// cwr_array.cpp  
// compile with: /ZW  
using namespace Platform;  
ref class MyClass {};  
int main() {  
   // one-dimensional array  
   Array<MyClass^>^ My1DArray = ref new Array<MyClass^>(100);  
   My1DArray[99] = ref new MyClass();  
}  
```  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
  
### <a name="syntax"></a>構文  
  
 構文の最初の例では、`gcnew`キーワードを配列を割り当てます。 2 番目の例では、ローカルの配列を宣言します。  
  
```  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier = 
    gcnew [cli::]array<initialization-type[,rank]>(rank-size-list[,...]) [{initialization-list [,...]}]  
  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier = 
    {initialization-list [,...]}  
```  
  
 *修飾子*[オプション]  
 1 つ以上のこれらのストレージ クラス指定子:[変更可能な](../cpp/mutable-data-members-cpp.md)、[揮発性](../cpp/volatile-cpp.md)、 [const](../cpp/const-cpp.md)、 [extern](../cpp/using-extern-to-specify-linkage.md)、[静的](../cpp/static-members-cpp.md).  
  
 `array-type`  
 配列変数の型。 有効な種類は Windows ランタイム クラスと基本型、ref クラスと構造体、値クラスと構造体、ネイティブ ポインター (`type*`)、およびネイティブ POD (プレーンな古いデータ) の型。  
  
 `rank` [オプション]  
 配列の次元の数。 既定値は 1 です。最大値は 32 です。 配列の各次元では、配列自体です。  
  
 `identifier`  
 配列変数の名前。  
  
 `initialization-type`  
 配列を初期化する値の型。 通常、`array-type`と`initialization-type`は同じ型です。 ただし、指定できる型からの変換がある場合は、異なる`initialization-type`に`array-type`— たとえば場合、`initialization-type`から派生した`array-type`です。  
  
 `rank-size-list`  
 配列内の各次元のサイズのコンマ区切りの一覧。 また場合、`initialization-list`パラメーターが指定されている場合、コンパイラは、各次元のサイズを推測できますと`rank-size-list`を省略できます。 
  
 `initialization-list` [オプション]  
 配列の要素の初期化は中かっこ内の値のコンマ区切りのリスト。 コンマ区切りの一覧が入れ子になったまたは*初期化リスト*多次元配列内の要素を初期化する項目。  
  
 たとえば場合、`rank-size-list`された`(3)`、3 つの要素の 1 次元配列を宣言しています`initialization list`可能性があります`{1,2,3}`です。 If`rank-size-list`された`(3,2,4)`、最初の次元、2 つの要素の 1 秒間、および 3 番目、4 つの要素の 3 つの要素の 3 次元の配列を宣言しています`initialization-list`可能性があります`{{1,2,3},{0,0},{-5,10,-21,99}}`)。  
  
### <a name="remarks"></a>コメント  
  
 `array` [プラットフォーム、既定値、および cli 名前空間](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)名前空間。  
  
 標準の C++ と同様に、配列のインデックスは 0 から始まる、および角かっこ () を使用して、配列が添字です。 標準の C++ とは異なり、多次元配列のインデックスは、一連の各ディメンションの角かっこ ([) 演算子ではなく各次元のインデックスの一覧で指定されます。 たとえば、*識別子*[*index1*、 *index2*] の代わりに*識別子*[*index1*] [ *index2*] です。  
  
 すべてのマネージ配列を継承`System::Array`です。 任意のメソッドまたはプロパティの`System::Array`配列変数に直接適用できます。  
  
 ポインターとする配列を割り当てて、要素型は、マネージ クラスを要素は、0 に初期化します。  
  
 値の型とする配列を割り当てて、要素型は`V`の既定のコンス トラクター`V`は配列の各要素に適用します。 詳細については、次を参照してください。 [C++ ネイティブ型と等価な .NET Framework (C + + CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)です。  
  
 コンパイル時に、型との共通言語ランタイム (CLR) 配列かどうかを検出できます`__is_ref_array(type)`です。 詳細については、次を参照してください。[型の特徴のコンパイラ サポート](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)です。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/clr**  
  
### <a name="examples"></a>使用例  
 次の例では、100 個の要素のある 1 次元配列と最初の次元の 3 つの要素、2 番目、5 の要素と 3 番目の 6 つの要素を持つ 3 次元の配列を作成します。  
  
```cpp  
// clr_array.cpp  
// compile with: /clr  
ref class MyClass {};  
int main() {  
   // one-dimensional array  
   array<MyClass ^> ^ My1DArray = gcnew array<MyClass ^>(100);  
   My1DArray[99] = gcnew MyClass();  
  
   // three-dimensional array  
   array<MyClass ^, 3> ^ My3DArray = gcnew array<MyClass ^, 3>(3, 5, 6);  
   My3DArray[0,0,0] = gcnew MyClass();  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)